# Personal Agents

## Overview
Personal Agents is a team of AI-powered assistants that collaborate to manage emails, schedules, and web exploration tasks efficiently. These agents specialize in different functionalities to ensure optimal performance and reduce hallucinations common in AI models.

## Demo
[Watch Demo](https://youtu.be/l65S0ZVM9Io)

## Technology Stack
- **Programming Language**: Python
- **AI & NLP**: OpenAI GPT (Vision, Function Calling, Whisper for Speech-to-Text)
- **APIs & Automation**:
  - Google Calendar API
  - Gmail API
  - Playwright (for web automation)
  - BeautifulSoup (for web scraping)
- **Other Dependencies**:
  - `python-dotenv` for environment variables
  - `Pillow` for image processing
  
## System Architecture
When a user makes a request, the primary agent ("Jarvis") determines if it can handle it. If additional assistance is needed, Jarvis assigns tasks to specialized sub-agents:
- **Email Agent**: Manages email retrieval, sending, and replies.
- **Calendar Agent**: Retrieves and schedules Google Calendar events.
- **Scraper Agent**: Navigates and extracts data from websites.

Each agent has its own specialized functions, improving efficiency and accuracy in handling user requests.

## Agents and Their Functions

### Main Agent: Jarvis
- Acts as the central coordinator.
- Delegates tasks to specialized agents when required.

### Email Agent
- Integrates with Gmail API.
- Retrieves emails based on user-defined time ranges.
- Sends and replies to emails intelligently by interpreting user intent.

### Calendar Agent
- Integrates with Google Calendar API.
- Fetches scheduled events based on user queries.
- Creates new events in the user's calendar.

### Scraper Agent
- Uses Playwright and BeautifulSoup for web interaction and data extraction.
- Can perform actions like clicking, navigating, and form submissions.
- Uses GPT Vision to "see" elements on the webpage before interacting.

## Speech-to-Text Functionality
- Uses OpenAI Whisper API for transcribing spoken input.
- Allows users to interact with the system via voice commands.

## Installation and Setup

### Prerequisites
- Python 3.8+
- Google Cloud Project (for API access)
- OpenAI API Key
- Google Chrome (for Playwright automation)

### Installation Steps
1. **Clone the repository:**
   ```sh
   git clone https://github.com/your-repo/PersonalAgents.git
   cd PersonalAgents
   ```

2. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

3. **Set up environment variables:**
   - Create a `.env` file in the project root.
   - Add your OpenAI API key:
     ```env
     OPENAI_API_KEY=your_openai_api_key_here
     ```

4. **Set up Google Cloud credentials:**
   - Enable Google Calendar and Gmail APIs.
   - Download `credentials.json` and place it in the project root.

5. **Modify Playwright settings:**
   - Update `user_data_dir` in `main_agent.py` to match your Chrome profile path.

6. **Run the main agent:**
   ```sh
   python main_agent.py
   ```

## Potential & Limitations
- **Advantages**:
  - Task specialization prevents AI hallucination.
  - Multi-agent collaboration improves task efficiency.
  - Expands automation potential beyond traditional scripting.

- **Challenges**:
  - Multiple API calls may increase costs.
  - Playwright-based web navigation can be token-intensive.
  - Model hallucinations may occasionally misinterpret UI elements.

## Future Improvements
- Fine-tuning AI agents for better context understanding.
- Reducing API call costs with optimized prompts.
- Expanding capabilities with more integrations (e.g., Slack, Trello).

## Contribution
Feel free to submit issues and pull requests. We welcome improvements and new features!

## License
This project is licensed under the MIT License. See `LICENSE` for details.
