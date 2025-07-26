```mermaid
flowchart TD
    %% Mobile App Flow
    A((Mobile App)) --> A1[Real Events]
    A1 --> A2[Event Mapper]
    A2 --> A3[Data Transfer Objects]
    A3 --> B{ReST API}
    
    %% ReST API Complex Schema Processing
    B --> B1[DTO Validation]
    B1 --> B2[Schema Transformation]
    B2 --> B3[Business Logic Layer]
    B3 --> B4[Application Models]
    B4 --> C[("Redis - Real-time Storage")]
    
    %% Separate Pipeline Flow
    C --> P1[Data Pipeline Trigger]
    P1 --> P2[Stream Processor]
    P2 --> P3[Data Aggregation]
    P3 --> P4[Format Converter]
    P4 --> E[("S3 - CSV Files")]
    E --> F[/"Athena - Query Engine"/]
    
    %% Styling
    style A fill:#d4eaff,stroke:#007acc
    style B fill:#c1e1c1,stroke:#2e8b57
    style C fill:#fdfd96,stroke:#f1c232
    style E fill:#e0e0e0,stroke:#7f8c8d
    style F fill:#dad0ff,stroke:#8e44ad
    
    %% Transformation stages styling
    style A1 fill:#ffe6e6,stroke:#ff4d4d
    style A2 fill:#e6f3ff,stroke:#0080ff
    style A3 fill:#e6ffe6,stroke:#00b300
    style B1 fill:#fff0e6,stroke:#ff8000
    style B2 fill:#f0e6ff,stroke:#8000ff
    style B3 fill:#ffe6f0,stroke:#ff0080
    style B4 fill:#e6fff0,stroke:#00ff80
    
    %% Pipeline styling
    style P1 fill:#ffeecc,stroke:#cc8800
    style P2 fill:#ccffee,stroke:#008855
    style P3 fill:#eeccff,stroke:#5500cc
    style P4 fill:#ffccee,stroke:#cc0055

    click A href "https://developer.apple.com/design/human-interface-guidelines/workouts" _blank
    click E href "https://us-west-1.console.aws.amazon.com/s3/buckets/csai381-data" _blank
```
