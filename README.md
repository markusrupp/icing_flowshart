flowchart LR
    subgraph DataSources
        SCADA[SCADA data source]
        MEPS[MEPS weather data source]
    end

    SCADA -->|Icing loss| DSF[Data storage file]
    MEPS --> DSF
    MEPS --> IM[Icing model]
    IM -->|Icing Forecast| DSF

    style SCADA fill:#e0e0e0,stroke:#333,stroke-width:1px
    style MEPS fill:#e0e0e0,stroke:#333,stroke-width:1px
    style IM fill:#d0f0ff,stroke:#333,stroke-width:1px
    style DSF fill:#fff3cd,stroke:#333,stroke-width:1px
