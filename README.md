# Agentic Application

A Python-based agent framework built with LangGraph and LangChain, designed to create intelligent agents with advanced capabilities.

## Agentic Design Patterns

### Definition
Proven solution for common challenges in AI Agent workflows

### Patterns

1) **Planning**: Breaking down complex tasks into smaller subtasks
   - LLM Generates series of steps
   - Subsystem carries out these steps using the same agent or delegate to sub-agent
   
   
   ```
   +----------------+     +----------------------+
   |  Complex Task  |---->|  LLM Generates Steps |
   +----------------+     +----------+-----------+
                                    |
                    +----------------+------------------+
                    |                 |                 |
           +--------v----+  +--------v----+  +---------v-----+
           |  Subtask 1  |  |  Subtask 2  |  |  Subtask 3   |
           +------+------+  +------+------+  +------+--------+
                  |                |                 |
                  +--------+-------+-----------------+
                           |
                    +------v------+
                    |  Execute/   |
                    |  Delegate   |
                    +------+------+
                           |
                    +------v------+
                    |  Final     |
                    |  Result    |
                    +------------+
   ```

2) **Reflection**: Self assessment and learning
   - Agent reviews its past actions and outputs
   - It prompts an LLM to assess the quality of its chosen actions
   - The actions were taken based on the tools, environment (another agent, humans, etc)
   - Based on the assessment, the agent can:
     - Replan: Adjusts strategies
     - Search: explores alternative actions
     - Evaluate: Grading/Critiquing outputs to ensure quality
   - Create a mermaid script so its visible in README

3) **Map-Reduce**: Handles parallel processing
4) **Multi-Agent**: Multiple agents working together
5) **Human-in-the-Loop**: Human intervention when needed
   - **Approval workflow**: Agent pauses for human approval before executing specific tool
     - Example: Approving DB changes
   - **Wait for input**: Agent pauses to request additional details from humans
     - Example: Select one from a list of options
   - **Time travel**: Allow humans to review and edit previous checkpoints
     - Example: Going back to previous steps and fixing a prompt
   - **Review tool calls**: Human inspects and approves tool calls before executing them
     - Example: Reviewing and approving email content before a tool sends it out

## 🚀 Features

### 1. Structured Output
Extract structured information from unstructured text and return it as JSON.

**Example:**
```
Input: "John Doe is a 30 years old man"
Output: {"name": "John Doe", "age": 30, "gender": "male"}
```

### 2. Tool Calling
Enable LLMs to utilize external functions (tools) to perform specific actions.

**Example Flow:**
```
Thought: "I need to get the current weather"
Action: "Get the current weather"
LLM: "What is the weather in New York?"
Tool: "The weather in New York is sunny."
```

### 3. Memory
Maintain context across interactions for more natural conversations.

**Example Conversation:**
```
User: Get me list of flights to New York today
Agent: I need to get the list of flights to New York today
Tool: "Get me list of flights to New York today"
LLM: "The list of flights to New York today is: ..."

User: I want to book the first flight
Agent: I need to book the first flight
Tool: "Book the first flight"
LLM: "The first flight is booked."
```

## 🛠️ Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd agentic-app
   ```

2. Create and activate a virtual environment (recommended):
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## 🚦 Getting Started

Run the application:
```bash
python main.py
```

## 🧪 Testing

To run tests (when available):
```bash
# Coming soon
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
