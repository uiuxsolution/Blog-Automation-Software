# AI Blog Automation Tool

An automated workflow system that generates and publishes SEO-optimized blog posts about AI tools using multiple AI services.

## Features

- Automated keyword research using Perplexity AI
- Website and YouTube tutorial data collection
- SEO-optimized content generation using NotebookLM and Claude AI
- Automated content storage in Airtable
- Comprehensive metadata and formatting

## Prerequisites

- Python 3.8+
- API keys for:
  - Perplexity AI
  - NotebookLM
  - Claude AI (Anthropic)
  - Google (YouTube)
  - Airtable

## Installation

1. Clone this repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file with your API keys and configuration:
   ```
   # Google API Keys
   GEMINI_API_KEY=your_key_here
   GOOGLE_API_KEY=your_key_here

   # Airtable Configuration
   AIRTABLE_API_KEY=your_key_here
   AIRTABLE_BASE_ID=your_base_id_here
   AIRTABLE_TABLE_NAME=your_table_name
   ```

## Airtable Setup

1. Create an Airtable account at https://airtable.com/create-account
2. Create a new base with the following columns:
   - Title (Single line text)
   - Content (Long text)
   - Meta Description (Long text)
   - Main Keywords (Single line text)
   - Long Tail Keywords (Single line text)
   - Competitor Keywords (Single line text)
   - Use Case Keywords (Single line text)
   - YouTube Embed (URL)
3. Get your API key from https://airtable.com/account
4. Get your base ID from the URL when viewing your base:
   - Open your base in Airtable
   - Look at the URL: https://airtable.com/appXXXXXXXXXXXXX
   - The string after '/app' is your base ID
5. Set your table name in the .env file

## Usage

1. Run the main script with required arguments:
   ```bash
   python main.py --tool-name "AI Tool Name" --website-url "https://tool-website.com"
   ```

2. The script will automatically:
   - Research keywords related to the AI tool
   - Collect information from the tool's website
   - Find relevant YouTube tutorials
   - Generate comprehensive blog content
   - Store the content in Airtable with proper formatting

## Generated Content Structure

The tool generates blog posts with the following sections:
- Title
- Introduction
- Features
- Use Cases
- Pricing
- Competitor Analysis
- Tutorial (with YouTube embed)
- Conclusion

## Project Structure

```
├── main.py                 # Main workflow controller
├── keyword_research.py     # Perplexity AI integration
├── data_collection.py      # Website/YouTube data scraping
├── content_generation.py   # NotebookLM/Claude integration
├── airtable_publisher.py   # Airtable integration
├── utils.py               # Helper functions
├── requirements.txt        # Project dependencies
└── .env                   # API keys and credentials
```

## License

MIT