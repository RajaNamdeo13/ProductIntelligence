# 🚀 ProductPulse

<h3 align="center">Product Analytics & Experimentation Platform</h3>

<p align="center">
  Analyze user behavior · Track feature adoption · Run A/B experiments · Monitor retention
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-18.x-green" />
  <img src="https://img.shields.io/badge/React-18.x-61DAFB" />
  <img src="https://img.shields.io/badge/MongoDB-Local%20%2F%20Mongoose-green" />
  <img src="https://img.shields.io/badge/TypeScript-5.x-blue" />
  <img src="https://img.shields.io/badge/License-MIT-blue" />
</p>

<p align="center">
  <a href="#features">Features</a> ·
  <a href="#architecture">Architecture</a> ·
  <a href="#api-reference">API Reference</a> ·
  <a href="#getting-started">Getting Started</a> ·
  <a href="#testing">Testing</a>
</p>

---

## 📖 Overview

ProductPulse is a full-stack product analytics platform designed to help product teams understand user behavior and make data-driven decisions.

It provides insights into user activity, conversion funnels, retention trends, feature adoption, and A/B experiments using event-based product data.

The platform brings these workflows together in one dashboard so teams can identify product trends, investigate user behavior, and evaluate product changes.

---

## 🖼️ UI Preview

### Landing Page

![ProductPulse Landing Page](screenshots/landing-page.png)

### Dashboard

![ProductPulse Dashboard](screenshots/dashboard.png)

### Funnel Analysis

![ProductPulse Funnel Analysis](screenshots/funnel-analysis.png)

### Retention Analysis

![ProductPulse Retention](screenshots/retention.png)

### Feature Adoption

![ProductPulse Feature Adoption](screenshots/feature-adoption.png)

### A/B Experiments

![ProductPulse Experiments](screenshots/experiments.png)

---

## ✨ Features

### 🔐 Authentication
- User registration and login
- JWT-based authentication
- Protected application routes

### 📊 Product Analytics
- Daily and monthly active users
- Event-based analytics
- Conversion metrics
- KPI monitoring
- Product usage trends

### 🔻 Funnel Analysis
Analyze how users move through a defined product journey and identify where users drop off.

Example:

`Landing Page → Product View → Add to Cart → Checkout → Purchase`

### 🔁 Retention Analysis
Track returning users across different time periods and understand how engagement changes over time.

### 🚀 Feature Adoption
Measure how frequently users interact with individual product features and compare adoption across users.

### 🧪 A/B Experimentation
Create experiments with control and variant groups and compare their performance using measurable product metrics.

### 📥 Event Data Ingestion
Upload CSV-based event data and process it for analytics and visualization.

## 🏗️ Architecture

```text
┌──────────────────────────────┐
│        React Frontend        │
│     TypeScript + Vite       │
│   Tailwind + Recharts       │
└──────────────┬───────────────┘
               │
               │ REST API
               ▼
┌──────────────────────────────┐
│       Express Backend        │
│      Node.js + TypeScript    │
│                              │
│ Authentication               │
│ Analytics Engine             │
│ Funnel Analysis              │
│ Retention Analysis           │
│ Experimentation              │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│          MongoDB             │
│      Mongoose ODM            │
│                              │
│ Users · Events · Experiments │
│ Funnels · Analytics         │
└──────────────────────────────┘


## Data Flow


User Events
     ↓
Event Ingestion
     ↓
MongoDB
     ↓
Analytics Processing
     ↓
Product Metrics
     ↓
Dashboard & Reports
     ↓
Product Decisions


## 🛠️ Tech Stack

| Layer    | Technology                                                    |
| -------- | ------------------------------------------------------------- |
| Frontend | React 18, TypeScript, Vite, Tailwind CSS, shadcn/ui, Recharts |
| Backend  | Node.js, Express.js, JWT, Multer, CSV Parser                  |
| Database | MongoDB with Mongoose ODM                                     |
| Testing  | Jest, Supertest                                               |
| Icons    | Lucide React                                                  |
| Routing  | React Router DOM                                              |

---

## 📂 Project Structure

```text
ProductPulse/
│
├── client/
│   └── src/
│       ├── components/       # Reusable UI components
│       ├── pages/            # Route-level pages
│       ├── hooks/            # Custom React hooks
│       ├── lib/              # Utility functions
│       └── styles/           # Global styles
│
└── server/
    ├── models/
    │   ├── User.js
    │   ├── Event.js
    │   ├── Upload.js
    │   └── Experiment.js
    │
    ├── routes/
    │   ├── auth.js
    │   ├── analytics.js
    │   ├── upload.js
    │   ├── events.js
    │   └── experiments.js
    │
    ├── middleware/           # Authentication & error middleware
    ├── tests/                # Jest + Supertest test suites
    └── server.js
