Week 3 Pipeline Decisions
1. Requirements Traceability
The Week 3 pipeline supports the data preparation and evaluation needs of the AI Trending Video Analyzer.
Relevant Topic 2 requirements include:
•	O1 / FR2: Analyse audio and visual content.
•	FR3 / RAI1: Provide timestamps and evidence.
•	O3 / NFR2: Measure detection accuracy.
The current Week 3 implementation is a structured tabular data preparation pipeline. It does not implement the main multimodal video analysis components such as video preprocessing, Gemini analysis, timestamped evidence generation or dashboard output.
2. Selected Data Source
The selected source is the BestiVictoryLab (VADB) dataset.
•	Source file: train.csv
•	Local source: data/raw/vadb_train.csv
•	Records: 10,488
•	Original columns: 17
The dataset contains annotated visual video metadata such as composition, shot size, lighting, visual tone, colour, depth of field, expression, movement, costume and makeup.
VADB is treated as a supporting offline dataset rather than a replacement for the planned Gemini-based video-analysis system.
3. Part B Preparation Comparison
Two preparation approaches were compared.
Approach	Records	Columns	Decision
Approach 1: Keep all columns	10,488	17	Not selected
Approach 2: Keep expected columns	10,488	13	Selected

Approach 2 was selected because it removes unnamed columns while preserving all 10,488 records and the original missing values. No exact duplicate rows were found. Missing values were preserved rather than imputed.
4. Selected Preparation Configuration
The selected configuration:
•	Retain the 13 expected VADB columns.
•	Exclude the four unnamed columns.
•	Do not remove exact duplicates.
•	Do not trim text.
•	Do not impute missing values.
•	Preserve all 10,488 records.
5. Pipeline Stage Contracts
Stage	Contract	Evidence	Failure Response
Ingest	Source CSV can be read successfully	Source file and dataset dimensions	Stop and report input error
Inspect	Dataset structure and quality are checked	Shape, columns, missing values and duplicate checks	Review source before preparation
Prepare / Transform	Expected columns are retained without unjustified changes	Prepared CSV and configuration	Stop if required columns are missing
Validate Output	Prepared output exists and has the expected structure	Output shape, columns and non-empty check	Stop and report validation failure
Record Lineage	Source, output and processing details are recorded	Lineage and pipeline manifests	Report provenance failure
6. ETL / ELT Decision
ETL was selected.
The source CSV is first extracted and inspected, then transformed by retaining the required columns, and finally saved as the prepared output.
7. Batch / Streaming Decision
Batch processing was selected because VADB is a static dataset rather than a continuous data stream.
The complete CSV can be processed as a single dataset, making batch processing simpler and appropriate for this stage.
8. Outputs and Provenance
Part B
Prepared output:
data/processed/prepared_table.csv
Lineage manifest:
data/week3_manifest.json
Part C
Prepared output:
data/pipeline_v1/tabular/prepared_table.csv
Pipeline run manifest:
data/pipeline_v1/tabular/pipeline_manifest.json
The repeatability and provenance verification completed successfully. Source fingerprints, prepared outputs and source to output mappings matched during the repeatability check.
9. Relationship to the V1 Architecture
The main V1 architecture remains centred on:
User → Upload Validation → Video Preprocessing → Multimodal Analysis → Insight Generation → Output Validation → Dashboard
The VADB pipeline is an additional offline supporting component:
VADB → Ingest → Inspect → Prepare → Validate → Record Lineage
This supporting pipeline can provide prepared reference data for future exploration and evaluation. 
10. Accepted Limitations
The selected VADB source contains annotated metadata rather than the original video files. 
Therefore, this Week 3 pipeline does not perform:
•	Video frame extraction
•	Audio extraction
•	Speech transcription
•	OCR
•	Gemini-based multimodal analysis
•	Timestamped marketing evidence generation
11. Provenance and Access Caveat
The VADB dataset is used as the selected source for this pipeline. Any public redistribution of the original or prepared dataset must be in accordance with the dataset's applicable licence and access conditions. Restricted source data must not be committed to the public GitHub repository without permission.
12. Conclusion
The Week 3 pipeline provides a repeatable process for VADB metadata preparation. It keeps the source records, strips out the unwanted columns, validates the output and records the provenance via lineage and pipeline manifests.
