# Challenge 9

1.  Machine Learning (ML) has demonstrated an ability to identify data patterns that exceed human capabilities. This raises the question: if an ML model can predict the likelihood of a crime by recognizing specific patterns, would you, as an AI solution architect, be willing to act on such predictions? Would you consider taking preventive measures or incarcerating a potential offender before the crime occurs? Moreover, what safeguards would you put in place to ensure the system's reliability and accuracy?

As an AI Solution Architect, I would approach the use of predictive policing systems cautiously, considering their potential benefits and ethical implications. I would not support incarcerating a potential offender before a crime occurs solely on the basis of a probabilistic prediction. A prediction is not proof of intent, nor is it a completed action. Preventive measures must be proportionate and non-punitive. For example, a model identifying elevated risk in a region might justify allocating social services, community programs, or increased lighting and infrastructure improvements—not preemptive detention.

The academic analysis in these two documents "[Algorithmic fairness in predictive policing](https://link.springer.com/article/10.1007/s43681-024-00541-3)" - AI and Ethics and “[Code is law: how COMPAS affects the way the judiciary handles the risk of recidivism](https://link.springer.com/article/10.1007/s10506-024-09389-8)" - Artificial Intelligence and Law highlight concerns about bias and unfairness in such systems, which could lead to disproportionate targeting certain demographics.

Specifically, the first paper discusses how fairness metrics such as equalized odds and demographic parity can conflict with each other, forcing policymakers to make explicit trade-offs rather than hiding behind technical neutrality. In terms of preventing crime, it's important to remember that while ML models can identify patterns, they do not inherently understand the context or moral implications of those patterns.

The second paper demonstrates that while COMPAS, a risk assessment tool used in U.S. courts, may achieve reasonable aggregate predictive accuracy, calibration differs across demographic groups. The algorithm begins shaping sentencing behavior, effectively becoming a normative actor within the justice system.

Therefore, I would not advocate for taking preventive measures or incarcerating a potential offender based solely on predictions, as this could infringe upon civil liberties and lead to unjust outcomes.

Human review must remain central. Algorithms can inform risk assessment but should never autonomously determine deprivation of liberty. Transparency is essential, because without it, we risk transforming statistical correlation into institutionalized discrimination.

To ensure the system's reliability and accuracy, several safeguards can be put in place:

- Transparency: The workings of the model should be explainable, allowing for a better understanding of how decisions are made. This could help identify and correct any bias or errors.

- Auditing: Regular audits and tests should be conducted to assess the system's accuracy and fairness over time.

- Public oversight: Public involvement in the development and oversight of these systems is crucial to ensure accountability and trust.

*Dr. Haba:*

*Interesting answer. Pre-crime prediction has transitioned from science fiction to reality, with AI-driven technologies already in use. For instance, predictive policing in Los Angeles analyzes data to forecast crime hotspots, while AI is employed in finance to detect potential fraud before it occurs. As AI solution architects, we possess the technical expertise necessary to design these systems, but this is only one part of the equation. To ensure these technologies are effective, ethical, and socially responsible, we must collaborate with domain experts, government privacy officials, and social psychologists. Their insights and expertise are crucial for developing practical, balanced, and ethical solutions for all stakeholders and users, ensuring these technologies operate effectively within the complexities of our world.*

1. Which is more reliable: a fully autonomous ML-powered vehicle or a vehicle equipped with ML-powered driver assistance? If the fully autonomous vehicle faced a decision between causing significant damage to your car or hitting a deer crossing the street, how would you instruct the ML algorithm to respond?

Property damage is financially recoverable; loss of life, any kind of life, is not. In the case of a decision between causing significant damage to my car or hitting a deer crossing the street, I would instruct the ML algorithm to prioritize avoiding harm to other road users, including pedestrians and animals, over protecting the vehicle. The system should brake maximally and maintain lane stability to avoid secondary collisions, accepting vehicle damage if necessary to prevent harm to people. Striking wildlife may sometimes be unavoidable, but swerving into oncoming traffic to avoid a deer would typically increase overall risk.

A fully autonomous vehicle, which operates independently without human intervention, may be more reliable in the long run because it eliminates the potential for human error caused by distraction, fatigue, or impairment. From a systems perspective, fully autonomous vehicles have the advantage of eliminating human error factors such as distraction, intoxication, and fatigue.

On the other hand, driver-assistance systems (Level 2 or 3 autonomy) can introduce ambiguity, as the human operator may overtrust the automation. This “automation complacency” has been documented in human factors research. Therefore partial automation can sometimes be less predictable than full autonomy, because responsibility is split.

The reliability question in autonomous mobility is more empirical. The [Moral Machine experiment](https://www.moralmachine.net/) conducted by the MIT Media Lab collected 40 million decisions from 2 million respondents about ethical dilemmas in autonomous driving. The data revealed significant cultural variation in moral preferences regarding age, social status, and number of lives saved. The takeaway was sobering: there is no universally accepted moral consensus to encode into a vehicle’s decision logic.

The September 2024 article *“*[Ethical Considerations of the Trolley Problem in Autonomous Driving](https://www.mdpi.com/journal/wevj)” in the World Electric Vehicles Journal argues that focusing narrowly on trolley-style dilemmas oversimplifies real-world driving ethics. In reality, autonomous systems are designed to minimize risk probabilistically rather than to choose between clearly defined victims. The article suggests shifting from dramatic moral hypotheticals to harm minimization frameworks grounded in traffic safety engineering.

When we look at operational data, companies such as [Waymo](https://waymo.com/safety/impact/) have reported over 22 million rider-only miles and statistically significant reductions in injury-causing crashes compared to human drivers, according to their public safety reports. While such reports should always be independently verified, the trend suggests that in controlled deployment domains, fully autonomous systems can outperform average human drivers in certain safety metrics.

The central insight from autonomous driving is that machine learning should augment human safety, not override human dignity. Reliability must be defined not just statistically but ethically.

The question is not whether machines can outperform humans in pattern recognition. They often can. The real question is how we constrain their deployment so that technical capability does not outpace moral responsibility.

*Dr. Haba:*

*Nice answer. This question feels more suited for a blockbuster movie than our class discussion. :-) As an AI Solution Architect, I would prefer to implement driving assistance technology over fully autonomous driving. Driving assistance is a more manageable project with a narrower focus, making it easier to design and implement.*

*Regarding the ethical dilemma of choosing between saving your car or sparing a deer, this scenario mostly serves as a thought experiment. In reality, our jobs often involve making moral decisions that are rarely as dramatic as this one. We do strive to create an ethical ranking score, though it may seem arbitrary, because it is the best tool we have for navigating the complex moral landscape of AI-driven decisions.*
