# Challenge 11

1. Imagine you have launched a machine learning (ML) application for a global news service. The app has become a huge success, receiving millions of requests per hour. However, your serverless architecture—such as that provided by Google Cloud or AWS—is running slowly, and the cost of automatically scaling services exceeds your budget. As an AI Solution Architect (AISA), how would you recommend addressing this issue?

**Hints:**

Consider using various caching algorithms in conjunction with ML.

For this specific issue, the architecture must evolve from purely serverless execution toward intelligent caching, request optimization, and model-serving efficiency.

By combining predictive caching, batch inference, dedicated model serving, and edge caching, the architecture can maintain low latency while reducing cloud compute costs.

#### Recommended solutions

1. Introducing [multi-layer caching strategies ](https://oneuptime.com/blog/post/2026-01-30-llm-caching-strategies/view)around the ML inference layer. In a news platform, a large percentage of requests are repetitive. For example, if users frequently request article recommendations, trending topics, or summaries for popular articles, the system may recompute the same model outputs thousands of times per minute. Instead of recomputing predictions each time, the application can store recent results in a distributed cache.

Technologies such as Redis or Memcached can store the outputs of ML predictions so that identical or similar requests can be served instantly. For instance, if a user asks for the “top technology news recommendations” and this query occurs thousands of times across regions, the recommendation result can be cached for a short period (for example, 30–60 seconds). This approach significantly reduces both latency and compute cost, because the ML model is invoked far less frequently.

2. Another powerful technique involves [cache-aware machine learning pipelines](https://chaimrand.medium.com/a-caching-strategy-for-identifying-bottlenecks-on-the-data-input-pipeline-8e52060b402f). Instead of generating predictions on demand, the system periodically precomputes predictions for high-traffic content. For example, the recommendation engine can run batch inference every few minutes to generate personalized feeds for millions of users. These results are stored in a database or cache layer, allowing the front-end API to simply retrieve the precomputed result rather than executing the model each time. This architecture is commonly used by large-scale recommendation platforms such as Netflix and YouTube.

3. [Caching algorithms](https://dl.acm.org/doi/10.1145/3723178.3723250) themselves can also be optimized. Instead of simple key-value caching, the system can implement adaptive caching algorithms such as Least Recently Used (LRU), Least Frequently Used (LFU), or machine-learning-based cache prediction. For example, if the platform detects that certain articles are trending globally, the system can prioritize caching model predictions for those articles while evicting rarely requested content. Research into ML-driven caching demonstrates that predictive caching can dramatically reduce infrastructure costs by anticipating which content users are most likely to request next.

4. Beyond caching, the architecture should move away from invoking heavy ML models inside every serverless request. Instead, it is often better to deploy models using dedicated model-serving infrastructure. Platforms such as TensorFlow Serving, KServe, or TorchServe allow models to run on optimized infrastructure such as GPUs or CPU clusters. These services can handle batch inference, request batching, and optimized hardware utilization, which dramatically improves performance and reduces cost compared to invoking models individually through serverless functions.

5. Content delivery networks (CDN) also play an important role. By caching API responses closer to users via services like Cloudflare or Akamai, the system reduces load on backend services and speeds up response times globally.

In practice, a redesigned architecture might work as follows: trending news recommendations are generated every few minutes via batch ML jobs; results are stored in Redis and served via a CDN. When a user request arrives, the system first checks the cache. Only if the result is not cached does the system call the model-serving endpoint. This dramatically lowers the number of expensive ML inference operations.

References:

[https://aws.amazon.com/machine-learning/](https://aws.amazon.com/machine-learning/)[https://cloud.google.com/architecture/mlops-continuous-delivery-and-automation-pipelines-in-machine-learning](https://cloud.google.com/architecture/mlops-continuous-delivery-and-automation-pipelines-in-machine-learning)[https://redis.io/solutions/caching/](https://redis.io/solutions/caching/)

*Dr. Haba:*

*Nice answer. This exercise is challenging because the solution is not directly related to the machine learning (ML) deployment itself. As an AI Solution Architect, I often encounter situations where the ML inference engine is mistakenly blamed for latency issues, while the real problem typically lies with server deployment. Although this primarily falls under DevOps, I recommend running load-balancing tests and exploring various caching strategies, such as caching the most recent or most frequently accessed content.*

*The purpose of this exercise is to highlight that an architect must have a comprehensive understanding of every component within a project. For instance, a CNN image classifier, the Butterfly app, or the LLM Horoscope app may take around 16 to 28 seconds to respond. However, when examining the details using Jupyter Notebook, the CPU and system time are approximately 230 milliseconds (1/4 of a second). The average round-trip time of 22 seconds is primarily due to network transport time between servers, including Hugging Face, as well as the upload and download speeds for images and donut charts.*

1. As an international news organization, how would you use ML to combat the spread of "fake news"?

For an international news organization, machine learning can play a critical role in identifying and limiting the spread of misinformation. The goal is not to replace journalists but to provide automated intelligence tools that help detect suspicious or misleading content at scale.

One of the most important applications of ML in this area is automated text classification. Natural language processing models can analyze news articles, social media posts, and headlines to identify patterns associated with misinformation. These models are trained on datasets containing both verified news articles and known examples of false information. By learning linguistic patterns such as sensational language, inconsistent facts, or emotionally manipulative phrasing, the model can estimate the probability that a piece of content is misleading.

Modern NLP systems often rely on transformer-based models such as BERT developed by Google, or GPT models developed by OpenAI. These models can analyze the semantic meaning of text rather than just individual keywords, making them more effective at detecting subtle misinformation.

Another important strategy is source credibility analysis. ML systems can evaluate the historical

reliability of a news source by analyzing past content, citation patterns, and correction history. For example, if a particular website frequently publishes articles that later require fact-check corrections, the system can automatically assign it a lower credibility score. When new content from that source appears, it may be flagged for additional review.

Machine learning can also help identify coordinated misinformation campaigns by analyzing social network behavior. Graph analysis techniques allow the system to detect patterns where large numbers of accounts simultaneously share the same article or message. These patterns may indicate bot networks or coordinated manipulation efforts. Companies such as Meta and Twitter have used similar approaches to detect influence campaigns and automated bot activity.

Image and video verification is another critical area. Modern misinformation campaigns frequently use manipulated images or videos. Computer vision models can detect signs of manipulation such as altered pixels, deepfakes, or inconsistent lighting patterns. Deepfake detection tools often rely on neural networks trained to recognize artifacts generated by generative models.

Another powerful technique is cross-reference fact verification. ML systems can compare claims in an article with trusted knowledge bases such as Wikidata or other verified news databases. If a claim contradicts verified information or lacks corroborating sources, the system can flag it for editorial review.

In practice, a large international news organization might implement a workflow where every incoming article passes through an ML pipeline. The system performs text classification to estimate misinformation probability, checks the credibility of the source, analyzes propagation patterns across social media, and verifies factual claims against trusted databases. Articles that exceed certain risk thresholds are automatically sent to human fact-checkers for verification before being widely distributed.

References:

[https://ai.googleblog.com/2020/06/detecting-misinformation-with-ai.html](https://ai.googleblog.com/2020/06/detecting-misinformation-with-ai.html)

[https://www.brookings.edu/research/how-artificial-intelligence-can-help-fight-fake-news/](https://www.brookings.edu/research/how-artificial-intelligence-can-help-fight-fake-news/)

[https://www.sciencedirect.com/science/article/pii/S2666651021000038](https://www.sciencedirect.com/science/article/pii/S2666651021000038)

*Dr. Haba:*

*Interesting answer. I posed this question to encourage deeper reflection on the complexities of combating fake news. The main challenge is identifying false information, especially given the increasing sophistication of large language models (LLMs) that can generate convincing misinformation. Open-source LLMs, in particular, often lack the safeguards needed to prevent the spread of fake news, making the task even more difficult.*

*No news organization currently has the resources to build a machine learning server that uses a reinforcement learning algorithm to continuously improve; it's simply too costly. While tech giants like Google, Facebook, Apple, and Microsoft have the resources to address this issue, the return on investment or the potential impact might not align with their corporate interests. Governments may have the funding to support such initiatives, but they often lack the governance and expertise necessary for effective implementation.*
