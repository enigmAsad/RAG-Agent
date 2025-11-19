# Agentic RAG

**A high-performance Agentic RAG starter kit using LangGraph, LangChain, and Groq.**

![Banner](docs/image/banner.png)

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Architecture](#architecture)
- [Contributing](#contributing)
- [License](#license)

## Features

*   **High-Speed Inference**: Utilizes [Groq](https://groq.com/) with `Gemma2-9b-It` for near-instant LLM responses.
*   **Agentic Workflow**: Built on [LangGraph](https://langchain-ai.github.io/langgraph/) for stateful, cyclic agent orchestration.
*   **Advanced Retrieval**: Integrates **ChromaDB** and **HuggingFace Embeddings** (`all-MiniLM-L6-v2`) for semantic search.
*   **Extensible Tools**: Pre-configured with `WebBaseLoader` and `RecursiveCharacterTextSplitter` for dynamic data ingestion.
*   **Observability**: Full integration with **LangSmith** for tracing and debugging agent steps.

## Installation

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/agentic-rag.git
    cd agentic-rag
    ```

2.  **Create a virtual environment (optional but recommended):**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

## Usage

This project is structured as a Jupyter Notebook for interactive development and testing.

1.  **Start Jupyter Notebook:**

    ```bash
    jupyter notebook
    ```

2.  **Open `agentic-rag.ipynb`**:
    Run the cells sequentially to initialize the agent, tools, and graph.

3.  **Invoke the Agent:**
    The notebook demonstrates how to query the LLM:

    ```python
    llm.invoke("How does Agentic RAG work?")
    ```

    *(Future updates will include the full graph execution flow)*

## Configuration

Create a `.env` file in the root directory and add your API keys:

```ini
# Groq API Key for LLM Inference
GROQ_API_KEY=your_groq_api_key_here

# LangSmith API Keys for Tracing (Optional)
LANGSMITH_API_KEY=your_langsmith_api_key_here
LANGCHAIN_TRACING_V2=true
LANGCHAIN_ENDPOINT=https://api.smith.langchain.com
```

## Architecture

The project uses a modular architecture powered by LangGraph:

*   **StateGraph**: Manages the flow between the LLM and tools.
*   **VectorStore**: ChromaDB acts as the knowledge base.
*   **Embeddings**: HuggingFace models convert text to vectors.

![Architecture Diagram](docs/image/architecture.png)

### Directory Structure

```
/
├── agentic-rag.ipynb    # Main entry point and logic
├── requirements.txt     # Python dependencies
├── docs/
│   └── image/           # Documentation assets
└── README.md            # Project documentation
```

## Contributing

Contributions are welcome! Please follow these steps:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/amazing-feature`).
3.  Commit your changes (`git commit -m 'Add amazing feature'`).
4.  Push to the branch (`git push origin feature/amazing-feature`).
5.  Open a Pull Request.

## License

Distributed under the MIT License. See `LICENSE` for more information.
