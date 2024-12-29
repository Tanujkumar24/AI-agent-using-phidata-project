# ReadMe for Multi-Agent System using PHI and OpenAI

## Project Overview
This project implements a multi-agent system using the PHI framework and OpenAI. The code defines two specialized agents: one for web searches and another for financial data analysis. These agents are integrated into a playground application that allows interactive usage. 

### Features:
- **Web Search Agent**: Leverages DuckDuckGo to perform web searches and provides results with source citations.
- **Finance AI Agent**: Uses financial tools to fetch stock prices, analyst recommendations, stock fundamentals, and company news, displaying the data in tabular format.
- **Multi-Agent Collaboration**: Combines agents into a unified interface, enabling collaborative capabilities.

## Prerequisites
Ensure the following are installed and configured:

1. **Python**: Python 3.7+
2. **PHI Framework**: Install using the official PHI documentation.
3. **dotenv Library**: `pip install python-dotenv`
4. **OpenAI API Key**: Obtain from [OpenAI](https://openai.com/api/).
5. **PHI API Key**: Obtain from the PHI documentation or provider.
6. **Environment File (.env)**:
   ```plaintext
   PHI_API_KEY=<your_phi_api_key>
   OPENAI_API_KEY=<your_openai_api_key>
   ```

## Code Explanation

### 1. **Imports and Setup**
- The necessary libraries and modules are imported:
  - `openai` and `phi` for AI functionalities.
  - `dotenv` to load environment variables.
  - `os` to fetch API keys from the environment.
  
- Environment variables are loaded using `load_dotenv()`, ensuring the PHI and OpenAI API keys are available.

### 2. **Web Search Agent**
The `web_search_agent` is defined as follows:
- **Purpose**: To search the web and provide results with citations.
- **Model**: Uses Groq's `llama3-groq-70b-8192-tool-use-preview` for processing.
- **Tool**: Utilizes the DuckDuckGo tool for web searches.
- **Instructions**: Specifies that all results must include sources.
- **Features**:
  - Displays tool calls.
  - Outputs results in Markdown format.

### 3. **Finance AI Agent**
The `finance_agent` is defined as follows:
- **Purpose**: To fetch financial data and present it in tabular format.
- **Model**: Also uses the `llama3-groq-70b-8192-tool-use-preview` model.
- **Tool**: Leverages `YFinanceTools` for stock price analysis, recommendations, and news.
- **Instructions**: Emphasizes using tables to display data.
- **Features**:
  - Displays tool calls.
  - Outputs results in Markdown format.

### 4. **Multi-Agent System**
The `multi_ai_agent` combines the `web_search_agent` and `finance_agent`:
- **Purpose**: Facilitates collaboration between agents.
- **Team**: Consists of the two agents.
- **Instructions**: 
  - Requires including sources.
  - Uses tables for data presentation.
- **Features**:
  - Displays tool calls.
  - Outputs results in Markdown format.

### 5. **Playground Application**
The `Playground` class is used to create an interactive environment:
- **Agents**: Includes `finance_agent` and `web_search_agent`.
- **App**: A playground application is generated using `get_app()`.

### 6. **Running the Application**
The application is served using `serve_playground_app()`:
- **Entry Point**: The script runs if executed directly (`if __name__ == "__main__":`).
- **Hot Reload**: Enabled with `reload=True` for dynamic code updates during development.

## How to Run
1. Clone the repository and navigate to the project directory.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file and add the required API keys.
4. Run the application:
   ```bash
   python <script_name>.py
   ```
5. Open the playground interface and interact with the agents.

## Future Enhancements
- Add more tools and capabilities to the agents.
- Integrate additional APIs for diverse data analysis.
- Enhance the user interface for better interactivity.

## Contact
For further assistance or queries, please contact the developer or refer to the PHI and OpenAI documentation.
