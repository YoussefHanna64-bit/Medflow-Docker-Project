# MedFlow – Docker Deployment Guide

MedFlow is a full-stack clinical platform built with the MERN stack (MongoDB, Express, React, Node.js). This repository contains everything needed to run the project locally using Docker — no manual installation of Node.js or dependencies required.

---

## Prerequisites

Before you begin, make sure you have the following installed on your machine:

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) — available for Windows, Mac, and Linux

That's it. You do not need Node.js, npm, or MongoDB installed locally.

---

## How to Run

**1. Make sure Docker Desktop is open and running**
Look for the Docker whale icon in your taskbar/system tray. Wait until it is fully started before continuing.

**2. Place the `docker-compose.yml` file in any folder on your machine**

**3. Open a terminal in that folder and run:**

```bash
docker compose up
```

Docker will automatically pull the backend and frontend images from Docker Hub and start both services. This may take a minute on the first run.

**4. Open your browser and go to:**

```
http://localhost:5173
```

The application should be fully running.

---

## Services

| Service  | URL                      | Description              |
|----------|--------------------------|--------------------------|
| Frontend | http://localhost:5173    | React + Vite client app  |
| Backend  | http://localhost:5000    | Node.js + Express API    |

The backend connects to a hosted MongoDB Atlas database — no local database setup needed.

---

## Docker Hub Images

| Image                          | Description       |
|--------------------------------|-------------------|
| `azouz08/medflow-backend`      | Express API server |
| `azouz08/medflow-frontend`     | React Vite client  |

---

## Stopping the Application

To stop the running containers, press `Ctrl + C` in the terminal, then run:

```bash
docker compose down
```

---

## Project Structure (Source)

```
MERN-MedFlow/
├── BackEnd/          # Node.js + Express API
│   ├── config/
│   ├── controllers/
│   ├── middlewares/
│   ├── models/
│   ├── routes/
│   ├── utils/
│   ├── Dockerfile
│   └── server.js
├── FrontEnd/         # React + Vite client
│   ├── src/
│   ├── public/
│   ├── Dockerfile
│   └── vite.config.js
└── docker-compose.yml
```

---

## Built With

- **Frontend:** React, Vite, Tailwind CSS
- **Backend:** Node.js, Express.js
- **Database:** MongoDB Atlas
- **Containerization:** Docker, Docker Compose