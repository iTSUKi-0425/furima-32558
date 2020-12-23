# README

## usersテーブル

| Column     | Type    | Options     |
| ---------- | ------- | ------------|
| nickname   | string  | null: false |
| email      | string  | null: false |
| password   | string  | null: false |
| name       | string  | null: false |
| name_kana  | string  | null: false |


### Association

- has_many :items
- has_many :comments

## items テーブル

| Column              | Type       | Options                        |
| ----------          | ---------- | ------------------------------ |
| item_name           | string     | null: false                    |
| product_name        | string     | null: false                    |
| product_description | text       | null: false                    |
| user                | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_many :comments

## commentsテーブル

| Column     | Type           | Options                        |
| ---------- | -------------- | ------------------------------ |
| text       | text           | null: false                    |
| user       | references     | null: false  foreign_key: true |
| item       | references     | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :item