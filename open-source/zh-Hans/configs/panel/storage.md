# 存储设置

> 控制面板 > 系统 > 存储设置

## 图片设置

| 栏目标题 | 键名 | 默认键值 | 键值类型 | 说明 |
| --- | --- | --- | --- | --- |
| 存储平台 | image_service |  | **plugin** | 用途场景 `storage` |
| Secret ID | image_secret_id |  | string | 举例又拍云：操作员账号 |
| Secret Key | image_secret_key |  | string | 举例又拍云：操作员密码 |
| Secret App | image_secret_app |  | string |  |
| 存储配置名称 | image_bucket_name |  | string | 举例又拍云：服务名(空间名) |
| 存储配置地域 | image_bucket_region |  | string | 举例又拍云：用不到，留空 |
| 存储配置域名 | image_bucket_domain |  | string | http:// 或 https:// 开头，结尾不带 / |
| 文件系统磁盘 | image_filesystem_disk |  | string | `local` 或 `remote` |
| 支持的扩展名 | image_extension_names |  | string | 以英文逗号 , 隔开 |
| 支持的最大尺寸 | image_max_size | 5 | number | 单位：MB |
| 防盗链功能 | image_url_status | false | boolean | 使用状态 |
| 防盗链 Key | image_url_key |  | string |  |
| 防盗链签名有效期 | image_url_expire | 10 | number | 单位：分钟 |
| 图片处理位置 | image_handle_position | end | string | `{空}` 不使用<br>`path-start` 路径开始位置<br>`path-end` 路径结尾位置<br>`name-start` 文件名开头位置<br>`name-end` 文件名结尾位置（扩展名之前） |
| 配置图参数 | image_thumb_config |  | string | 配置图专用 |
| 等比例缩略图参数 | image_thumb_ratio |  | string | 等比例缩小或者压缩图片 |
| 正方形缩略图参数 | image_thumb_square |  | string | 强制输出正方形缩略图，不是正方形则会裁剪 |
| 原图压缩图参数 | image_thumb_big |  | string | 原始图片压缩 |

- 支持的扩展名示例: `png,gif,jpg,jpeg,bmp,heic`

## 视频设置

| 栏目标题 | 键名 | 默认键值 | 键值类型 | 说明 |
| --- | --- | --- | --- | --- |
| 存储平台 | video_service |  | **plugin** | 用途场景 `storage` |
| Secret ID | video_secret_id |  | string |  |
| Secret Key | video_secret_key |  | string |  |
| Secret App | video_secret_app |  | string |  |
| 存储配置名称 | video_bucket_name |  | string |  |
| 存储配置地域 | video_bucket_region |  | string |  |
| 存储配置域名 | video_bucket_domain |  | string | http:// 或 https:// 开头，结尾不带 / |
| 文件系统磁盘 | video_filesystem_disk |  | string | `local` 或 `remote` |
| 视频支持的扩展名 | video_extension_names |  | string | 以英文逗号 , 隔开 |
| 支持的最大尺寸 | video_max_size | 50 | number | 单位：MB |
| 视频支持的最大时长 | video_max_duration | 60 | number | 单位：秒 |
| 防盗链功能 | video_url_status | false | boolean | 使用状态 |
| 防盗链 Key | video_url_key |  | string |  |
| 防盗链签名有效期 | video_url_expire | 10 | number | 单位：分钟 |
| 视频转码参数 | video_transcode_parameter |  | string |  |
| 视频转码参数处理位置 | video_transcode_handle_position |  | string | `{空}` 不使用<br>`path-start` 路径开始位置<br>`path-end` 路径结尾位置<br>`name-start` 文件名开头位置<br>`name-end` 文件名结尾位置（扩展名之前） |
| 视频封面图参数 | video_poster_parameter |  | string |  |
| 视频封面图参数处理位置 | video_poster_handle_position |  | string | `{空}` 不使用<br>`path-start` 路径开始位置<br>`path-end` 路径结尾位置<br>`name-start` 文件名开头位置<br>`name-end` 文件名结尾位置（扩展名之前） |

