# Challenge 3

**Thought Experiment: What are your questions when clients or stakeholders say, "We have all the data that we need for the Machine Learning (ML) project?"**

Regarding data, I understand that in ML the questions should be more comprehensive like: Do you have the right data, with the right labels, at the right quality, with the right permissions, for the right business outcome? As a consequence, before moving forward we need to validate: label quality, representativeness, access, drift, and whether it supports the business decision. We could confirm this with a data audit.

The right questions in more detail:

**A)** Do you have enough data for the rare cases?

What’s the positive class rate? How many positives do we have?

Example: “We want to detect production incidents early”. If incidents happen 2 times per quarter, you don’t have enough supervised data for ML, then you’ll need rules including anomaly detection, human-in-the-loop and a good simulation test.

**B)** Is all the data accessible?

Data is not always queryable, extractable, permitted to be accessed.

I’d ask: Where does it live? On-Prem, SaaS? Can we legally use it?  Who owns it?

Example: A Healthcare organization might say, “We have the patient notes.” But Legal says we cannot export outside environment, we cannot use for training without specific consent, etc

**C)** What exact decision will the model improve? What is the model supposed to change? Who uses the output? What action happens after the prediction?

Example: “We want churn prediction.” My follow-up would be asking: What action happens when churn risk is high? Discount? Outreach? Product intervention? If there is no action, churn prediction becomes a dashboard, not a business solution.

**D)** What is the target label and how is it defined?

Most ML projects fail because the label is unclear. What’s the source of truth? Who created it? Is it consistent across teams?

Example: A FinTech “We have fraud labels.” Follow-up: “Is ‘fraud’ confirmed by chargeback? Manual review? customer complaint? suspicion score?

Also this might also uncover Hidden Biases: What geographic regions, time periods, and customer segments are missing?

Example: Financial fraud detection trained only on East Coast data failed miserably in California.

**E)** What’s the refresh rate and data drift risk?

What’s the frequency of data being updated? Do definitions change? Does the business process change?

Example, Marketing model trained on 2022 campaigns fails in 2026 because customer behavior changed, acquisition channels changed, or privacy rules changed.

**F)** How much data is usable after cleaning?

Stakeholders often count “rows” as value. But how many rows have missing critical fields? How many are duplicates? How many are inconsistent? How many are outdated?

Example: “We have 10 million support tickets.” Reality is that 30% missing customer ID, or 20% duplicated from merges, or 40% are “test tickets” from internal QA

**G)** Data Quality & Completeness. How recent is the newest data? Also it is important to establish what is the data coverage percentage across all predicted scenarios.

Example: a retail client claimed complete customer data, but had zero records for customers over 70 - missed 15% of their market

*Dr Haba:*

1. *Nice answer. When talking to the client, highlight that the Data Engineering team will soon assess the data. If your team is currently short-staffed or still in the onboarding process, you should carry out an initial check as the AI solution architect. This process involves logging in to access the data and reviewing key aspects such as data completeness, size, privacy, potential biases, and relevance. This initial review can help identify any immediate issues and ensure that the data is ready for more in-depth analysis by the engineering team.*

**Thought Experiment: What are your reactions when you read: "AI took my job and ruined me."**

I can share a clear example about this: My wife worked at Google for about 11 years, and her entire team was laid off and replaced by AI, with only one human kept in the loop. She previously worked on Google Search ad review and campaign operations. A highly trained team, long tenure and deep institutional knowledge, replaced by automation and leaving one human in the loop.

For ad review specifically, that’s scary because mistakes aren’t harmless as false approvals can enable scams, fraud, harmful content, false rejections can destroy legitimate businesses and policy enforcement becomes inconsistent. Unfortunately these jobs were already structured like pipelines, which makes them easier to automate.

My wife's team was not replaced by AI. Instead they were replaced by Google's profit margins. Here's what I know about Google's ad review automation:

2019-2023: Google gradually automated ad policy enforcement

2024: Major layoffs hit ad review teams globally

2025: "One human oversight" became the standard

