# comments *评论主表*

| 字段名 | 字段类型 | 字段注释 | 默认值 | 可空 | 备注 |
| --- | --- | --- | --- | --- | --- |
| id | bigint *UNSIGNED* | 主键 ID | | NO | 自动递增 |
| cid | varchar(32) | 对外公开 ID |  | NO | **唯一值** |
| post_id | bigint *UNSIGNED* | 帖子 ID |  | NO | 关联字段 [posts->id](posts.md) |
| top_parent_id | bigint *UNSIGNED* | 顶级评论 ID |  | YES | 所属哪个评论，为空代表不属于任何评论 |
| parent_id | bigint *UNSIGNED* | 父级评论 ID |  | YES | 为空代表一级评论 |
| user_id | bigint *UNSIGNED* | 发表者 ID |  | NO | 关联字段 [users->id](../users/users.md) |
| types | varchar(128) | 内容搜索类型 |  | NO | 多个以英文逗号隔开<br>例如 `image,video` 代表评论带图片和视频 |
| content | longtext | 内容 |  | YES |  |
| lang_tag | char(16) | 语言标签 |  | YES |  |
| writing_direction | char(3) | 语言写作方向 |  | YES |   |
| is_markdown | tinyint *UNSIGNED* | 内容是否为 MD 格式 | 0 | NO | 0.否 / 1.是 |
| is_anonymous | tinyint *UNSIGNED* | 是否匿名 | 0 | NO |  0.否 / 1.是 |
| map_id | tinyint *UNSIGNED* | 地图-服务商编号 |  | YES | 来源地图服务商键值字典 |
| map_longitude | decimal(12,8) | 地图-经度 |  | YES | 浮点数，范围为-180~180，负数表示西经 |
| map_latitude | decimal(12,8) | 地图-纬度 |  | YES | 浮点数，范围为-90~90，负数表示南纬 |
| is_sticky | tinyint *UNSIGNED* | 是否置顶 | 0 | NO |  0.否 / 1.是 |
| digest_state | tinyint *UNSIGNED* | 精华状态 | 1 | NO |  1.否 / 2.普级精华 / 3.高级精华 |
| like_count | int *UNSIGNED* | 点赞数 | 0 | NO | 有多少用户点赞了该条评论 |
| dislike_count | int *UNSIGNED* | 点踩数 | 0 | NO | 有多少用户点踩了该条评论 |
| follow_count | int *UNSIGNED* | 关注数 | 0 | NO | 有多少用户关注了（收藏）该条评论 |
| block_count | int *UNSIGNED* | 屏蔽数 | 0 | NO | 有多少用户屏蔽了（不感兴趣）该条评论 |
| comment_count | int *UNSIGNED* | 评论数 | 0 | NO | 回复这条评论的数量 |
| comment_digest_count | int *UNSIGNED* | 评论精华总数 | 0 | NO | 回复这条评论的精华总数 |
| comment_like_count | int *UNSIGNED* | 子级评论点赞数 | 0 | NO | 回复这条评论的所有评论点赞总数 |
| comment_dislike_count | int *UNSIGNED* | 子级评论点踩数 | 0 | NO | 回复这条评论的所有评论点踩总数 |
| comment_follow_count | int *UNSIGNED* | 子级评论关注数 | 0 | NO | 回复这条评论的所有评论关注总数 |
| comment_block_count | int *UNSIGNED* | 子级评论屏蔽数 | 0 | NO | 回复这条评论的所有评论屏蔽总数 |
| latest_edit_at | timestamp | 编辑时间 |  | YES | 如果发表后可以编辑，此处记录编辑时间 |
| latest_comment_at | timestamp | 评论时间 |  | YES | 最新一条评论的时间<br>有用户回复了该条评论 |
| is_enable | tinyint *UNSIGNED* | 是否有效 | 1 | NO | 0.无效（仅自己可见） / 1.有效 |
| created_at | timestamp | 创建时间 | CURRENT_TIMESTAMP | NO | 发表时间 |
| updated_at | timestamp | 更新时间 |  | YES |  |
| deleted_at | timestamp | 删除时间 |  | YES |  |

## 类型说明

| 类型 | 说明 |
| --- | --- |
| text | 帖子是纯文本内容，不附带文件，不附带扩展内容 |
| image | 帖子带图片文件（图片附件） |
| video | 帖子带视频文件（视频附件） |
| audio | 帖子带音频文件（音频附件） |
| document | 帖子带文档文件（文档附件） |
| {unikey} | 插件 unikey 值，代表帖子附带该插件增加的扩展内容 |