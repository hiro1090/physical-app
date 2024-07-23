# テーブル設計

## users テーブル

| Column             | Type    | Options                       |
| ------------------ | ------- | ----------------------------- |
| id                 | integer | primary key, auto increment   |
| name               | string  | null: false                   |
| email              | string  | null: false, unique: true     |
| encrypted_password | string  | null: false                   |

### Association

- has_many :physicals
- has_many :lists

## lists テーブル

| Column         | Type   | Options     |
| -------------- | ------ | ----------- |
| id             | integer | primary key, auto increment |
| user_id        | integer | foreign key |
| past_records   | text   | null: false |

### Association

- belongs_to :user

## physicals テーブル

| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| id                 | integer    | primary key, auto increment    |
| user_id            | integer    | foreign key, null: false       |
| height             | decimal    | null: false                    |
| body_weight        | decimal    | null: false                    |
| body_temperature   | decimal    | null: false                    |
| condition          | string     | null: false                    |

### Association

- belongs_to :user