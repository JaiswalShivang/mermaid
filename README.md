# AI Resume Builder & Career Platform - Workflow

```mermaid
flowchart TD
    %% User Upload & AI Enhancement
    subgraph Resume_Enhancement["Resume Upload and AI Enhancement"]
        A["Upload PDF Resume"] --> B["Text Extraction using pdf-parse"]
        B --> C["Prompt Engineering: Role + Keywords"]
        C --> D["Google Gemini 2_5 AI"]
        D --> E["ATS Score and Improvement Suggestions"]
        E --> F["Professional Summary Generated"]
        F --> G["Harvard Template Resume Formatting"]
        G --> H["Store Enhanced Resume in MongoDB"]
        H --> I["Download as PDF"]
    end

    %% Job Alerts
    subgraph Job_Alerts["Job Search and Alerts"]
        J["Set Job Alerts: Keywords, Location, Salary, Type"] --> K["BullMQ Queue triggers Job Fetch via RapidAPI"]
        K --> L["Deduplication and Filtering"]
        L --> M["Email Notification and Real-Time Socket Notification"]
        M --> N["Job Alert Dashboard: Quick Apply, Save, Track"]
    end

    %% Application Tracker
    subgraph Tracker["Job Application Tracker"]
        O["Track Application Status: Saved - Applied - Interviewing - Offered - Rejected"] --> P["Add Notes and Comments"]
        P --> Q["Kanban-Style Dashboard: Drag and Drop Updates"]
        Q --> R["Statistics Overview: Total Jobs, Status Distribution"]
    end

    %% Community Platform
    subgraph Community["Community Platform"]
        S["Join Channels and Topic-Based Discussions"] --> T["Post, Comment, React"]
        T --> U["Direct Messaging: Private Rooms"]
        U --> V["Real-Time Presence Indicators: Online/Offline"]
        V --> W["Connect with Fellow Job Seekers"]
    end

    %% Notifications
    subgraph Notifications["Notifications and Real-Time Updates"]
        X["Socket.IO Connection Authenticated"] --> Y["Receive Events: Job Alerts, Messages, Community Updates"]
        Y --> Z["Frontend Toast Notifications and Email via Nodemailer"]
    end

    %% Exports & Backup
    subgraph Exports["Download and Export"]
        AA["Enhanced Resume PDF Export"] --> AB["Job History and Alerts Export (CSV or JSON)"]
        AB --> AC["Offline Access and Backup"]
    end

    %% Connecting main workflow
    I --> J
    N --> O
    R --> S
    W --> X
    Z --> AA
