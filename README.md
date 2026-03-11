<p align="center">
  <img src="./assets/banner.png" alt="SpeakHarvest Banner" width="100%"/>
</p>

<h1 align="center">🌾 SpeakHarvest — Voice-Powered Multilingual Agri Marketplace</h1>

<p align="center">
  <b>Bridging the communication gap between Indian farmers and buyers through AI-powered voice, real-time translation, and smart market insights.</b>
</p>

<p align="center">
  <a href="#-key-features"><img src="https://img.shields.io/badge/Features-🎙️_Voice_AI-059669?style=for-the-badge&labelColor=1a1a2e" alt="Features"/></a>
  <a href="#-tech-stack"><img src="https://img.shields.io/badge/Stack-React_|_Node_|_Gemini-3b82f6?style=for-the-badge&labelColor=1a1a2e" alt="Tech Stack"/></a>
  <a href="#-getting-started"><img src="https://img.shields.io/badge/Setup-Quick_Start-f59e0b?style=for-the-badge&labelColor=1a1a2e" alt="Setup"/></a>
  <a href="#-system-architecture"><img src="https://img.shields.io/badge/Docs-Architecture-8b5cf6?style=for-the-badge&labelColor=1a1a2e" alt="Architecture"/></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/React-19-61dafb?logo=react&logoColor=white" alt="React 19"/>
  <img src="https://img.shields.io/badge/TypeScript-5.8-3178c6?logo=typescript&logoColor=white" alt="TypeScript"/>
  <img src="https://img.shields.io/badge/Vite-6.2-646cff?logo=vite&logoColor=white" alt="Vite"/>
  <img src="https://img.shields.io/badge/Node.js-Express_5-339933?logo=nodedotjs&logoColor=white" alt="Node.js"/>
  <img src="https://img.shields.io/badge/MongoDB-Mongoose_9-47a248?logo=mongodb&logoColor=white" alt="MongoDB"/>
  <img src="https://img.shields.io/badge/Google_Gemini-2.0_Flash-4285f4?logo=googlegemini&logoColor=white" alt="Gemini AI"/>
  <img src="https://img.shields.io/badge/License-ISC-green" alt="License"/>
</p>

---

## 🚀 The Problem

> **75% of Indian farmers** speak regional languages and lack digital literacy. Existing agri-marketplaces are text-heavy, English-first, and inaccessible — leaving millions unable to negotiate fair prices or access market intelligence.

**SpeakHarvest** solves this with a **voice-first, AI-native** platform where farmers and buyers can list, discover, negotiate, and trade crops — **entirely through voice**, in **6+ Indian languages**, with **zero typing required**.

---

## ✨ Key Features

### 🎙️ Intelligent Voice Assistant (Gemini Live)
The platform features a deeply integrated, real-time voice assistant powered by **Google Gemini 2.0 Flash** with **multilingual** support (English & Regional Languages):

<table>
<tr>
<td width="50%">

#### 🛒 For Buyers
- **Advanced Market Search** — Filter by location, price range, freshness, farmer name, or crop
  - *"Show me wheat available in Punjab"*
  - *"Crops under ₹50/kg"*
  - *"Show listings added today"*
- **Negotiation Aide** — AI reads message history & sends replies via voice
- **Smart Sorting** — Instant sort by price (Low ↔ High)

</td>
<td width="50%">

#### 🧑‍🌾 For Farmers
- **Hands-Free Inventory** — Create, update & delete listings by voice
  - *"Post 100kg of Potatoes at ₹25/kg in Nashik"*
  - *"Change the price of Onions to ₹30"*
- **Voice Inbox** — *"Do I have any new messages?"*
- **Instant Replies** — Dictate responses without typing
- **Market Insights** — AI-generated pricing & trend analysis

</td>
</tr>
</table>

### 🌐 Multilingual & Accessible
| Feature | Description |
|:--------|:------------|
| **Real-time Chat Translation** | Messages auto-translate between farmer & buyer preferred languages |
| **6 Language Support** | Hindi, English, Marathi, Telugu, Tamil, Bengali |
| **Audio-First Interface** | Full platform control through voice — zero typing needed |

### ✨ Premium UI/UX
| Feature | Description |
|:--------|:------------|
| 🌙 **Immersive Dark Mode** | Circular reveal animation, system preference detection, persistent settings |
| 🔮 **Glassmorphism** | Modern translucent UI elements with backdrop blur |
| ⚡ **Micro-interactions** | Hover lifts, glow effects, press-scale, ripple buttons, shine overlays |
| 🎨 **Dynamic Transitions** | Seamless color morphing across all themes |

