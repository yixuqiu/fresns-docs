# 更新设置信息

- 接口地址：`/api/fresns/v1/user/setting`
- 请求方式：`PATCH`
- 传参方式：`application/json`

## Headers 可选参数

| 参数名 | 公开模式（是否必传） | 私有模式（是否必传） |
| --- | --- | --- |
| X-Fresns-Aid | YES | YES |
| X-Fresns-Aid-Token | YES | YES |
| X-Fresns-Uid | YES | YES |
| X-Fresns-Uid-Token | YES | YES |

## Body 参数

| 参数名 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| conversationPolicy | Number | NO | 对话设置 |
| commentPolicy | Number | NO | 评论设置 |
| deviceToken | String | NO | iOS 或 Android 设备 Token |

**接口使用说明**

- 对话设置和评论设置
    - `1` 所有人
    - `2` 你关注的人
    - `3` 你关注的人和已认证的人
    - `4` 不允许所有人

## 返回结果

```json
{
    "code": 0,
    "message": "ok",
    "data": null
}
```
