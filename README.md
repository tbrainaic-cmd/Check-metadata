# Check-metadata
## Overview

The notebook is designed to check whether a **text snippet** appears inside an **document** and classify that snippet according to various **structural content types**, such as:

- **Textual body** – long text body (≥ 5 paragraphs, each with ≥ 5 lines)  
- **Simple / Complex Header** – simple titles or nested headings  
- **Simple / Complex Table** – simple or complex tables with text and numeric content  
- **Simple / Complex List** – flat or nested lists  
- **Footnotes** – footnotes or references

## How to Use

### 1. Preparing
- `file_id`: The Google Sheet ID containing the text snippets you want to check. 
- `zip_path`: A ZIP archive containing all the documents you want to search through.
- `API-key`: GPT and Claude API

```python
file_id = "1paO76gmkgoJRor986J0MB9Ntt40D-7nYcHkMhvVXk-Q"
zip_path = "/content/Devops.zip"
```

Make sure:

The ZIP file contains all .docx or .txt documents you want to analyze.

Your Google Sheet is accessible and has the snippets listed (one per row or column).

### 2. Run 
Open the notebook in Google Colab and execute the cells in order.
After running the script, the output for each snippet will look like this:

```json
{
  "found": true,
  "categories": [
    "Textual body",
    "Simple Table"
  ]
}
```

- `found`: `true` if the snippet appears in any of the documents, false otherwise.
- `categories`: A list of structural types associated with the snippet.
