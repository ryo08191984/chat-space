# README

## userテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false,add_index|
|email|integer|null: false,add_index|
|password|integer|null: false|

## Association
has_many :group, through:members
has_many :members

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false|

## Association
has_many :user, through:members
has_many :members

## membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## messegeテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user