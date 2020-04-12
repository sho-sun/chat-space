# README

* Deployment instructions

* ...
## usersテーブル

|Column|Type|Options|
|------|----|-------|
|email|string|null: false, index: true|
|password|string|null: false, index: true|
|nickname|string|null: false, index: true|

### Association
- has_many :comments
- has_many  :groups,  through:  :groups_users
- belongs_to :groups_users

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|

### Association
- has_many :comments
- has_many :groups_users
- has_many  :users,  through:  :groups_users

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|
|image|text|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group
