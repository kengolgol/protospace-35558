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

# テーブル設計

##　usersテーブル

| column     | type   | options     |
|------------|--------|-------------|
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :prototypes
- has_many :comments


## prototypesテーブル

| column     | type       | options           |
|------------|------------|-------------------|
| title      | string     | null: false       |
| catch_copy | text       | null: false       |
| concept    | text       | null: false       |
| user       | references | foreign_key: true |

### Association

- belongs_to :user
- has_many :comments


## commentsテーブル

| column    | type       | options           |
|-----------|------------|-------------------|
| text      | text       | null: false       |
| user      | references | foreign_key: true |
| prototype | references | foreign_key: true |

### Association

- belongs_to :user
- belongs_to :comment
