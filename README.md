# Live-Internet-browsing-using-LLM 🚀


## What it Solves 🧩:
This notebook demonstrates an intelligent agent system that answers user queries by combining internal knowledge and live web data. It efficiently handles queries that need up-to-date information from the internet.

## How it Works 🔧:
- **LangChain** powers the AI with GPT to generate responses.
- **Tavily API** fetches relevant URLs when the agent needs to pull in live information.
- **LangGraph** manages the flow, deciding when to answer directly and when to use the web.

### Key Components:
1. **get_urls**: Uses Tavily API to fetch relevant URLs.
2. **convert_html_to_markdown**: Converts HTML content into markdown format.
3. **Flow**: The agent first tries to answer directly, then pulls information from the web when needed.

## Flow Diagram 🔄:

### 1. **General Agent Node**:
   - The first step is to process the user query.
   - If the agent has enough knowledge, it answers the query directly.
   - If it needs more information, it sends the query to the **Internet Agent** node.

### 2. **Internet Agent Node**:
   - This node fetches relevant URLs based on the query using the **get_urls** tool (via Tavily).
   - It then converts the HTML content of those URLs into markdown format using the **convert_html_to_markdown** tool.
   - After retrieving and converting the data, it sends this information back to the **General Agent** node.

### 3. **Combining Responses**:
   - The **General Agent** then combines the answer from its internal knowledge and the markdown content from the internet.
   - It provides a complete, concise response to the user.

## Example 🌐:
The notebook processes a query like "What is square root of 25? and What is apple stock health on 22 Jan 2025?"—answering the math question directly and fetching the latest stock info from the web.

## Conclusion 💡:
This system seamlessly combines pre-existing knowledge with real-time data, providing accurate answers by pulling from both internal and web sources.

## Resources 📚:
- [LangGraph Tutorial - Introduction](https://langchain-ai.github.io/langgraph/tutorials/introduction/#requirements)
- [LangGraph Tutorial - Multi-Agent Supervisor](https://langchain-ai.github.io/langgraph/tutorials/multi_agent/agent_supervisor/)
- [Tavily API Python SDK - Search API Reference](https://docs.tavily.com/docs/python-sdk/tavily-search/api-reference)