```

---

## 🗄️ Data Models

The application currently works with the following core models:

* **User** — Authentication and user information
* **Event** — User activity and product events
* **Upload** — CSV upload history and metadata
* **Experiment** — A/B testing configuration and results

---

## 🔌 API Reference

### Authentication

| Method | Endpoint             | Description            |
| ------ | -------------------- | ---------------------- |
| `POST` | `/api/auth/register` | Register a new user    |
| `POST` | `/api/auth/login`    | Login and receive JWT  |
| `GET`  | `/api/auth/me`       | Get authenticated user |

### Analytics

| Method | Endpoint                   | Description                                 |
| ------ | -------------------------- | ------------------------------------------- |
| `GET`  | `/api/analytics/kpis`      | DAU, MAU, conversion rate and event metrics |
| `GET`  | `/api/analytics/funnel`    | Funnel steps and conversion rates           |
| `GET`  | `/api/analytics/retention` | Cohort retention analysis                   |
| `GET`  | `/api/analytics/features`  | Feature adoption and usage statistics       |

### Experiments

| Method   | Endpoint               | Description          |
| -------- | ---------------------- | -------------------- |
| `GET`    | `/api/experiments`     | List experiments     |
| `POST`   | `/api/experiments`     | Create an experiment |
| `PATCH`  | `/api/experiments/:id` | Update an experiment |
| `DELETE` | `/api/experiments/:id` | Delete an experiment |

### Events & Uploads

| Method | Endpoint              | Description           |
| ------ | --------------------- | --------------------- |
| `POST` | `/api/events`         | Ingest a new event    |
| `POST` | `/api/upload/csv`     | Upload CSV event data |
| `GET`  | `/api/upload/history` | View upload history   |

---

# 🚀 Getting Started

## Prerequisites

Make sure you have:

* Node.js 18+
* MongoDB Community Server
* MongoDB Compass
* npm

---

## 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/ProductPulse.git
cd ProductPulse
```

Replace `YOUR_USERNAME` with your GitHub username.

---

## 2. Configure MongoDB

ProductPulse can run using a local MongoDB instance.

Make sure MongoDB is running and accessible through:

```text
mongodb://127.0.0.1:27017/
```

MongoDB Compass can be used to inspect the database and collections.

The application uses a database named:

```text
ProductPulse
```

---

## 3. Configure Environment Variables

Create a `.env` file inside the `server/` directory:

```env
PORT=5000
MONGODB_URI=mongodb://127.0.0.1:27017/ProductPulse
JWT_SECRET=your_jwt_secret_key
CLIENT_ORIGIN=http://localhost:5173
```

> Never commit your `.env` file to GitHub.

---

## 4. Start the Backend

Open a terminal:

```bash
cd server
npm install
npm run dev
```

The backend will run at:

```text
http://localhost:5000
```

You should see:

```text
✓ MongoDB connected
✓ API running on http://localhost:5000
```

---

## 5. Start the Frontend

Open a second terminal:

```bash
cd client
npm install
npm run dev
```

The frontend will run at:

```text
http://localhost:5173
```

Open the URL in your browser to access ProductPulse.

---

# 🧪 Testing

The backend includes API tests using Jest and Supertest.

Run:

```bash
cd server
npm test
```

The test suite covers key backend functionality including:

* Authentication
* KPI analytics
* Funnel analytics
* Retention analytics
* Feature adoption
* Experiment APIs

---

# 🗺️ Future Enhancements

Planned improvements include:

* 🤖 AI-powered product insights
* 🔎 Automated KPI anomaly detection
* 🧠 AI-assisted root-cause analysis
* 💬 Customer feedback analysis
* 📈 Predictive user behavior modeling
* 🧪 Advanced experimentation
* 🏢 Multi-tenant organizations
* 👥 Team collaboration and permissions
* 📧 Scheduled product reports
* 📤 CSV / PDF data exports

---

## 🔒 Environment & Security

The following files and directories should remain local and should not be committed:

```text
.env
node_modules/
dist/
*.log
```

The repository includes a `.gitignore` to prevent sensitive configuration and generated dependencies from being uploaded.

---

## 👨‍💻 Project

**ProductPulse**

A full-stack product analytics platform for understanding user behavior, evaluating product performance, and supporting data-driven product decisions.

---

## 📄 License

This project is intended for educational and portfolio purposes.
