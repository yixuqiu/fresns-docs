# file_downloads

| Column Name | Type | Comment | Default | Null | Remark |
| --- | --- | --- | --- | --- | --- |
| id | bigint *UNSIGNED* | Primary Key ID |  | NO | 自动递赠 |
| file_id | bigint *UNSIGNED* | 文件 ID |  | NO | 关联字段 [files->id](files.md) |
| file_type | tinyint *UNSIGNED* | 文件类型 | 1 | NO | 1.图片 / 2.视频 / 3.音频 / 4.文档 |
| account_id | bigint *UNSIGNED* | 下载者账号 ID |  | NO | 关联字段 [accounts->id](../accounts/accounts.md) |
| user_id | bigint *UNSIGNED* | 下载者用户 ID |  | YES | 关联字段 [users->id](../users/users.md) |
| plugin_unikey | varchar(64) | 下载者插件 |  | YES | 关联字段 [plugins->unikey](../plugins/plugins.md)<br>如果在插件中下载，则是该插件 unikey |
| object_type | tinyint *UNSIGNED* | 下载来源类型 | 1 | NO | 1.用户 / 2.小组 / 3.话题 / 4.帖子 / 5.评论 / 6.扩展内容 |
| object_id | bigint *UNSIGNED* | 来源目标主键 ID |  | NO |  |
| created_at | timestamp | 使用时间 | CURRENT_TIMESTAMP | NO | 下载时间 |
| updated_at | timestamp | Update Time |  | YES |  |
| deleted_at | timestamp | Delete Time |  | YES |  |