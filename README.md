# LLM-JSON-Extraction

## Overview
This tool extracts structured information from natural language queries about company performance metrics. It leverages the Groq API with LLaMA 3.1 to parse queries and maintain a history of previous extractions.

## Features
- Extracts company names, performance metrics, and date ranges from queries
- Automatically handles abbreviations and formatting
- Maintains a history of previous extractions
- Sets default date ranges when not specified (last 12 months)
- Returns structured JSON data for further processing

## Requirements
- Python 3.8+
- Groq API key

## Installation

1. Clone the repository
2. Install dependencies:
```bash
pip install groq python-dotenv
```
3. Create a `.env` file in the project root with your Groq API key:
```
GROQ_API_KEY=your_api_key_here
```

## Usage

Run the Jupyter notebook `main.ipynb` and enter your query when prompted.

### Example Queries
- "What was Amazon's revenue in the last quarter?"
- "Compare GMV for Walmart and Target between January and March 2023"
- "Show me Netflix subscriber growth since 2022"

### Output Format
The tool extracts information into a structured JSON format with the following fields:
- `entity`: Company name (e.g., "Amazon", "Google")
- `parameter`: Performance metric (e.g., "Revenue", "Gross Merchandise Value")
- `start_date`: ISO format date (YYYY-MM-DD)
- `end_date`: ISO format date (YYYY-MM-DD)

If dates are not specified in the query, the tool defaults to a one-year period ending on the current date.

## How It Works
1. User inputs a natural language query
2. The query is sent to the Groq API using LLaMA 3.1
3. The LLM extracts structured information based on the system prompt
4. The response is parsed into JSON
5. Default dates are applied if needed
6. The extraction is saved to the history file
7. Results are displayed to the user

## History
Th
