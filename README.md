
# 🏠 RentEase — Peer-to-Peer Rental Platform

[![Next.js](https://img.shields.io/badge/Next.js-15-black?style=flat-square&logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19-blue?style=flat-square&logo=react)](https://react.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.0-06B6D4?style=flat-square&logo=tailwind-css)](https://tailwindcss.com/)
[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=flat-square&logo=node.js)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=flat-square&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)

A modern, full-stack peer-to-peer rental marketplace that empowers local communities to rent, lend, and share items sustainably. Built with a high-performance **Next.js 15** frontend and a robust **Node.js/Express** backend, RentEase streamlines the sharing economy with real-time interactions, native payment processors, and intensive security profiling.

---

## ✨ Features

### 🎯 Core Platform Architecture
* **Item Listings:** Dynamic CRUD engine to create and manage rental items with automated image optimization.
* **Browse & Local Search:** Precision category filtering and map-based search parameters.
* **Rental Requests Workflow:** Structured state machine processing (Pending ➡️ Approved ➡️ Rented ➡️ Returned).
* **Real-time Chat:** Low-latency built-in messaging for active negotiation between renters and lenders.
* **Payment Integration:** Secure end-to-end payment processing via **Razorpay API Gateway**.
* **Unified Auth:** Multi-provider authentication using secure OAuth (Google, Apple) alongside verified email/password.
* **Location Intelligence:** Interactive map overlays powered by **Leaflet** for localized hyper-local exploration.

### 📊 Dashboard & Advanced Analytics
* **Data Visualization:** Gorgeous interactive financial and activity metrics graphs built with **Chart.js**.
* **Metrics Monitoring:** Global state telemetry rendering total items, operational earnings, active rentals, and user ratings.
* **Live Action Logs:** High-fidelity feed rendering live notifications on payment completions and active order requests.

### 🔐 Hardened Security Profile
* **Token Access Control:** Stateful and stateless safety layers processing custom JWT payloads.
* **Role-Based Access Control (RBAC):** Rigid behavioral boundaries decoupling tenant capabilities from provider resources.
* **Input Scrubber:** Total request data schema confirmation using strict **Joi validation middleware**.
* **DDoS & Abuse Shielding:** Global rate-limiting constraints monitoring IP traffic pools.

---

## 🏗️ System Architecture



                   ┌─────────────────────────┐
                   │   Next.js 15 Client     │
                   └────────────┬────────────┘
                                │ (HTTPS & REST API)
                                ▼
                   ┌─────────────────────────┐
                   │   Node.js Server (JWT)  │
                   └──────┬───────────┬──────┘
                          │           │
       ┌──────────────────▼──┐     ┌──▼──────────────────┐
       │ MongoDB Database    │     │ Cloudinary CDN      │
       └─────────────────────┘     └─────────────────────┘



### Tech Stack Breakdown

| Layer | Frontend Component Ecosystem | Backend & Operations Infrastructure |
| :--- | :--- | :--- |
| **Engine** | Next.js 15 (React 19 App Router) | Node.js & Express.js Core |
| **Design** | Tailwind CSS v4.0 + Custom UI Components | Joi Schema Validations |
| **Data** | React Hooks & Native Context Providers | MongoDB Atlas + Mongoose ODM |
| **Charts** | Chart.js (`react-chartjs-2`) | Winston Logging System + PM2 Processors |
| **Maps** | Leaflet Client Engine (`react-leaflet`) | Razorpay Commercial SDK |
| **Motion** | Framer Motion Vector Transitions | Cloudinary Media Storage Integration |

---

## 🚀 Getting Started

### Prerequisites
* **Node.js** v18.0.0 or higher
* Running local instance of **MongoDB** or a **MongoDB Atlas** Cloud Cluster
* Verified **Cloudinary**, **Razorpay**, and **SMTP Mail** access credentials

### Installation

1. **Clone the project repository:**
   ```bash
   git clone <repository-url>
   cd project1

```

2. **Install node dependencies across workspaces:**
```bash
# Build the client ecosystem
cd Client && npm install

# Build the service backend
cd ../Server && npm install

```


3. **Configure Environment Declarations:**
Create a `.env.local` inside `/Client`:
```env
NEXT_PUBLIC_API_URL=http://localhost:5000
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=your_cloud_name

```


Create a `.env` inside `/Server`:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/rentease
JWT_SECRET=your_jwt_secret_long_hash
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
RAZORPAY_KEY_ID=your_razorpay_key
RAZORPAY_KEY_SECRET=your_razorpay_secret
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_app_password

```


4. **Booting Application Workspaces:**
```bash
# Run Node API Server (From inside /Server execution pipeline)
npm run dev

# Run Next.js Application Core (From inside /Client execution pipeline)
npm run dev

```



---

## 📱 Platform Map Route Layout

### Public Surface

* `/` — Immersive Landing Matrix with dynamic Call-To-Actions.
* `/browse` — Global market exploration engine with category matrices.
* `/pricing` — Platform micro-transaction structure breakdowns.
* `/safety` — Trust verification protocols and physical sharing safety standard definitions.

### Authenticated & Shielded Corridors

* `/dashboard` — Master interface housing analytical metrics components.
* `/list-item` — Multi-step item deployment canvas.
* `/requests` — Rental state management cockpit.
* `/chats` — Dedicated communication hub.

---

## 🔧 Core API Specifications

### Authentication Engine (`/api/auth`)

* `POST /register` — Provisions identity details into the collection.
* `POST /login` — Evaluates verification parameters and delivers signed JWT access structures.

### Marketplace Infrastructure (`/api/items`)

* `GET /` — Fetches optimized asset matrices depending on geographical parameters.
* `POST /` — Validates payload shapes using Joi rules and writes asset records to database collection.
* `PUT /:id` — Runs evaluation criteria on ownership status and patches changes.

### Processing Engine (`/api/payments`)

* `POST /create-order` — Triggers checkout sequences on Razorpay network infrastructure.
* `POST /verify` — Evaluates cryptographic checksum signatures from webhooks.

---

## 🧪 Automated Testing

Verify stability profiles across the microservices layers:

```bash
# Frontend Unit Affirmation Checks
cd Client && npm run test

# Integration & Endpoint Assertions
cd Server && npm run test

```

---

## 📈 Optimization Implementations

* **Code Segregation:** Leveraging Next.js dynamic code splitting features to drastically reduce initial JS bundles.
* **Asset Transformation:** Utilizing Next.js native `<Image />` handlers to optimize format distributions (WebP/AVIF).
* **Database Indexes:** Query acceleration via strategically mapped index arrays on searching conditions within MongoDB collections.
* **Network Throttling:** Gzip compression filters attached on outgoing express processing arrays.

---

## 🌟 Future Roadmap

* **Mobile Matrix:** Cross-platform native deployment utilizing a shared React Native codebase.
* **Heuristic Engine:** AI recommendation algorithms predicting context-aware rental matches based on user habits.
* **Video Handshakes:** Direct internal streaming components for safe, pre-checkout digital asset inspections.
* **Insurance Pipelines:** Native contractual protection bonds covering asset breakages or operational loss.

---

## 🤝 Contributing

1. Fork the Project Core Repository
2. Initialize Features Branch (`git checkout -b feature/AmazingFeature`)
3. Commit Atomic Adjustments (`git commit -m 'feat: Add Awesome Feature'`)
4. Push directly upwards to Upstream Remote (`git push origin feature/AmazingFeature`)
5. Open an official, peer-reviewable Pull Request

---

## 📄 License

Distributed under the terms of the MIT Open Source License. Review accompanying `LICENSE` documents for contextual boundaries.

---

**Built with ❤️ by the RentEase Engineering Core Team**

```

```
