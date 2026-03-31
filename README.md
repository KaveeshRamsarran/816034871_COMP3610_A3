# COMP3610 Assignment 3: LLM-Powered Applications and Distributed Computing

## Overview

This project integrates distributed data processing with PySpark, a Retrieval-Augmented Generation (RAG) pipeline over NYC transportation policy documents, and a unified natural language application that routes queries across structured data and document sources.

## Structure

```
├── assignment3.ipynb       # Main notebook with all tasks
├── docs/                   # Transportation policy PDFs (downloaded at runtime)
├── requirements.txt        # Python dependencies
├── .gitignore              # Exclusions for generated files
└── README.md               # This file
```

## Setup

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
2. Set the `LLM_API_KEY` environment variable:
   ```bash
   export LLM_API_KEY="your-api-key-here"   # Linux/macOS
   $env:LLM_API_KEY = "your-api-key-here"    # PowerShell
   ```
3. Open `assignment3.ipynb` in VS Code and run all cells sequentially.

## Parts

- **Part 1**: Distributed Data Processing with Spark (setup, cleaning, SQL analytics, optimization)
- **Part 2**: RAG Pipeline (document ingestion, chunking/embedding, retrieval, evaluation)
- **Part 3**: Integrated Application (query router, data handler, end-to-end demo)
- **Part 4**: Documentation and code quality

## Data Sources

- NYC Yellow Taxi January 2024 trip data (Parquet)
- NYC Taxi Zone Lookup (CSV)
- NYC transportation policy PDFs (downloaded programmatically)

## AI Tools Used

GitHub Copilot was used in a supporting role during development. Below are selected examples:

- **Spark configuration**: Consulted Copilot for recommended SparkSession settings (AQE, memory allocation for local mode).
- **Data cleaning filters**: Used Copilot to draft PySpark filter conditions for removing records with negative fares and zero-distance trips.
- **ChromaDB integration**: Copilot assisted with the syntax for creating a ChromaDB collection and inserting embeddings with metadata.
- **RAG prompt design**: Got suggestions for structuring the grounded prompt template that restricts the LLM to retrieved context only.
- **SQL debugging**: Used Copilot to help diagnose and fix issues in LLM-generated Spark SQL (e.g., wrong column names, unsupported syntax).
