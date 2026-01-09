# AI Resume Builder & Career Platform Workflow

```mermaid
flowchart TD
    %% User Registration & Login
    A[User Registration / Login] --> B[Firebase Auth (Email / Google OAuth)]
    B --> C[JWT Token Issued → Access Dashboard]

    %% Resume Upload & Management
    C --> D[Upload PDF Resume (Drag & Drop)]
    D --> E[Text Extraction (pdf-parse)]
    E --> F[Store Original Resume in MongoDB]
    F --> G[Multiple Versions Supported → View / Delete / Download]

    %% AI Resume Enhancement
    G --> H[Select Resume to Enhance]
    H --> I[Prompt Engineering (Role + Keywords + Preferences)]
    I --> J[Google Gemini 2.5 AI]
    J --> K[ATS Score + Improvement Suggestions]
    K --> L[Professional Summary Generated]
    L --> M[Harvard Template Resume Formatting]
    M --> N[Store Enhanced Resume in MongoDB → Download as PDF]

    %% Job Search & Alerts
    N --> O[Set Job Alerts (Keywords, Location, Salary, Type)]
    O --> P[BullMQ Queue Triggers Job Fetch via RapidAPI]
    P --> Q[Deduplication & Filtering]
    Q --> R[Email Notification + Real-Time Socket Notification]
    R --> S[Job Alert Dashboard → Quick Apply / Save / Track]

    %% Job Application Tracker
    S --> T[Track Application Status (Saved → Applied → Interviewing → Offered → Rejected)]
    T --> U[Add Notes & Comments]
    U --> V[Kanban-Style Dashboard → Drag & Drop Updates]
    V --> W[Statistics Overview (Total Jobs, Status Distribution)]

    %% Community Platform
    W --> X[Join Channels / Topic-Based Discussions]
    X --> Y[Post, Comment, React]
    Y --> Z[Direct Messaging (Private Rooms)]
    Z --> AA[Real-Time Presence Indicators (Online/Offline)]
    AA --> AB[Connect with Fellow Job Seekers]

    %% Notifications & Real-Time Updates
    AB --> AC[Socket.IO Connection Authenticated]
    AC --> AD[Receive Events: Job Alerts, Messages, Community Updates]
    AD --> AE[Frontend Toast Notifications + Email via Nodemailer]

    %% Download & Export
    AE --> AF[Enhanced Resume PDF Export]
    AF --> AG[Job History / Alerts Export (Optional CSV/JSON)]
    AG --> AH[Offline Access & Backup]
