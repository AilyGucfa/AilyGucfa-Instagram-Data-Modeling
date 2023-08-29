
# This is my diagram code for the database model of Instagram 


## User
-----------------------
id integer PK
username string 
email string
password Integer
full_name string
bio string
profile_picture string
post string
followers FK >- Follower.id
following Fk >- Following.id


Post
---------------------
id integer PK
user.id integer
image_url string
caption string
upload_time DateTime
location string
users FK >- User.id
likes FK >- Like.id


Follower
------------------
id integer PK
user_id integer FK >- User.id
count_followers Integer
follower_id integer FK >- User.id
follower_time DateTime

Following
------------------
id integer PK
user_id integer FK >- User.id
count_followings Integer
following_id integer FK >- User.id
following_time DateTime



Like
---------------------
id integer PK
user.id integer FK
post.id integer FK
like_time DateTime
count_likes Integer
user FK >- User.id
post FK >- Post.id


Comment
------------------------
id integer PK
user.id integer
post.id integer
text_comment string
comment_time DateTime
users FK >- User.id
posts FK >- Post.id
likes FK >- Like.id
