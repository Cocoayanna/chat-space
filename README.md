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

|column|type|options|
|group_id|integer|
|group_name|string|null: false|
|member|user_id|foreign_key: true|

## Association
- has_many :messages
- has_many :users, through: groups_users##

## messageテーブル 

|column|type|options|
|body|text|
|image|string|
|user_id |integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

## Association
- belongs_to :user
- belongs_to :group

## groups_usersテーブル

column|type|option
|user_id |integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

## Association
- belong_to :user
- belong_to :group