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
		string name
		string info
		string parent
	}
	POSTS {
		string title
		longText content
		string image_path
		date published_date
	}
	TAG {
		string name
	}
	COMMENTS {
		string title
		longText content
		ipAddress ip_address
	}
	CORRECTNESS {
		int rating
		ipAddress ip_address
	}
	USER {
		string name
		string password
		string email
		longText bio
	}
	CATEGORY }|--o{ POSTS : has
	TAG }o--o{ POSTS : has
	COMMENTS }o--o{ POSTS : has
```
