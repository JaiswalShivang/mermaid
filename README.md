# AI Resume Builder & Career Platform - Complete Workflow

```mermaid
flowchart TD
    %% =======================
    %% Main Sections Overview
    %% =======================
    section1[Resume Enhancement]
    section2[Job Alerts]
    section3[Application Tracker]
    section4[Community Platform]
    section5[Notifications]
    section6[Exports & Backup]

    %% =======================
    %% Resume Enhancement Flow
    %% =======================
    subgraph Resume_Enhancement["Resume Upload and AI Enhancement"]
        RE1["Upload PDF Resume"] --> RE2["Text Extraction using pdf-parse"]
        RE2 --> RE3["Prompt Engineering: Role and Keywords"]
        RE3 --> RE4["Google Gemini 2_5 AI"]
        RE4 --> RE5["ATS Score and Improvement Suggestions"]
        RE5 --> RE6["Professional Summary Generated"]
        RE6 --> RE7["Harvard Template Resume Formatting"]
        RE7 --> RE8["Store Enhanced Resume in MongoDB"]
        RE8 --> RE9["Download as PDF"]
    end

    %% =======================
    %% Job Alerts Flow
    %% =======================
    subgraph Job_Alerts["Job Search and Alerts"]
        JA1["Set Job Alerts: Keywords, Location, Salary, Type"] --> JA2["BullMQ Queue triggers Job Fetch via RapidAPI"]
        JA2 --> JA3["Deduplication and Filtering"]
        JA3 --> JA4["Email Notification and Real-Time Socket Notification"]
        JA4 --> JA5["Job Alert Dashboard: Quick Apply, Save, Track"]
    end

    %% =======================
    %% Application Tracker Flow
    %% =======================
    subgraph Tracker["Job Application Tracker"]
        T1["Track Application Status: Saved - Applied - Interviewing - Offered - Rejected"] --> T2["Add Notes and Comments"]
        T2 --> T3["Kanban-Style Dashboard: Drag and Drop Updates"]
        T3 --> T4["Statistics Overview: Total Jobs, Status Distribution"]
    end

    %% =======================
    %% Community Platform Flow
    %% =======================
    subgraph Community["Community Platform"]
        C1["Join Channels and Topic-Based Discussions"] --> C2["Post, Comment, React"]
        C2 --> C3["Direct Messaging: Private Rooms"]
        C3 --> C4["Real-Time Presence Indicators: Online/Offline"]
        C4 --> C5["Connect with Fellow Job Seekers"]
    end

    %% =======================
    %% Notifications Flow
    %% =======================
    subgraph Notifications["Notifications and Real-Time Updates"]
        N1["Socket.IO Connection Authenticated"] --> N2["Receive Events: Job Alerts, Messages, Community Updates"]
        N2 --> N3["Frontend Toast Notifications and Email via Nodemailer"]
    end

    %% =======================
    %% Exports & Backup Flow
    %% =======================
    subgraph Exports["Download and Export"]
        E1["Enhanced Resume PDF Export"] --> E2["Job History and Alerts Export (CSV or JSON)"]
        E2 --> E3["Offline Access and Backup"]
    end

    %% =======================
    %% Connect Main Workflow
    %% =======================
    RE9 --> JA1
    JA5 --> T1
    T4 --> C1
    C5 --> N1
    N3 --> E1
