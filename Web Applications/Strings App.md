### Models
- **Category**
	- ID
	- Name
	- Info
	- Parent
- **Tag**
	- ID
	- Name
- **User**
	- ID
	- Name
	- E-mail
	- Password
	- Bio
	- Last Login
	- Registration Date
	- Date of birth
	- Photo
- **Correctness**
	- ID
	- UserID
	- Rating
	- IP
- **Comment**
	- ID
	- UserID
	- PostID
	- Title
	- Content
	- IP
- **Post**
	- ID
	- Title
	- Content
	- Featured Image
	- UserID
	- CategoryID
	- TagID
	- Last Update
	- Pubished Date


Entity Relationship Diagram

```mermaid
erDiagram
	CATEGORY {
		int ID PK
		string name
		string info
		string parent
	}
	POSTS {
		int ID PK
		string title
		longText content
		string image_path
		date published_date
		int correctness_id FK
		int user_id FK
	}
	POST-CATEGORY {
		int post_id
		int category_id
	}
	TAG {
		int ID PK
		string name
	}
	POST-TAG {
		int post_id
		int tag_id
	}
	COMMENTS {
		int ID PK
		string title
		longText content
		ipAddress ip_address
		int post_id FK
		int user_id FK
	}
	CORRECTNESS {
		int ID PK
		int rating
		ipAddress ip_address
		int post_id FK
		int user_id FK
	}
	USER {
		int ID PK
		string name
		string password
		string email
		longText bio
		int post_id FK
	}
	CATEGORY ||--o{ POST-CATEGORY : has
	POSTS ||--o{ POST-CATEGORY : has
	TAG ||--o{ POST-TAG : has
	POSTS ||--o{ POST-TAG : has
	COMMENTS }o--|| POSTS : has
	CORRECTNESS }o--|| POSTS : has
	USER ||--o{ POSTS : has
```

Entity Relationship Diagram (Simpler)

```mermaid
erDiagram
	CATEGORY {
		int ID PK
		string name
		string info
		string parent
	}
	POSTS {
		int ID PK
		string title
		longText content
		string image_path
		date published_date
		int user_id FK
	}
	POST-CATEGORY {
		int post_id
		int category_id
	}
	COMMENTS {
		int ID PK
		string title
		longText content
		ipAddress ip_address
		int post_id FK
		int user_id FK
	}
	USER {
		int ID PK
		string name
		string password
		string email
		longText bio
		int post_id FK
	}
	CATEGORY ||--o{ POST-CATEGORY : has
	POSTS ||--o{ POST-CATEGORY : has
	COMMENTS }o--|| POSTS : has
	USER ||--o{ POSTS : has
```
