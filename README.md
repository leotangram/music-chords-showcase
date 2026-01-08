<div align="center">
  <img src="./assets/banner.png" alt="Music Chords Sync Banner" width="100%" />

  # 🎵 Music Chords Sync
  
  **The Real-time Setlist Synchronization Platform for Live Bands.**
  
  <p align="center">
    <img src="https://img.shields.io/badge/Next.js_16-black?style=for-the-badge&logo=next.js&logoColor=white" />
    <img src="https://img.shields.io/badge/React_19-61DAFB?style=for-the-badge&logo=react&logoColor=black" />
    <img src="https://img.shields.io/badge/NestJS_11-E0234E?style=for-the-badge&logo=nestjs&logoColor=white" />
    <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" />
  </p>

  <p align="center">
    <a href="#-technical-stack">Tech Stack</a> • 
    <a href="#-architecture">Architecture</a> • 
    <a href="#-roadmap">Roadmap</a>
  </p>
</div>

---

## 🚀 The Mission
Live performances rely on perfect synchronization. Traditional paper sheets or unconnected tablets lead to confusion on stage. 

**Music Chords Sync** solves this by creating a **master-slave WebSocket connection**, ensuring every musician sees exactly the same chart, scroll position, and annotations in real-time, with **zero latency**.

---

## 🛠 Technical Stack
This project is built on a **Bleeding-Edge Stack** (2025/2026 standards) to ensure maximum performance, type safety, and developer experience.

### 🎨 Frontend (The Cutting Edge)
| Technology | Version | Role in Architecture |
| :--- | :--- | :--- |
| **Next.js** | `v16.0.1` | App Router, Server Actions & SSR for SEO. |
| **React** | `v19.2.0` | Leveraging the new React Compiler & Hooks. |
| **Tailwind CSS** | `v4.0` | Styling using the new Oxide engine (Rust-based). |
| **Zustand** | `v5.0` | Transient client-state management (lighter than Redux). |
| **Playwright** | `v1.56` | E2E Testing for critical sync flows. |
| **Radix UI** | `Latest` | Headless, accessible UI primitives. |

### ⚙️ Backend (Scalable & Clean)
| Technology | Version | Role in Architecture |
| :--- | :--- | :--- |
| **NestJS** | `v11.0` | Modular Architecture with strict Dependency Injection. |
| **Socket.io** | `v4.8` | Real-time bi-directional communication events. |
| **Redis** | `Adapter` | Pub/Sub for horizontal scaling of WebSocket nodes. |
| **Prisma** | `v6.19` | Type-safe ORM for PostgreSQL. |
| **Docker** | `Latest` | Containerization for consistent deployments. |

---

## 🏗 System Architecture

The system is built following **Clean Architecture** principles to decouple business logic from frameworks.

### 1. Real-time Sync Engine
To handle unreliable networks in venues (bad Wi-Fi), the system implements an **Optimistic UI + Eventual Consistency** pattern:
* **Leader Action:** When the Band Leader changes a song, their UI updates instantly (0ms latency).
* **Broadcast:** The event sends a payload via WebSockets.
* **Redis Pub/Sub:** The payload is distributed via Redis, allowing the backend to scale across multiple instances/containers without losing context.
* **Client Reconciliation:** Connected devices ("Slave" mode) receive the signal and strictly sync their state.

### 2. Micro-interactions
* **Drag & Drop:** Powered by `@dnd-kit` for setlist management.
* **Validations:** Strict runtime validation using `Zod` on both ends.

---

## 📸 Preview
<div align="center">
  <img src="./assets/app-demo.gif" alt="App Realtime Demo" width="800" />
  
  <p><em>Figure 1: Real-time synchronization between Leader (Left) and Band Member (Right). (Still working)</em></p>
</div>

---

## 🗺 Roadmap
- [x] **Core:** WebSocket Engine & Room Management.
- [x] **Auth:** JWT & Role-based Access Control (RBAC).
- [x] **UI:** Dark Mode & Responsive Canvas.
- [ ] **Q2 2026:** MIDI Foot Pedal Integration (Web MIDI API).
- [ ] **Q3 2026:** Native Mobile Wrapper (React Native).

---

## 📞 Contact & Access
**Leonardo Omaña** *Tech Lead | Frontend Architect | SaaS Builder*

> This project is currently in **Closed Beta**. I am open to technical discussions regarding the architecture or potential partnerships.

[LinkedIn](https://www.linkedin.com/in/leotangram/) | [GitHub Profile](https://github.com/leotangram) | [leotangram](https://leoomana.com)
