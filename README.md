# Icing Forecasting System

This repository contains flowcharts describing the data flow and model pipeline for icing forecasting.

---

## Flowchart 1: Data Flow

# Icing Forecasting System

This repository contains flowcharts describing the data flow and model pipeline for icing forecasting.

---

## Flowchart 1: Data Flow

```mermaid
flowchart LR
    subgraph DataSources
        SCADA(SCADA data source)
        MEPS(MEPS weather data source)
    end

    SCADA -->|SCADA loss| DSF(Data storage file)
    MEPS --> DSF
    MEPS --> IM(Icing model)
    IM -->|Icing Forecast| DSF
```

---

## Flowchart 2: Model Training Pipeline

```mermaid
flowchart TD
    DSF[Data storage file] -->|2022-2023, 2024-2025| TrD[Training data]
    DSF -->|2023-2024| TeD[Test data]

    TrD --> FT[Finetuning] --> OM[Optimised model]
    OM --> TR[Training]
    TrD --> TR
    TR --> TM[Trained Model]

    TM --> MoPr[Model Predictions]
    TeD -->|Weather, Icing data and SCADA loss if available| MoPr
    MoPr --> EvR[Evaluation Results]
    TeD -->|SCADA loss| EvR



