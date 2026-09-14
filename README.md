## 🔄 Agent Execution Flow

The AI agent follows a continuous tool-calling loop to process user queries and provide accurate career insights and job opportunities.

![Agent Execution Flow](agent-flow.png)

### Flow Description

**1. Start**

The process begins when the user submits a query to the AI Career Agent.

**2. Agent Node Calls Model**

The Agent Node sends the current messages and user query to the Google Gemini model for analysis.

**3. Model Decision**

The model determines whether external tools are required to answer the user's query.

**4. If Tool Calls Are Required**

If the model decides that additional information is required:

- The appropriate tool is executed.
- Tavily Search is used for skill demand, career trends, salary information, and technology research.
- RapidAPI JSearch is used to retrieve relevant job listings.
- The tool results are added to the conversation as a `ToolMessage`.
- The updated messages are sent back to the Agent Node.
- The model is called again with the updated information.

**5. Loop Continues**

The process continues in a loop whenever the model requests additional tool calls.

**6. If No Tool Call Is Required**

When the model determines that no additional tools are required, it generates the final response.

**7. Return Final Answer**

The agent returns the final answer containing relevant skill insights, career information, and/or job listings.

**8. End**

The process terminates after the final answer is generated and returned to the user.

### 🔁 Agent Workflow
<img width="1287" height="442" alt="image" src="https://github.com/user-attachments/assets/356f6f5a-65e6-492a-8deb-5824b9f6c6f9" />


