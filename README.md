# CS472 Final Project March 2025: Blog Management Platform
Description: Build a blog management application where users can create, organize, and share blog posts. Use Node filesystem to store posts and comments in JSON files. Implement advanced state management with React Context, Reducer Function. Jotai will only be used to track post visits history.

### Core Functionality
* Create, edit, and delete blog posts. Store posts in `posts.json` with fields: `id` (UUID), `title`, `content`, `author`, `tags` (array), `date`, `bookmarked` (boolean). Use `uuid` package for generating unique IDs.
* Filter displayed posts by received tags or authors.
* Add and delete comments on posts. Store comments in `comments.json` with `id`, `postId`, `author`, `content`, `date`.
* Bookmark important posts. Bookmarked posts appear at the top of the list.
* Search by post title. 
* Export all posts as individual Markdown files and download as a `.zip`. Use `json2md` package to generate Markdown files. Use `archiver` package for ZIP compression.
* Centralize state for posts, comments, and UI interactions (e.g., loading states).
* Use Jotai to track post visits history, when the user clicks and visits a post, save the post ID in Jotai. When displaying the list of posts, visited posts must appear differently than un-visited posts. Visits history should be maintained between sessions. Allow users to clear the visits history.

### API Endpoints:
* `GET /posts`: Fetch all posts in pages of 15, sorted by date, expect a `page` query paramter, and return first page when `page` is not included.
* `POST /posts`: Create a new post.
* `PATCH /posts/:id`: Update a post.
* `DELETE /posts/:id`: Delete a post.
* `GET /posts/:id/comments`: Fetch all comments for a post.
* `POST /posts/:id/comments`: Add a comment.
* `DELETE /comments/:id`: Delete a comment.
* `GET /posts/search`: expect a `q` query parameter and return posts that contains the text in the title, if no `q` is passed, return the first 15 posts.
* `GET /posts/export`: Export all posts as Markdown files in a ZIP.
  
**Note:** It is required to validate user input against a schema using Zod.

### File-Based Storage Examples:
posts.json

```typescript
[  
  {  
    "id": "6ec0bd7f-11c0-43da-975e-2a8ad9ebae0b",  
    "title": "Introduction to React",  
    "content": "Lorem ipsum...",  
    "author": "John Doe",  
    "tags": ["react", "frontend"],  
    "date": "2026-01-10T12:34:56Z",  
    "bookmarked": true  
  }  
]
```
comments.json

```typescript
[  
  {  
    "id": "550e8400-e29b-41d4-a716-446655440000",  
    "postId": "6ec0bd7f-11c0-43da-975e-2a8ad9ebae0b",  
    "author": "Jane Smith",  
    "content": "Great post!",  
    "date": "2026-01-10T13:00:00Z"  
  }  
]
```
### Tech Stack:
* Frontend: React, React Router, TailwindCSS.
* Backend: Express, Zod (validation), Node filesystem.

### Evaluation Criteria:
<ins>**Version Control (10 points):**</ins>
50% of the grade will be based on the proper use of version control, including clear and descriptive commit messages that follow best practices (e.g., concise, meaningful, and referencing specific tasks or features). Additionally, students must demonstrate consistent daily progress by pushing their work to the remote repository daily throughout the project duration.

   
<ins>**Code Quality and Feature Implementation (10 points):**</ins>
The remaining 50% of the grade will be awarded based on the quality and completeness of the codebase. This includes successfully implementing all required features, adhering to coding best practices (e.g., clean code, proper input validation using Zod on the backend, responsive and intuitive UI with TailwindCSS, and efficient algorithms), and ensuring the project is functional, well-structured, and free of critical errors.


### Notes
Students are expected to be available on MS-Teams to receive calls and check on their progress every day from 10:00 AM to 12:00 PM, and 2:00 PM to 3:00 PM during the project.

### Need Assistance?
Contact me during office hours (10:00 AM–12:00 PM and 2:00–3:00 PM, Mon–Sat). Support includes design reviews, and best practices guidance.

### Final Submission:
* Deadline: Wednesday at 9:00 PM. Record a demo video (no code explanation) and send me the link by email.

Good luck, and happy coding!

_Code Honor Submission Policy: Remember to respect the code honor submission policy. All written code must be original. You may not share any part of your code with other students. Code duplications will results to receiving NC for the final project. Presenting any code as one’s own work when it came from another source is plagiarism, which includes any matching patterns and code snippets, and will affect your grade. The use of AI is not permitted in this assignment. For more details, check the full course policies in the syllabus._
