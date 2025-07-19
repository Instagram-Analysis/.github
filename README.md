# Instagram Analytics

Welcome to the **Instagram Analytics** project—a full‑stack application for analyzing Instagram follower and engagement data. This repository serves as the organizational hub and provides an overview, setup instructions, and architecture for both the Frontend and Backend components.

## Repositories

- **Frontend**: [instagram-analytics-FE](https://github.com/Instagram-Analysis/instagram-analytics-FE)  
  A Next.js + TypeScript application that provides the user interface to view followers, following, non-followers, and top likers.

- **Backend**: [instagram-analytics-BE](https://github.com/Instagram-Analysis/instagram-analytics-BE)  
  An Express.js + TypeScript API server that handles authentication, session management, and fetches Instagram data via an API integration.

## Architecture

```
Browser (Next.js FE)
    ↕  HTTPS (credentials included)
Express.js + TypeScript BE
    ↕  Instagram Graph API (OAuth & Access Token)
Instagram Platform
```

- The **Frontend** communicates with the Backend over HTTP, including user sessions.  
- The **Backend** will use the **Official Instagram Graph API** (OAuth flow) to securely obtain data.  

## Setup

### Prerequisites

- Node.js ≥ 14
- npm ≥ 6

### Frontend

1. Clone and install:
   ```bash
   git clone https://github.com/Instagram-Analysis/instagram-analytics-FE.git
   cd instagram-analytics-FE
   npm install
   ```
2. Create `.env.local`:
   ```dotenv
   NEXT_PUBLIC_API_URL=http://localhost:4000
   ```
3. Start:
   ```bash
   npm run dev
   ```

### Backend

1. Clone and install:
   ```bash
   git clone https://github.com/Instagram-Analysis/instagram-analytics-BE.git
   cd instagram-analytics-BE
   npm install
   ```
2. Create `.env`:
   ```dotenv
   PORT=4000
   FRONTEND_URL=http://localhost:3000
   SESSION_SECRET=<your-session-secret>
   INSTAGRAM_GRAPH_TOKEN=<your-long-lived-graph-token>
   ```
3. Start:
   ```bash
   npm run dev
   ```

## Instagram API Integration

> As of [N/A], we have migrated from using the unofficial `instagram-private-api` package to the **Official Instagram Graph API**. Users will authenticate via OAuth, and the backend will use long‑lived access tokens to fetch:
>
> - Followers: `GET /me/followers`
> - Following: `GET /me/following`
> - Media metrics: `GET /me/media?fields=like_count`
>
> See the Backend README for detailed Graph API setup.

## Contributing

1. Fork this organization’s repos.  
2. Create feature branches.  
3. Submit pull requests.

## License

This project is licensed under the MIT License.
