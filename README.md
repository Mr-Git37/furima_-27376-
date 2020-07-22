# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
|name|string|null: false|
|birthday|integer|null: false|
### Association
- has_many :exhibition
- has_many :buy
- has_many :comments

## exhibitionテーブル
|Column|Type|Options|
|------|----|-------|
|image|string|null: false|
|title|text|null: false|
|description|string|null: false|
|user_id|integer|null: false, forign_key: true|
### Association
- has_many :comments
- belongs_to :user

## detailテーブル
|Column|Type|Options|
|------|----|-------|
|category|string|null: false|
|condition|string|null: false|
|delivery fee|string|null: false|
|shipping|string|null: false|
|day|integer|null: false|
|price|integer|null: false|
### Association
- belongs_to :exhibition

## buyテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|nummber|integer|null: false|
|deadline|string|null: false|
|user_id|integer|null: false, forign_key: true|
### Association
- belongs_to :user
- belongs_to :exhibition

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, forign_key: true|
|exhibition_id|integer|null: false, forign_key: true|
### Association
- belongs_to :user
- belongs_to :exhibition