## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|
## Association
- has_many :groups_users
- has_many :users, through: :groups_users
- hus_many :messages

### usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :groups_users
- has_many :groups, through: :groups_users
- has_many :messages

### messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|group_id|integer|null: false|
|user_id|integer|null: false|
## asociation
- belongs_to :user
- belongs_to :group

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

