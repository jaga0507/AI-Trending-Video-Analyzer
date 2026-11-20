Week 3 Data Inventory
1. Selected Data Source
•	Dataset: BestiVictoryLab (VADB)
•	Source file: train.csv
•	Local source: data/raw/vadb_train.csv
•	Data type: Annotated tabular video metadata
•	Records: 10,488
•	Original columns: 17
The selected VADB dataset contains video level annotations including composition, shot size, lighting, visual tone, colour, depth of field, expression, movement, costume, makeup, score and label.
2. Initial Inspection
The original CSV contained 17 columns. Four unnamed columns were identified during inspection.
The dataset contained:
•	10,488 records
•	No exact duplicate rows
•	Missing values in expression, movement, costume and makeup
•	Three empty unnamed columns
•	One additional unnamed: 16 value containing extra comma separated numeric data
3. Preparation
The selected preparation retained the 13 expected VADB columns and excluded the four unnamed columns.
Preparation decisions:
•	Exact duplicate removal: Not applied
•	Text trimming: Not applied
•	Missing-value imputation: Not applied
•	Records removed: 0
•	Records preserved: 10,488
•	Prepared columns: 13
The original missing values were preserved because there was no sufficient justification for imputing them.
4. Output
The Part B prepared dataset is stored at:
data/processed/prepared_table.csv
The integrated Part C pipeline output is stored at:
data/pipeline_v1/tabular/prepared_table.csv
5. Processing Scope and Limitation
This Week 3 pipeline processes VADB annotated metadata in CSV format.
It does not process the original video files. Video frame extraction, audio extraction, speech transcription, OCR and Gemini based multimodal analysis are outside the scope of this tabular data preparation stage.
VADB is therefore used as a supporting dataset for data preparation, exploration and potential future evaluation rather than as a replacement for the planned AI video-analysis pipeline.
6. Provenance
Source to output lineage and processing information were recorded during the pipeline.
The Part B lineage manifest is:
data/week3_manifest.json
The Part C pipeline manifest is:
data/pipeline_v1/tabular/pipeline_manifest.json

