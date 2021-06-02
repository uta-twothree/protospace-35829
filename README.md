# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
| profile            | text   | null: false |
| ocupation          | text   | null: false |
| position           | text   | null: false |

### Association

- has_many :prototypes
- has_many :comments

## prototypes テーブル

| Column     | Type         | Options                        |
| ---------- | ------------ | ------------------------------ |
| title      | string       | null: false                    |
| catch_copy | text         | null: false                    |
| concept    | text         | null: false                    |
| image      |              |                                |
| user       | references   | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_many :comments

## comments テーブル

| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| text        | string     | null: false                    |
| user        | references | null: false, foreign_key: true |
| prototype   | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :prototype