- 支持的扩展名示例: `wmv,rm,mov,mpeg,mp4,<br>3gp,flv,avi,rmvb`

## 音频设置

| 栏目标题 | 键名 | 默认键值 | 键值类型 | 说明 |
| --- | --- | --- | --- | --- |
| 存储平台 | audio_service |  | **plugin** | 用途场景 `storage` |
| Secret ID | audio_secret_id |  | string |  |
| Secret Key | audio_secret_key |  | string |  |
| Secret App | audio_secret_app |  | string |  |
| 存储配置名称 | audio_bucket_name |  | string |  |
| 存储配置地域 | audio_bucket_region |  | string |  |
| 存储配置域名 | audio_bucket_domain |  | string | http:// 或 https:// 开头，结尾不带 / |
| 文件系统磁盘 | audio_filesystem_disk |  | string | `local` 或 `remote` |
| 音频支持的扩展名 | audio_extension_names |  | string | 以英文逗号 , 隔开 |
| 支持的最大尺寸 | audio_max_size | 50 | number | 单位：MB |
| 音频支持的最大时长 | audio_max_duration | 60 | number | 单位：秒 |
| 防盗链功能 | audio_url_status | false | boolean | 使用状态 |
| 防盗链 Key | audio_url_key |  | string |  |
| 防盗链签名有效期 | audio_url_expire | 10 | number | 单位：分钟 |
| 音频转码参数 | audio_transcode_parameter |  | string |  |
| 音频转码参数处理位置 | audio_transcode_handle_position |  | string | `{空}` 不使用<br>`path-start` 路径开始位置<br>`path-end` 路径结尾位置<br>`name-start` 文件名开头位置<br>`name-end` 文件名结尾位置（扩展名之前） |

- 支持的扩展名示例: `mp3,wav,m4a`

## 文档设置

| 栏目标题 | 键名 | 默认键值 | 键值类型 | 说明 |
| --- | --- | --- | --- | --- |
| 存储平台 | document_service |  | **plugin** | 用途场景 `storage` |
| Secret ID | document_secret_id |  | string |  |
| Secret Key | document_secret_key |  | string |  |
| Secret App | document_secret_app |  | string |  |
| 存储配置名称 | document_bucket_name |  | string |  |
| 存储配置地域 | document_bucket_region |  | string |  |
| 存储配置域名 | document_bucket_domain |  | string | http:// 或 https:// 开头，结尾不带 / |
| 文件系统磁盘 | document_filesystem_disk |  | string | `local` 或 `remote` |
| 支持的扩展名 | document_extension_names |  | string | 以英文逗号 , 隔开 |
| 支持的最大尺寸 | document_max_size | 10 | number | 单位：MB |
| 防盗链功能 | document_url_status | false | boolean | 使用状态 |
| 防盗链 Key | document_url_key |  | string |  |
| 防盗链签名有效期 | document_url_expire | 10 | number | 单位：分钟 |
| 文档预览插件 | document_preview_service |  | **plugin** | 用途场景 `documentPreview` |
| 支持预览的扩展名 | document_preview_extension_names |  | string |  |

- 支持的扩展名示例: `doc,docx,xls,xlsx,csv,<br>ppt,pptx,pps,ppts,<br>pdf,<br>txt,md,markdown,<br>rar,zip,7z,<br>epub,mobi`
- 支持预览的扩展名示例: `doc,docx,xls,xlsx,csv,ppt,pptx,pdf`

## 补位图上传

| 栏目标题 | 键名 | 默认键值 | 键值类型 | 说明 |
| --- | --- | --- | --- | --- |
| 图片无效提示图 | image_substitution |  | **file** |  |
| 视频无效提示图 | video_substitution |  | **file** |  |
| 音频无效提示图 | audio_substitution |  | **file** |  |
| 文档无效提示图 | document_substitution |  | **file** |  |
