# Enhancing Event Timelines through the Integration of Coreference Resolution, Single Mention Detection and NER : A Case Study of World War II

An end-to-end Natural Language Processing pipeline for transforming large collections of unstructured historical text into structured, chronological event timelines.

This project analyzes World War II-related documents using **coreference resolution, Named Entity Recognition (NER), temporal extraction, text preprocessing, and summarization techniques** to identify important people, countries, dates, and events and organize them into interpretable historical timelines.

## Project Overview

Historical documents contain large volumes of unstructured text, making it difficult to systematically identify relationships between people, locations, dates, and events.

This project builds an NLP workflow that converts raw historical documents into structured timeline-ready data.

The pipeline:

- extracts and preprocesses text from historical PDF documents
- resolves entity references using **coreference resolution**
- identifies **people, countries, and temporal information** using NER
- organizes extracted information chronologically by year
- generates structured event-level representations
- creates concise historical event summaries for downstream timeline analysis

## Key Highlights

- Processed **6,488 historical articles/documents**
- Extracted **20,436+ paragraphs** related to historical years, people, countries, and events
- Applied **coreference resolution and Named Entity Recognition** to improve entity consistency and event extraction
- Used **TextRank and GPT-3.5** to generate and analyze **150 concise historical event titles and summaries**
- Built structured datasets linking **years, people, countries, and historical events**
- Developed the project collaboratively as part of a **5-person team**

## NLP Pipeline

```text
Historical PDF Documents
        ↓
Text Extraction
        ↓
Text Cleaning & Normalization
        ↓
Coreference Resolution
        ↓
Stop-word Removal & Lemmatization
        ↓
Temporal Extraction
        ↓
Named Entity Recognition
   ├── People
   └── Countries / Locations
        ↓
Structured Event Data
        ↓
Event Summarization
        ↓
Chronological Historical Timeline
```

### Contributers:
- Ayushi Amin <i>(ayushima@usc.edu)</i>
- Tanisha Rathi <i>(trathi@usc.edu)</i>
- Oishi Saha <i>(osaha@usc.edu)</i>
- Chahita Verma <i>(cverma@usc.edu)</i>
- Manorama Patil <i>(manorama@usc.edu)</i>
