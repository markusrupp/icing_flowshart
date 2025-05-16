# Icing Forecasting System

This repository contains flowcharts describing the data flow and model pipeline for icing forecasting.

---

## Flowchart 1: Data Flow

```mermaid
flowchart LR
    subgraph DataSources
        SCADA[SCADA data source]
        MEPS[MEPS weather data source]
    end

    SCADA -->|Icing loss| DSF[Data storage file]
    MEPS --> DSF
    MEPS --> IM[Icing model]
    IM -->|Icing Forecast| DSF
```

---

## Flowchart 2: Model Training Pipeline

```mermaid
flowchart TD
    RAW[Raw Weather Data] --> PREP[Preprocessing]
    PREP --> TRAIN[Train Icing Model]
    TRAIN --> EVAL[Evaluate Model]
    EVAL --> DEPLOY[Deploy Model]
```

