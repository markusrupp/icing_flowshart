```mermaid
flowchart LR
    subgraph DataSources
        SCADA[SCADA loss]
        MEPS[MEPS weather data source]
    end

    SCADA -->|SCADA loss| DSF[Data storage file]
    MEPS --> DP((Data Preprocessing))
    DP --> DSF
    MEPS --> IM[Icing model]
    IM -->|Icing Intensity, Blade Ice Mass| DSF
```



```mermaid
flowchart LR
    subgraph Stored Files
        CSV[Data File .csv]
        MS[Model Specification .json]
        MF[Trained Models .json or .pkl]
    end

    
```
