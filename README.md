# Meesho-main (local run instructions)

This project includes a Node/Express backend in `src/` and static frontend HTML files at the project root.

## Requirements
- Node.js (16+ recommended)
- npm
- MongoDB (local) or a MongoDB Atlas connection string

## Quick run (PowerShell)
1. Open PowerShell and change to the project directory:

```powershell
cd "C:\Users\shrey\Desktop\NIT-KKR\Meesho-main"
```

2. Install dependencies:

```powershell
npm install
```

3a. Run with local MongoDB (recommended for offline dev):
- Start your local MongoDB server (e.g., `mongod` service)
- Then:

```powershell
npm start
```

3b. Run with MongoDB Atlas / remote DB:
- Create a `.env` file in the project root (copy `.env.example`) and set `MONGODB_URL`.
- Note: The project currently contains a hardcoded Atlas URI in `src/configs/db.js`.

```powershell
# copy example and edit
copy .env.example .env
notepad .env
# then
npm start
```

The server listens on http://localhost:3000 by default. Endpoints are available under routes like `/products`, `/womens`, `/jwelleries`, `/users`, `/register`, `/login`.

## Frontend
There are static HTML files at the repo root (e.g., `index.html`, `product_description.html`, etc.). You can open them directly in a browser or serve them from the backend if you modify `src/index.js` to serve static files from the project root.

## Troubleshooting
- If you see `querySrv ENOTFOUND _mongodb._tcp...`, your DNS cannot resolve the Atlas SRV host. Use a local MongoDB URI or verify your network/DNS.
- To stop the server in PowerShell: press Ctrl+C in the terminal running `npm start`.
- To run the server directly without npm scripts:

```powershell
node src/index.js
```

## Optional improvements
- Modify `src/configs/db.js` to read `process.env.MONGODB_URL` with a local fallback.
- Add `.env` usage in `src/index.js` (require `dotenv`).
- Add a `serve` script to package.json to serve static frontend files.

If you'd like, I can make the env-based DB change and add `.env` loading automatically — tell me and I'll update the files for you.

