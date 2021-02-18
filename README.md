# テーブル設計

## users テーブル

| Column     | Type   | Option      |
| ---------- | ------ | ------------|
| email      | string | null: false |
| password   | string | null: false |
| name       | text   | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :comments
- has_many :prototypes

## prototypes テーブル

| Column     | Type        | Option                         |
| ---------- | ----------- | -------------------------------|
| title      | string      | null: false                    |
| catch_copy | text        | null: false                    |
| concept    | text        | null: false                    |
| user       | references  | null: false, foreign_key: true |

### Association

- has_many :comments
- belong_to :user

## commentsテーブル

| Column    | Type        | Option                         |
| --------- | ----------- | -------------------------------|
| text      | text        | null: false                    |
| user      | references  | null: false, foreign_key: true |
| prototype | references  | null: false, foreign_key: true |

### Association

- belong_to :user
- belong_to :prototype
