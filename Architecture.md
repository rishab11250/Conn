# Conn Architecture Overview

Conn is built as a robust, scalable Node.js application leveraging Express for the backend API and serving vanilla HTML/CSS/JS for a lightning-fast frontend. Data persistence and real-time capabilities are powered by Supabase (PostgreSQL).

## 🏗️ System Architecture

### 1. Frontend (Client Layer)
The frontend is built without heavy frameworks to ensure maximum performance, instant load times, and a high SEO score.
- **Static Delivery**: Pages (`/public/*.html`) are served statically to the client.
- **Client-side JS**: Vanilla JavaScript (`/public/js/*.js`) handles DOM manipulation, form submissions, and API interactions using the native `fetch` API.
- **Styling**: Pure CSS (`/public/css/*.css`) using CSS variables (custom properties) to dynamically render the 26+ available themes instantly without requiring page reloads.

### 2. Backend (API Layer)
The backend is an Express.js server (`server.js`) that acts as the intermediary between the frontend and the database, ensuring sensitive operations remain on the server.
- **Routing**: API routes (`/api/auth`, `/api/links`, `/api/profile`) handle all core business logic.
- **Authentication**: JWT-based authentication. Tokens are generated upon successful login and stored in `httpOnly` cookies. This approach inherently protects the application against Cross-Site Scripting (XSS) attacks.
- **Middleware**: Custom middleware functions (e.g., `authenticateToken`) intercept requests to verify JWTs, protecting private endpoints.

### 3. Database Layer (Supabase)
Conn utilizes Supabase, providing a highly scalable, managed PostgreSQL database.
- **Data Access**: The `db.js` file exports a singleton Supabase client. It is instantiated using the `service_role` key to bypass Row Level Security (RLS) entirely, since the Express backend acts as the single authoritative server dictating access control.
- **Schema**: 
  - `users`: Stores profile data, auth credentials (hashed), and active theme.
  - `links`: Stores individual URLs, titles, and display order mappings.

## 🔄 Data Flow & Request Lifecycle

1. **Client Request**: A visitor navigates to a creator's public profile (e.g., `/u/username`).
2. **Server Handling**: 
   - Express receives the request and serves the generic `index.html` file.
   - The client-side JavaScript reads the username directly from the URL and initiates an asynchronous API call to `/api/u/:username/profile`.
3. **Database Query**: 
   - The Express server receives the API request, sanitizes the input, and queries Supabase (via `db.js`) for the user's profile metadata and active links.
4. **Response**: 
   - Express formats the data and returns a JSON response to the client.
5. **DOM Render**: 
   - The client-side JS dynamically builds the DOM elements (buttons, images, titles) to construct the user's customized link-in-bio page and injects the chosen theme's CSS variables into the document root.

## 📡 Networking & Connection Management

- **Stateless REST API**: The API is strictly stateless. No session data is stored in memory. This architectural choice makes Conn perfectly suited for serverless deployments (like Vercel).
- **Security & CORS**: CORS is configured to restrict access and prevent abuse when the API is deployed across different domains. The `cookie-parser` middleware is used to securely parse `httpOnly` authentication cookies attached to incoming requests.
- **Serverless Integration**: The `vercel.json` file dictates how Vercel handles requests. It rewrites all dynamic incoming requests to `server.js` while serving files in `/public` as static assets directly from Vercel's Edge Network, achieving optimal latency.

## 🔄 Simplified Request Flow

```text
User
  ↓
Frontend (HTML/CSS/JS)
  ↓
Express.js API Server
  ↓
Supabase Database
  ↓
Response Returned to User
```
## 🔐 Authentication Lifecycle

1. User submits login credentials
2. Express server validates user details
3. JWT token is generated after successful login
4. Token is stored securely in an `httpOnly` cookie
5. Protected API routes verify the JWT before granting access

## ⚙️ Key Design Principles

- Stateless backend (no server sessions)
- API-first architecture
- Secure authentication using JWT
- Mobile-first frontend design
- Serverless deployment ready (Vercel compatible)