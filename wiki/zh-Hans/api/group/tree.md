# 获取小组[树结构列表]

- 接口地址：`/api/v2/group/tree`
- 请求方式：`GET`

## Headers 可选参数

| 参数名 | 公开模式（是否必传） | 私有模式（是否必传） |
| --- | --- | --- |
| aid | NO | YES |
| uid | NO | YES |
| token | NO | YES |

**接口使用说明**

- 本接口将获取全部小组，然后组装成树结构输出。
- 本接口使用场景类似于传统 BBS 版区，以树结构平铺所有小组（版区）。

## 返回结果

```json
{
    "code": 0,
    "message": "ok",
    "data": [
        {
            "gid": "String / 小组 ID",
            "gname": "String / 小组名称",
            "description": "String / 小组描述",
            "cover": "String / 小组封面图地址",
            "banner": "String / 小组条幅图地址",
            "groups": [
                {
                    // 通用数据结构->小组信息
                }
            ]
        }
    ]
}
```

::: details 开发说明
- 小组数据表 `type_find=2` 只有当前请求的用户已经 follow 了该小组才输出，否则不输出在列表中。
:::