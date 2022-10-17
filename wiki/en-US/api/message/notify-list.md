# [Notify] List

- Endpoint Path: `/api/v2/notify/list`
- Method: `GET`
- Request: `Query`

## Headers Optional Parameter

| Parameter Name | Public Mode (Required) | Private Mode (Required) |
| --- | --- | --- |
| aid | **required** | **required** |
| uid | **required** | **required** |
| token | **required** | **required** |

## Query Params

| Parameter Name | Type | Required | Description |
| --- | --- | --- | --- |
| types | String | *optional* | 1.对全员的系统通知 / 2.系统通知 / 3.推荐 / 4.关注<br>5.点赞 / 6.提及（艾特） / 7.评论 |
| status | Boolean | *optional* | `0` 未读<br>`1` 已读<br>留空输出未读 |
| pageSize | Number | *optional* | 每页显示条数（默认 15 条） |
| page | Number | *optional* | 页码（默认 1） |

**Request Description**

- `type` 留空输出全部，传参支持多个，以英文逗号隔开。
- 按时间倒序排列，最新的在前面。
- **系统消息解读：**
    - `type=1` 代表系统给全员发了一条 `content` 消息内容（用户不可删除）
        - `isAccessPlugin` 是否访问插件页
        - `actionType + actionInfo` 是否有附带内容
    - `type=2` 代表系统给你发了一条 `content` 消息内容
        - `isAccessPlugin` 是否访问插件页
        - `actionUser` 是否有触发用户
        - `actionType + actionInfo` 是否有附带内容
- **推荐消息解读：**
    - `type=3` 代表系统给你推荐了内容
        - `content` 推荐语
        - `isAccessPlugin` 是否访问插件页
        - `actionUser` 是否有触发用户
        - `actionType + actionInfo` 推荐的内容
- **互动消息解读：**
    - `type=4` 代表 `actionUser` 关注了你
    - `type=5` 代表 `actionUser` 点赞了你的 `actionType + actionInfo`
    - `type=6` 代表 `actionUser` 在 `actionType + actionInfo` 中提及了你
        - `content` 提及内容的摘要
    - `type=7` 代表 `actionUser` 发表 `actionType + actionInfo` 评论了你
        - `content` 评论内容的摘要


## Return

```json
{
    "code": 0,
    "message": "ok",
    "data": {
        "pagination": {
            "total": "Number / How much data in total",
            "pageSize": "Number / How much data on each page",
            "currentPage": "Number / Current page number",
            "lastPage": "Number / Last page number"
        },
        "list": [
            {
                "notifyId": "Number / 通知 ID",
                "type": "Number / 通知类型",
                "content": "String / 通知内容",
                "isMarkdown": "Boolean / 内容是否为 Markdown 格式",
                "isAccessPlugin": "Boolean / 是否访问插件页",
                "pluginUrl": "String / 插件页地址",
                "actionUser": {
                    // 触发消息的用户信息
                    // Common Data Structure -> User Info Profile
                },
                "actionType": "Number / 触发内容类型",
                "actionInfo": {
                    // 触发关联内容（公共数据结构）
                    // actionType=1  用户信息
                    // actionType=2  小组信息
                    // actionType=3  话题信息
                    // actionType=4  帖子信息
                    // actionType=5  评论信息
                },
                "notifyTime": "String / 通知时间",
                "notifyTimeFormat": "String / 通知时间格式化",
                "readStatus": "Boolean / 阅读状态"
            }
        ]
    }
}
```