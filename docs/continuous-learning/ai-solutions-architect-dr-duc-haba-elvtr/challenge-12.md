# Challenge 12

1. Your company relies heavily on Generative AI (GenAI) to train and develop new sales associates and programmers. GenAI effectively bridges the competence gap between junior employees and top-performing senior employees. Would your company consider paying its younger employees the same salary as experienced employees? Please explain your reasoning.

Even if generative AI tools significantly reduce the skill gap between junior and senior employees, most organizations would not pay junior employees the same salary as experienced professionals. GenAI bridges execution gaps, not judgment gaps.

The reason is that salary reflects accumulated expertise, judgment, accountability, and the capacity to handle complex, ambiguous situations that AI cannot reliably manage.

The company should adopt a performance-adjusted compensation model. If a junior employee, augmented by Gen AI consistently delivers senior-level outcomes, then their compensation should reflect that. This creates an incentive structure that rewards results rather than tenure. Think of it as compressing the timeline to higher pay, not flattening the criteria for it.

Generative AI clearly improves the productivity of less experienced workers. Multiple studies show that AI tools help junior employees perform tasks that previously required more experience. For example, research examining generative AI in programming found that AI-assisted tools increased code output by more than 50%, with the strongest gains observed among entry-level developers. Another set of studies reported that junior workers experienced productivity gains of around 27–43% when using AI coding assistants, while senior developers saw smaller improvements of roughly 8–17%.

At first glance, these numbers might suggest that the economic value of junior employees should converge with that of senior employees. However, productivity improvements on routine tasks do not equate to the full scope of professional competence. Experienced employees bring several forms of tacit knowledge that AI cannot easily replicate. Senior engineers, for instance, typically possess deep understanding of system architecture, long-term maintainability, risk assessment, and business impact. These capabilities allow them to evaluate AI-generated output critically. In contrast, inexperienced workers may accept AI suggestions without recognizing subtle errors or security flaws, which can introduce technical debt or vulnerabilities.

Another factor influencing compensation is responsibility. Senior employees are typically accountable for decisions that affect large systems, financial outcomes, or legal exposure. An organization may rely on them to approve architectural designs, sign off on deployments, or mentor junior colleagues. Even if AI helps junior staff perform certain tasks at a higher level, organizations still rely on experienced professionals to oversee quality and manage risk.

Finally, compensation reflects long-term career incentives. Organizations intentionally maintain salary progression to motivate employees to develop expertise over time. If junior employees were immediately paid the same as senior staff, the incentive structure that encourages professional development would weaken.

External sources:

