# AI Resume Builder & Career Platform - Architecture Flow

```mermaid
flowchart TD
    %% =======================
    %% Main Page (Top Level)
    %% =======================
    MainPage["🚀 AI Resume Builder & Career Platform"]
    
    %% =======================
    %% 5 Main Features (Level 1)
    %% =======================
    MainPage --> RE["📄 Resume Enhancement"]
    MainPage --> JA["🔔 Job Alerts"]
    MainPage --> AT["📊 Application Tracker"]
    MainPage --> CP["👥 Community Platform"]
    MainPage --> NT["📬 Notifications & Exports"]

    %% =======================
    %% Resume Enhancement Flow
    %% =======================
    RE --> RE1["📤 Upload PDF Resume"]
    RE1 --> RE2["📝 Text Extraction<br/>(pdf-parse)"]
    RE2 --> RE3["🎯 Prompt Engineering<br/>(Role + Keywords)"]
    RE3 --> RE4["🤖 Google Gemini 2.5 AI"]
    RE4 --> RE5["📈 ATS Score &<br/>Improvement Suggestions"]
    RE5 --> RE6["✨ Professional Summary<br/>Generated"]
    RE6 --> RE7["📋 Harvard Template<br/>Resume Formatting"]
    RE7 --> RE8["💾 Store in MongoDB"]
    RE8 --> RE9["⬇️ Download as PDF"]

    %% =======================
    %% Job Alerts Flow
    %% =======================
    JA --> JA1["⚙️ Set Alerts:<br/>Keywords, Location,<br/>Salary, Type"]
    JA1 --> JA2["📡 BullMQ Queue<br/>RapidAPI Fetch"]
    JA2 --> JA3["🔍 Deduplication<br/>& Filtering"]
    JA3 --> JA4["📧 Email + Socket<br/>Notifications"]
    JA4 --> JA5["📋 Dashboard:<br/>Apply, Save, Track"]

    %% =======================
    %% Application Tracker Flow
    %% =======================
    AT --> AT1["📌 Track Status:<br/>Saved → Applied →<br/>Interview → Offer"]
    AT1 --> AT2["📝 Add Notes<br/>& Comments"]
    AT2 --> AT3["📊 Kanban Board<br/>Drag & Drop"]
    AT3 --> AT4["📈 Statistics:<br/>Total Jobs, Status"]

    %% =======================
    %% Community Platform Flow
    %% =======================
    CP --> CP1["💬 Join Channels<br/>Topic Discussions"]
    CP1 --> CP2["📢 Post, Comment<br/>& React"]
    CP2 --> CP3["✉️ Direct Messaging<br/>Private Rooms"]
    CP3 --> CP4["🟢 Real-Time Presence<br/>Online/Offline"]
    CP4 --> CP5["🤝 Connect with<br/>Job Seekers"]

    %% =======================
    %% Notifications & Exports Flow
    %% =======================
    NT --> NT1["🔐 Socket.IO<br/>Authenticated"]
    NT1 --> NT2["📥 Receive Events:<br/>Alerts, Messages"]
    NT2 --> NT3["🔔 Toast + Email<br/>Notifications"]
    NT3 --> NT4["📄 PDF Export<br/>Enhanced Resume"]
    NT4 --> NT5["📊 CSV/JSON Export<br/>Job History"]
    NT5 --> NT6["💾 Offline Access<br/>& Backup"]

    %% =======================
    %% Styling
    %% =======================
    style MainPage fill:#4F46E5,stroke:#3730A3,color:#fff,stroke-width:3px
    style RE fill:#059669,stroke:#047857,color:#fff
    style JA fill:#D97706,stroke:#B45309,color:#fff
    style AT fill:#7C3AED,stroke:#6D28D9,color:#fff
    style CP fill:#DB2777,stroke:#BE185D,color:#fff
    style NT fill:#0891B2,stroke:#0E7490,color:#fff
```

---

## 📋 Feature Overview

### 1. 📄 Resume Enhancement
| Step | Description |
|------|-------------|
| Upload | Upload PDF resume to the platform |
| Extract | Text extraction using pdf-parse library |
| Engineer | Prompt engineering with role & keywords |
| AI Process | Google Gemini 2.5 AI enhancement |
| Score | ATS score & improvement suggestions |
| Summary | Professional summary generation |
| Format | Harvard template formatting |
| Store | Save enhanced resume to MongoDB |
| Download | Export as polished PDF |

### 2. 🔔 Job Alerts
| Step | Description |
|------|-------------|
| Configure | Set keywords, location, salary, job type |
| Fetch | BullMQ queue triggers RapidAPI job fetch |
| Filter | Deduplication & smart filtering |
| Notify | Email + real-time socket notifications |
| Manage | Dashboard for quick apply, save & track |

### 3. 📊 Application Tracker
| Step | Description |
|------|-------------|
| Track | Status flow: Saved → Applied → Interview → Offer/Reject |
| Notes | Add personal notes & comments |
| Kanban | Drag & drop status updates |
| Stats | Overview of total jobs & status distribution |

### 4. 👥 Community Platform
| Step | Description |
|------|-------------|
| Channels | Join topic-based discussion channels |
| Engage | Post, comment & react to content |
| DM | Private direct messaging rooms |
| Presence | Real-time online/offline indicators |
| Network | Connect with fellow job seekers |

### 5. 📬 Notifications & Exports
| Step | Description |
|------|-------------|
| Auth | Authenticated Socket.IO connection |
| Events | Receive job alerts, messages, updates |
| Alerts | Toast notifications + email via Nodemailer |
| PDF | Enhanced resume PDF export |
| Data | CSV/JSON export for job history |
| Backup | Offline access & data backup |

---

## 🛠️ Tech Stack

| Layer | Technologies |
|-------|--------------|
| **Frontend** | React, Vite, Tailwind CSS |
| **Backend** | Node.js, Express |
| **Database** | MongoDB, Firebase Firestore |
| **AI** | Google Gemini 2.5 |
| **Queue** | BullMQ, Redis |
| **Real-time** | Socket.IO |
| **Email** | Nodemailer |
| **APIs** | RapidAPI (Job Search) |
