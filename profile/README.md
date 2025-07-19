# 📊 Instagram Analytics

> A comprehensive full-stack application for advanced Instagram follower and engagement analysis with real-time insights and secure OAuth integration.

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?logo=typescript&logoColor=white)](https://typescriptlang.org/)


## 🚀 Overview

Instagram Analytics is a modern, secure platform that provides deep insights into your Instagram account performance. Built with enterprise-grade architecture, it offers real-time analysis of follower dynamics, engagement patterns, and audience behavior through Instagram's official Graph API.


### ✨ Key Features

- **Follower Analysis** - Track followers, following, and identify non-mutual connections
- **Engagement Insights** - Analyze top likers and interaction patterns
- **Secure Authentication** - OAuth 2.0 integration with Instagram's official API
- **Real-time Data** - Live synchronization with Instagram platform
- **Modern UI/UX** - Responsive design with intuitive dashboard

## 🏗️ Architecture

```mermaid
graph TD
    A[Next.js Frontend] -->|HTTPS + Session Auth| B[Express.js Backend]
    B -->|OAuth 2.0| C[Instagram Graph API]
    C -->|JSON Response| B
    B -->|Processed Data| A
    
    style A fill:#ff5733
    style B fill:#d6ff33
    style C fill:#33f2ff
```

**Technology Stack:**
- **Frontend**: Next.js 14+ with TypeScript, CSS
- **Backend**: Express.js with TypeScript, secure session management
- **API Integration**: Instagram Graph API with long-lived access tokens
- **Authentication**: OAuth 2.0 flow with Instagram Platform

## 📦 Repository Structure

| Repository | Description | Tech Stack |
|------------|-------------|------------|
| [**Frontend**](https://github.com/Instagram-Analysis/instagram-analytics-FE) | User interface and dashboard | Next.js + TypeScript |
| [**Backend**](https://github.com/Instagram-Analysis/instagram-analytics-BE) | API server and Instagram integration | Express.js + TypeScript |

## 🛠️ Quick Start

### Prerequisites

Ensure you have the following installed:
- **Node.js** `>=14.0.0` ([Download](https://nodejs.org/))
- **npm** `>=6.0.0` or **yarn** `>=1.22.0`
- **Git** for version control

### 🎨 Frontend Setup

```bash
# Clone the repository
git clone https://github.com/Instagram-Analysis/instagram-analytics-FE.git
cd instagram-analytics-FE

# Install dependencies
npm install

# Configure environment
cp .env.example .env.local
```

**Environment Configuration (`.env.local`):**
```env
# API Configuration
NEXT_PUBLIC_API_URL=http://localhost:4000
NEXT_PUBLIC_APP_NAME=Instagram Analytics

# Optional: Analytics & Monitoring
NEXT_PUBLIC_GA_ID=your-google-analytics-id
```

```bash
# Start development server
npm run dev
# 🚀 Frontend available at http://localhost:3000
```

### ⚡ Backend Setup

```bash
# Clone the repository
git clone https://github.com/Instagram-Analysis/instagram-analytics-BE.git
cd instagram-analytics-BE

# Install dependencies
npm install

# Configure environment
cp .env.example .env
```

**Environment Configuration (`.env`):**
```env
# Server Configuration
PORT=4000
NODE_ENV=development
FRONTEND_URL=http://localhost:3000

# Security
SESSION_SECRET=your-super-secure-session-secret-here
CORS_ORIGIN=http://localhost:3000

# Instagram Graph API
INSTAGRAM_APP_ID=your-instagram-app-id
INSTAGRAM_APP_SECRET=your-instagram-app-secret
INSTAGRAM_GRAPH_TOKEN=your-long-lived-access-token

# Optional: Database & Caching
DATABASE_URL=postgresql://username:password@localhost:5432/instagram_analytics
REDIS_URL=redis://localhost:6379
```

```bash
# Start development server
npm run dev
# 🚀 Backend API available at http://localhost:4000
```

## 🔐 Instagram API Integration

### Official Graph API Migration

We've transitioned to Instagram's **Official Graph API** for enhanced security, reliability, and compliance with platform policies.

**Supported Endpoints:**
- `GET /me/followers` - Retrieve follower list
- `GET /me/following` - Get following accounts  
- `GET /me/media` - Fetch media with engagement metrics
- `GET /me/insights` - Access account analytics

**OAuth 2.0 Flow:**
1. User initiates login via frontend
2. Redirect to Instagram OAuth endpoint
3. Exchange authorization code for access token
4. Store long-lived token securely
5. Make authenticated API requests

> 📚 **Detailed Setup Guide**: Refer to the [Backend README](https://github.com/Instagram-Analysis/instagram-analytics-BE#readme) for comprehensive Graph API configuration instructions.

## 🧪 Development

### Running Tests
```bash
# Frontend tests
cd frontend
npm run dev

# Backend tests  
cd backend
npm run dev
```


## 🚀 Deployment

### Production Build
```bash
# Frontend
npm run build
npm run start

# Backend
npm run build
npm run start:prod
```


## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### Development Workflow
1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request


## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## 🙋‍♂️ Support

- 📖 **Documentation**: Check our [README](https://github.com/Instagram-Analysis/.github/blob/main/profile/README.md)
- 🐛 **Issues**: Report bugs on [GitHub Issues](https://github.com/Instagram-Analysis/instagram-analytics-BE/issues)

---

<div align="center">

**by @vxnquish**

[⭐ Star this repo](https://github.com/Instagram-Analysis) • [🐛 Report Bug](https://github.com/Instagram-Analysis/instagram-analytics-BE/issues) • [✨ Request Feature](https://github.com/Instagram-Analysis/instagram-analytics/issues](https://github.com/Instagram-Analysis/instagram-analytics-FE/issues))

</div>
