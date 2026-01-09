# AI Resume Builder Workflow

```mermaid
flowchart TD
    %% User Registration & Login
    A[User Registration or Login] --> B[Firebase Auth Email or Google OAuth]
    B --> C[JWT Token Issued to Access Dashboard]

    %% Resume Upload & Management
    C --> D[Upload PDF Resume]
    D --> E[Text Extraction using pdf-parse]
    E --> F[Store Original Resume in MongoDB]
    F --> G[Multiple Versions Supported - View or Delete or Download]

    %% AI Resume Enhancement
    G --> H[Select Resume to Enhance]
    H --> I[Prompt Engineering with Role and Keywords]
    I --> J[Google Gemini 2.5 AI]
    J --> K[ATS Score and Improvement Suggestions]
    K --> L[Professional Summary Generated]
    L --> M[Harvard Template Resume Formatting]
    M --> N[Store Enhanced Resume in MongoDB and Download as PDF]

    %% Job Search and Alerts
    N --> O[Set Job Alerts - Keywords, Location, Salary, Type]
    O --> P[BullMQ Queue Triggers Job Fetch via RapidAPI]
    P --> Q[Deduplication and Filtering]
    Q --> R[Email Notification and Real-Time Socket Notification]
    R --> S[Job Alert Dashboard - Quick Apply or Save or Track]

    %% Job Application Tracker
    S --> T[Track Application Status - Saved to Applied to Interviewing to Offered to Rejected]
    T --> U[Add Notes and Comments]
    U --> V[Kanban-Style Dashboard - Drag and Drop Updates]
    V --> W[Statistics Overview - Total Jobs and Status Distribution]

    %% Community Platform
    W --> X[Join Channels or Topic-Based Discussions]
    X --> Y[Post, Comment, React]
    Y --> Z[Direct Messaging - Private Rooms]
    Z --> AA[Real-Time Presence Indicators Online or Offline]
    AA --> AB[Connect with Fellow Job Seekers]

    %% Notifications and Real-Time Updates
    AB --> AC[Socket.IO Connection Authenticated]
    AC --> AD[Receive Events - Job Alerts, Messages, Community Updates]
    AD --> AE[Frontend Toast Notifications and Email via Nodemailer]

    %% Download and Export
    AE --> AF[Enhanced Resume PDF Export]
    AF --> AG[Job History or Alerts Export as CSV or JSON]
    AG --> AH[Offline Access and Backup]
