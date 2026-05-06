# Transcript Intelligence Take-Home Assignment Solution

## Overview

This repository contains the solution for the Transcript Intelligence take-home assignment. The project analyzes approximately 100 sample call transcripts from a B2B SaaS company to build a categorization pipeline, perform sentiment analysis, and derive actionable insights for stakeholders.

## Dataset

The dataset consists of call transcripts stored in individual folders, each containing:
- `summary.json`: Pre-generated topics and overall sentiment (assumed from LLM processing)
- `transcript.json`: Sentence-level data with sentiment types
- `meeting-info.json`: Metadata like title, start time
- `speaker-meta.json`: Speaker names and roles

Transcripts are categorized into three types: customer support calls, external calls (account management), and internal calls.

## Approach

- **Data Processing**: Load and parse JSON files into a structured DataFrame.
- **Categorization**: 
  - Call types: Rule-based classification using title keywords.
  - Topics: Aggregated from `summary.json`.
- **Sentiment Analysis**: Analyze overall scores and sentence-level sentiments across call types and over time.
- **Insights**: 
  - Customer churn risk scoring.
  - Agent coaching metrics based on sentiment deltas.

## Requirements

- Python 3.12+
- Dependencies listed in `../requirements.txt`

## Installation

1. Clone or navigate to the repository.
2. Activate the virtual environment: `source ../langgraphenv/bin/activate`
3. Install dependencies: `pip install -r ../requirements.txt`
4. Ensure the `dataset/` folder is present with transcript data.

## Usage

### Running the Notebook

1. Open `Solution_details.ipynb` in Jupyter or VS Code.
2. Configure the Python kernel if needed.
3. Run cells sequentially to process data and generate insights.

### Key Outputs

- Call type distributions
- Topic frequency analysis
- Sentiment trends and visualizations
- Customer churn risk scores
- Agent performance metrics

### Slide Deck

- `Transcript_Intelligence_Solution.pptx`: Presentation slides for the 30-minute demo.

### Video Demo

- Record a walkthrough of the notebook execution and key findings (5-10 minutes).

## Project Structure

```
interview-assignment/
├── Solution_details.ipynb          # Main analysis notebook
├── Transcript_Intelligence_Solution.pptx  # Slide deck
├── create_slides.py               # Script to generate PPTX
├── dataset/                       # Transcript data (folders with JSON files)
│   ├── [meeting_id]/
│   │   ├── summary.json
│   │   ├── transcript.json
│   │   ├── meeting-info.json
│   │   └── speaker-meta.json
│   └── ...
└── README.md                      # This file
```

## Results Summary

- **Categorization**: Identified 63 internal, 27 support, 10 external calls with key topics like billing and support issues.
- **Sentiment**: Support calls show lowest sentiment; trends indicate areas for improvement.
- **Insights**: Churn risk model highlights at-risk customers; agent deltas measure coaching opportunities.

## Technologies Used

- Python (Pandas, Matplotlib, Seaborn)
- Jupyter Notebook
- python-pptx for slide generation

## Author

Sharan Badni

## Notes

- Topics and sentiments in `summary.json` are assumed to be LLM-generated.
- For production, integrate with real-time processing and dashboards.
- Video demo should demonstrate the pipeline in action.
