# 下载过文件的用户

- 接口地址：`/api/fresns/v1/common/file/{fid}/users`
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
| fid | String | YES | 文件 FID |

## Query 参数

| 参数名 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| filterUserType | String | NO | `whitelist` 只返回给定键名的键值对<br>`blacklist` 从返回数据中删除指定的键值对<br>仅对返回结果中 `user` 参数有效 |
| filterUserKeys | String | NO | 多个以英文逗号隔开，支持「点表示法」表示多维数组 |
| pageSize | Number | NO | 每页显示条数（默认 15 条） |
| page | Number | NO | 页码（默认 1） |

## 返回结果

```json
{
    "code": 0,
    "message": "ok",
    "data": {
        "pagination": {
            "total": "Number / 一共有多少条数据",
            "pageSize": "Number / 每页有多少条数据",
            "currentPage": "Number / 当前页码",
            "lastPage": "Number / 最后一页页码"
        },
        "list": [
            {
                "datetime": "String / 下载时间",
                "timeAgo": "String / 人性化的下载时间",
                "user": {
                    // 通用数据结构->用户信息
                }
            }
        ]
    }
}
```

- [通用数据结构->用户信息](../../reference/data/user.md)
