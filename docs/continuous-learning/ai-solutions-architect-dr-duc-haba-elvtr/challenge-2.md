# Challenge 2

**How can you effectively communicate to stakeholders that their acceptance criteria or KPIs are unrealistic for a machine learning project?**

As an AI Architect this is one of the most important parts of the job. The job is not to protect the model but to protect the business from magical thinking. Navigating the gap between business requirements and technical feasibility is one of the most critical parts of the role. When stakeholders present unrealistic KPI, often fueled by AI hype or a misunderstanding of how stochastic systems work, the AI Architect must act as a "translator" rather than a "gatekeeper."

The goal is not to tell stakeholders they’re wrong, but to reframe expectations using evidence, trade-offs, and risk language they already understand.

Effectively communicating these limitations requires a shift from saying "We can't do this" to "Here is the cost, risk, and data requirement to get closer to that goal."

Below is a practical approach and fictitious examples, and the exact framing I’d use in executive and product conversations.

1. Most stakeholders think ML behaves like traditional software. The first job is to reset the mental model. Is a Probabilistic vs. Deterministic Thinking. Educate stakeholders on the difference between traditional software (if X, then Y) and ML (if X, then probably Y)

What I’d say: “I want to align on something important: machine learning systems don’t converge on certainty but probabilities. So acceptance criteria need to reflect risk, not perfection.”

2. Translate KPIs into ML Reality Stakeholders often define KPIs like 100% accuracy, zero hallucinations, Fully automated, No human review, etc. These are business desires, not ML requirements.

Break each KPI into What signal are we measuring?, Under what data distribution? At what cost and risk?

Playbook for AI Architect to avoid stakeholders confrontation:

1. Use Facts, Benchmarks and Baselines

What not to say:  “OpenAI / Google / Meta can’t do this either.”

What to say: “State-of-the-art systems on public benchmarks achieve X under controlled conditions. Our data is noisier, more domain-specific, and higher risk.”

This grounds expectations and avoids vendor comparisons

2. Instead of rejecting KPIs outright, propose roadmaps:

Example

Phase 1 (Pilot):

- Offline metrics

- Human-in-the-loop

- Error analysis

Phase 2 (Limited Production):

- Narrow scope

- Guardrails

- Manual override

Phase 3 (Scale):

- KPI tuning

- Cost optimization

- Expanded automation

3. When KPIs are unrealistic, I explicitly ask: “If the system meets this KPI but makes a high-impact mistake, who owns the risk?” This usually triggers further analysis such as Legal, Compliance and Security

4. Never Say “Impossible”.  Instead say: “High risk”, “Not measurable”, “Unstable at scale”, “Requires trade-offs” and “Not observable with current data”

5. Summary: The Architect’s Playbook

To communicate unrealistic ML KPIs effectively:

1. Validate the business goal

2. Reframe ML as probabilistic, not deterministic

3. Anchor the discussion in data and trade-offs

4. Translate ML metrics into business risk

5. Offer safer, phased alternatives

6. Make risk ownership explicit

#### Fictitious Examples

**1.** Fraud Detection with “Zero False Positives”

Stakeholder KPI: “We want 99% fraud detection accuracy with zero false positives.”

Step 1: Expose the Trade-Off.  “In fraud systems, accuracy is a misleading metric. Improving recall always increases false positives.”

Step 2: Quantify the Cost of Perfection. “To eliminate false positives entirely, the model would only flag the most obvious fraud. That would let ~40% of real fraud through.” Now perfection sounds expensive.

Step 3: Replace with Business-Aligned Metrics. Instead of zero false positives, I’d recommend:

- Cost-weighted loss (fraud loss vs customer friction)

- Separate KPIs for high-value transactions

- Manual review thresholds based on risk score

**2. ** LLM Hallucinations (“It Must Never Be Wrong”)

Stakeholder Requirement:  “The chatbot must never hallucinate or give incorrect answers.”

Step 1: Normalize the limitation: “No probabilistic language model can guarantee zero hallucinations, just like no human agent is correct 100% of the time.”

Step 2: What we can control is:

- Where the model is allowed to answer

- When it must refuse

- How uncertainty is handled

Step 3: Propose acceptance criteria that make sense. A realistic acceptance framework would be:

- <1% hallucinations on curated test sets

- Mandatory citations from approved sources

- Explicit ‘I don’t know’ responses when confidence is low

*Dr Haba: *

*Nice answer. Letting data drive the discussion is essential, whether we address training and QA data issues, machine learning readiness, deployment challenges, benchmark results, or measurable outcomes. Facts and metrics keep conversations focused and productive, ensuring that decisions are based on evidence rather than assumptions. One of the biggest missteps in a major meeting is blindsiding stakeholders with unexpected schedule delays. Instead of waiting until everyone is gathered to reveal setbacks, communicate early. Keeping stakeholders informed ahead of time allows for adjustments to be made proactively, preventing last-minute panic and rushed decisions.*

*This approach is about more than just damage control. It builds trust and transparency. When stakeholders see that challenges are being managed with foresight and professionalism, confidence in the team grows. Meetings then become a space for problem-solving and strategy, rather than reacting to surprises. The result? More effective collaboration, fewer disruptions, and a smoother path forward.*