### 🔒 Enterprise-Grade Security
| Layer | Implementation |
|:------|:--------------|
| **DDoS Protection** | `express-rate-limit` — brute-force & bot swarm prevention |
| **NoSQL Injection Defense** | `mongo-sanitize` — input scrubbing on all objects |
| **Header Armor** | `helmet` — XSS, clickjacking, MIME-sniffing protection |
| **Payload Limits** | 50KB JSON body caps — prevents memory-exhaustion DOS |

---

## 🛠 Tech Stack

```
┌─────────────────────────────────────────────────────────┐
│                    FRONTEND (Client)                     │
│  React 19 · TypeScript · Vite 6 · TailwindCSS · Lucide  │
│  Google GenAI SDK · WebSocket Streaming                  │
├─────────────────────────────────────────────────────────┤
│                     BACKEND (Server)                     │
│  Node.js · Express 5 · Mongoose 9 · Multer · Cloudinary │
│  Helmet · Rate-Limiter · Mongo-Sanitize                  │
├─────────────────────────────────────────────────────────┤
│                     DATA & AI LAYER                      │
│  MongoDB · Google Gemini 2.0 Flash · Cloudinary CDN      │
└─────────────────────────────────────────────────────────┘
```

---

## 📐 System Architecture

```mermaid
graph TD
    classDef client fill:#e3f2fd,stroke:#1565c0,stroke-width:2px;
    classDef server fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px;
    classDef db fill:#fff3e0,stroke:#ef6c00,stroke-width:2px;
    classDef external fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px;
    classDef actor fill:#fafafa,stroke:#333,stroke-width:1px,stroke-dasharray: 5 5;

    Farmer["🧑‍🌾 Farmer"]
    Buyer["🏢 Buyer"]

    subgraph Client ["Frontend — React / Vite"]
        direction TB
        App["App.tsx — Router & State"]
        UI["UI Components — Farmer & Buyer Dashboards"]
        API_Client["api.ts — HTTP Fetch Wrapper"]
        Gemini_Service["geminiService.ts — AI Client SDK"]

        App --> UI
        UI --> API_Client
        UI --> Gemini_Service
    end

    subgraph Backend ["Backend — Node.js / Express"]
        direction TB
        Server_Entry["src/index.js — Entry Point"]
        Auth_Route["User Routes — /api/users"]
        Listing_Route["Listing Routes — /api/listings"]
        Message_Route["Message Routes — /api/messages"]

        Server_Entry --> Auth_Route
        Server_Entry --> Listing_Route
        Server_Entry --> Message_Route
    end

    subgraph Database ["Data Layer — MongoDB"]
        Mongo_Users[("User Collection")]
        Mongo_Listings[("Listing Collection")]
        Mongo_Messages[("Message Collection")]
    end

    subgraph External ["External Services"]
        Google_AI["✨ Google Gemini 2.0 Flash"]
        Cloudinary_CDN["☁️ Cloudinary CDN"]
    end

    Farmer -->|Uses UI| Client
    Buyer -->|Uses UI| Client

    API_Client -->|REST JSON| Server_Entry
    Gemini_Service <-->|WebSocket Stream — Audio & Text| Google_AI

    Auth_Route -->|Read/Write| Mongo_Users
    Listing_Route -->|Read/Write| Mongo_Listings
    Message_Route -->|Read/Write| Mongo_Messages
    Listing_Route -->|Image Upload| Cloudinary_CDN

    class Client client;
    class Backend server;
    class Database db;
    class External external;
    class Farmer,Buyer actor;
```

---

## 📁 Project Structure

```
XIBIT-2k26/
├── frontend/                   # React + TypeScript + Vite
│   ├── src/
│   │   ├── App.tsx             # Main controller — routing & state
│   │   ├── api.ts              # Centralized backend API calls
│   │   ├── types.ts            # TypeScript interfaces
│   │   ├── constants.ts        # Translations, mock data, configs
│   │   ├── index.css           # Global styles & design system
│   │   ├── components/
│   │   │   ├── LanguageSelector.tsx
│   │   │   ├── LanguageDropdown.tsx
│   │   │   ├── LiveAssistant.tsx    # Gemini voice UI
│   │   │   ├── ThemeToggle.tsx      # Dark mode toggle
│   │   │   └── NameCollectionModal.tsx
│   │   ├── pages/
│   │   │   ├── FarmerDashboard.tsx   # Full farmer experience
│   │   │   └── BuyerDashboard.tsx    # Full buyer experience
│   │   ├── services/
│   │   │   └── geminiService.ts     # Google GenAI integration
│   │   ├── context/                 # React context providers
│   │   └── utils/                   # Utility functions
│   ├── index.html
│   ├── vite.config.ts
│   └── tsconfig.json
│
├── backend/                    # Node.js + Express
│   ├── src/
│   │   ├── index.js            # Server entry — middleware & routes
│   │   ├── config/             # Database & service configs
│   │   ├── models/
│   │   │   ├── User.js
│   │   │   ├── Listing.js
│   │   │   └── Message.js
│   │   ├── routes/
│   │   │   ├── userRoutes.js
│   │   │   ├── listingRoutes.js
│   │   │   └── messageRoutes.js
│   │   ├── middlewares/        # Auth, rate-limit, sanitization
│   │   └── utils/              # Helper functions
│   └── package.json
│
├── DEPLOYMENT.md               # Deployment guide (Vercel + Render)
└── README.md                   # ← You are here
```

