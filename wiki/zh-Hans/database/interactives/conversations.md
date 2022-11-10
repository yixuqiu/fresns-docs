# conversations *对话表*

| 字段名 | 字段类型 | 字段注释 | 默认值 | 可空 | 备注 |
| --- | --- | --- | --- | --- | --- |
| id | bigint *UNSIGNED* | 主键 ID |  | NO | 自动递赠 |
| a_user_id | bigint *UNSIGNED* | 对话 A 用户 ID |  | NO | 关联字段 [users->id](../users/users.md) |
| b_user_id | bigint *UNSIGNED* | 对话 B 用户 ID |  | NO | 关联字段 [users->id](../users/users.md) |
| latest_message_id | bigint *UNSIGNED* | 最新一条消息 ID |  | YES | 关联字段 conversation_messages > id |
| latest_message_time | timestamp | 最新一条消息时间 |  | YES | 关联字段 conversation_messages > created_at |
| latest_message_text | text | 最新一条消息内容 |  | YES | 关联字段 conversation_messages > message_text |
| a_is_read | tinyint *UNSIGNED* | 用户 A 阅读状态 | 1 | NO | 0.未读 / 1.已读 |
| b_is_read | tinyint *UNSIGNED* | 用户 B 阅读状态 | 1 | NO | 0.未读 / 1.已读 |
| a_is_display | tinyint *UNSIGNED* | 用户 A 对话列表是否隐藏  | 1 | NO | 0.隐藏 / 1.显示 |
| b_is_display | tinyint *UNSIGNED* | 用户 B 对话列表是否隐藏  | 1 | NO | 0.隐藏 / 1.显示 |
| a_is_sticky | tinyint *UNSIGNED* | 用户 A 对话列表是否置顶  | 0 | NO | 0.否 / 1.是 |
| b_is_sticky | tinyint *UNSIGNED* | 用户 B 对话列表是否置顶  | 0 | NO | 0.否 / 1.是 |
| a_is_deactivate | tinyint *UNSIGNED* | 用户 A 账号状态 | 1 | NO | 0.已删除或注销 / 1.正常 |
| b_is_deactivate | tinyint *UNSIGNED* | 用户 B 账号状态 | 1 | NO | 0.已删除或注销 / 1.正常 |
| created_at | timestamp | 创建时间 | CURRENT_TIMESTAMP | NO |  |
| updated_at | timestamp | 更新时间 |  | YES |  |
| deleted_at | timestamp | 删除时间 |  | YES |  |