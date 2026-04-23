## Day 87 -- Introduction to Agentic AI for DevOps

#### Task 1: Understand Agentic AI for DevOps
What is an AI agent?
An AI agent is a system that can perceive its environment, make decisions, and take actions to achieve a goal—often with some level of autonomy.
An AI agent = Perception + Decision-making + Action

1. What is an AI agent?
 - AI agents are autonomous software programs that use large language models (LLMs) to perceive their environment, interact with real time system.
 - Unlike a chatbot that only generates text, an agent can run commands, read files, call APIs
 - The LLM decides which tool to use, with what arguments, based on the user's question
2. Why agents for DevOps?
  Agents for DevOps (Agentic DevOps) are autonomous software systems that use AI to reason, plan, and act, transforming DevOps from passive, manual tasks to proactive, automated operations. They are used to reduce manual toil, speed up incident response, optimize cloud costs, and enhance CI/CD pipelines, acting as intelligent
Key Reasons for Using Agents in DevOps:
- Reduced Human Error:
- Improved Efficiency and Speed
- Cost Reduction & Resource Optimization
- Proactive Problem Prevention
- Contect Intelligence

3. The ReAct pattern (Reason + Act):

   Key Components of ReAct:
   - Thought: The agent reasons about the current state, identifies what it needs to know, and plans the next step.
   - Action (Act): The agent calls an external tool (e.g., web search, database API, calculator).
   - Observation: The agent receives the output from the tool and evaluates the new information.
 4. Key components:

    LLM -- the brain (Ollama/Gemma 4 locally, or Claude/GPT for production)
    Tools -- Python functions that wrap CLI commands (the hands)
    Agent framework -- user LangChain's & Langgraph create_react_agent orchestrates the reasoning loop
    MCP (Model Context Protocol) -- a standard for exposing tools to any AI client
