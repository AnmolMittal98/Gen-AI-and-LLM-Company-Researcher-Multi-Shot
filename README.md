# README: Sales Brochure Generator Notebook

This project is a Jupyter notebook that automatically generates a company sales brochure by scraping relevant information from a company's website and using an LLM (OpenAI GPT-4o-mini) to summarize and present it. Below is a step-by-step explanation of what each part of the code does, so anyone new can follow along easily.

## Step-by-Step Guide

### 1. Import Libraries
- `os`, `requests`, `json`, `typing.List`: Standard Python libraries for file operations, HTTP requests, and data handling.
- `dotenv.load_dotenv`: Loads environment variables (like your OpenAI API key) from a `.env` file.
- `BeautifulSoup`: Parses HTML content from web pages.
- `IPython.display`: For displaying Markdown output in the notebook.
- `openai.OpenAI`: The OpenAI Python client for accessing GPT models.

### 2. Initialize API and Constants
- Loads your OpenAI API key from the environment and checks if it looks valid.
- Sets the model to use (`gpt-4o-mini`).
- Initializes the OpenAI client.

### 3. Website Scraping Class
- Defines a `Website` class to fetch a web page, parse its content, extract the title, main text, and all links.
- Cleans up the HTML by removing scripts, styles, images, and input fields for better text extraction.

### 4. Example Usage
- Shows how to create a `Website` object for a given URL and access its links.

### 5. System Prompt for Link Selection
- Prepares a prompt for GPT to help decide which links (like About, Careers, etc.) are relevant for a company brochure.

### 6. User Prompt for Link Selection
- Builds a user prompt listing all links found on the website, asking GPT to select only the relevant ones for the brochure.

### 7. Link Extraction Function
- Defines a function to automate the process of scraping a website, sending the links to GPT, and parsing the JSON response.

### 8. Example: HuggingFace Website
- Demonstrates scraping and link extraction for the HuggingFace website.

### 9. Get All Details Function
- Fetches the main page and all relevant subpages, then combines their content for brochure generation.

### 10. Brochure Generation Prompt
- Prepares a system prompt for GPT to generate a concise, informative brochure in Markdown format.
- Optionally, you can switch to a humorous tone by changing the prompt.

### 11. Brochure User Prompt
- Builds a user prompt with all the scraped content, truncated if too long, for GPT to use as input.

### 12. Brochure Creation Function
- Sends the prompts to GPT and displays the generated brochure in Markdown.

### 13. Streaming Brochure Function
- Streams the brochure output from GPT in real time for a smoother user experience.

### 14. Example Calls
- Shows how to generate and display a brochure for HuggingFace, both in standard and streaming modes.

---

## How to Use
1. Make sure you have a valid OpenAI API key in your `.env` file as `OPENAI_API_KEY`.
2. Run each cell in order, or adapt the code for your own company/website.
3. The notebook will scrape the website, select relevant pages, and generate a readable brochure for you!

Feel free to modify the prompts or add your own logic to customize the brochure's tone and content.
