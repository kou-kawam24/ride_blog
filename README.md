# DB 設計

## users table

| Column               | Type        | Options                   |
|----------------------|-------------|---------------------------|
| name                 | string      | null: false               |
| email                | string      | null: false, unique:true  |
| encrypted_password   | string      | null: false               |
| owned_bike           | string      |                           |

### Association

- has_many :posts
- has_many :comments

## posts table

| Column             | Type       | Options           |
|--------------------|------------|-------------------|
| title              | string     | null: false       |
| text               | text       | null: false       |
| date               | datetime   | null: false       |
| user               | references | foreign_key: true |

### Association

- belongs_to :user
- has_many :comments

## comments table

| Column          | Type       | Options           |
|-----------------|------------|-------------------|
| text            | string     | null: false       |
| user            | references | foreign_key: true |
| post            | references | foreign_key: true |

### Association

- belongs_to :user
- belongs_to :posts

## bikes table

| Column          | Type       | Options           |
|-----------------|------------|-------------------|
| model_name      | string     | null: false       |
| maker_id        | integer    | null: false       |
| displacement    | string     | null: false       |
| model_year      | string     | null: false       |
| evaluation      | string     | null: false       |
| ride_num        | string     | null: false       |
| review          | text       | null: false       |

### Association

## routes table

| Column          | Type       | Options           |
|-----------------|------------|-------------------|
| spot_name       | string     | null: false       |
| prefecture_id   | integer    | null: false       |
| evaluation      | string     | null: false       |
| ride_num        | string     | null: false       |
| review          | text       | null: false       |

### Association