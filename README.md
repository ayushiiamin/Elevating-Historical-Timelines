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

---

### 5. Entity-Based Timeline Construction

Extracted entities are grouped according to their associated year.

This creates structured relationships between:

```text
Year
 ├── People
 ├── Countries
 └── Event Sentences
```

For example:

```text
1940
 ├── Person: Winston Churchill
 ├── Country: United Kingdom
 └── Event: Winston Churchill became Prime Minister.
```

This structure enables chronological exploration of people, countries, and historical events.

---

### 6. Structured Data Generation

The extracted information is transformed into structured datasets using pandas.

Two primary representations are generated:

```text
Year | Person | Event Sentence
```

and

```text
Year | Country | Event Sentence
```

Duplicate entries are removed before exporting the processed data.

This creates cleaner datasets that can be used for further analysis, visualization, or timeline generation.

---

### 7. Event Summarization

Historical passages can contain significant amounts of contextual information, making them difficult to display directly in a concise timeline.

To address this, the project explores summarization techniques including:
- TextRank
- GPT-3.5

These techniques are used to condense larger event descriptions into shorter, more interpretable summaries.

The summarized output can be represented as:

```text
Original Historical Passage
        ↓
Event Extraction
        ↓
Summarization
        ↓
Concise Event Title + Summary
```

This makes the final timeline easier to read and analyze.

---

### 8. End-to-End NLP Pipeline

The complete processing workflow can be summarized as:

```text
Historical PDF Documents
        ↓
PDF Text Extraction
        ↓
Text Cleaning & Normalization
        ↓
Coreference Resolution
        ↓
Stop-word Removal
        ↓
Lemmatization
        ↓
Temporal Extraction
        ↓
Named Entity Recognition
   ├── People
   └── Countries / Locations
        ↓
Entity + Event Association
        ↓
Structured Data Generation
        ↓
Event Summarization
        ↓
Chronological Historical Timeline
```

The pipeline demonstrates how multiple NLP techniques can be combined to transform large collections of unstructured historical text into structured, timeline-ready information.

## Tech Stack

### Programming Language
- Python
### NLP & Machine Learning
- spaCy
- NLTK
- NeuralCoref
- TextRank
- GPT-3.5
### Data Processing
- pandas
- Regular Expressions
- PyPDF2
- PyMuPDF
### Development Environment
- Jupyter Notebook
- Google Colab

## Repository Structure

```text
Elevating-Historical-Timelines/
│
├── Data/
│   └── Project datasets and processed outputs
│
├── group_30.ipynb
│   └── Main experimentation and NLP pipeline notebook
│
├── group_30.py
│   └── Python implementation of the NLP workflow
│
└── README.md
    └── Project documentation
```

## Example Workflow

A simplified example of the pipeline looks like this:

### Raw Input
```text
In 1940, Winston Churchill became Prime Minister of the United Kingdom.
He played a major role in Britain's wartime leadership.
```
### Coreference Resolution
```text
In 1940, Winston Churchill became Prime Minister of the United Kingdom.
Winston Churchill played a major role in Britain's wartime leadership.
```
### Temporal Extraction
```text
Year: 1940
```
### Named Entity Recognition
```text
PERSON: Winston Churchill
GPE: United Kingdom
```
### Structured Output
```text
Year: 1940
Person: Winston Churchill
Country: United Kingdom
Event: Winston Churchill became Prime Minister and played a major role in Britain's wartime leadership.
```

## Results

The project demonstrates how a combination of NLP techniques can transform large-scale historical text into structured, timeline-ready information.

The resulting pipeline supports:
- historical event extraction
- chronological organization
- person and country identification
- entity relationship analysis
- timeline generation
- concise event summarization

This approach reduces the need for fully manual historical document analysis and provides a scalable framework for exploring large text collections.


## Contributers:
Developed as a team project at the University of Southern California.
- Ayushi Amin
- Tanisha Rathi
- Oishi Saha
- Chahita Verma
- Manorama Patil
