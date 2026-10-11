# P. Sreenivasulu — Developer Portfolio

A responsive, dark-themed portfolio built with React, Vite, Tailwind CSS, React Router, and Framer Motion, with an Express and MongoDB API.

## Requirements

- Node.js 20 or newer and npm
- A MongoDB Atlas connection string for database-backed pages and the contact form

## Run locally

1. Install all workspace packages from the repository root:

   ```sh
   npm install
   ```

2. Copy `server/.env.example` to `server/.env`, then set `MONGODB_URI`. The local defaults use port `5000` and allow the Vite origin `http://localhost:5173`.

3. Start the frontend and API together:

   ```sh
   npm run dev
   ```

   Open the Vite URL printed in the terminal (normally `http://localhost:5173`). Vite proxies `/api` requests to the local Express API.

The API can also be run alone with `npm run dev:api`. Its health endpoint is `http://localhost:5000/api/health`.

## Add portfolio data

The public API intentionally has no project or skill write endpoints. Add project records in the MongoDB `projects` collection using the fields in `server/src/models/Project.js`; use a unique lowercase slug. Project details, categories, technology lists, links, images, and completion status should describe real work only.

To add the skills and learning interests already provided for this portfolio, run:

```sh
npm --prefix server run seed
```

The seed operation inserts missing starter skills and leaves existing records untouched. You can edit or remove records in MongoDB afterward. Skills are grouped by category and marked `listed` or `learning`; no proficiency percentages are used.

## Environment variables

### API (`server/.env`)

| Variable | Purpose |
| --- | --- |
| `MONGODB_URI` | MongoDB Atlas connection string; required for projects, skills, and contact submissions |
| `CLIENT_ORIGIN` | Allowed browser origin(s) for CORS; local default is `http://localhost:5173`. Separate multiple origins with commas. |
| `PORT` | Local Express port; defaults to `5000` |

### Frontend (`client/.env`)

Copy `client/.env.example` to `client/.env` if you need to set any of these:

| Variable | Purpose |
| --- | --- |
| `VITE_API_URL` | API origin for production, for example `https://your-api.vercel.app`; leave blank locally to use Vite’s proxy |
| `VITE_GITHUB_URL` | Personal GitHub profile URL; leave blank until the real URL is known |
| `VITE_LINKEDIN_URL` | Personal LinkedIn profile URL; leave blank until the real URL is known |

Keep database credentials on the API side. Vite variables are public in the browser bundle and must not contain secrets.

## Vercel deployment

Deploy this repository as **two Vercel projects** so the Vite static site and Express API have separate roots and environment settings:

1. Create the API project with the repository root directory set to `server`. Vercel detects the Express app exported from `src/app.js`; `src/index.js` remains the local listener. Set `MONGODB_URI` and `CLIENT_ORIGIN` in the API project. Set `CLIENT_ORIGIN` to the deployed frontend origin.
2. Deploy the frontend with the repository root directory set to `client`. Vite builds to `dist`; `client/vercel.json` rewrites browser routes to `index.html` so React Router deep links work on refresh.
3. Set `VITE_API_URL` in the frontend project to the API project’s origin (without a trailing slash). Add the real GitHub or LinkedIn URLs if available, then redeploy the frontend so Vite includes them.
4. Configure MongoDB Atlas network access for the deployed API and confirm `/api/health`, `/api/projects`, `/api/skills`, and the contact form after deployment.

The API uses a serverless-compatible Express app export and connects to MongoDB when a database-backed request arrives. The local `listen()` entry point is not used as the Vercel function entry point. The contact rate limiter uses the default in-memory store; for high-volume deployments, replace it with a shared rate-limit store.

## Content placeholders

No resume file, personal profile URLs, published projects, awards, employment history, certifications, or coding statistics were provided. The UI leaves profile URLs unset, labels the resume as available on request, and shows clear empty states for projects. Add authentic information before publishing those sections.
