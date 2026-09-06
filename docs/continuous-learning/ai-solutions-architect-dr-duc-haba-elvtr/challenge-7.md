# Challenge 7

1. How can you determine if the user feedback for your machine learning app is biased? For instance, could a small, vocal group of users be disproportionately influencing the results to benefit their own views unfairly?

Building machine learning applications and opening the gates for users to tell us how we are doing, we implicitly assume that the crowd is wise, that the aggregate of individual voices will converge on something resembling truth. This assumption is almost always wrong, or at least dangerously incomplete, and any AI Solutions Architect worth their salt needs to treat user feedback not as ground truth, but as often distorted signals that must be interrogated before it is trusted.

Determining whether user feedback is biased or not requires stepping back and treating feedback itself as a dataset subject to the same scrutiny as any training corpus. The first and most fundamental step in detecting bias is understanding who is actually giving you feedback. One of the most common and subtle failure modes is participation bias, where the users who provide feedback are not representative of the users who remain silent. I understand that the feedback volume follows this law distribution: a small percentage of users produce the majority of feedback. This creates the illusion of consensus when, in reality, it may simply reflect the persistence or motivation of a minority.

For example, imagine a machine learning system that recommends technical documentation articles to engineers. Suppose a small group of senior engineers dislikes beginner-oriented content and consistently downvotes those recommendations. If we blindly treat their feedback as representative, the model will gradually suppress beginner content, even though junior engineers—who may be less likely to provide feedback—are actually benefiting from it. The system begins optimizing for the loudest voices rather than the majority of users.

Another technique is to compare explicit feedback with implicit behavioral signals. Implicit signals are often more representative because they capture behavior from all users, not just those motivated to respond. If a user rates a recommendation positively but immediately closes the browser tab, that behavioral signal contradicts the explicit rating. If a user rates a model output negatively but spends six minutes reading it before navigating to related content, the behavior suggests the explicit rating may have been reflexive rather than reflective.

Explicit feedback includes ratings, thumbs up/down, or written comments. Implicit feedback includes actions such as whether users actually use the recommendation, how long they engage with it, or whether they return to the system.

It is also important to monitor feedback stability over time. Coordinated or disproportionate influence often appears as sudden spikes in feedback volume or sentiment. For example, if a new feature is released and negative feedback suddenly appears concentrated among a small cluster of accounts, that may indicate organized influence rather than organic dissatisfaction. Statistical techniques such as anomaly detection, clustering, and entropy analysis can reveal whether feedback diversity is shrinking or being dominated by specific users or viewpoints.

Finally not all feedback should be treated equally. A user who interacts with the system daily and has demonstrated engagement across diverse features may provide more reliable signals than a user who interacts once and leaves a single extreme rating. This is not about ignoring minority voices, but about contextualizing feedback based on usage patterns and representativeness.

External references:

