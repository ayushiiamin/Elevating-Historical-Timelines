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

## Technical Approach

### 1. Document Processing

The project begins by converting historical PDF documents into machine-readable text.

The preprocessing pipeline includes:

- removing non-textual content such as images
- extracting raw text from PDF files
- expanding contractions
- removing unnecessary characters and formatting artifacts
- normalizing whitespace
- tokenizing text
- removing stop words
- lemmatizing words to their base forms

This preprocessing stage produces cleaner text for downstream NLP tasks and reduces noise in the source documents.

---

### 2. Coreference Resolution

Historical documents often refer to the same entity using pronouns or shortened references across multiple sentences.

For example:

```text
Winston Churchill addressed Parliament.
He later discussed Britain's wartime strategy.
```

Without coreference resolution, ```He``` may be treated as an unrelated entity.

The pipeline applies coreference resolution so downstream NLP stages can better associate references such as ```He``` with their corresponding entities such as ```Winston Churchill```.

This improves entity consistency across sentences and paragraphs.

---

### 3. Temporal Event Extraction

To construct historical timelines, the pipeline identifies sentences associated with specific years.

A regular-expression-based temporal extraction step detects four-digit year references and maps sentences to their corresponding years.

Example:

```text
1940 → Historical event
1942 → Historical event
1945 → Historical event
```

Each sentence containing a year is associated with that year and stored in a structured representation.

This allows historical events to be organized chronologically for timeline generation.

---

### 4. Named Entity Recognition

The project uses <b>spaCy Named Entity Recognition (NER)</b> to identify important entities within historical text.

The primary entity categories include:
- ```PERSON``` — historical figures and individuals
- ```GPE``` — countries, cities, and geopolitical locations

For example:

```text
In 1940, Winston Churchill became Prime Minister of the United Kingdom.
```

The pipeline can extract:

```text
PERSON: Winston Churchill
GPE: United Kingdom
YEAR: 1940
```

These entities are then linked with their corresponding event sentences.


#### Contributers:
- Ayushi Amin <i>(ayushima@usc.edu)</i>
- Tanisha Rathi <i>(trathi@usc.edu)</i>
- Oishi Saha <i>(osaha@usc.edu)</i>
- Chahita Verma <i>(cverma@usc.edu)</i>
- Manorama Patil <i>(manorama@usc.edu)</i>
