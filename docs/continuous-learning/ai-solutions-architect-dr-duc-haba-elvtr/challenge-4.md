# Challenge 4

1. **Thought Experiment: **If there is no labeled data indicating that the text is toxic, such as harassment or sexual content, how would you assess the accuracy of the LLM model?

[Accuracy](https://developers.google.com/machine-learning/crash-course/classification/accuracy-precision-recall) definition assumes a ground truth, a reliable data. When there is no labeled data explicitly marking text as toxic or non-toxic, the concept of *accuracy* has to be redefined. Without labeled data, accuracy cannot be assessed with a single numerical score but with expert judgment, consistency checks, reference testing, and user feedback.

Without labels, there is no single objective truth to compare predictions against, so measuring accuracy in the classic sense becomes impossible.

In this situation, the first step is to remember that the model's output is probabilistic and not a factual determination. The model is estimating how likely a piece of text aligns with patterns it learned during training. Instead of asking “Is the model correct?” the better question is “is the model consistent, reasonable, and useful for the intended purpose?”

How to deal with no labeled data:

- One practical approach is [human-in-the-loop evaluation](https://cloud.google.com/discover/human-in-the-loop). Domain experts or reviewers examine a representative sample of the model’s outputs and judge whether the classifications align with human expectations. For example, if an LLM flags “I’m going to hurt you” as violent toxicity with high confidence, this is reliable even without formal labels.

- Another way is through[ behavioral testing.](https://machinelearning.apple.com/research/automating-behavioral-testing) You deliberately feed the model well-known toxic and non-toxic examples sourced from public datasets, policy documents, or synthetic prompts. Even if these examples are not part of your production dataset, they act as reference points. For instance, if the model treats “I disagree with your opinion” and “You should be punched for saying that” similarly, that signals a problem in discrimination capability.

- A third angle is[ cross-model comparison](https://www.statsig.com/perspectives/crossmodeleval-faircomparison). Running the same inputs through multiple moderation or classification models can reveal patterns. If your model’s outputs align closely with well-established systems across a wide range of cases, that increases confidence that it is behaving sensibly. Large deviations, especially in edge cases, highlight risk areas that need attention.

*Dr Haba: *

1. *Nice answer. It is common for AI scientists to encounter situations where no labeled data is available for testing large language models (LLMs) or natural language processing (NLP) systems. Without labeled data, unsupervised algorithms cannot be trained or fine-tuned for making predictions. This absence of labeled data also hinders quality assurance (QA) efforts in testing the accuracy of NLP models, forcing them to rely solely on published benchmark scores. One potential solution is to gather a new dataset and have domain experts or the QA team label each record. However, this approach can be both expensive and time-consuming.*

1. *** T*****hought Experiment:** If your machine learning project is at risk of not being completed on time, when should stakeholders be informed?

The short answer is stakeholders should be informed as soon as the risk becomes credible, not when failure is guaranteed.

ML projects are inherently uncertain, probabilistic. Data quality issues, unexpected model behavior, infrastructure constraints, or integration challenges often emerge late. The mistake many teams make is waiting for “certainty” before escalating. By the time certainty exists, options are limited and trust is already damaged.

For example, imagine a toxicity moderation system that depends on multilingual performance. Two weeks into testing, the team realizes the model performs well in English but poorly in Spanish and French, and retraining will take an additional month. Informing stakeholders immediately allows them to choose between delaying the launch, releasing English-only functionality, or accepting reduced accuracy in other languages. Waiting until the final week would force a rushed or risky decision.

A rule of thumb is: if the team cannot longer meet the agreed milestone without reducing scope, quality, or reliability, then the stakeholders need to know as soon as possible. Early communication preserves decision-making power.

From an architectural perspective, transparency is not just good communication—it’s risk management. Trust compounds when stakeholders see problems surfaced early, even if those problems are uncomfortable.

I believe that these two questions are pointing to the same underlying principle: machine learning systems and ML projects are probabilistic, there is a significant grade of uncertainty. Success depends less on perfect accuracy metrics and more on how well uncertainty is measured and managed.

*Dr Haba: *

1. *Good answer: Throughout the lifecycle of a machine learning (ML) project, the AI solution architect must maintain regular communication with stakeholders. Holding frequent review meetings is essential, as the complexity of ML projects can make it difficult for project managers or client partners to convey updates effectively. By consistently informing stakeholders, the AI solution architect ensures that everyone is aligned and aware of project developments. This alignment is crucial for success, particularly if the project starts to encounter delays.*