1. [https://developers.google.com/machine-learning/crash-course/fairness/types-of-bias](https://developers.google.com/machine-learning/crash-course/fairness/types-of-bias)

2. [https://medinform.jmir.org/2022/5/e36388](https://medinform.jmir.org/2022/5/e36388)

3. [https://link.springer.com/article/10.1007/s44248-024-00007-1](https://link.springer.com/article/10.1007/s44248-024-00007-1)

4. [https://www.emergentmind.com/papers/1908.09635](https://www.emergentmind.com/papers/1908.09635)

*Dr Haba:*

*1. Interesting answer: Detecting bias in feedback is an essential task that requires careful examination due to the potential risks associated with skewed data. This process involves more than just simple checks; it requires the combined expertise of domain experts, data engineers, and AI solution architects.*

*A fundamental step in this process is to statistically assess the proportion of the audience or members providing feedback. When feedback primarily comes from a small, vocal minority, there is a high risk of bias that could distort the overall data. Identifying other types of bias can be even more challenging, as human opinions inherently carry biases.*

*Without thorough analysis, feedback may be misleading, leading to decisions that reflect the perspectives of a few individuals rather than the broader reality.*

1. How do you choose between A/B testing, user feedback, round-table discussions, or expert reviews when looking to improve the accuracy of your machine learning model? What factors influence your decision, and when is it more appropriate to use certain methods over others?

The real question is about what kind of uncertainty is trying to be resolved. Each evaluation method reveals a different kind of truth. How do we know what is true about the system? Some reveal statistical truth, others reveal behavioral truth, and others reveal structural or conceptual truth.

Each method is different, optimized to reveal a different class of truth, and selecting the wrong one is not merely inefficient — it can actively mislead you, giving you confident but wrong answers and causing you to move the model in the wrong direction.

The most effective strategy is not choosing one method, but orchestrating all of them in sequence. Expert review ensures the system is structurally sound. User feedback ensures it aligns with human expectations. Round-tables ensure it aligns with organizational and ethical goals. A/B testing ensures it performs optimally at scale.

A/B testing — presenting variant A of your model to one randomly selected cohort of users and variant B to another, then measuring which variant produces better outcomes on a predefined metric — is a genuinely powerful tool, but only when three conditions are met simultaneously. You must have a metric that accurately captures what you care about and that can be measured reliably at scale. Second, you must have sufficient traffic to achieve statistical significance within a reasonable timeframe. Third, the effect you are trying to detect must be large enough relative to the natural variance in your metric that the experiment will not require months of runtime to complete.

When these conditions are met, A/B testing is unparalleled for answering questions of the form "does change X improve outcome Y in our real production environment?" It is the closest thing to a controlled experiment you can run on real user behavior, and it eliminates most of the confounds that plague other methods. For instance, if you are trying to decide between two versions of a natural language processing model for classifying customer support tickets — one trained with a larger, more general dataset and one fine-tuned on your specific domain — an

However, A/B testing fails when the metric you are measuring is a proxy for something deeper that you cannot directly observe. Imagine you are building a mental health support chatbot and you want to evaluate a new empathy model against the current version. You could measure session length, user return rate, or even explicit satisfaction ratings. The variant that produces longer sessions and higher explicit satisfaction ratings might look like a clear winner in your A/B test. But if that variant achieves its results by telling users what they want to hear rather than what is therapeutically appropriate, you have optimized for engagement at the expense of genuine help, and your A/B test has led you toward harm. This is precisely the category of problem where A/B testing is insufficient, and where you need qualitative methods to interrogate the nature of the outcome, not just its magnitude.

User feedback is particularly valuable in early-stage systems, where metrics may be unreliable or incomplete. Feedback helps identify conceptual failures such as trust issues, perceived unfairness, or usability problems. Research into AI-generated feedback systems has shown that human-centered feedback can reveal subtle interaction issues and improve model usability and fairness.

Expert review is most appropriate when the correctness criteria for your model's output are domain-specific, require specialized knowledge to evaluate, and cannot be easily reduced to a behavioral metric. Medical diagnosis assistance, legal document analysis, financial risk modeling, and scientific literature summarization are all domains where the average user literally does not have the background to evaluate ground truth quality, and where the cost of error is high enough that you cannot afford to learn exclusively from aggregate user behavior. In these contexts, a structured expert review process — where domain specialists evaluate model outputs against carefully defined rubrics, ideally in a blinded fashion where the expert does not know which model version produced which output — gives you the highest quality signal on correctness and safety that you can obtain.

The limitation of expert review is cost and scalability. You cannot have cardiologists evaluate every echocardiogram interpretation your model produces. Expert review therefore works best at key decision gates: before a major model updates ships to production, when you are investigating specific failure modes that users have flagged, or when you are establishing the ground truth labels that will be used to train and evaluate the next generation of the model. Think of expert review as the method you use to calibrate your cheaper, faster evaluation methods. You use expert review to establish what "correct" looks like, then you use A/B testing and user feedback to measure whether you are achieving it at scale.

Round-table discussions serve a different purpose entirely. They bring together stakeholders with diverse perspectives, such as engineers, product managers, domain experts, and end users. These discussions are invaluable when the problem is ambiguous or multidimensional. Public policy research on algorithmic fairness has emphasized the importance of multidisciplinary roundtables to surface trade-offs, identify blind spots, and balance technical performance with ethical considerations.

External references:

1. [https://arxiv.org/abs/2307.03109](https://arxiv.org/abs/2307.03109)

2. [https://queue.acm.org/detail.cfm?id=3722043](https://queue.acm.org/detail.cfm?id=3722043)

3. [https://en.wikipedia.org/wiki/Expert\_review\_(method)](https://en.wikipedia.org/wiki/Expert_review_(method))

4. [https://www.brookings.edu/research/algorithmic-bias-detection-and-mitigation-best-practices-and-policies-to-reduce-consumer-harms/](https://www.brookings.edu/research/algorithmic-bias-detection-and-mitigation-best-practices-and-policies-to-reduce-consumer-harms/)

5. [https://academic.oup.com/jamiaopen/article/doi/10.1093/jamiaopen/ooae106/7826763](https://academic.oup.com/jamiaopen/article/doi/10.1093/jamiaopen/ooae106/7826763)

6. [https://arxiv.org/abs/2307.03109](https://arxiv.org/abs/2307.03109)

*Dr Haba:*

*Nice answer. This question is complex because there isn't a single "right" answer. The best approach depends on the project's specific scope and goals. AI solution architects often prefer passive data collection methods, such as analyzing browser history, articles read, videos watched, and site visit duration, to understand user preferences. This method helps mitigate biases that can arise from direct feedback, where questions may be poorly framed, and responses can be less than completely honest.*

*However, it's important to acknowledge that passive data collection is just one tool among many at our disposal. A/B testing provides concrete, data-driven insights; user feedback offers personal perspectives; round-table discussions foster in-depth dialogue; and expert reviews bring valuable experience and judgment. The key takeaway is that there is no one-size-fits-all solution. The chosen method must align with the project's unique needs to yield the most accurate and actionable insights.*
