# Ice Breaker LLM

An AI-powered application that generates personalized conversation starters and insights by analyzing LinkedIn profiles. Simply input a person's name, and the system will find their LinkedIn profile, extract key information, and create engaging ice breakers using local LLM models.

## 🚀 Features

- **Automated LinkedIn Profile Discovery**: Uses Tavily search API to find LinkedIn profiles from names
- **AI-Powered Profile Analysis**: Leverages Ollama (Llama 3/3.1) for intelligent content processing
- **Smart Content Generation**: Creates personalized summaries, interesting facts, topics of interest, and ice breakers
- **Modern Web Interface**: Clean, responsive Flask-based web application
- **Privacy-Focused**: Uses local LLM models (Ollama) instead of cloud-based APIs
- **Professional Data Extraction**: Integrates with Proxycurl API for comprehensive LinkedIn data

## 🛠️ Technology Stack

- **Backend**: Python, Flask
- **AI/ML**: LangChain, Ollama (Llama 3/3.1), Pydantic
- **APIs**: Proxycurl (LinkedIn data), Tavily (web search)
- **Frontend**: HTML, CSS, JavaScript
- **Environment**: Python-dotenv for configuration

## 📋 Prerequisites

Before running this application, ensure you have:

1. **Python 3.8+** installed
2. **Ollama** installed and running locally
3. **API Keys**:
   - Proxycurl API key (for LinkedIn data extraction)
   - Tavily API key (for web search)

## 🔧 Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/DahalRojan/ice-breaker-llm.git
   cd ice-breaker-llm
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up Ollama**:
   ```bash
   # Install Ollama (visit https://ollama.ai for installation instructions)
   # Pull required models
   ollama pull llama3
   ollama pull llama3.1
   ```

4. **Configure environment variables**:
   Create a `.env` file in the project root:
   ```env
   PROXYCURL_API_KEY=your_proxycurl_api_key_here
   TAVILY_API_KEY=your_tavily_api_key_here
   ```

## 🚀 Usage

1. **Start the application**:
   ```bash
   python app.py
   ```

2. **Access the web interface**:
   Open your browser and navigate to `http://localhost:5000`

3. **Generate ice breakers**:
   - Enter a person's full name in the search form
   - Click "Do Your Magic"
   - Wait for the AI to process the information
   - View the generated summary, facts, interests, and ice breakers

## 🏗️ System Architecture

### Workflow

1. **Input Processing**: User enters a person's name through the web interface
2. **Profile Discovery**: Tavily search API finds the corresponding LinkedIn profile URL
3. **Data Extraction**: Proxycurl API retrieves comprehensive LinkedIn profile data
4. **AI Analysis**: Three specialized LangChain pipelines process the data:
   - **Summary Chain**: Creates professional summary and interesting facts
   - **Interests Chain**: Identifies topics that might interest the person
   - **Ice Breaker Chain**: Generates personalized conversation starters
5. **Output Generation**: Results are formatted and displayed with profile picture

### Key Components

- **`app.py`**: Flask web server and API endpoints
- **`ice_breaker.py`**: Core orchestration logic
- **`agents/`**: LinkedIn profile lookup agents using LangChain
- **`chains/`**: LLM processing chains for different output types
- **`third_parties/`**: External API integrations (LinkedIn, Twitter)
- **`output_parsers.py`**: Pydantic models for structured data output
- **`tools/`**: Utility functions for web search and data processing

## 🔧 Configuration Options

### Environment Variables

Create a `.env` file with the following variables:

```env
# Required API Keys
PROXYCURL_API_KEY=your_proxycurl_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here

# Optional: OpenAI API (if you want to use GPT instead of Ollama)
# OPENAI_API_KEY=your_openai_api_key_here
```

### Mock Mode

For testing purposes, you can use mock LinkedIn data by modifying `third_parties/linkedin.py`:

```python
# In ice_breaker.py, change:
linkedin_data = scrape_linkedin_profile(linkedin_profile_url=linkedin_username, mock=True)
```

## 📡 API Endpoints

### POST /process

Processes a person's name and returns ice breaker information.

**Request Body:**
```json
{
  "name": "John Doe"
}
```

**Response:**
```json
{
  "summary_and_facts": {
    "summary": "Professional summary...",
    "facts": ["Fact 1", "Fact 2"]
  },
  "interests": {
    "topics_of_interest": ["Topic 1", "Topic 2", "Topic 3"]
  },
  "ice_breakers": {
    "ice_breakers": ["Ice breaker 1", "Ice breaker 2"]
  },
  "picture_url": "https://profile-pic-url.com"
}
```

## 🧪 Testing

To test the application with mock data:

1. Set `mock=True` in the `scrape_linkedin_profile` function call
2. The system will use predefined mock data instead of making API calls
3. This is useful for development and testing without consuming API credits

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

## 🛠️ Troubleshooting

### Common Issues

1. **Ollama not running**: Ensure Ollama is installed and running (`ollama serve`)
2. **Missing API keys**: Check your `.env` file for correct API key configuration
3. **Model not found**: Pull required models (`ollama pull llama3` and `ollama pull llama3.1`)
4. **Port already in use**: Change the port in `app.py` if 5000 is occupied

### Support

For issues and questions, please open an issue on the [GitHub repository](https://github.com/DahalRojan/ice-breaker-llm/issues).

## 📸 Screenshots

<img width="706" alt="LinkedIn profile discovery process" src="https://github.com/user-attachments/assets/810b5275-8865-40f1-bfe9-98d5dc553c52">

<img width="853" alt="Generated ice breaker results" src="https://github.com/user-attachments/assets/5a0b2ad9-e6b0-4c7b-9e93-93ecef1b0c95">
