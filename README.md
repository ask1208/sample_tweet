## sample_tweetのDB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: flase|
|password|string|null:flase|
|nickname|string|null: flase|

###　アソシエーション
- has_many :tweets
- has_many :comments


## tweetsテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
|title|text||
|user_id|integer|null: flase,foreign_key: true|

### アソシエーション
- belongs_to :user
- has_many :comments
- has_many :tweets_tags
- has_many :tags, through: :tweets_tags


## tags テーブル
|Column|Type|Options|
|------|----|-------|
|text|text||

### アソシエーション
- has_many :tweets_tags
- has_many :tweet, through: :tweets_tags


## tweet_tags
|Column|Type|Options|
|------|----|-------|
|tweet_id|integer|null: flase,foreign_key: true|
|tag_id|integer|null: flase,foreign_key: true|

### アソシエーション
- belongs_to :tweet
- belongs_to :tag


## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: flase|
|user_id|string|null: flase,foreign_key: true|
|tweet_id|string|null: flase,foreign_key: true|

###　アソシエーション
- belongs_to :tweets
- belongs_to :user










