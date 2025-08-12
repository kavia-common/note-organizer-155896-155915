# Notes Frontend (SvelteKit)

A minimalistic, light-themed notes application with a responsive sidebar and a main editing area. Features:
- List notes
- Create notes
- Edit notes
- Delete notes
- Search notes

Colors used:
- Primary: `#4F46E5`
- Secondary: `#6366F1`
- Accent: `#F59E42`

## Running locally

Install dependencies and start dev server:

```bash
npm install
npm run dev
```

Open the app at the URL printed by the dev server.

## Backend configuration

This app is ready to connect to the `notes_database` backend. Configure the base API URL using an environment variable:

- Copy `.env.example` to `.env` and set:
  ```
  VITE_NOTES_API_BASE_URL=http://localhost:8000/api
  ```

If `VITE_NOTES_API_BASE_URL` is not set, the app will use `localStorage` as a fallback to persist notes.

### Expected backend endpoints (REST)

- `GET    /notes`                → list notes
- `GET    /notes/{id}`           → get a note
- `POST   /notes`                → create a note (body: { title, content })
- `PUT    /notes/{id}`           → update a note (body: { title?, content? })
- `DELETE /notes/{id}`           → delete a note
- `GET    /notes?search=QUERY`   → search notes

> You can replace or adjust the endpoints in `src/lib/services/api.ts` if your backend differs.

## Project scripts

```bash
npm run dev       # start dev server
npm run build     # production build
npm run preview   # preview production build
npm run check     # type and svelte-check
npm run lint      # eslint
npm test          # unit tests (if any)
```
