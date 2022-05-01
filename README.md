

## userテーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| email   | string | null: false |ユニーク制約|
| encrypted_password  | string | null: false |
| name | string | null: false |
| profile | text | null: false |
| occupation | text | null: false |
| position | text | null: false |

### Association
- has_many :prototypes
- has_many :comments

## prototypeテーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| title | string | null: false |
| catch_copy | text | null: false |
| concept | text | null: false |
| user | references | foreign_key: true | null: false |


### Association
- has_many :comments
- belongs_to :user

##  commentテーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| content | text | null: false |
| prototype | references | foreign_key: true | null: false |
| user | references | foreign_key: true | null: false |

### Association
- belongs_to :prototype
- belongs_to :user