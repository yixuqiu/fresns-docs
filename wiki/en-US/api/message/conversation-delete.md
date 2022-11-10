# [Conversation] Delete Conversation or Messages

- Endpoint Path: `/api/v2/conversation/delete`
- Method: `DELETE`
- Request: `application/json`

## Headers Optional Parameter

| Parameter Name | Public Mode (Required) | Private Mode (Required) |
| --- | --- | --- |
| aid | **required** | **required** |
| uid | **required** | **required** |
| token | **required** | **required** |

## Body Params

| Parameter Name | Type | Required | Description |
| --- | --- | --- | --- |
| type | String | **required** | `conversation` 或 `message` |
| conversationId | Number | *optional* |  |
| messageIds | String | *optional* | 多个以英文逗号隔开 |

**Request Description**

- `conversationId` 和 `messageIds` 二选一传参，不可同时传参。
- `type = conversation` 使用 `conversationId` 参数，将当前对话框设置为删除，并将对话下属于当前用户的消息全部删除。
- `type = message` 使用 `messageIds` 参数，批量删除指定 ID 的消息。

## Return

```json
{
    "code": 0,
    "message": "ok",
    "data": null
}
```