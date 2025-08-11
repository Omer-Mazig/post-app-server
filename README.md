## PostApp — API (Dev Server)

This is a minimal Express server that provides an in‑memory API to support the client during development. It is not the focus of the assignment; it exists to enable richer client features (create/delete posts, pagination, comments, and a stubbed current user).

### How to run (development)

- **Requirements**: Node.js 20+ and npm 10+

Steps:

1. `cd server`
2. `npm install`
3. Start the server:
   - `npm run dev` (uses nodemon; if you don't have it, run `npx nodemon server.js`), or
   - `node server.js`
4. The API will run on `http://localhost:3000`.

### Endpoints (summary)

- `GET /api/posts` — Cursor‑based pagination with optional `q` search. Accepts `cursor`, `limit`.
- `GET /api/posts/:id` — Fetch a post by id.
- `GET /api/posts/:id/comments` — Cursor‑based comments pagination. Accepts `cursor`, `limit`.
- `POST /api/posts` — Create a new post. Body: `{ title, body, userId }`.
- `DELETE /api/posts/:id` — Delete a post.
- `GET /api/me` — Returns a stubbed current user.

Notes:

- All data is in‑memory and resets on restart.
- CORS and JSON body parsing are enabled.
