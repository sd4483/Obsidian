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
		string content
	}
	CORRECTNESS
	USER
```