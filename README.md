<div align="center">
  <h1>🚀 Telaten Apps</h1>
  <p><strong>AI-Powered Business Growth Platform</strong></p>
  <p><em>Empowering Indonesian MSMEs with intelligent milestone tracking, financial management, and gamified business development</em></p>

[![Backend](https://img.shields.io/badge/Backend-FastAPI-009688?style=for-the-badge&logo=fastapi)](./telaten-backend)
[![Frontend](https://img.shields.io/badge/Frontend-Next.js-000000?style=for-the-badge&logo=next.js)](./telaten-client)
[![AI](https://img.shields.io/badge/AI-LlamaIndex-FF6B35?style=for-the-badge)](./telaten-backend)
[![Database](https://img.shields.io/badge/Database-PostgreSQL-336791?style=for-the-badge&logo=postgresql)](./telaten-backend)

</div>

---

## 🌟 What is Telaten?

Telaten is an **AI-powered business growth platform** specifically designed for Indonesian MSMEs (Micro, Small, and Medium Enterprises). The platform combines intelligent milestone generation, comprehensive financial tracking, and engaging gamification to help business owners achieve sustainable growth.

### ✨ Key Features

| **Feature**                | **Description**                                         | **Technology**                  |
| -------------------------- | ------------------------------------------------------- | ------------------------------- |
| 🤖 **AI Business Advisor** | Context-aware chat assistant with business intelligence | LlamaIndex + MCP                |
| 🎯 **Smart Milestones**    | AI-generated, personalized business goals and tasks     | OpenAI/Groq + Custom workflows  |
| 💰 **Financial Tracking**  | Comprehensive transaction management with analytics     | PostgreSQL + Real-time insights |
| 🏆 **Gamification System** | Points, levels, achievements, and leaderboards          | Custom gamification engine      |
| 📱 **Mobile-First Design** | Responsive interface optimized for mobile usage         | Next.js + Tailwind CSS          |
| 🔄 **Real-time Updates**   | Live milestone generation and chat responses            | Server-Sent Events (SSE)        |

---

## 📂 Repository Structure

This **monorepo** contains three main components:

| **Component**                                 | **Technology Stack**                     | **Purpose**                                |
| --------------------------------------------- | ---------------------------------------- | ------------------------------------------ |
| 🔧 **[telaten-backend](./telaten-backend)**   | Python, FastAPI, PostgreSQL, LlamaIndex  | AI-powered backend API with business logic |
| 🎨 **[telaten-client](./telaten-client)**     | Next.js, React, TypeScript, Tailwind CSS | Modern web application frontend            |
| 📚 **[telaten-docs-api](./telaten-docs-api)** | Bruno Collection                         | Interactive API documentation and testing  |

---

## 🚀 Getting Started

### 📥 Cloning the Repository

> **⚠️ Important**: This repository uses **Git Submodules**. You must clone it properly to ensure all components are available.

#### Option 1: Fresh Clone (Recommended)

```bash
# Clone with submodules
git clone --recurse-submodules https://github.com/username/telaten-apps.git
cd telaten-apps
```

#### Option 2: Fix Empty Submodules

If you already cloned normally and submodule folders are empty:

```bash
# Initialize and update submodules
git submodule update --init --recursive
```

### 🔧 Prerequisites

Before starting, ensure you have the following installed:

| **Component**      | **Required Version** | **Installation**                                        |
| ------------------ | -------------------- | ------------------------------------------------------- |
| **Python**         | ≥ 3.12               | [Download Python](https://python.org/downloads/)        |
| **Node.js**        | ≥ 18.0               | [Download Node.js](https://nodejs.org/)                 |
| **PostgreSQL**     | ≥ 14.0               | [Download PostgreSQL](https://postgresql.org/download/) |
| **Bun** (Optional) | Latest               | `npm install -g bun`                                    |
| **uv** (Optional)  | Latest               | `pip install uv`                                        |

---

## 🛠️ Setup & Development

### 🔧 Backend Setup (`telaten-backend`)

> **🎯 Tech Stack**: Python 3.12, FastAPI, PostgreSQL, LlamaIndex, SQLModel

#### 📋 Setup Steps

**1️⃣ Navigate to Backend Directory**

```bash
cd telaten-backend
```

**2️⃣ Environment Configuration**

```bash
# Copy environment template
cp .env.example .env
```

**📝 Required Environment Variables:**

```ini
# Database Configuration
DATABASE_URL=postgresql+asyncpg://user:password@localhost:5432/telaten

# Security
SECRET_KEY=your-super-secret-jwt-key

# AI Provider (Choose one)
LLM_API_KEY=your-api-key
LLM_BASE_URL=https://api.groq.com/openai/v1  # or OpenAI, Together AI, etc.
LLM_MODEL_NAME=llama-3.1-70b-versatile

# Optional: Logging
LOG_LEVEL=INFO
```

**3️⃣ Install Dependencies**

| **Method** | **Command**        | **Recommended For**    |
| ---------- | ------------------ | ---------------------- |
| **uv** ⭐  | `uv sync`          | Development (fastest)  |
| **pip**    | `pip install -e .` | Production/traditional |

**4️⃣ Database Setup**

```bash
# The app will automatically create tables on first run
# Ensure PostgreSQL is running and database exists
```

**5️⃣ Start Development Server**

| **Method** | **Command**            | **URL**               |
| ---------- | ---------------------- | --------------------- |
| **uv** ⭐  | `uv run python run.py` | http://localhost:8000 |
| **python** | `python run.py`        | http://localhost:8000 |

#### 🔗 Backend Features

- **📚 API Documentation**: Visit `http://localhost:8000/docs` (Swagger UI)
- **🤖 MCP Server**: Available at `http://localhost:8000/mcp/sse`
- **🔄 Auto-reload**: Enabled in development mode
- **📊 Structured Logging**: JSON-formatted logs for production

---

### 🎨 Frontend Setup (`telaten-client`)

> **🎯 Tech Stack**: Next.js 14, React 18, TypeScript, Tailwind CSS, shadcn/ui

#### 📋 Setup Steps

**1️⃣ Navigate to Frontend Directory**

```bash
cd telaten-client
```

**2️⃣ Environment Configuration**

```bash
# Copy environment template
cp .env.example .env.local
```

**📝 Required Environment Variables:**

```ini
# API Configuration
NEXT_PUBLIC_API_BASE_URL=http://localhost:8000/api/v1

# Optional: App Configuration
NEXT_PUBLIC_APP_NAME="Telaten"
NEXT_PUBLIC_APP_URL="http://localhost:3000"
```

**3️⃣ Install Dependencies**

| **Method** | **Command**    | **Recommended For**         |
| ---------- | -------------- | --------------------------- |
| **bun** ⭐ | `bun install`  | Development (fastest)       |
| **npm**    | `npm install`  | Traditional/CI environments |
| **yarn**   | `yarn install` | Alternative package manager |

**4️⃣ Start Development Server**

| **Method** | **Command**   | **URL**               |
| ---------- | ------------- | --------------------- |
| **bun** ⭐ | `bun dev`     | http://localhost:3000 |
| **npm**    | `npm run dev` | http://localhost:3000 |

#### 🎯 Frontend Features

- **📱 Mobile-First**: Responsive design optimized for mobile devices
- **🎨 Modern UI**: shadcn/ui components with Tailwind CSS
- **⚡ Fast**: Next.js 14 with App Router and Server Components
- **🔄 Real-time**: SSE integration for live updates
- **🌐 PWA Ready**: Progressive Web App capabilities
- **🎭 Animations**: Smooth transitions and micro-interactions

---

### 📚 API Documentation (`telaten-docs-api`)

> **🎯 Tech Stack**: Bruno Collections for interactive API testing

#### 📋 Setup Steps

**1️⃣ Install Bruno**

```bash
# Visit https://www.usebruno.com/ and download Bruno
# Or install via package manager
brew install bruno  # macOS
```

**2️⃣ Open API Collection**

1. Launch Bruno application
2. Select **"Open Collection"**
3. Navigate to `telaten-docs-api` folder
4. Set environment to **"local"** for development

#### 🔗 Available Environments

| **Environment** | **Base URL**                     | **Usage**            |
| --------------- | -------------------------------- | -------------------- |
| **local**       | `http://localhost:8000/api/v1`   | Development testing  |
| **deploy**      | `https://api.telaten.com/api/v1` | Production API       |
| **colab**       | Custom URL                       | Testing environments |

#### 🛠️ Testing Features

- **🔐 Authentication**: Auto-token management
- **📋 Request Collections**: Organized by module
- **🧪 Environment Variables**: Easy environment switching
- **📊 Response Validation**: Built-in testing capabilities

---

## 📸 Application Preview

<div align="center">

### 🖥️ Desktop Experience

<img src="preview/demo.gif" alt="Desktop Experience" />

### 📱 Mobile Experience

<img src="preview/mobile.gif" width="300" alt="Mobile Experience" />

</div>

---

## 🐳 Docker Deployment

### 🚀 Quick Start with Docker

Docker support is available for simplified deployment and development.

**Backend Only:**

```bash
cd telaten-backend
docker-compose up -d
```

**Full Stack Setup:**

```bash
# Backend
cd telaten-backend
docker-compose up -d

# Frontend (separate terminal)
cd ../telaten-client
bun install && bun dev
```

### 🔧 Docker Configuration

| **Service**    | **Port** | **Description**      |
| -------------- | -------- | -------------------- |
| **Backend**    | `8000`   | FastAPI application  |
| **PostgreSQL** | `5432`   | Database service     |
| **Redis**      | `6379`   | Caching (if enabled) |

---

## 🏗️ Architecture Overview

```mermaid
graph TB
    subgraph "🖥️ Client Layer"
        WEB[Next.js Frontend]
        MOBILE[Mobile PWA]
    end

    subgraph "🔗 API Gateway"
        API[FastAPI Backend]
        DOCS[API Documentation]
    end

    subgraph "🤖 AI Layer"
        LLM[LlamaIndex Workflows]
        MCP[MCP Server]
        TOOLS[Agent Tools]
    end

    subgraph "💾 Data Layer"
        DB[(PostgreSQL)]
        CACHE[(Redis)]
    end

    WEB --> API
    MOBILE --> API
    API --> LLM
    LLM --> MCP
    MCP --> TOOLS
    TOOLS --> DB
    API --> DB
    API --> CACHE
```

---

## 📚 Backend Architecture & Documentation

### 🏗️ System Architecture Overview

```mermaid
graph TB
    subgraph "🎯 User Layer"
        UI[Frontend App]
        API[REST API]
    end

    subgraph "🧠 AI Layer"
        MCP[MCP Server]
        AGENT[AI Agents]
        TOOLS[Agent Tools]
    end

    subgraph "💼 Business Layer"
        AUTH[Authentication]
        BIZ[Business Logic]
        GAMIFY[Gamification]
    end

    subgraph "🗄️ Data Layer"
        DB[(PostgreSQL)]
        CACHE[(Redis)]
    end

    UI --> API
    API --> AUTH
    API --> BIZ
    API --> GAMIFY
    API --> MCP
    MCP --> AGENT
    AGENT --> TOOLS
    TOOLS --> BIZ
    BIZ --> DB
    GAMIFY --> DB
    AUTH --> DB
```

### 🎯 Backend Key Features

#### 🤖 **AI-Powered Business Assistance**

- **Smart Milestone Generation**: AI creates tailored business milestones
- **Interactive Chat**: Context-aware business advisor
- **Automated Workflows**: Seamless task progression and completion

#### 🏢 **Comprehensive Business Management**

- **Profile System**: Complete business information and stages
- **Financial Tracking**: Income/expense monitoring with categories
- **Progress Monitoring**: Milestone and task management

#### 🎮 **Gamification System**

- **Points & Levels**: Progress-based advancement
- **Achievement System**: Unlockable badges and rewards
- **Leaderboards**: Competitive business rankings

### 🛠️ Backend Technology Stack

| **Layer**          | **Technology**           | **Purpose**                          |
| ------------------ | ------------------------ | ------------------------------------ |
| **Framework**      | FastAPI                  | High-performance async API           |
| **Database**       | PostgreSQL + SQLModel    | Robust data persistence              |
| **AI/ML**          | LlamaIndex + MCP         | Agent workflows and tool integration |
| **Authentication** | JWT + bcrypt             | Secure user management               |
| **Real-time**      | Server-Sent Events (SSE) | Live updates and streaming           |

### 📖 Detailed Documentation

| 📂 **Category**        | 📄 **Document**                                                    | 🎯 **Purpose**                                |
| ---------------------- | ------------------------------------------------------------------ | --------------------------------------------- |
| 🏗️ **Architecture**    | [Infrastructure](./telaten-backend/docs/INFRASTRUCTURE.md)         | Core configuration, security, MCP integration |
| 🤖 **AI & Workflows**  | [Agent & Main](./telaten-backend/docs/AGENT_MAIN.md)               | AI workflows, tools, and MCP server setup     |
| 👤 **User Management** | [Auth & Business](./telaten-backend/docs/AUTH_BUSINESS.md)         | Authentication, business profiles, levels     |
| 💰 **Business Logic**  | [Finance & Milestone](./telaten-backend/docs/FINANCE_MILESTONE.md) | Financial tracking and milestone management   |
| 🎮 **Engagement**      | [Gamification & Chat](./telaten-backend/docs/GAMIFICATION_CHAT.md) | Achievements, leaderboard, AI chat system     |
| 🌐 **API Reference**   | [Bruno Collection](./telaten-docs-api/)                            | Interactive API testing and documentation     |
| 🗄️ **Database**        | [ERD Diagram](./telaten-backend/docs/ERD.md)                       | Complete database schema and relationships    |

### 📋 Development Guidelines

#### 🔄 **Workflow Integration**

All major business actions are integrated with AI workflows for intelligent automation and user guidance.

#### 🔐 **Security Best Practices**

- JWT-based authentication with refresh tokens
- Password hashing using bcrypt
- Role-based access control (User/Admin)

#### 📊 **Data Architecture**

- Soft deletion for data integrity
- Audit trails with timestamps
- JSON fields for flexible schema evolution

### 📚 Component Documentation

| **Component**   | **Documentation**                  | **Location**                                             |
| --------------- | ---------------------------------- | -------------------------------------------------------- |
| 🔧 **Backend**  | Complete API and architecture docs | [`telaten-backend/docs/`](./telaten-backend/docs/)       |
| 🎨 **Frontend** | Component and page documentation   | [`telaten-client/README.md`](./telaten-client/README.md) |
| 📚 **API**      | Interactive API testing collection | [`telaten-docs-api/`](./telaten-docs-api/)               |

---

## 🤝 Contributing

We welcome contributions! Please follow these guidelines:

### 🔄 Development Workflow

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Make your changes** with proper documentation
4. **Test thoroughly** on both backend and frontend
5. **Submit a pull request** with clear description

### 📝 Code Standards

- **Backend**: Follow PEP 8, use type hints, add docstrings
- **Frontend**: Use TypeScript, follow ESLint rules, document components
- **Commits**: Use conventional commits (`feat:`, `fix:`, `docs:`, etc.)

### 🧪 Testing

```bash
# Backend tests
cd telaten-backend
pytest

# Frontend tests
cd telaten-client
bun test
```

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **FastAPI** - High-performance web framework
- **LlamaIndex** - AI orchestration framework
- **Next.js** - React framework for production
- **shadcn/ui** - Beautiful UI components
- **Bruno** - API testing made simple

---

<div align="center">
  <h3>🚀 Built with ❤️ for Indonesian MSMEs</h3>
  <p><strong>Empowering businesses through AI-driven growth</strong></p>
  
  [![GitHub Stars](https://img.shields.io/github/stars/TELATEN/telaten-apps?style=social)](https://github.com/TELATEN/telaten-apps)
  
  **[🌐 Visit Website](https://telaten.com)** • **[📚 Documentation](./telaten-backend/docs/)** • **[🐛 Report Bug](https://github.com/username/telaten-apps/issues)**
</div>