---

## ⚡ Getting Started

### Prerequisites

| Tool | Version |
|:-----|:--------|
| **Node.js** | v18+ recommended |
| **MongoDB** | Local or [Atlas](https://www.mongodb.com/atlas) |
| **Gemini API Key** | [Get one here](https://aistudio.google.com/apikey) |

### 1. Clone the Repository

```bash
git clone https://github.com/ANTHELIS/XIBIT-2k26.git
cd XIBIT-2k26
```

### 2. Backend Setup

```bash
cd backend
npm install
```

Create a `backend/.env` file:
```env
PORT=5000
MONGO_URI=your_mongodb_connection_string

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

### 3. Frontend Setup

```bash
cd frontend
npm install
```

Create a `frontend/.env` file:
```env
GEMINI_API_KEY=your_gemini_api_key_here
```

### 4. Run the Application

Open **two terminals**:

```bash
# Terminal 1 — Backend
cd backend
npm run dev          # → http://localhost:5000
```

```bash
# Terminal 2 — Frontend
cd frontend
npm run dev          # → http://localhost:5173
```

> **🎉 That's it!** Open `http://localhost:5173` in your browser and start speaking!

---

## 🌍 Deployment

The app is designed for seamless cloud deployment:

| Service | Platform | Root Directory |
|:--------|:---------|:---------------|
| **Backend** | [Render](https://render.com) | `backend/` |
| **Frontend** | [Vercel](https://vercel.com) | `frontend/` |

> See the full deployment guide in [`DEPLOYMENT.md`](./DEPLOYMENT.md).

---

## 🔌 API Reference

### User Routes — `/api/users`
| Method | Endpoint | Description |
|:-------|:---------|:------------|
| `POST` | `/api/users/login` | Login or auto-register a user |
| `PUT` | `/api/users/:id` | Update user profile |

### Listing Routes — `/api/listings`
| Method | Endpoint | Description |
|:-------|:---------|:------------|
| `GET` | `/api/listings` | Fetch all crop listings |
| `POST` | `/api/listings` | Create a new listing |
| `PUT` | `/api/listings/:id` | Update an existing listing |
| `DELETE` | `/api/listings/:id` | Delete a listing |

### Message Routes — `/api/messages`
| Method | Endpoint | Description |
|:-------|:---------|:------------|
| `GET` | `/api/messages/:userId` | Get messages for a user |
| `POST` | `/api/messages` | Send a new message |

---

## 🤝 Contributing

We welcome contributions! Here's how to get started:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feat/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feat/amazing-feature`)
5. **Open** a Pull Request

---

## 👥 Team

<table>
<tr>
  <td align="center">
    <a href="https://github.com/ANTHELIS">
      <img src="https://github.com/ANTHELIS.png" width="80px;" alt="ANTHELIS" style="border-radius:50%"/>
      <br/>
      <sub><b>@ANTHELIS</b></sub>
    </a>
    <br/>
    <sub>Full-Stack • AI Integration • Architecture</sub>
  </td>
  <td align="center">
    <a href="https://github.com/urmipaul007">
      <img src="https://github.com/urmipaul007.png" width="80px;" alt="urmipaul007" style="border-radius:50%"/>
      <br/>
      <sub><b>@urmipaul007</b></sub>
    </a>
    <br/>
    <sub>Frontend Enhancements • UI Polish</sub>
  </td>
  <td align="center">
    <a href="https://github.com/pritamroman07-droid">
      <img src="https://github.com/pritamroman07-droid.png" width="80px;" alt="pritamroman07-droid" style="border-radius:50%"/>
      <br/>
      <sub><b>@pritamroman07-droid</b></sub>
    </a>
    <br/>
    <sub>Contributor</sub>
  </td>
  <td align="center">
    <a href="https://github.com/bidisha861-dev">
      <img src="https://github.com/bidisha861-dev.png" width="80px;" alt="bidisha861-dev" style="border-radius:50%"/>
      <br/>
      <sub><b>@bidisha861-dev</b></sub>
    </a>
    <br/>
    <sub>Contributor</sub>
  </td>
</tr>
</table>

---

## 📜 License

This project is licensed under the **ISC License**.

---

<p align="center">
  <sub>Built with ❤️ for Indian farmers and buyers • Powered by Google Gemini AI</sub>
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Made_in-India_🇮🇳-059669?style=flat-square" alt="Made in India"/>
</p>
