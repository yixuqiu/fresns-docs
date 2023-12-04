# 模板标签

## 路由

```php
{{ fs_route(route('路由名')) }}

{{ fs_route(route('fresns.user.index')) }}
```

- `route` 系统中实际的路由
- `fs_route` 处理路由为多语言路由

## 配置值

### 接口配置

从 API [全局配置信息](../../api/global/configs.md)获取配置值

```php
{{ fs_api_config('配置键名') }}
```

### 数据库配置

从本地数据库 [configs](../../database/systems/configs.md) 表获取配置值

```php
{{ fs_db_config('配置键名') }}
```

## 语言配置

- [语言包信息](../../database/dictionary/language-pack.md)
- 配置位置 `控制面板 > 客户端 > 语言包配置`

```php
{{ fs_lang('语言键名') }}
```

- [状态码信息](../../api/error-code.md)
- 配置位置 `控制面板 > 客户端 > 状态码配置`

```php
{{ fs_code_message('编号') }}
```

## 账号和用户参数

```php
# 是否登录账号
fs_account()->check()
fs_account()->guest()

# 是否登录用户
fs_user()->check()
fs_user()->guest()
```

```php
# 账号参数
fs_account('参数名')

# 用户参数
fs_user('参数名')
```

- 参数名来自 API `data` 参数。
- [账号 API](../../api/account/detail.md)
- [用户 API](../../api/user/detail.md)

## 频道扩展

```php
fs_channels()
```

## 全局数据

### 用户面板

```php
fs_user_panel('key')
// 或者
fs_user_panel('key.key')
```

- 参数来自[用户面板](../../api/user/panel.md)接口 `data`

### 小组

```php
fs_groups('categories') // 小组分类
fs_groups('tree') // 树结构全部小组
```

### 首页列表

```php
fs_index_list('users') // 用户首页列表
fs_index_list('groups') // 小组首页列表
fs_index_list('hashtags') // 话题首页列表
fs_index_list('posts') // 帖子首页列表
fs_index_list('comments') // 评论首页列表
```

以上封装函数仅获取第一页内容，如需翻页，则使用以下接口。

```php
// 1.路由方式
route('fresns.api.index.list', [$type => 'users', 'page' => 2]) // 用户首页列表
route('fresns.api.index.list', [$type => 'groups', 'page' => 2]) // 小组首页列表
route('fresns.api.index.list', [$type => 'hashtags', 'page' => 2]) // 话题首页列表
route('fresns.api.index.list', [$type => 'posts', 'page' => 2]) // 帖子首页列表
route('fresns.api.index.list', [$type => 'comments', 'page' => 2]) // 评论首页列表

// 2.路径方式
/api/engine/index-list/users?page=2
/api/engine/index-list/groups?page=2
/api/engine/index-list/hashtags?page=2
/api/engine/index-list/posts?page=2
/api/engine/index-list/comments?page=2
```

### 列表

```php
fs_list('users') // 用户列表
fs_list('groups') // 小组列表
fs_list('hashtags') // 话题列表
fs_list('posts') // 帖子列表
fs_list('comments') // 评论列表
```

以上封装函数仅获取第一页内容，如需翻页，则使用以下接口。

```php
// 1.路由方式
route('fresns.api.list', [$type => 'users', 'page' => 2]) // 用户首页列表
route('fresns.api.list', [$type => 'groups', 'page' => 2]) // 小组首页列表
route('fresns.api.list', [$type => 'hashtags', 'page' => 2]) // 话题首页列表
route('fresns.api.list', [$type => 'posts', 'page' => 2]) // 帖子首页列表
route('fresns.api.list', [$type => 'comments', 'page' => 2]) // 评论首页列表

// 2.路径方式
/api/engine/list/users?page=2
/api/engine/list/groups?page=2
/api/engine/list/hashtags?page=2
/api/engine/list/posts?page=2
/api/engine/list/comments?page=2
```

### 置顶帖子

```php
# 全局置顶
fs_sticky_posts()

# 指定小组的置顶
fs_sticky_posts($gid)
```

### 置顶评论

```php
fs_sticky_comments($pid)
```

### 内容类型

```php
fs_content_types($type) // post or comment
```

### 表情

```php
fs_stickers()
```

## 客户端判断

```html
@mobile
    <p>This is the MOBILE template!</p>
    @include('your-mobile-template')
@endmobile

@tablet
    <p>This is the TABLET template!</p>
    <link rel="stylesheet" href="tablet.css" title="Reduce the page size, load what the user need">
@endtablet

@desktop
    <p>This is the DESKTOP template!</p>
@enddesktop

<!-- Every result key is supported -->
@browser('isBot')
    <p>Bots are identified too :)</p>
@endbrowser
```

## 列表和详情页

参数名详见对应接口的 API 数据和[通用数据结构](../../api/data-structure.md)。