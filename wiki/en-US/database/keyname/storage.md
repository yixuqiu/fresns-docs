# Storage

> Panel > Systems > Storage

## Image

| Menu Title | Key Name | Default Key Value | Value Type | Description |
| --- | --- | --- | --- | --- |
| 存储平台 | image_service |  | **plugins** | 插件应用场景参数 `storage` |
| SecretID | image_secret_id |  | string | 举例又拍云：操作员账号 |
| SecretKey | image_secret_key |  | string | 举例又拍云：操作员密码 |
| 存储配置名称 | image_bucket_name |  | string | 举例又拍云：服务名(空间名) |
| 存储配置地域 | image_bucket_area |  | string | 举例又拍云：用不到，留空 |
| 存储配置域名 | image_bucket_domain |  | string | http:// 或 https:// 开头，结尾不带 / |
| 文件系统磁盘 | image_filesystem_disk | remote | string | 用于定义 URL 规则<br>`local` 会将 /storage 添加到给定的路径<br>`remote` 完全限定的远程 URL |
| 支持的扩展名 | image_extension_names | png,gif,jpg,jpeg,bmp,heic | string | 以英文逗号 , 隔开 |
| 支持的最大尺寸 | image_max_size | 5 | number | 单位：MB |
| 防盗链功能 | image_url_status | false | boolean | 使用状态 |
| 防盗链 Key | image_url_key |  | string |  |
| 防盗链签名有效期 | image_url_expire | 10 | number | 单位：分钟 |
| 图片处理位置 | image_handle_position | end | string | `start` or `end` |
| 配置图参数 | image_thumb_config |  | string | 配置图专用 |
| 头像图参数 | image_thumb_avatar |  | string | 头像图专用 |
| 等比例缩略图参数 | image_thumb_ratio |  | string | 等比例缩小或者压缩图片 |
| 正方形缩略图参数 | image_thumb_square |  | string | 强制输出正方形缩略图，不是正方形则会裁剪 |
| 原图压缩图参数 | image_thumb_big |  | string | 原始图片压缩 |

## Video

| Menu Title | Key Name | Default Key Value | Value Type | Description |
| --- | --- | --- | --- | --- |
| 存储平台 | video_service |  | **plugins** | 插件应用场景参数 `storage` |
| SecretID | video_secret_id |  | string |  |
| SecretKey | video_secret_key |  | string |  |
| 存储配置名称 | video_bucket_name |  | string |  |
| 存储配置地域 | video_bucket_area |  | string |  |
| 存储配置域名 | video_bucket_domain |  | string | http:// 或 https:// 开头，结尾不带 / |
| 文件系统磁盘 | video_filesystem_disk | remote | string | local 或 remote |
| 视频支持的扩展名 | video_extension_names | wmv,rm,mov,mpeg,mp4,<br>3gp,flv,avi,rmvb | string | 以英文逗号 , 隔开 |
| 支持的最大尺寸 | video_max_size | 50 | number | 单位：MB |
| 视频支持的最大时长 | video_max_time | 15 | number | 单位：秒 |
| 防盗链功能 | video_url_status | false | boolean | 使用状态 |
| 防盗链 Key | video_url_key |  | string |  |
| 防盗链签名有效期 | video_url_expire | 10 | number | 单位：分钟 |
| 视频转码参数 | video_transcode |  | string |  |
| 视频水印参数 | video_watermark |  | string |  |
| 视频截图参数 | video_screenshot |  | string |  |
| 视频转动图参数 | video_gift |  | string |  |

## Audio

| Menu Title | Key Name | Default Key Value | Value Type | Description |
| --- | --- | --- | --- | --- |
| 存储平台 | audio_service |  | **plugins** | 插件应用场景参数 `storage` |
| SecretID | audio_secret_id |  | string |  |
| SecretKey | audio_secret_key |  | string |  |
| 存储配置名称 | audio_bucket_name |  | string |  |
| 存储配置地域 | audio_bucket_area |  | string |  |
| 存储配置域名 | audio_bucket_domain |  | string | http:// 或 https:// 开头，结尾不带 / |
| 文件系统磁盘 | audio_filesystem_disk | remote | string | local 或 remote |
| 音频支持的扩展名 | audio_extension_names | mp3,wav,m4a | string | 以英文逗号 , 隔开 |
| 支持的最大尺寸 | audio_max_size | 50 | number | 单位：MB |
| 音频支持的最大时长 | audio_max_time | 60 | number | 单位：秒 |
| 防盗链功能 | audio_url_status | false | boolean | 使用状态 |
| 防盗链 Key | audio_url_key |  | string |  |
| 防盗链签名有效期 | audio_url_expire | 10 | number | 单位：分钟 |
| 音频转码参数 | audio_transcode |  | string |  |

## Document

| Menu Title | Key Name | Default Key Value | Value Type | Description |
| --- | --- | --- | --- | --- |
| 存储平台 | document_service |  | **plugins** | 插件应用场景参数 `storage` |
| SecretID | document_secret_id |  | string |  |
| SecretKey | document_secret_key |  | string |  |
| 存储配置名称 | document_bucket_name |  | string |  |
| 存储配置地域 | document_bucket_area |  | string |  |
| 存储配置域名 | document_bucket_domain |  | string | http:// 或 https:// 开头，结尾不带 / |
| 文件系统磁盘 | document_filesystem_disk | remote | string | local 或 remote |
| 支持的扩展名 | document_extension_names | doc,docx,xls,xlsx,csv,<br>ppt,pptx,pps,ppts,<br>pdf,<br>txt,md,markdown,<br>rar,zip,7z,<br>epub,mobi | string | 以英文逗号 , 隔开 |
| 支持的最大尺寸 | document_max_size | 10 | number | 单位：MB |
| 防盗链功能 | document_url_status | false | boolean | 使用状态 |
| 防盗链 Key | document_url_key |  | string |  |
| 防盗链签名有效期 | document_url_expire | 10 | number | 单位：分钟 |
| 预览地址规则 | document_online_preview |  | string | 支持变量名 {docurl} 或 {fid} |
| 支持预览的扩展名 | document_preview_extension_names | doc,docx,xls,xlsx,csv,ppt,pptx,pdf | string |  |

## Substitution

| Menu Title | Key Name | Default Key Value | Value Type | Description |
| --- | --- | --- | --- | --- |
| 图片无效提示图 | image_substitution |  | **file** |  |
| 视频无效提示图 | video_substitution |  | **file** |  |
| 音频无效提示图 | audio_substitution |  | **file** |  |
| 文档无效提示图 | document_substitution |  | **file** |  |