1. Bank for International Settlements – Generative AI and productivity
    [https://www.bis.org/publ/work1208.htm](https://www.bis.org/publ/work1208.htm)

2. Jonathan Albarran – AI Transformation of Knowledge Work
    [https://jonathanalbarran.com/insights/ai-transformation-of-knowledge-work/](https://jonathanalbarran.com/insights/ai-transformation-of-knowledge-work/)

3. AI Buzz – GenAI Coding Tools and Developer Skill Gap
    [https://www.ai-buzz.com/gen-ai-coding-tools-senior-gains-widen-developer-skill-gap](https://www.ai-buzz.com/gen-ai-coding-tools-senior-gains-widen-developer-skill-gap)

*Dr. Haba:*

* Interesting answer. The case study highlights how generative AI, such as GPT-4, has the potential to bridge the skill gap between novice and experienced employees. However, this approach has its limitations. When seasoned professionals use generative AI to refine their expertise and enhance their skills, the gap can not only close but actually widen. While generative AI is a powerful tool for accelerating learning and skill acquisition, it cannot replicate the depth of understanding and nuanced decision-making that come from years of hands-on experience. This creates an intriguing dynamic: the technology that aims to level the playing field can also enable experienced individuals to push their capabilities further, emphasizing the irreplaceable value of real-world practice and expertise.*

1. Your company's legal department has raised concerns about whether large language models (LLMs), such as those similar to GPT-4 or Gemini, use private data in their training processes. While companies specializing in GenAI have not disclosed the percentage of public versus private data involved in training their LLMs, your competitors are already utilizing these models. As an AI Solution Architect (AISA), what is your recommendation regarding the use of LLMs?

Leading LLM providers have not been fully transparent about the composition of their training data. Litigation is ongoing in multiple jurisdictions regarding copyright and private data ingestion.

The question about LLM training data is both legal and strategic. LLM systems are trained on massive datasets containing publicly available text, user-generated content, and sometimes copyrighted material. Because the exact composition of these datasets is often undisclosed, organizations worry about whether private or proprietary information might have been included.

There are also documented legal controversies regarding how some models were trained. In one high-profile case, an AI company digitized millions of books and even downloaded millions from piracy websites to train its models. A U.S. court ruled that training on lawfully acquired books could qualify as fair use, but the use of pirated content remained legally problematic. These disputes highlight the broader uncertainty around intellectual property in the generative AI ecosystem.

From a purely defensive perspective, one might conclude that organizations should avoid LLMs until full transparency exists about training data sources. However, as an AI Solutions Architect advising a competitive business, that approach would be unrealistic. Competitors are already integrating LLM capabilities into development, marketing, analytics, and customer support. Ignoring these technologies could place a company at a severe strategic disadvantage.

Instead, the rational recommendation is a controlled adoption strategy that balances innovation with governance.

Organizations should prefer enterprise-grade or private LLM deployments. Public API-based LLMs (e.g., GPT-4 via OpenAI's API) carry higher exposure risk since data may be used for further training unless enterprise agreements explicitly prohibit it. The company should prioritize vendors offering *enterprise data agreements* with explicit no-training guarantees, or evaluate *self-hosted/private deployment* options (e.g., open-weight models like LLaMA or Mistral deployed on-premises), where data never leaves the company's environment. Public LLM services sometimes store or analyze prompts, which means that confidential information entered into the system may be used to improve future versions of the model or processed by third parties. Private or enterprise versions mitigate this risk by ensuring that the organization’s data is not used to retrain public models and remains isolated within controlled environments.

Companies must implement strict data-handling policies. Employees should never input sensitive client information, proprietary algorithms, or confidential business strategies into public AI tools. The legal implications can be significant because sharing protected information with an external AI system could violate privacy regulations such as GDPR or CCPA, as well as contractual obligations like NDAs.

Third, organizations should build governance frameworks for AI usage. This includes auditing AI outputs, maintaining logs of model interactions, and establishing review processes for high-risk decisions. AI systems are powerful pattern recognition tools, but they can also reproduce biases, inaccurate information, or fragments of training data. Human oversight remains essential.

Finally, companies should maintain technological independence where possible. Many organizations are beginning to deploy internal LLMs or hybrid architectures combining open-source models with proprietary datasets. This approach reduces dependency on external vendors while allowing the organization to control its own data lifecycle.

The recommendation is not to avoid LLMs, but to adopt them responsibly. The competitive advantages of generative AI—improved productivity, faster knowledge retrieval, and automation of routine cognitive tasks—are too significant to ignore. However, organizations must pair adoption with strong data governance, legal awareness, and technical safeguards.

External sources:

1. Data Mastery – Privacy and LLMs
    [https://datamastery.pro/blog/privacy-and-llms-balancing-innovation-and-user-rights](https://datamastery.pro/blog/privacy-and-llms-balancing-innovation-and-user-rights)

2. Business Insider – AI Training Data and Copyright Case
    [https://www.businessinsider.com/anthropic-cut-pirated-millions-used-books-train-claude-copyright-2025-6](https://www.businessinsider.com/anthropic-cut-pirated-millions-used-books-train-claude-copyright-2025-6)

Geldards Law Firm – Copyright and Confidentiality Issues with LLMs

[https://www.geldards.com/insights/what-are-the-copyright-and-confidentiality-issues-arising-from-use-of-public-and-private-large-language-models-llms/](https://www.geldards.com/insights/what-are-the-copyright-and-confidentiality-issues-arising-from-use-of-public-and-private-large-language-models-llms/)

*Dr. Haba:*

*Good answer. The AI, machine learning (ML), and generative AI (GenAI) industries have long faced challenges regarding the use of private data in training large language models (LLMs). While legal regulations clearly state that using or deploying solutions that contain "private" data is not permissible, the industry struggles to define what exactly constitutes "private data" and at what point its use becomes illegal.*

*Despite the urgent need for transparency in the use of private data, the potential benefits of LLMs may outweigh these concerns. Private LLM companies like OpenAI and Google need to disclose the percentage of private data used in training their models. This transparency is crucial to balancing ethical considerations with the immense potential of these technologies.*
