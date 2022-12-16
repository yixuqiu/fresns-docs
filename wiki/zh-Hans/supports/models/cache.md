# Cache

- 以下列表为缓存键名规则和标签，一个缓存键可能有多个标签。
- 注意：使用 `file`、`dynamodb` 或 `database` 缓存驱动程序时不支持缓存标记。

```php
use App\Helpers\CacheHelper;

CacheHelper::isSupportTags();
// false or true
```

## 无标签

```php
fresns_cache_is_support_tags
fresns_crontab_items
install_{$step}
autoUpgradeStep
autoUpgradeTip
physicalUpgradeStep
physicalUpgradeTip
```

## 系统

- tag: `fresnsSystems`

```php
fresns_current_version
fresns_new_version
fresns_news
fresns_database_timezone
fresns_database_datetime
fresns_panel_login_path
fresns_panel_translation_{$locale}
fresns_model_key_{$appId}
```

## 配置

- tag: `fresnsConfigs`

```php
fresns_default_langTag
fresns_default_timezone
fresns_lang_tags
fresns_config_{$itemKey}_{$langTag}
fresns_config_keys_{$key}_{$langTag}
fresns_config_tag_{$itemTag}_{$langTag}
fresns_config_file_accept
fresns_config_file_url_expire
fresns_plugin_url_{$unikey}
fresns_content_block_words // fresns_{$type}_block_words
fresns_user_block_words // fresns_{$type}_block_words
fresns_conversation_block_words // fresns_{$type}_block_words
fresns_content_ban_words
fresns_content_review_words
fresns_user_ban_words
fresns_conversation_ban_words
fresns_editor_{$type}_extends_{$roleId}_{$langTag}
```

## 多语言

- tag: `fresnsLanguages`
- tag: `fresnsUnknownLanguages`
- tag: `fresnsPluginUsageLanguages`
- tag: `fresnsRoleLanguages`
- tag: `fresnsStickerLanguages`
- tag: `fresnsNotificationLanguages`

```php
fresns_{$tableName}_{$tableColumn}_{$tableId}_{$langTag}
```

## 状态码描述

- tag: `fresnsCodeMessages`

```php
fresns_code_messages_{$unikey}_{$langTag}
```

## 账号

- tag: `fresnsAccounts`

```php
fresns_token_account_{$accountId}_{$token}   // +tag: fresnsAccountTokens
fresns_model_account_{$aid}                  // +tag: fresnsAccountModels
fresns_api_account_{$aid}_{$langTag}         // +tag: fresnsAccountData
```

## 用户

- tag: `fresnsUsers`

```php
fresns_token_user_{$userId}_{$token}                         // +tag: fresnsUserTokens
fresns_model_user_{$uidOrUsername}                           // +tag: fresnsUserModels
fresns_model_user_{$userId}                                  // +tag: fresnsUserModels
fresns_model_conversation_{$userId}_{$conversationUserId}    // +tag: fresnsUserConversations
fresns_user_{$userId}_main_role_{$langTag}                   // +tag: fresnsUserRoles
fresns_user_{$userId}_roles_{$langTag}                       // +tag: fresnsUserRoles
fresns_publish_{$type}_config_{$userId}_{$langTag}           // +tag: fresnsUserConfigs
fresns_interaction_status_{$markType}_{$markId}_{$userId}    // +tag: fresnsUserInteractions
fresns_follow_{$type}_array_by_{$userId}                     // +tag: fresnsUserInteractions, fresnsFollowData
fresns_block_{$type}_array_by_{$userId}                      // +tag: fresnsUserInteractions, fresnsBlockData
fresns_seo_user_{$userId}                                    // +tag: fresnsUserData
fresns_api_user_{$uid}_{$langTag}                            // +tag: fresnsUserData
fresns_api_user_panel_conversations_{$uid}                   // +tag: fresnsUserData, fresnsUserConversations
fresns_api_user_panel_notifications_{$uid}                   // +tag: fresnsUserData, fresnsUserNotifications
fresns_api_user_panel_drafts_{$uid}                          // +tag: fresnsUserData, fresnsUserDrafts
```

## 小组

- tag: `fresnsGroups`

