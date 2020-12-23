# README

## usersテーブル

| Column               | Type    | Options      |
| -------------------- | ------- | ------------ |
| nickname             | string  | null: false  |
| email                | string  | unique: true |
| encrypted_password   | string  | null: false  |
| last_name            | string  | null: false  |
| first_name           | string  | null: false  |
| last_name_kana       | string  | null: false  |
| first_name_kana      | string  | null: false  |
| birthday             | string  | null: false  |


### Association

- has_many :items

## items テーブル

| Column              | Type       | Options                        |
| ------------------- | ---------- | ------------------------------ |
| name                | string     | null: false                    |
| description         | text       | null: false                    |
| user                | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :address

## addresses テーブル

| Column           | Type       | Options                        |
| ---------------- | ---------- | ------------------------------ |
| postcode         | integer    | null: false                    |
| prefectures      | string     | null: false                    |
| address_city     | string     | null: false                    |
| address_street   | string     | null: false                    |
| address_building | string     |                                |
| phone_number     | integer    | null: false                    |
| user             | references | null:false, foreign_key: true  |


### Association

- belongs_to :user
- belongs_to :item

## histories テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null:false, foreign_key: true  | 
| name   | string     | null:false                     |

### Association
- belongs_to :address

