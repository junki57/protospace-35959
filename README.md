# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | null: false |
| password           | string | null: false |
| name               | string | null: false |
| profile            | text   | null: false |
| occupation         | text   | null: false |
| position           | text   | null: false |

### Association

- has_many :comments
- has_many :prototype

## comments テーブル

| Column             | Type   | options     |
| ------------------ | ------ | ----------- |
| text               | text   | null: false |
| user               | references |          |
| prototype          | references |          |

### Association
- belongs_to :user
- belongs_to :prototype

## prototype

| Column             | Type   | options     |
| ------------------ | ------ | ----------- |
| title              | string | null: false |
| catch              | text   | null: false |
| concept            | text   | null: false |
| user               | references |         |

### Association
- belongs_to :user
- has_many :comments