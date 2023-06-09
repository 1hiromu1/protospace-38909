# テーブル設計

## users テーブル

| Column             | Type   | Options                 |
| ------------------ | ------ | ----------------------- |
| email              | string | null: false, ユニーク制約 |
| encrypted_password | string | null: false             |
| name               | string | null: false             |
| profile            | text   | null: false,            |
| occupation         | text   | null: false             |
| position           | text   | null: false             |

### Association

- has_many :prototypes
- has_many :comments

## prototypes テーブル

| Column     | Type       | Options             |
| ---------- | ---------- | ------------------- |
| title      | string     | null: false         |
| catch_copy | text       | null: false         |
| concept    | text       | null: false         |
| user       | references | null: false, 外部キ- |

### Association

- has_many :comments
- belongs_to :users

## comments テーブル

| Column    | Type       | Options             |
| --------- | ---------- | ------------------- |
| content   | text       | null: false         |
| prototype | references | null: false, 外部キ- |
| user      | references | null: false, 外部キ- |

### Association

- belongs_to :users
- belongs_to :prototypes

