# User
### association
- has_many :prototypes, :comments, :likes, :captured_image

### table
| column | Type | Options |
|:--|:--:|:--|
| name | string | unique :true, null :false |
| email | string | unique :true, null :false |
| password | string | null :false |
| avatar | string |  |
| top_aligned_media | string|  |
| profile | string |  |
| works | string |  |

# Prototype
### association
- belongs_to :user
- has_many :comments, :captured_images
- has_many :likes, dependent: :destroy

### table
| column | Type | Options |
|:--|:--:|:--|
| title | string | null :false |
| catch_copy | string |  |
| concept | string |  |
| likes_count | integer |  |
| user_id | integer | null: false, foreign_key :ture |

# CapturedImage
### association
- belongs_to :user, :prototype

### table
| column | Type | Options |
|:--|:--:|:--|
| image | string | null: false |
| status | enum | main:1, sub:2 |
| user_id | integer | null: false, foreign_key: ture |
| prototype_id | integer | null: false, foreign_key: true |

# Like
### association
- belongs_to :user
- belongs_to :prototype, counter_cache: :likes_count

### table
| column | Type | Options |
|:--|:--:|:--|
| user_id | integer | null :false, foreign_key :ture |
| prototype_id | integer | null :false, foreign_key :true |

# Comment
### association
- belongs_to :user, :prototype

### table
| column | Type | Options |
|:--|:--:|:--|
| comment | string |  |
| user_id | integer | null :false, foreign_key :ture |
| prototype_id | integer | null :false, foreign_key :true |

