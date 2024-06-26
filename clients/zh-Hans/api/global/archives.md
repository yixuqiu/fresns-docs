# 扩展档案

- 接口地址：`/api/fresns/v1/global/{type}/archives`
- 请求方式：`GET`
- 传参方式：`Rest` + `Query`

## Headers 可选参数

| 参数名 | 公开模式（是否必传） | 私有模式（是否必传） |
| --- | --- | --- |
| X-Fresns-Aid | YES | YES |
| X-Fresns-Aid-Token | YES | YES |
| X-Fresns-Uid | YES | YES |
| X-Fresns-Uid-Token | YES | YES |

## Path 变量

| 变量名 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| type | String | YES | `user`,`post`,`comment` |

## Query 参数

| 参数名 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| gid | String | NO | 配合 `post` 或 `comment` 使用，获取指定小组的内容配置 |

## 返回结果

```json
{
    "code": 0,
    "message": "ok",
    "data": [
        {
            "fskey": "String / 应用 Fskey",
            "name": "String / 名称",
            "description": "String / 描述",
            "code": "String / Code",
            "formElement": "String / HTML 表单元素",
            "elementType": "String / 表单元素类型",
            "elementOptions": "Array / 选项类型配置值",
            "isMultiple": "Boolean / 是否多选，对 select,file 等元素有效",
            "isRequired": "Boolean / 是否必填",
            "fileType": "Number / 1.图片 2.视频 3.音频 4.文档", // elementType 为 file 时使用
            "fileExtensions": "String / 支持的文件后缀，例如 jpg,png", // elementType 为 file 时使用
            "fileAccept": "String / 支持的文件后缀，例如 .jpg,.png", // elementType 为 file 时使用
            "inputPattern": "String / 自定义正则表达式",
            "inputMax": "Number / 最大值",
            "inputMin": "Number / 最小值",
            "inputMaxlength": "Number / 最大长度",
            "inputMinlength": "Number / 最小长度",
            "inputSize": "Number / 大小",
            "inputStep": "Number / 步骤",
            "valueType": "String / 数据值类型"
        }
    ]
}
```
