# Functions

## Theme Info

```php
fs_theme('fskey', '')
```

- `fskey`
- `version`
- `assets`, `{file/path}`
- `lang`
- `login`, `redirectURL`

## Config Items

Get configuration values from API [global configuration information](../../reference/configs.md)

```php
fs_config('item_key')
```

## Language Pack

- [Language Pack Information](../../reference/language-pack.md)
- Configuration Path `Panel > Clients > Language Packs`

```php
fs_lang('KeyName')
```

## Channel Extends

- [Channel Information](../../api/global/channels.md)

```php
fs_channels()
```

## Content Types

- [Content Types Array](../../api/global/content-types.md)

```php
fs_content_types('post') // post or comment
```

## Content Data

### Content List

```php
fs_content_list('Channel', 'Type')
```

- Channel
    - `user`
    - `group`
    - `hashtag`
    - `geotag`
    - `post`
    - `comment`
- Type
    - `home`
    - `list`

### Sticky Post List

```php
# Global Sticky
fs_sticky_posts()

# Sticky of the group
fs_sticky_posts($gid)
```

### Sticky Comment List

```php
fs_sticky_comments($pid)
```

## Account and User

```php
# Is the account logged in
fs_account()->check()
fs_account()->guest()

# Is the user logged in
fs_user()->check()
fs_user()->guest()
```

```php
# Account Parameters
fs_account('key') // supports "dot notation" for multi-dimensional arrays

# User Parameters
fs_user('key') // supports "dot notation" for multi-dimensional arrays

# User Overview Parameters
fs_user_overview('key', 'uidOrUsername') // supports "dot notation" for multi-dimensional arrays
// uidOrUsername If empty, uses the currently logged in user
```

- The parameter key comes from the API `data` parameter.
- [Account Detail API](../../api/account/detail.md)
- [User Detail API](../../api/user/detail.md)
- [User Overview API](../../api/user/overview.md)

## Editor Configs

- [Editor Configs](../../api/editor/configs.md)
- [Stickers Array](../../api/global/stickers.md)

```php
fs_editor_post('key') // supports "dot notation" for multi-dimensional arrays

fs_editor_comment('key') // supports "dot notation" for multi-dimensional arrays

fs_editor_stickers()
```

## Helpers

```php
fs_helpers('Helper', 'Method', $data, $options)

fs_helpers('Arr', 'get', $data, $options)
```

::: details Get Specified Value `Arr::get`
From an array, get the array with the specified key name for the specified key value.

- Helper: `Arr`
- Method: `get`
- Arr Data: `$data`
- Options: `$options`
    - `key` Arr List Key Name
    - `values` The key value that matches the condition, a single string or multiple arrays
    - `asArray` Boolean value, whether to keep it in array format when there is only one entry left in the result
:::

::: details Remove Specified Value `Arr::forget`
From an array, removes the array with the specified key name for the specified key value.

- Helper: `Arr`
- Method: `forget`
- Arr Data: `$data`
- Options: `$options`
    - `key` Arr List Key Name
    - `values` The key value that matches the condition, a single string or multiple arrays
    - `asArray` Boolean value, whether to keep it in array format when there is only one entry left in the result
:::

::: details Return and Clear Specified Value `Arr::pull`
Returns the value of the specified key from the array and removes this key-value pair.

- Helper: `Arr`
- Method: `pull`
- Arr Data: `$data`
- Options: `$options`
    - `key` Arr List Key Name
    - `values` The key value that matches the condition, a single string or multiple arrays
    - `asArray` Boolean value, whether to keep it in array format when there is only one entry left in the result
:::

## Client Options

Reference: [https://github.com/hisorange/browser-detect](https://github.com/hisorange/browser-detect)

```blade
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
