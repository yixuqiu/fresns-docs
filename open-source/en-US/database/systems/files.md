---
aside: false
---

# files

| Column Name | Type | Comment | Default | Null | Remark |
| --- | --- | --- | --- | --- | --- |
| id | bigint *UNSIGNED* | Primary Key ID |  | NO | Auto Increment |
| fid | varchar(32) | Publicly available ID |  | NO | **Unique** |
| type | tinyint *UNSIGNED* | File Type | 1 | NO | 1.Image / 2.Video / 3.Audio / 4.Document |
| name | varchar(128) | File Name |  | NO | Full original name, filename when uploading, including extension |
| mime | varchar(255) | File Mime Type |  | NO | For example: image/jpeg or video/mp4 |
| extension | varchar(32) | File Extension Name |  | NO | For example: jpg or jpeg |
| size | int *UNSIGNED* | File Size |  | NO | Unit Byte |
| width | smallint *UNSIGNED* | Image Width |  | YES | Image file specific: pixels px |
| height | smallint *UNSIGNED* | Image Height |  | YES | Image file specific: pixels px |
| duration | smallint *UNSIGNED* | Audio and Video Duration |  | YES | Unit: seconds |
| sha | varchar(128) | File sha |  | YES | File sha encoding |
| sha_type | varchar(16) | File sha Type |  | YES | For example, `sha1` or `sha256` |
| warning_type | tinyint *UNSIGNED* | Warning Type | 1 | NO | 1.No 2.Nudity 3.Violence 4.Sensitive |
| path | varchar(255) | File Path |  | NO | **Relative path** |
| transcoding_state | tinyint *UNSIGNED* | Audio or Video Attachment Transcoding Status | 1 | YES | Transcoding status: 1.Pending 2.Transcoding 3.Transcoding Completed 4.Transcoding Failed |
| transcoding_reason | varchar(255) | Audio or Video Attachment Transcoding Failure Reason |  | YES | Transcoding failure reason |
| video_poster_path | varchar(255) | Video Cover Image |  | YES | Video cover image path |
| original_path | varchar(255) | Original File Path |  | YES | **Relative path**<br>If the file involves transcoding, the storage path of the file before transcoding<br>If not, leave empty |
| is_long_image | tinyint *UNSIGNED* | Is Long Image | 0 | NO | Image file specific<br>0.No / 1.Yes |
| is_uploaded | tinyint *UNSIGNED* | Is Uploaded | 1 | NO | 0.No / 1.Yes |
| is_enabled | tinyint *UNSIGNED* | Is Valid | 1 | NO | 0.Invalid / 1.Valid |
| physical_deletion | tinyint *UNSIGNED* | Physical Deletion Status | 0 | NO | 0.No / 1.Yes (File physically deleted) |
| created_at | timestamp | Create Time | useCurrent | NO | For example, MySQL defaults to `CURRENT_TIMESTAMP` |
| updated_at | timestamp | Update Time |  | YES |  |
| deleted_at | timestamp | Delete Time |  | YES |  |

## File Types

| type | File Type | Domain stored in which key name | Backend Setting Interface |
| --- | --- | --- | --- |
| 1 | Image | image_bucket_domain | Panel > Systems > Storage > Image |
| 2 | Video | video_bucket_domain | Panel > Systems > Storage > Video |
| 3 | Audio | audio_bucket_domain | Panel > Systems > Storage > Audio |
| 4 | Document | document_bucket_domain | Panel > Systems > Storage > Document |

## Long Image Description

Field: `is_long_image`

When the image width is greater than 700, if the height is equal to or greater than 3.5 times the width, it is considered a long image.

For example:
- image_width = 700
- image_height = 2100
