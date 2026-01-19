%%{init: {'theme': 'base', 'themeVariables': { 'primaryColor': '#5f7c8a', 'primaryTextColor': '#ffffff', 'primaryBorderColor': '#3a4d57', 'lineColor': '#333333', 'secondaryColor': '#718792', 'tertiaryColor': '#e8e8e8', 'fontFamily': 'Arial, sans-serif'}}}%%

flowchart TB
    %% Resume Enhancement Pipeline
    subgraph Resume["<b>Resume Enhancement Pipeline</b>"]
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

    %% Job Alert Automation
    subgraph Jobs["<b>Job Alert Automation</b>"]
        direction TB
        J1["User Alert<br/>Preferences"]
        J2["BullMQ Queue"]
        J3["RapidAPI Job Fetch"]
        J4["Deduplication Check"]
        J5["Email Notification"]
        J6["Real-time Socket<br/>Alert"]
        
        J1 --> J2
        J2 --> J3
        J3 --> J4
        J4 --> J5
        J5 --> J6
    end

    %% Real-Time Community Flow
    subgraph Community["<b>Real-Time Community Flow</b>"]
        direction TB
        C1["User Login"]
        C2["Socket Authentication<br/>(JWT)"]
        C3["Join Channel /<br/>DM Room"]
        C4["Message Broadcast"]
        C5["Presence Update<br/>(Online / Offline)"]
        
        C1 --> C2
        C2 --> C3
        C3 --> C4
        C4 --> C5
    end

    %% Security Flow
    subgraph Security["<b>Security Flow</b>"]
        direction TB
        S1["Firebase Auth"]
        S2["JWT Verification"]
        S3["Protected API<br/>Routes"]
        S4["Rate Limiting +<br/>Helmet"]
        S5["Secure Data Access"]
        
        S1 --> S2
        S2 --> S3
        S3 --> S4
        S4 --> S5
    end

    %% Interview Preparation Flow
    subgraph Interview["<b>Interview Prep Flow</b>"]
        direction TB
        I1["Select Role +<br/>Industry"]
        I2["Groq AI Question<br/>Generation"]
        I3["Voice Recording +<br/>Transcription"]
        I4["Answer Analysis"]
        I5["Performance<br/>Feedback"]
        
        I1 --> I2
        I2 --> I3
        I3 --> I4
        I4 --> I5
    end

    %% Fellowship Flow
    subgraph Fellowship["<b>Fellowship Flow</b>"]
        direction TB
        F1["Email Verification<br/>(Academic)"]
        F2["Corporate Posts<br/>Challenge"]
        F3["Student Submits<br/>Proposal"]
        F4["Razorpay Escrow<br/>Payment"]
        F5["Approval +<br/>Notification"]
        
        F1 --> F2
        F2 --> F3
        F3 --> F4
        F4 --> F5
    end

    %% Styling
    classDef pipeline fill:#5f7c8a,stroke:#3a4d57,stroke-width:2px,color:#fff,font-weight:bold
    classDef step fill:#718792,stroke:#4a5a63,stroke-width:1px,color:#fff

    class R1,R2,R3,R4,R5,R6,R7 step
    class J1,J2,J3,J4,J5,J6 step
    class C1,C2,C3,C4,C5 step
    class S1,S2,S3,S4,S5 step
    class I1,I2,I3,I4,I5 step
    class F1,F2,F3,F4,F5 step
