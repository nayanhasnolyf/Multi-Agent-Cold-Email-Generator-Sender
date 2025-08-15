# Multi-Agent Cold Email Generator & Sender

## This project is a multi-agent orchestration system that generates, formats, and sends cold sales emails using Google Gemini API (via OpenAI client) and SendGrid.

## 🚀 Features

### Three specialized AI sales agents:

1. Serious & professional cold emails

2. Witty & engaging cold emails

3. Concise & direct cold emails

### Sales Manager Agent:

1. Tries all three sales agents

2. Picks the most effective email

3. Hands it off for formatting & sending

### Email Manager Agent:

1. Generates a catchy subject line

2. Converts plain text email to HTML

3. Sends the email via SendGrid

## 🖼 Workflow Diagram
``` mermaid
flowchart TD
    A[Input Message] --> B[Sales Manager Agent]
    B --> C1[Sales Agent 1 - Serious]
    B --> C2[Sales Agent 2 - Witty]
    B --> C3[Sales Agent 3 - Concise]
    C1 --> D[Best Email Selection]
    C2 --> D
    C3 --> D
    D --> E[Email Manager Agent]
    E --> F[Subject Writer Tool]
    E --> G[HTML Converter Tool]
    E --> H[SendGrid Email Sender]
    F --> I[Final Email Sent]
    G --> I
    H --> I
```

## 🛠 Tech Stack

Python 3.9+

Google Gemini API

OpenAI Python SDK

SendGrid Python SDK

dotenv for environment variables

agents framework for tool-based multi-agent orchestration

asyncio for asynchronous execution

## 📦 Installation

### 1. Clone the repository
``` bash
git clone https://github.com/yourusername/multi-agent-emailer.git
cd multi-agent-emailer
```

### 2. Create a virtual environment
``` bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Set environment variables
Create a .env file in the root folder:
```bash
GEMINI_API_KEY=your_gemini_api_key
SENDGRID_API_KEY=your_sendgrid_api_key
```
## ⚙️ Usage

Run the script:
```bash
python main.py
```

### The flow:

1. Sales Manager Agent prompts all 3 Sales Agents.

2. Picks the best email.

3. Passes it to the Email Manager Agent.

4. Formats it (subject + HTML).

5. Sends via SendGrid.

## 📂 Project Structure
``` bash
.
├── main.py              # Main entry point
├── agents/              # Agent classes and tools
├── requirements.txt     # Dependencies
```
## 🛡 Environment Variables
Variable	Description
GEMINI_API_KEY	API key for Google Gemini
SENDGRID_API_KEY	API key for SendGrid service

## 📝 Example Output

### Plain Text Email:
``` CSS
Dear CEO,

I noticed your company is scaling fast, and I believe our SOC2 compliance SaaS can streamline your audit preparation...
```

### Generated HTML Email:
``` html
<html>
<body>
  <h2>Dear CEO,</h2>
  <p>I noticed your company is scaling fast...</p>
</body>
</html>
```
## ⚠️ Notes

This project requires valid Google Gemini and SendGrid API keys.

Emails will be sent to the address specified in the send_html_email function.

## 📜 License

MIT License – feel free to use, modify, and distribute.

## Made By Nayan
