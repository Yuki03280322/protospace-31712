# ProtoSpaceのER図

## users テーブル

| Column     | Type   | Option      |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :comments
- has_many :prototypes

## comments テーブル

| Column    | Type       | Option            |
| --------- | ---------- | ----------------- |
| text      | text       | null: false       |
| user      | references | foreign_key: true |
| prototype | references | foreign_key: true |

### Association

- belongs_to :user
- belongs_to :prototype

## prototypes テーブル

| Column     | Type       | Option            |
| ---------- | ---------- | ----------------- |
| title      | string     | null: false       |
| catch_copy | text       | null: false       |
| concept    | text       | null: false       |
| image      |            |                   |
| user       | references | foreign_key: true |

## Association

- belongs_to :user
- has_many :comments
