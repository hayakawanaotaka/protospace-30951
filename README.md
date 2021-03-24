# テーブル設計

## users テーブル

| Column      | Type   | Options     |
| --------    | ------ | ----------- |
| email       | string | null: false |
| password    | string | null: false |
| name        | string | null: false |
| profile     | tet    | null: false |
| occupation  | text   | null: false |
| position    | text   | null: false |

### Association

- has_many :prototypes
- has_many :comments

## comments テーブル

| Column     | Type       | Options         |
| ------     | ------     | -----------     |
| text       | text       | null: false     |
| user       | references |foreign_key: true|
| prototype  | references |foreign_key: true|

### Association

- belongs_to :user
- belongs_to :prototypes

## prototypes テーブル

| Column      | Type       | Options          |
| -------     | ---------- | ---------------  |
| title       | string     | null: false      |
| cact_copy   | text       | null: false      |
| concept     | text       | null: false      |
| user        | refereces  | foreign_key: true|

### Association

- belongs_to :comments
- belongs_to :user