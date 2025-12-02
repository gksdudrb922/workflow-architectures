# Workflow Architectures Study

A study project exploring different workflow architectures for AI agents, as
described in [Anthropic's guide to building effective
agents](https://www.anthropic.com/engineering/building-effective-agents).

## Overview

This project demonstrates how to build agentic systems using simple,
composable patterns rather than complex frameworks. It implements various
workflow architectures to understand their strengths, use cases, and
implementation patterns.

## Workflow Patterns Studied

Based on the [Anthropic
article](https://www.anthropic.com/engineering/building-effective-agents), this
project explores the following workflow patterns:

1. **Prompt Chaining**: Decomposes a task into a sequence of steps, where each
   LLM call processes the output of the previous one
2. **Routing**: Classifies input and directs it to specialized follow-up tasks
3. **Parallelization**: Runs tasks simultaneously with outputs aggregated
   programmatically (sectioning and voting patterns)
4. **Orchestrator-Workers**: A central LLM dynamically breaks down tasks,
   delegates to worker LLMs, and synthesizes results
5. **Evaluator-Optimizer**: One LLM generates a response while another provides
   evaluation and feedback in a loop

## Key Concepts

### Workflows vs Agents

As described in the [Anthropic
article](https://www.anthropic.com/engineering/building-effective-agents):

- **Workflows**: Systems where LLMs and tools are orchestrated through
  predefined code paths
- **Agents**: Systems where LLMs dynamically direct their own processes and
  tool usage

This project focuses on **workflows** - exploring different patterns for
orchestrating LLM calls and tools in structured ways.

### Why Study Workflow Architectures?

Workflow architectures offer:

- **Predictability**: Well-defined execution paths
- **Consistency**: Repeatable results for similar inputs
- **Debugging**: Clear visibility into each step
- **Composability**: Simple patterns that can be combined

These patterns are building blocks that can be combined and customized to fit
different use cases.

## Prerequisites

- Python 3.13+
- OpenAI API key (set in environment or `.env` file)
- [uv](https://github.com/astral-sh/uv) package manager (recommended)

## Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd workflow-architectures
```

1. Install dependencies.

   Using uv:

```bash
uv sync
```

   Or using pip:

```bash
pip install -e .
```

1. Set up your OpenAI API key.

   Option 1: Set environment variable:

```bash
export OPENAI_API_KEY="your-api-key-here"
```

   Option 2: Create a `.env` file:

```text
OPENAI_API_KEY=your-api-key-here
```

## Usage

### Running the Notebook

1. Open `main.ipynb` in Jupyter
2. Navigate to the workflow pattern you want to study
3. Run the cells to see the workflow in action

Each workflow implementation demonstrates the pattern with a practical example.

## Implementation Notes

All workflows are built using **LangGraph**, which provides:

- **Nodes**: Each workflow step is a node
- **Edges**: Define the flow between nodes
- **Conditional Edges**: Enable dynamic routing based on state
- **State Management**: TypedDict State objects for data flow
- **Graph Cycles**: Model iterative loops and feedback

This makes the workflow patterns explicit and easy to understand.

## References

- [Building Effective Agents - Anthropic
  Engineering](https://www.anthropic.com/engineering/building-effective-agents)
- [LangGraph Documentation](https://langchain-ai.github.io/langgraph/)
- [LangChain Documentation](https://python.langchain.com/)

## License

This is a study project for educational purposes.
