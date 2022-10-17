# 账号功能

## 添加账号

```php
\FresnsCmdWord::plugin('Fresns')->addAccount($wordBody)
```
| 参数名 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| type | Number | YES | 账号类型：1.邮箱 / 2.手机号 / 3.互联平台 |
| account | String | NO/YES | 邮箱或手机号专用：邮箱地址 / 手机号码（`type=1 或 2` 时必填） |
| countryCode | Number | NO/YES | 手机号专用：国际区号（`type=2` 时必填） |
| connectInfo | Array | NO/YES | 互联平台专用：平台信息（`type=3` 时必填） |
| password | String | NO | 登录密码 |

::: details 结果示例
```json
{
    "code": 0,
    "message": "ok",
    "data": {
        "type": "accounts > type",
        "aid": "accounts > aid"
    }
}
```
:::

::: details 查看 connectInfo 参数介绍
支持多个，例如微信平台会同时有 UnionID 和 OpenID 两个参数。
```json
[
    {
        "connectId": 8, //存储到 account_connects > connect_id
        "connectToken": "unionid", //存储到 account_connects > connect_token
        "connectRefreshToken": null, //存储到 account_connects > connect_refresh_token
        "connectName": "账号名", //存储到 account_connects > connect_name
        "connectNickname": "昵称", //存储到 account_connects > connect_nickname
        "connectAvatar": "头像 URL", //存储到 account_connects > connect_avatar
    },
    {
        "connectId": 9,
        "connectToken": "openid",
        "connectRefreshToken": null,
        "connectName": "账号名",
        "connectNickname": "昵称",
        "connectAvatar": "头像 URL",
    }
]
```
:::

::: details 查看注册逻辑
- 注册时需要生成的数据清单
    - 账号主表 `accounts`
    - 账号钱包表 `account_wallets`
    - 其余传参有值时直接录入，无值时留空。
- 注册完成后，增加数据统计。配置表键值 `accounts_count +1`。
:::

## 校验账号

```php
\FresnsCmdWord::plugin('Fresns')->verifyAccount($wordBody)
```
| 参数名 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| type | Number | YES | 账号类型：1.邮箱 / 2.手机号 |
| account | String | YES | 邮箱地址<br>手机号码 |
| countryCode | Number | NO | 手机号专用：国际区号（`type=2` 时必填） |
| password | String | NO | 以密码校验专用 |
| verifyCode | String | NO | 以验证码校验专用（命令字 [checkCode](#校验验证码) 查验） |

::: details 结果示例
```json
{
    "code": 0,
    "message": "ok",
    "data": {
        "type": "accounts > type",
        "aid": "accounts > aid",
    }
}
```
:::

## 创建交互凭证

```php
\FresnsCmdWord::plugin('Fresns')->createSessionToken($wordBody)
```
| 参数名 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| platformId | Number | YES | 平台编号（配置表 [platforms](../../database/dictionary/platforms.md) 键名的键值） |
| aid | String | YES | 账号参数 `session_tokens > account_id`<br>存储时由 `aid` 转换成 `accounts > id` |
| uid | Number | NO | 用户参数 `session_tokens > user_id`<br>存储时由 `uid` 转换成 `users > id` |
| expiredTime | Number | NO | 过期时间，单位：小时（为空代表永久有效） |

::: details 创建逻辑
- 账号（aid）或者账号+用户（aid+uid），同一个平台编号（platformId）仅能存在一个 token
- 创建时如果存在则更新 token 或删除旧的，生成新的
:::
::: details 结果示例
```json
{
    "code": 0,
    "message": "ok",
    "data": {
        "aid": "accounts > aid",
        "uid": "users > uid", //没有则输出 null
        "token": "session_tokens > token",
        "expiredTime": "session_tokens > expired_at 留空代表永久有效，格式为 Y-m-d H:i:s" //没有则输出 null
    }
}
```
:::

## 校验交互凭证

```php
\FresnsCmdWord::plugin('Fresns')->verifySessionToken($wordBody)
```
| 参数名 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| platformId | Number | YES | 平台编号（配置表 [platforms](../../database/dictionary/platforms.md) 键名的键值） |
| aid | String | YES | 账号参数 `session_tokens > account_id`<br>查验时由 `aid` 转换成 `accounts > id` |
| uid | Number | NO | 用户参数 `session_tokens > user_id`<br>查验时由 `uid` 转换成 `users > id` |
| token | String | YES | 身份凭证（凭证表 `session_tokens > token` 字段） |

## 逻辑删除账号

```php
\FresnsCmdWord::plugin('Fresns')->logicalDeletionAccount($wordBody)
```
| 参数名 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| aid | Number | YES | `accounts > aid` |