# User
### association
- has_many :prototypes, :comments, :likes, :captured_image

### table
- name
- email
- password
- avatar
- top_aligned_media
- profile
- works

# Prototype
### association
- belongs_to :user
- has_many :comments, :likes, :captured_images

### table
- title
- catch_copy
- concept
- user_id

# CapturedImage
### association
- belongs_to :user, :prototype

### table
- image
- user_id
- prototype_id

# Like
### association
- belongs_to :user, :prototype

### table
- user_id
- prototype_id

# Comment
### association
- belongs_to :user, :prototype

### table
- comment
- prototype_id
- user_id

