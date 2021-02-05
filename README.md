## usersテーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false | 
| password   | string | null: false | 
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :prototype
- has_many :comments

## prototypesテーブル

| Colum      | Type       | Options     |
| ---------- | ---------- | ----------- |
| title      | string     | null: false |
| catch_copy | text       | null: false |
| concept    | text       | null: false |
| image      | image      | null: false |
| user       | references |             |

### Association

- has_many :comments
- belong_to :user

## commentsテーブル

| Colum     | Type       | Options     |
| --------- | ---------- | ----------- |
| text      | text       | null: false |
| user      | references |             |
| prototype | references |             |

### Association

- belong_to :user
- belong_to :prototype
