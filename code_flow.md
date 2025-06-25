## new one
```mermaid
flowchart TD

    %% === Files ===
    subgraph Files
        CSV[📄 CSV data file]
        MODEL_JSON[📄 Model spec JSON]
        TRAINED_MODELS[📄 Trained models (.pkl/.json)]
    end

    %% === CSV creation and update ===
    A[1️⃣ Create CSV data file] --> CSV
    CSV --> B[2️⃣ Update CSV data file]
    B --> CSV  %% loop: update leads to new version of the same file

    %% === Model specification setup ===
    C[3️⃣ Write model specs to JSON file] --> MODEL_JSON

    %% === Execution script ===
    D[4️⃣ Run tune_and_train.py]
    D --> E[5️⃣ Load CSV file for training]
    E --> CSV

    D --> F[6️⃣ Write or overwrite model spec JSON]
    F --> MODEL_JSON

    D --> G[7️⃣ Load model specs into regressors]
    G --> MODEL_JSON
```
    G --> H[8️⃣ Tune models and update JSON]
    H --> MODEL_JSON
```mermaid
