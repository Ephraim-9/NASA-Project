# NASA Mission Control Dashboard

[![Live Demo](https://img.shields.io/badge/demo-online-brightgreen?logo=firefox&logoColor=white)](http://13.62.6.123:8000/)
[![AWS](https://img.shields.io/badge/hosted_on-AWS_EC2-FF9900?logo=amazon-aws&logoColor=white)](https://aws.amazon.com/ec2/)
[![MongoDB Atlas](https://img.shields.io/badge/db-MongoDB_Atlas-47A248?logo=mongodb&logoColor=white)](https://www.mongodb.com/atlas)
[![Docker](https://img.shields.io/badge/dockerized-yes-2496ED?logo=docker&logoColor=white)](https://www.docker.com/)
[![CI](https://github.com/Ephraim-9/NASA-Project/actions/workflows/node.yml/badge.svg)](https://github.com/Ephraim-9/NASA-Project/actions)

A full-stack web application that simulates a NASA-style mission control dashboard for scheduling and tracking interstellar missions to habitable exoplanets. Built with React (frontend), Node.js + Express (backend), and MongoDB (database), this project integrates real SpaceX launch data and NASA's Kepler exoplanet dataset.

> ⚠️ **This is a demo/educational project and is NOT affiliated with NASA, SpaceX, or any official space agency.**

---

## 🌌 Features

- **Launch Missions**: Schedule custom interstellar missions to confirmed habitable exoplanets.
- **Upcoming Missions**: View both user-scheduled and real SpaceX launches.
- **Mission History**: Browse historical SpaceX launches since 2006.
- **Responsive UI**: Futuristic UI powered by the [Arwes](https://arwes.dev) design framework with sound effects and animations.
- **Real Data**:
  - Launch data from [SpaceX API](https://github.com/r-spacex/SpaceX-API)
  - Habitable exoplanets filtered from NASA’s Kepler dataset

---

## 🛠️ Tech Stack

### Frontend

- React 17
- React Router v5
- Arwes UI library (sci-fi themed components)
- Create React App

### Backend

- Node.js + Express
- MongoDB (via Mongoose ODM)
- Axios (for external API calls)
- CSV parsing (for Kepler dataset)

### DevOps & Tooling

- Docker
- GitHub Actions (CI pipeline)
- Jest + Supertest (testing)
- Nodemon (dev server reloading)

---

## 📦 Project Structure

```

nasa-project/
├── client/ # React frontend
├── server/ # Node.js + Express backend
├── Dockerfile # Docker build config
├── .github/workflows/ # CI pipeline (Node.js test + build)
├── package.json # Root scripts for managing client/server
└── ...

```

---

## 🚀 Getting Started

### Prerequisites

- Node.js v16+
- npm or yarn
- MongoDB instance (we recommend [MongoDB Atlas](https://www.mongodb.com/atlas))
- (Optional) Docker for containerized deployment

### 1. Clone the repo

```bash
git clone https://github.com/Ephraim-9/NASA-Project.git
cd NASA-Project
```

### 2. Set up environment

Create a `.env` file in the **server** directory:

```env
MONGO_URL=mongodb+srv://<user>:<password>@cluster0.xxxxx.mongodb.net/nasa-project?retryWrites=true&w=majority
PORT=8000
```

> Replace the `MONGO_URL` with your actual MongoDB Atlas connection string.

### 3. Install dependencies

```bash
npm install
npm run install
```

### 4. Run in development mode

```bash
npm run watch
```

- Frontend: `http://localhost:3000`
- Backend: `http://localhost:8000`

> The client proxies API requests to `/v1` on the backend.

### 5. Build for production

```bash
npm run build --prefix client
npm start --prefix server
```

The built React app will be served from `server/public`.

---

## 🐳 Docker Deployment

Build and run with Docker:

```bash
docker build -t nasa-mission-control .
docker run -p 8000:8000 nasa-mission-control
```

> Ensure your `MONGO_URL` is accessible from within the container (e.g., use MongoDB Atlas or configure Docker networking).

### Deployed on AWS

This app is currently live on **AWS EC2**:
🔗 **[Live Demo](http://13.62.6.123:8000/)**

---

## 🧪 Testing

Run backend tests:

```bash
npm test --prefix server
```

Run frontend tests:

```bash
npm test --prefix client
```

Run all tests:

```bash
npm run test
```

---

## 📄 License & Disclaimer

This project is for **educational and demonstration purposes only**.

> 🚫 **Not affiliated with NASA, SpaceX, or any government space agency.**  
> 🌍 All data is used under fair use for learning and portfolio.

---

## 🙌 Acknowledgements

- [SpaceX API](https://github.com/r-spacex/SpaceX-API) for real launch data
- NASA Exoplanet Archive for Kepler dataset

---

> 🌠 “The Earth is the cradle of humanity, but mankind cannot stay in the cradle forever.” — Konstantin Tsiolkovsky
