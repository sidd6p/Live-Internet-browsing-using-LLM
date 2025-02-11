# Live-Internet-browsing-using-LLM 🚀


## What it Solves 
This notebook demonstrates an intelligent agent system that answers user queries by combining internal knowledge and live web data. It efficiently handles queries that need up-to-date information from the internet.

## Example 
### User query: 
"What is square root of 25? and What is apple stock health on 22 Jan 2025"

### Agents Output: 

The square root of 25 is **5**.

Regarding the health of Apple stock on January 22, 2025, here are the key points:

1. **Sales Decline**: Apple faced an **18.2% decline in iPhone sales** specifically in China during the December quarter, leading to a drop in stock price by **4.4%**. Analysts expressed concerns regarding the ongoing decline in sales.

2. **Analysts' Downgrades**: This sales drop prompted several analysts to downgrade their ratings on Apple stock, signaling worries about weak iPhone sales in a challenging consumer electronics market.

3. **Relative Strength Index (RSI)**: By January 21, 2025, Apple’s stock entered an **oversold territory**, with an RSI reading of **28.2**. This suggests that selling pressure was potentially exhausting, indicating possible buying opportunities.

4. **Price Observations**: On January 22, 2025, Apple's shares were trading around **$220.09**. The stock had experienced significant fluctuations over the year, with a **52-week low of $164.075** and a high of **$260.10**.

5. **Consumer Sentiment and Strategy Issues**: Analysts observed that Apple's pricing strategy was not resonating well with many Chinese consumers, who tended to prefer more affordable options from local manufacturers.

This combination of factors indicates a challenging environment for Apple stock, with caution advised for potential investors despite some indicators suggesting possible future upside.

If you have further questions or need more details, feel free to ask!


## How it Works 🔧
- **LangChain** powers the AI with GPT to generate responses.
- **Tavily API** fetches relevant URLs when the agent needs to pull in live information.
- **LangGraph** manages the flow, deciding when to answer directly and when to use the web.

### Key Components:
1. **get_urls**: Uses Tavily API to fetch relevant URLs.
2. **convert_html_to_markdown**: Converts HTML content into markdown format.
3. **Flow**: The agent first tries to answer directly, then pulls information from the web when needed.

## Flow Diagram 🔄

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


## Conclusion 💡
This system seamlessly combines pre-existing knowledge with real-time data, providing accurate answers by pulling from both internal and web sources.

## Resources 📚
- [LangGraph Tutorial - Introduction](https://langchain-ai.github.io/langgraph/tutorials/introduction/#requirements)
- [LangGraph Tutorial - Multi-Agent Supervisor](https://langchain-ai.github.io/langgraph/tutorials/multi_agent/agent_supervisor/)
- [Tavily API Python SDK - Search API Reference](https://docs.tavily.com/docs/python-sdk/tavily-search/api-reference)