The AI isn't actually doing my wife's job. It's doing 30% of her job with 70% accuracy, but Google calculated that's "good enough" when multiplied by the cost savings of eliminating 40+ salaries.

She was not replaced by AI, but she was replaced by executives who confused cost reduction with value creation and Artificial intelligence with actual wisdom.

A responsible organization would pair AI rollout with internal mobility paths, paid reskilling, staged adoption, redeployment before layoffs, etc.

My wife's story isn't about A or about a cool AI success story. It's about what happens when we forget that technology should serve humanity, not replace it. This is a real life event, a major operational and ethical shift,  and it was paid for with real people’s lives.

So when someone says “AI ruined me,” I don’t argue.

*Dr Haba:*

1. *Interesting answer. I empathize with the speaker, but as the AI Solution Architect, I know that Artificial General Intelligence (AGI) is not a reality. Therefore, it is not the AI's fault but rather the fault of their manager, who does not understand the use of LLM. Instead of reducing the staff, the manager should focus on increasing revenue. To make an analogy, if GenAI makes us better at catching fish, the manager should maintain the same number of fishermen and increase the fish quota rather than reducing the number of fishermen to catch the same amount of fish.*

**Thought Experiment: When should you onboard the QA team for an ML project?**

Immediately, at project kickoff. QA should be involved from Day 1 of project conceptualization. Not before the release or after the model is trained. Shift left as much as we can is the best decision.

If QA sees the model for the first time 2 weeks before launch, you've already failed. They should know the model's weaknesses better than the data scientists who built it.

QA must be present during the requirements, the Data Collection, development sprints, pre-development and post-development phases. They also should be present during the definitions about what “correct” and “failure” means. What the system is allowed to do and what must never happen.

I understand  that ML QA is different from traditional software QA. Traditional QA checks deterministic outputs (ML is non-deterministic by definition), clear expected results and stable behavior.

ML systems are probabilistic, change over time, dependent on data quality, sensitive to prompt changes, model version changes, and edge cases.

What QA should do early is the following:

**A)** Define acceptance criteria that are testable. QA helps turn vague requirements into verifiable tests. Example: Precision ≥ 0.85 on high-risk class, recall ≥ 0.70, and no more than 2% false positives.

**B)** Build the test dataset strategy. Define the test set and determine if is it representative or not, include edge cases, etc

Example: Toxicity moderation. QA has to create tests like: toxicity, profanity, slurs, multilingual text, false positives, etc.

**C) **Define “model failure modes”

QA should document, false positives, false negatives, fairness issues, latency spikes, outages and degraded mode behavior

When QA is onboarded too late the project might result in unwanted issues such as “accuracy looks good” but production is unstable, no monitoring plan, no test harness, no rollback strategy or no baseline comparison.

Best practice timeline. Phase-by-phase QA responsibilities:

**Week 1-2:** Requirements Phase

- QA reviews: "How will we test if this model is fair?"

- Example: QA flagged that loan approval model needed testing across zip codes, not just overall accuracy

**Week 3-4**: Data Collection

- QA audits data quality, identifies edge cases

- Creates test datasets that mirror production complexity

- Example: Caught that "comprehensive" dataset had zero examples of Hispanic surnames

**Development Sprints**:

- QA continuously validates model outputs against business rules

- Tests model behavior on adversarial inputs

- Example: Chatbot QA discovered model gave different salary negotiation advice based on perceived gender from names

**Pre-deployment**:

- QA leads the \*\*model risk assessment

- Validates monitoring systems actually work

- Signs off on \*\*rollback criteria

**Post-deployment**:

- QA monitors drift, bias amplification

- Owns the \*\*incident response playbook

- Example: QA caught that recommendation engine started suggesting extreme content after 6 months due to user behavior drift.

*Dr Haba:*

1. *Good answer. You've rightly recognized the importance of onboarding the data engineering, AI scientist, and ML QA teams at the project's outset. To ensure the project's success, it's essential to have a clear document detailing the parallel work each team will undertake. By the end of Phase 1 in our data-driven process, we should define the API, establish accuracy benchmarks, and outline the QA process. This structured approach will help align the teams and set a solid foundation for the project's following stages.*