```php
fresns_group_count                                           // +tag: fresnsGroupConfigs
fresns_private_groups                                        // +tag: fresnsGroupConfigs
fresns_filter_groups_by_guest                                // +tag: fresnsGroupConfigs, fresnsUsers, fresnsUserInteractions
fresns_filter_groups_by_user_{$userId}                       // +tag: fresnsGroupConfigs, fresnsUsers, fresnsUserInteractions
fresns_model_group_{$gid}                                    // +tag: fresnsGroupModels
fresns_model_group_{$groupId}                                // +tag: fresnsGroupModels
fresns_group_admins_{$groupId}                               // +tag: fresnsGroupAdmins
fresns_seo_group_{$groupId}                                  // +tag: fresnsGroupData
fresns_guest_all_groups                                      // +tag: fresnsGroupData
fresns_user_{$userId}_all_groups                             // +tag: fresnsGroupData, fresnsUsers, fresnsUserData
fresns_follow_group_model_{$id}_by_{$userId}                 // +tag: fresnsGroupData, fresnsUsers, fresnsUserInteractions, fresnsFollowData
fresns_api_group_{$gid}_{$langTag}                           // +tag: fresnsGroupData
fresns_api_group_{$gid}_extensions_{$userId}_{$langTag}      // +tag: fresnsGroupExtensions
```

## 话题

- tag: `fresnsHashtags`

```php
fresns_model_hashtag_{$hid}              // +tag: fresnsHashtagModels
fresns_model_hashtag_{$hashtagId}        // +tag: fresnsHashtagModels
fresns_seo_hashtag_{$id}                 // +tag: fresnsHashtagData
fresns_api_hashtag_{$hid}_{$langTag}     // +tag: fresnsHashtagData
```

## 帖子

- tag: `fresnsPosts`

```php
fresns_model_post_{$pid}                             // +tag: fresnsPostModels
fresns_model_post_{$postId}                          // +tag: fresnsPostModels
fresns_seo_post_{$id}                                // +tag: fresnsPostData
fresns_api_post_{$pid}_{$langTag}                    // +tag: fresnsPostData
fresns_api_post_{$pid}_list_content                  // +tag: fresnsPostData
fresns_api_post_{$pid}_detail_content                // +tag: fresnsPostData
fresns_api_post_{$pid}_allow_{$uid}                  // +tag: fresnsPostData, fresnsUsers, fresnsUserData
fresns_api_post_{$postId}_top_comments_{$langTag}    // +tag: fresnsPostData, fresnsComments, fresnsCommentData
```

## 评论

- tag: `fresnsComments`

```php
fresns_model_comment_{$cid}                              // +tag: fresnsCommentModels
fresns_model_comment_{$commentId}                        // +tag: fresnsCommentModels
fresns_seo_comment_{$id}                                 // +tag: fresnsCommentData
fresns_api_comment_{$cid}_{$langTag}                     // +tag: fresnsCommentData
fresns_api_comment_{$cid}_list_content                   // +tag: fresnsCommentData
fresns_api_comment_{$cid}_detail_content                 // +tag: fresnsCommentData
fresns_api_comment_{$commentId}_sub_comments_{$langTag}  // +tag: fresnsCommentData
```

## 模型

- tag: `fresnsModels`

```php
fresns_model_file_{$fid}                         // +tag: fresnsFiles
fresns_model_file_{$fileId}                      // +tag: fresnsFiles
fresns_model_extend_{$eid}                       // +tag: fresnsExtends
fresns_model_extend_{$extendId}                  // +tag: fresnsExtends
fresns_model_archive_{$code}                     // +tag: fresnsArchives
fresns_model_archive_{$archiveId}                // +tag: fresnsArchives
fresns_model_operation_{$operationId}            // +tag: fresnsOperations
fresns_model_conversation_{$conversationId}      // +tag: fresnsConversations
```

## 扩展

- tag: `fresnsExtensions`

```php
fresns_wallet_extends_{$langTag}
fresns_{$type}_content_types_{$langTag}                  // +tag: fresnsConfigs
fresns_{$type}_manages_by_everyone_{$langTag}            // +tag: fresnsManages
fresns_{$type}_manages_by_group_{$langTag}               // +tag: fresnsManages, fresnsGroupConfigs
fresns_{$type}_manages_by_role_{$roleId}_{$langTag}      // +tag: fresnsManages
fresns_features_{$userId}_{$langTag}                     // +tag: fresnsUserData, fresnsUserFeatures
fresns_profiles_{$userId}_{$langTag}                     // +tag: fresnsUserData, fresnsUserProfiles
fresns_user_manages_{$rid}_{$langTag}                    // +tag: fresnsConfigs
```

## API 数据

- tag: `fresnsApiData`

```php
fresns_api_archives_{$type}_{$unikey}_{$langTag}     // +tag: fresnsArchives
fresns_api_sticker_tree_{$langTag}                   // +tag: fresnsConfigs
```