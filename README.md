%%{init: {'theme': 'base', 'themeVariables': { 'primaryColor': '#5f7c8a', 'primaryTextColor': '#ffffff', 'primaryBorderColor': '#3a4d57', 'lineColor': '#333333', 'secondaryColor': '#718792', 'tertiaryColor': '#e8e8e8', 'fontFamily': 'Arial, sans-serif'}}}%%

flowchart LR
    subgraph Resume["Resume Enhancement Pipeline"]
        direction TB
        R1["Upload PDF"]
        R2["Text Extraction<br/>(PDF Parse)"]
        R3["Prompt Engineering<br/>(Role + Keywords)"]
        R4["Google Gemini 2.5<br/>Flash"]
        R5["ATS Score +<br/>Suggestions"]
        R6["Format Resume"]
        R7["Store in MongoDB →<br/>Download as PDF"]
        
        R1 --> R2
        R2 --> R3
        R3 --> R4
        R4 --> R5
        R5 --> R6
        R6 --> R7
    end

    subgraph Jobs["Job Alert Automation"]
        direction TB
        J1["User Alert<br/>Preferences"]
        J2["BullMQ Queue"]
        J3["RapidAPI<br/>Job Fetch"]
        J4["Deduplication<br/>Check"]
        J5["Email<br/>Notification"]
        J6["Real-time<br/>Socket Alert"]
        
        J1 --> J2
        J2 --> J3
        J3 --> J4
        J4 --> J5
        J5 --> J6
    end

    subgraph Community["Real-Time Community Flow"]
        direction TB
        C1["User Login"]
        C2["Socket Authentication<br/>(JWT)"]
        C3["Join Channel /<br/>DM Room"]
        C4["Message<br/>Broadcast"]
        C5["Presence Update<br/>(Online / Offline)"]
        
        C1 --> C2
        C2 --> C3
        C3 --> C4
        C4 --> C5
    end

    subgraph Security["Security Flow"]
        direction TB
        S1["Firebase Auth"]
        S2["JWT Verification"]
        S3["Protected<br/>API Routes"]
        S4["Rate Limiting +<br/>Helmet"]
        S5["Secure Data<br/>Access"]
        
        S1 --> S2
        S2 --> S3
        S3 --> S4
        S4 --> S5
    end

    classDef box fill:#5f7c8a,stroke:#3a4d57,stroke-width:1px,color:#fff
    
    class R1,R2,R3,R4,R5,R6,R7 box
    class J1,J2,J3,J4,J5,J6 box
    class C1,C2,C3,C4,C5 box
    class S1,S2,S3,S4,S5 box
