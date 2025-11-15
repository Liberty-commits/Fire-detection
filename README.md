# Fire-detection
System block diagram 
graph TD
    subgraph System Start
        A[Start System / Power On] --> B(Initialize Microcontroller & Sensors);
    end

    subgraph Step 1: Continuous Monitoring
        B --> C{Continuous Monitoring};
        C --> D[Poll Temperature Sensor];
        C --> E[Poll Flame Sensor];
        C --> F[Poll CO Sensor];
    end

    subgraph Step 2: Fire Detection Algorithm
        D & E & F --> G{Evaluate Sensor Data};
        G --> H{Fire Confirmed?<br>Two or More Positive Readings};
        H -- No --> C;
        H -- Yes --> I(Fire Confirmed);
    end

    subgraph Step 3 & 4: Alarm, Notification & Suppression
        I --> J[Activate Buzzer];
        I --> K[Update LCD Display: "FIRE DETECTED!"];
        I --> L[Signal Solenoid Valve to Open];
        L --> M[Release Extinguishing Agent];
    end

    subgraph Step 5: Emergency Communication Protocol
        L --> N[Trigger Emergency Communication];
        N --> O[Command GPS Module for Location];
        O --> P{GPS Location Received?};
        P -- No --> O;
        P -- Yes --> Q[Format SMS Message];
        Q --> R[Command GSM Module to Transmit SMS];
        R --> S[Send Distress Signal to Emergency Contact];
    end

    J & K & M & S --> T(System in Alert/Suppression Mode);
    T --> End(System Continues Monitoring);

%% Flowchart Styling
    style B fill:#f9f,stroke:#333,stroke-width:2px
    style C fill:#ccf,stroke:#333,stroke-width:2px
    style H fill:#ffdd57,stroke:#333,stroke-width:2px
    style I fill:#f88,stroke:#333,stroke-width:2px
    style J fill:#f88,stroke:#333,stroke-width:2px
    style K fill:#f88,stroke:#333,stroke-width:2px
    style L fill:#f88,stroke:#333,stroke-width:2px
    style M fill:#f88,stroke:#333,stroke-width:2px
    style N fill:#ffaa00,stroke:#333,stroke-width:2px
    style O fill:#ffaa00,stroke:#333,stroke-width:2px
    style P fill:#ffdd57,stroke:#333,stroke-width:2px
    style Q fill:#ffaa00,stroke:#333,stroke-width:2px'''
    style R fill:#ffaa00,stroke:#333,stroke-width:2px
    style S fill:#ffaa00,stroke:#333,stroke-width:2px
    style T fill:#f9f,stroke:#333,stroke-width:2px
