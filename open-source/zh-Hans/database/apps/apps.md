---
aside: false
---

# apps *应用表*

| 字段名 | 字段类型 | 字段注释 | 默认值 | 可空 | 备注 |
| --- | --- | --- | --- | --- | --- |
| id | int *UNSIGNED* | 主键 ID |  | NO | 自动递增 |
| type | tinyint *UNSIGNED* | 类型 | 1 | NO | 1.插件<br>2.主题<br>3.远程应用<br>4.独立应用（下载使用） |
| fskey | varchar(64) | 标识名 |  | NO | **唯一值**，大驼峰格式 |
| name | varchar(64) | 名称 |  | NO |  |
| description | varchar(255) | 描述 |  | NO |  |
| version | varchar(16) | 语义化版本号 |  | NO | 用于展示的版本号 |
| author | varchar(64) | 开发者名称 |  | NO |  |
| author_link | varchar(128) | 开发者链接 |  | YES |  |
| panel_usages | json | 面板应用场景 |  | YES | 支持的应用场景参数<br>格式：`["apiKey","register"]` |
| app_host | varchar(128) | 插件自定义域名 |  | YES | http:// 或 https:// 开头，结尾不带 / |
| access_path | varchar(255) | 插件访问路径 |  | YES | 相对路径，支持变量名<br>当字段 `app_host` 为空时，与“后端域名”拼接成完整 URL |
| settings_path | varchar(128) | 设置页面 |  | YES | 相对路径，为空代表没有设置页面<br>主题如果有设置功能，则填入 fskey |
| is_upgrade | tinyint *UNSIGNED* | 是否有升级包 | 0 | NO | 0.无 / 1.有 |
| upgrade_version | varchar(16) | 新版本号 |  | YES |  |
| upgrade_code | varchar(32) | 升级码 |  | YES | 官方应用市场升级凭证 |
| is_enabled | tinyint *UNSIGNED* | 是否启用 | 1 | NO | 0.停用 / 1.启用 |
| created_at | timestamp | 创建时间 | useCurrent | NO  | 比如 MySQL 默认值为 CURRENT_TIMESTAMP |
| updated_at | timestamp | 更新时间 |  | NO  |  |
| deleted_at | timestamp | 删除时间 |  | YES |  |

## 地址拼接说明

- 1、插件完整的 URL 地址，由域名字段 `app_host` 加路径字段 `access_path` 拼接完成，当 `app_host` 为空时，与后端地址（配置表键名 `system_url`）拼接成完整 URL 地址。
- 2、如果是「插件关联使用表」的关联插件，先根据第 1 条的逻辑拼接成完整地址，然后以 `plugin_usages->parameter` 字段值替换 URL 地址中的 `{parameter}`，替换后输出 URL。
