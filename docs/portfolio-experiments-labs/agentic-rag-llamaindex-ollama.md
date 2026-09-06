# Agentic RAG - LlamaIndex/Ollama

This code builds a **practical Agentic RAG system (“Alfred”)** that: \* integrates multiple tools (RAG over custom data, web search, weather, etc.), \* retrieves structured + real-time information, \* and answers user queries by **choosing the right tool/workflow at runtime**.

**Agentic RAG (short technical view)** Agentic RAG extends classic Retrieval-Augmented Generation by adding an **agent layer (LLM with tool-use + planning)** on top of retrieval. Instead of a fixed pipeline (retrieve → stuff context → generate), the model can **decide dynamically**:

- what to retrieve,

- when to retrieve again (iterative loops),

- which tools to call (search, APIs, DBs),

- and how to combine intermediate results.

This turns RAG into a **closed-loop reasoning system** where the LLM orchestrates retrieval and reasoning steps, improving adaptability and multi-step problem solving

- [GitHub - JoseMorei/agentic-rag-llamaindex: This code builds a \*\*practical Agentic RAG system (“Alfred”)\*\* that:  \* integrates multiple tools (RAG over custom data, web search, weather, etc.), \* retrieves structured + real-time information, \* and answers user queries by \*\*choosing the right tool/workflow at runtime\*\*.](https://github.com/JoseMorei/agentic-rag-llamaindex/tree/main) — This code builds a \*\*practical Agentic RAG system (“Alfred”)\*\* that:  \* integrates multiple tools (RAG over custom data, web search, weather, etc.), \* retrieves structured + real-time information, ...
