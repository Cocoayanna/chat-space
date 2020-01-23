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

## groupテーブル

|Column|type|options|
|------|----|-------|
|group_id|integer|null: false|
|group_name|string|null: false|
|user_id|integer|null: false, foreign_key: true|

## Association
- has_many :messages
- has_many :users, through: groups_users##

## messageテーブル 

||Column|type|options|
|------|----|-------|
|body|text|null: false|
|image|string|null: false|
|user_id |integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

## Association
- belongs_to :user
- belongs_to :group

## groups_usersテーブル

|Column|type|options|
|------|----|-------|
|user_id |integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

## Association
- belong_to :user
- belong_to :group