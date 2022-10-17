# 编辑器配置信息

- 接口地址：`/api/v2/editor/{type}/config`
- 请求方式：`GET`
- 传参方式：`Rest`

## Headers 可选参数

| 参数名 | 公开模式（是否必传） | 私有模式（是否必传） |
| --- | --- | --- |
| aid | YES | YES |
| uid | YES | YES |
| token | YES | YES |

## Rest 参数

| 参数名 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| type | String | YES | `post` 或 `comment` |

## 返回结果

**帖子**

```json
{
    "code": 0,
    "message": "ok",
    "data": {
        "editor": {
            "toolbar": {
                "sticker": "Boolean / 是否启用表情",
                "image": {
                    "status": "Boolean / 是否启用图片",
                    "extensions": "String / 支持的扩展名，示例 png,gif,jpg,jpeg,bmp,heic",
                    "inputAccept": "String / 支持的扩展名，示例 .png,.gif,.jpg,.jpeg,.bmp,.heic",
                    "maxSize": "Number / 最大文件尺寸，单位 MB",
                    "uploadNumber": "Number / 允许上传个数"
                },
                "video": {
                    "status": "Boolean / 是否启用视频",
                    "extensions": "String / 支持的扩展名，示例 wmv,rm,mov,mpeg,mp4,3gp,flv,avi,rmvb",
                    "inputAccept": "String / 支持的扩展名，示例 .wmv,.rm,.mov,.mpeg,.mp4,.3gp,.flv,.avi,.rmvb",
                    "maxSize": "Number / 最大文件尺寸，单位 MB",
                    "maxTime": "Number / 最大文件时长，单位 秒",
                    "uploadNumber": "Number / 允许上传个数"
                },
                "audio": {
                    "status": "Boolean / 是否启用音频",
                    "extensions": "String / 支持的扩展名，示例 mp3,wav,m4a",
                    "inputAccept": "String / 支持的扩展名，示例 .mp3,.wav,.m4a",
                    "maxSize": "Number / 最大文件尺寸，单位 MB",
                    "maxTime": "Number / 最大文件时长，单位 秒",
                    "uploadNumber": "Number / 允许上传个数"
                },
                "document": {
                    "status": "Boolean / 是否启用文档",
                    "extensions": "String / 支持的扩展名，示例 doc,docx,xls,xlsx,csv,ppt,pptx,pps,ppts,pdf,txt,md,markdown,rar,zip,7z,epub,mobi",
                    "inputAccept": "String / 支持的扩展名，示例 .doc,.docx,.xls,.xlsx,.csv,.ppt,.pptx,.pps,.ppts,.pdf,.txt,.md,.markdown,.rar,.zip,.7z,.epub,.mobi",
                    "maxSize": "Number / 最大文件尺寸，单位 MB",
                    "uploadNumber": "Number / 允许上传个数"
                },
                "title": {
                    "status": "Boolean / 是否启用标题",
                    "view": "Number / 1.默认显示 2.默认隐藏",
                    "required": "Boolean / 是否必填",
                    "length": "Number / 最大长度"
                },
                "mention": "Boolean / 是否显示艾特按钮",
                "hashtag": {
                    "status": "Boolean / 是否显示话题按钮",
                    "showMode": "Number / 话题格式 1.单 # 2.双 #"
                },
                "expand": {
                    "status": "Boolean / 是否启用扩展",
                    "list": [
                        {
                            // 通用数据结构->扩展功能信息
                        }
                    ]
                }
            },
            "features": {
                "group": {
                    "status": "Boolean / 是否启用小组",
                    "required": "Boolean / 是否必选"
                },
                "location": {
                    "status": "Boolean / 是否启用位置",
                    "maps": [
                        {
                            // 通用数据结构->扩展功能信息
                        }
                    ]
                },
                "anonymous": "Boolean / 是否支持匿名",
                "contentLength": "Number / 内容最大长度"
            }
        },
        "publish": {
            "perm": {
                "draft": "Boolean / 是否可以创建新草稿",
                "publish": "Boolean / 是否有权限表表",
                "review": "Boolean / 发表是否需要审核",
                "emailRequired": "Boolean / 邮箱要求是否通过",
                "phoneRequired": "Boolean / 手机要求是否通过",
                "realNameRequired": "Boolean / 实名制要求是否通过",
                "tips": [
                    "String / 无要求的请求语 1",
                    "String / 无要求的请求语 2"
                ]
            },
            "limit": {
                "status": "Boolean / 是否有特殊规则",
                "type": "Number / 1.指定某个时间段范围内生效 2.指定每天的某个时间段范围内循环生效",
                "periodStart": "String / type=1 专用，开始日期时间",
                "periodEnd": "String / type=1 专用，结束日期时间",
                "cycleStart": "String / type=2 专用，开始时间",
                "cycleEnd": "String / type=2 专用，结束时间",
                "rule": "Number / 1.可以发表，但是需要审核 2.禁止发表",
                "tip": "String / 提示语"
            }
        },
        "editPerm": {
            "status": "Boolean / 是否有权编辑",
            "timeLimit": "Number / 多长时间内可以编辑",
            "editSticky": "Boolean / 帖子置顶后是否可编辑",
            "editDigest": "Boolean / 帖子加精后是否可编辑"
        }
    }
}
```