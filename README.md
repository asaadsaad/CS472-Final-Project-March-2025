# CS472 Final Project March 2025: Blog Management Platform
Description: Build a blog management application where users can create, organize, and share blog posts. Use Node filesystem to store posts and comments in JSON files. Implement advanced state management with React Context, `useReducer`.

### Core Functionality
* Create, edit, and delete blog posts. Store posts in `posts.json` with fields: `id` (UUID), `title`, `content`, `author`, `tags` (array), `date`, `bookmarked` (boolean). Use `uuid` package for generating unique IDs.
* Add and delete comments on posts. Store comments in `comments.json` with `id`, `postId`, `author`, `content`, `date`.
* Bookmark important posts. Bookmarked posts appear at the top of the list.
* Real-time search by post title/content (frontend filtering). Filter posts by tags or author.
* Export all posts as individual Markdown files and download as a `.zip`. Use `marked` package to generate Markdown content. Use `archiver` package for ZIP compression.
* Centralize state for posts, comments, and UI interactions (e.g., loading states).

### API Endpoints:
* `GET /posts`: Fetch all posts.
* `POST /posts`: Create a new post.
* `PATCH /posts/:id`: Update a post.
* `DELETE /posts/:id`: Delete a post.
* `GET /posts/:id/comments`: Fetch comments for a post.
* `POST /posts/:id/comments`: Add a comment.
* `DELETE /comments/:id`: Delete a comment.
* `GET /posts/export`: Export all posts as Markdown files in a ZIP.

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
* Implementation of all features, including advanced state management with Context/useReducer.
* Code organization (separation of concerns for UI, state, and API layers).
* Proper validation using Zod on both frontend and backend.
* Responsive and intuitive UI with TailwindCSS.
* Adherence to RESTful API design.
* Meaningful Git commits (one per feature) and daily pushes.

### Notes
* A daily push is required to track your code progress and measure your performance.
* Students are expected to be available on MS-Teams to receive calls and check on their progress every day from 10:00 AM to 12:00 PM, and 2:00 PM to 3:00 PM during the project.

### Need Assistance?
Contact me during office hours (10:00 AM–12:00 PM and 2:00–5:00 PM, Mon–Sat). Support includes debugging, design reviews, and best practices guidance.

### Final Submission:
* Deadline: Wednesday at 9:00 PM. Submit a demo video (no code explanation) and ensure code is pushed to the maharishi-university repository.

Good luck, and happy coding!

_Code Honor Submission Policy: Remember to respect the code honor submission policy. All written code must be original. You may not share any part of your code with other students. Code duplications will results to receiving NC for the final project. Presenting any code as one’s own work when it came from another source is plagiarism, which includes any matching patterns and code snippets, and will affect your grade. The use of AI is not permitted in this assignment. For more details, check the full course policies in the syllabus._
