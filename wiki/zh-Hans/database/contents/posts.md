# posts *帖子主表*

| 字段名 | 字段类型 | 字段注释 | 默认值 | 可空 | 备注 |
| --- | --- | --- | --- | --- | --- |
| id | bigint *UNSIGNED* | 帖子 ID | | NO | 自动递增 |
| pid | varchar(32) | 对外公开 ID |  | NO | **唯一值** |
| user_id | bigint *UNSIGNED* | 发布者 ID |  | NO | 关联字段 [users->id](../users/users.md) |
| group_id | int *UNSIGNED* | 小组 ID |  | YES | 关联字段 [groups->id](groups.md) |
| types | varchar(128) | 内容搜索类型 |  | NO | 多个以英文逗号隔开<br>例如 `image,video` 代表帖子带图片和视频 |
| title | varchar(255) | 标题 |  | YES |  |
| content | longtext | 内容 |  | YES |  |
| lang_tag | char(16) | 语言标签 |  | YES |  |
| writing_direction | char(3) | 语言写作方向 |  | YES |   |
| is_markdown | tinyint *UNSIGNED* | 内容是否为 MD 格式 | 0 | NO | 0.否 / 1.是 |
| is_anonymous | tinyint *UNSIGNED* | 是否匿名 | 0 | NO |  0.否 / 1.是 |
| map_id | tinyint *UNSIGNED* | 地图-服务商编号 |  | YES | 来源地图服务商键值字典 |
| map_longitude | decimal(12,8) | 地图-经度 |  | YES | 浮点数，范围为-180~180，负数表示西经 |
| map_latitude | decimal(12,8) | 地图-纬度 |  | YES | 浮点数，范围为-90~90，负数表示南纬 |
| sticky_state | tinyint *UNSIGNED* | 置顶状态 | 1 | NO |  1.否 / 2.小组页置顶 / 3.全局置顶 |
| digest_state | tinyint *UNSIGNED* | 精华状态 | 1 | NO |  1.否 / 2.普通精华 / 3.高级精华 |
| like_count | int *UNSIGNED* | 点赞数 | 0 | NO | 有多少用户点赞了该帖子 |
| dislike_count | int *UNSIGNED* | 点踩数 | 0 | NO | 有多少用户点踩了该帖子 |
| follow_count | int *UNSIGNED* | 关注数 | 0 | NO | 有多少用户关注了（收藏）该帖子 |
| block_count | int *UNSIGNED* | 屏蔽数 | 0 | NO | 有多少用户屏蔽了（不感兴趣）该帖子 |
| comment_count | int *UNSIGNED* | 评论数 | 0 | NO | 该帖子有多少条评论，包括评论二级回复 |
| comment_digest_count | int *UNSIGNED* | 评论精华总数 | 0 | NO | 该帖子评论的精华总数 |
| comment_like_count | int *UNSIGNED* | 评论点赞数 | 0 | NO | 所有评论被点赞总数 |
| comment_dislike_count | int *UNSIGNED* | 评论点踩数 | 0 | NO | 所有评论被点踩总数 |
| comment_follow_count | int *UNSIGNED* | 评论关注数 | 0 | NO | 所有评论被关注总数 |
| comment_block_count | int *UNSIGNED* | 评论屏蔽数 | 0 | NO | 所有评论被屏蔽总数 |
| latest_edit_at | timestamp | 编辑时间 |  | YES | 如果发表后可以编辑，此处记录编辑时间 |
| latest_comment_at | timestamp | 评论时间 |  | YES | 最新一条评论的时间 |
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

## 精华说明

**普通精华**
- 常规曝光
- 出现在关注了该小组的用户时间线里

*开启关注“小组”功能后，关注页信息流默认只展示“小组”下设为精华的内容*

**高级精华**
- 常规曝光
- 出现在所有用户时间线里