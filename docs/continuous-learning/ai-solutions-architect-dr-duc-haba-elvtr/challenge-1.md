# Challenge 1

1. **During a brainstorming session, your team starts by asking, “What possibilities does Generative AI, such as GPT-5, offer?” As an AI Solution Architect, how would you respond?**

Start with the business problem, not the technology. We must first clarify what we are trying to achieve. The right question is not what the technology can do, but what our users and the business need it to do. We should begin with business problems, not model capabilities.

A product is a specific application that solves a business problem. Generative AI is a technology, not a solution. Large Language Models (LLMs) and GenAI are general-purpose enablers, not the goal itself. Business requirements must always take precedence over technology choices.

Key questions to answer:

- Which business processes are slow, costly, error-prone, or difficult to scale?

- Where do people spend time on repetitive cognitive work?

- What decisions are currently made with incomplete, delayed, or low-quality information?

- Which risks are we trying to reduce (compliance, security, quality, operational)?

*1. Dr Haba: Interesting answer. First, establishing business requirements is crucial before diving into technical solutions like GPT-4o or Claude. As AI Solution Architects, our role is to step back and consider the bigger picture before addressing specific technical solutions. Rather than jumping straight to the latest advancements in AI or GenAI, our first priority should be understanding the business goals and outcomes our boss aims to achieve. We can ensure meaningful and effective results by aligning our solutions with those objectives.*

**2. A vendor claims that their AI is superior to GPT-5 or Claude 3.5. What questions should you ask this vendor?**

Claims that a model is “superior” or “better” are meaningless without context. Better at what tasks, and in which domains?

The objective is to select the model that is most efficient for our specific workload. That requires evidence in our company’s context, using our data, and operating under our constraints. Anything else is marketing.

Key questions to answer:

- What benchmarks are being used?

- Which tools are best suited for which tasks (reasoning, code generation, RAG, multilingual support, etc.)?

- Is the model included in independent comparison frameworks like [here](https://artificialanalysis.ai/models#intelligence-vs-price-log-scale)? (e.g., the Artificial Analysis Models Comparison chart)

- What is the architecture? Foundation model, fine-tuned model, or a wrapper around another LLM?

- How and where does inference run? SaaS only, VPC, on-premises, or air-gapped?

- What are the token limits and context window?

These are only baseline questions; in practice, the full evaluation checklist will be much larger.

*2. Dr Haba: Good answer. That’s a solid start to building a list of questions for the vendor. A thorough and well-rounded set of questions should cover key areas such as available APIs, access to testing data, accuracy benchmarks, scalability, cost, involvement of domain experts, quality assurance processes, and the fairness of their LLM. These aspects ensure you evaluate their solution comprehensively and align it with your business needs.*
