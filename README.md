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

| Column      | Type         | Options                         |
| ----------- | ------------ | ------------------------------- |
| nickname    | string       | null: false                     |
| email       | string       | null: false                     |
| encrypted   | string       | null: false                     |
-has_many :tweets
-has_many :comments

## tweetsテーブル

| Column      | Type         | Options                         |
| ----------- | ------------ | ------------------------------- |
| text        | string       |                                 |
| user        | references   | null: false, foreign_key: true  |
-belongs_to :user
-has_many :comments

## commentsテーブル
| Column      | Type         | Options                         |
| ----------- | ------------ | ------------------------------- |
| text        | string       | null: false                     |
| user        | references   | null: false, foreign_key: true  |
| tweet       | references   | null: false, foreign_key: true  |
-belongs_to :user
-belongs_to :tweet

