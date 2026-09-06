# Challenge 6

1. **Is fairness or bias a quantitative or qualitative value?**

Fairness is both quantitative and qualitative.

Quantitative metrics provide measurable, scalable assessment through formulas like demographic parity, equalized odds, and calibration. Qualitative methods provide context, capture justice principles, and surface issues metrics miss. Best practice requires integrating both through iterative measurement, stakeholder engagement, and ethical deliberation.

What feels “fair” in lending, hiring, or content moderation depends on cultural norms, legal frameworks, and stakeholder expectations. You can’t discover fairness the same way you discover latency or throughput.

Quantitative Fairness Metrics:Demographic Parity, Equalized Odds, Predictive Parity (Calibration) and Equal Opportunity.

Modern AI governance frameworks rely heavily on mathematical definitions of fairness that produce numerical metrics we can track over time. A useful analogy is “performance.” Everyone agrees performance matters, but what performance means depends on context. A race car and a delivery truck both need to perform, yet we measure one in lap times and the other in on-time deliveries.

Fairness works the same way: the meaning is qualitative, but the enforcement must be quantitative, or it stays aspirational and unenforceable.

Qualitative dimension of fairness: Fairness is deeply rooted in human ethical principles, social context, historical injustices, and value judgments that cannot be fully captured by mathematical formulas.

Qualitative is essential as provides: Contextual Understanding, Historical and Social Context, Stakeholder Perspectives and Unintended Consequences.

Real-world example: Microsoft's Hiring AI. Microsoft's approach to fair hiring AI demonstrates this integration:

- Quantitative: Tracks demographic parity (interview rates), equalized odds (false negative rates for qualified candidates), and calibration (prediction accuracy) across gender, race, and age

- Qualitative: Conducts quarterly focus groups with hiring managers, candidates from underrepresented groups, and diversity & inclusion teams

- Outcome: In 2025, metrics showed equal interview rates (quantitative ✓), but focus groups revealed women felt questions were coded in masculine language (qualitative ✗)

As a conclusion, fairness is both quantitative and qualitative.

Sources and References:

- [https://learn.microsoft.com/en-us/azure/machine-learning/concept-fairness-ml](https://learn.microsoft.com/en-us/azure/machine-learning/concept-fairness-ml)

- [https://shap.readthedocs.io/en/latest/example\_notebooks/overviews/Explaining%20quantitative%20measures%20of%20fairness.html](https://shap.readthedocs.io/en/latest/example_notebooks/overviews/Explaining%20quantitative%20measures%20of%20fairness.html)

- [https://dl.acm.org/doi/10.1145/3616865](https://dl.acm.org/doi/10.1145/3616865)

- [https://www.geeksforgeeks.org/artificial-intelligence/fairness-metrics-demographic-parity-equalized-odds/](https://www.geeksforgeeks.org/artificial-intelligence/fairness-metrics-demographic-parity-equalized-odds/)

- [https://fairlearn.org/main/user\_guide/assessment/common\_fairness\_metrics.html](https://fairlearn.org/main/user_guide/assessment/common_fairness_metrics.html)

*Dr. Haba:*

1. **Should fairness be an acceptance criterion in KPIs? How can it be measured?**

Yes, fairness should be an acceptance criterion, but not as a single universal KPI. Treating fairness as one number is usually a trap. Instead, fairness should function like a set of guardrails that models must stay within in order to be considered “acceptable for production.”

As of 2026, fairness has evolved from an ethical nice-to-have to a regulatory and business imperative. It should absolutely be an acceptance criterion in KPIs, and organizations that don't treat it as such face legal, reputational, and financial risks.

In practice, this looks similar to how we treat security or reliability. A model might hit its accuracy target, but if it systematically underperforms for a protected group, it fails acceptance. For instance, a credit scoring model could meet its business KPI for default prediction accuracy, yet still be rejected if approval rates for equally qualified applicants differ significantly across demographic groups.

A robust fairness KPI framework requires quantitative metrics, qualitative assessments, operational thresholds, and governance processes. Measurement depends on the domain, but it almost always involves comparing outcomes across cohorts. In healthcare triage, fairness might be measured by comparing false negative rates across age groups, ensuring no group is consistently under-prioritized. In content moderation, it could mean tracking appeal success rates by language or region to detect whether some users are disproportionately penalized.

The key architectural insight is that fairness KPIs are constraints, not optimization goals. You don’t usually want to “maximize fairness” at the expense of everything else; you want to ensure the system stays within acceptable fairness thresholds while optimizing for business value. This is why fairness metrics belong in model validation gates, dashboards, and ongoing monitoring, not just in a one-off ethics review.

From an AI solutions perspective, the real work isn’t picking a metric—it’s aligning stakeholders on which definition of fairness matters for that product, documenting the trade-offs, and making those trade-offs explicit in acceptance criteria. Once that alignment exists, fairness becomes something you can test, monitor, and govern, rather than something you hope for.

Sources and References:

- [https://samta.ai/blogs/ai-governance-kpis-for](https://samta.ai/blogs/ai-governance-kpis-for)

- [https://neontri.com/blog/measure-ai-performance/](https://neontri.com/blog/measure-ai-performance/)

- [https://www.visioneerit.com/blog/building-a-robust-ai-governance-framework-in-2026](https://www.visioneerit.com/blog/building-a-robust-ai-governance-framework-in-2026)

- [https://verifywise.ai/lexicon/key-performance-indicators-kpis-for-ai-governance](https://verifywise.ai/lexicon/key-performance-indicators-kpis-for-ai-governance)

- [https://www.epcgroup.net/blog/ai-governance-metrics-model-performance-compliance](https://www.epcgroup.net/blog/ai-governance-metrics-model-performance-compliance)

-

[https://corporatefinanceinstitute.com/resources/data-science/ai-kpis-tracking-performance/](https://corporatefinanceinstitute.com/resources/data-science/ai-kpis-tracking-performance/)

*Dr. Haba:*
