# Comment List by Nearby

- Endpoint Path: `/api/v2/comment/nearby`
- Method: `GET`
- Request: `Query`

## Headers Optional Parameter

| Parameter Name | Public Mode (Required) | Private Mode (Required) |
| --- | --- | --- |
| aid | *optional* | **required** |
| uid | *optional* | **required** |
| token | *optional* | **required** |

## Body Params

| Parameter Name | Type | Required | Description |
| --- | --- | --- | --- |
| mapId | Number | **required** | 地图服务商编号 |
| mapLng | String | **required** | 地图经度（用于查询附近帖子） |
| mapLat | String | **required** | 地图纬度（用于查询附近帖子） |
| unit | String | *optional* | 范围单位 km / mi |
| length | Number | *optional* | 范围 |
| contentType | String | *optional* | 指定类型：内容类型扩展配置的参数，为空或者为 all，则输出全部内容 |
| pluginRatingId | Number | *optional* | 排序编号（插件专用） |
| pageSize | Number | *optional* | 每页显示条数（默认 30 条） |
| page | Number | *optional* | 页码（默认 1） |

## Return

```json
{
    "code": 0,
    "message": "ok",
    "data": {
        "pagination": {
            "total": "Number / How much data in total",
            "current": "Number / Current page number",
            "pageSize": "Number / How much data on each page",
            "lastPage": "Number / Last page number"
        },
        "list": [
            {
                // Common Data Structure -> Comment Info
            }
        ]
    }
}
```