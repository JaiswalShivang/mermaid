%%{init: {'theme': 'base', 'themeVariables': { 'primaryColor': '#5f7c8a', 'primaryTextColor': '#ffffff', 'primaryBorderColor': '#3a4d57', 'lineColor': '#333333', 'fontFamily': 'Arial, sans-serif'}}}%%

flowchart TB
    subgraph Resume["Resume Enhancement Pipeline"]
        direction TB
        R1["Upload PDF"]
        R2["Text Extraction (PDF Parse)"]
        R3["Prompt Engineering (Role + Keywords)"]
        R4["Google Gemini 2.5 flash"]
        R5["ATS Score + Suggestions"]
        R6["Format Resume"]
        R7["Store in MongoDB → Download as PDF"]
        
        R1 --> R2 --> R3 --> R4 --> R5 --> R6 --> R7
    end

    subgraph Jobs["Job Alert Automation"]
        direction TB
        J1["User Alert Preferences"]
        J2["BullMQ Queue"]
        J3["RapidAPI Job Fetch"]
        J4["Deduplication Check"]
        J5["Email Notification"]
        J6["Real-time Socket Alert"]
        
        J1 --> J2 --> J3 --> J4 --> J5 --> J6
    end

    subgraph Community["Real-Time Community Flow"]
        direction TB
        C1["User Login"]
        C2["Socket Authentication (JWT)"]
        C3["Join Channel / DM Room"]
        C4["Message Broadcast"]
        C5["Presence Update (Online / Offline)"]
        
        C1 --> C2 --> C3 --> C4 --> C5
    end

    subgraph Security["Security Flow"]
        direction TB
        S1["Firebase Auth"]
        S2["JWT Verification"]
        S3["Protected API Routes"]
        S4["Rate Limiting + Helmet"]
        S5["Secure Data Access"]
        
        S1 --> S2 --> S3 --> S4 --> S5
    end

    %% Styling
    classDef box fill:#5f7c8a,stroke:#3a4d57,stroke-width:1px,color:#fff,rx:8,ry:8
    
    class R1,R2,R3,R4,R5,R6,R7 box
    class J1,J2,J3,J4,J5,J6 box
    class C1,C2,C3,C4,C5 box
    class S1,S2,S3,S4,S5 box
