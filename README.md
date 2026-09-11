# 🚀 ProductPulse

### Product Analytics & Experimentation Platform

**Analyze user behavior · Track feature adoption · Run A/B experiments · Monitor retention**

`Node.js` `React` `MongoDB` `TypeScript` `MIT License`

---

## 📖 Overview

ProductPulse is a full-stack product analytics platform designed to help product teams understand user behavior and make data-driven decisions.

It brings together key product metrics such as user activity, conversion funnels, retention, feature adoption, and A/B experiment performance in a single dashboard.

The platform supports event-based analytics, CSV data ingestion, funnel analysis, cohort retention, feature usage tracking, and experimentation workflows.

---

## ✨ Features

### 🔐 Authentication & Security

* JWT-based authentication
* Secure user registration and login
* Protected application routes
* User-specific data access
* Authentication middleware

### 📊 Analytics Dashboard

* **DAU / MAU** — Daily and Monthly Active Users
* **Conversion Rate** — Track end-to-end conversion
* **Event Analytics** — Analyze user events
* **KPI Monitoring** — Monitor important product metrics

### 🔽 Funnel Analysis

Analyze users across multi-step journeys:

```text
Signup → Activate → Purchase
```

* Step-wise user breakdown
* Conversion rate at each stage
* Drop-off identification
* Funnel performance analysis

### 🔁 Retention Analytics

* Cohort-based retention analysis
* Weekly retention tracking
* User engagement trends
* Retention matrix visualization

### 🧩 Feature Adoption

* Feature usage analytics
* Feature adoption percentages
* Most-used features
* Least-used features
* User interaction tracking

### 🧪 A/B Testing & Experimentation

* Create and manage experiments
* Support multiple experiment variants
* Compare conversion performance
* Calculate statistical significance
* Identify experiment winners

### 📁 CSV Data Ingestion

* Upload event data through CSV files
* Automated event processing
* Upload history tracking
* User-specific datasets

---

## 🏗️ Architecture

```text
┌──────────────────────────────────┐
│          React Frontend          │
│   Vite · TypeScript · Tailwind   │
└───────────────┬──────────────────┘
                │
                │ REST API
                ▼
┌──────────────────────────────────┐
│        Express Backend            │
│     JWT · REST APIs · Multer      │
└───────────────┬──────────────────┘
                │
                │ Mongoose ODM
                ▼
┌──────────────────────────────────┐
│        MongoDB Database           │
│ Users · Events · Experiments      │
└──────────────────────────────────┘
```

---

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
