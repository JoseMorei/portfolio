# Challenge 8

1. **Thought Experiment:** In what situations would you opt for CNN predictions over time series predictions? Please provide examples of machine learning projects.

The impact of Bias is because models learn the statistical patterns present in the data distribution they are exposed to. When a machine learning model is trained on biased data, it doesn't just learn the data; it amplifies the prejudices, gaps, and historical inequalities hidden within it.  The model perceives these biases as objective mathematical truths rather than human errors.

If the training data is imbalanced, incomplete, or skewed, the model internalizes those distortions and reflects them in predictions.

Examples:

1. A facial recognition project. If the training dataset contains a disproportionate number of lighter-skinned faces, the model may achieve very high overall accuracy but perform significantly worse on darker-skinned individuals. The bias reduces subgroup accuracy even if global metrics look acceptable. The issue is not the neural network architecture itself but the imbalance in representation within the dataset.

2. In credit scoring systems, bias can emerge when historical data reflects past discriminatory lending practices. If a model is trained on such data, it may learn correlations between geographic areas or demographic proxies and loan defaults. This can result in lower approval rates for certain communities and degraded fairness, even if the model performs well against historical validation data.

3. In natural language processing, bias can appear when models are trained predominantly on formal language. A sentiment analysis system trained on standard English may misinterpret slang, dialects, or informal phrasing as negative sentiment. In a moderation system, this could lead to disproportionate flagging of certain user groups. Technically, this reduces precision and recall for those subpopulations.

How to mitigate the Impact:

1. Diverse Data Collection: Ensuring the training set reflects the actual population.

2. Algorithmic Auditing: Testing the model against specific subgroups (Intersectional Analysis) rather than just looking at the overall accuracy score.

3. Adversarial Debiasing: Training a second model to "catch" the first model using protected attributes to make decisions.

Note: A model can be 99% accurate on paper but 0% fair in practice. Accuracy is a measure of how well a model matches its training, not how well it matches justice or reality.

Bias alters the probability distribution the model learns. It affects not only fairness but predictive robustness. To mitigate this, practitioners must use representative sampling, subgroup evaluation metrics, stratified validation, fairness-aware training techniques, and continuous monitoring after deployment. A model is only as reliable as the data foundation it is built upon.

External sources:

1. [https://www.researchgate.net/publication/385694931\_Bias\_and\_Its\_Consequences\_A\_Study\_of\_Machine\_Learning\_Performance](https://www.researchgate.net/publication/385694931_Bias_and_Its_Consequences_A_Study_of_Machine_Learning_Performance)

2. [https://scholarsmine.mst.edu/cgi/viewcontent.cgi?article=1030&context=peer2peer](https://scholarsmine.mst.edu/cgi/viewcontent.cgi?article=1030&context=peer2peer)

3. [https://www.crescendo.ai/blog/ai-bias-examples-mitigation-guide](https://www.crescendo.ai/blog/ai-bias-examples-mitigation-guide)

4. [https://github.com/Trusted-AI/AIF360](https://github.com/Trusted-AI/AIF360) (An open-source library that provides +10 bias mitigation algorithms)

*Dr. Haba:*

*Nice answer. While Convolutional Neural Networks (CNNs) can handle time-series data using a "sliding window" approach, Long Short-Term Memory (LSTM) networks are generally more effective for predicting future events from sequential data. This solution includes applications such as stock market forecasts, weather predictions, and sales estimates. LSTMs excel at capturing long-term dependencies in time-based data, making them ideal for these scenarios.*

*On the other hand, CNNs are better suited for classifying and categorizing static data such as images, text, or audio. They perform exceptionally well in recognizing objects in images, such as identifying species, detecting items like Nike shoes, spotting cancer cells, analyzing sentiment in text, and classifying music genres. CNNs are particularly strong at generalizing from training data to accurately classify new, unseen real-world data.*

*While both algorithms have some overlapping capabilities, the choice between them depends on whether the focus is on time-based predictions with LSTMs or pattern recognition in static data with CNNs.*

1. **Thought Experiment: **How does bias in training data impact the accuracy of machine learning models? Include examples of relevant machine learning projects.

The impact of Bias is because models learn the statistical patterns present in the data distribution they are exposed to. When a machine learning model is trained on biased data, it doesn't just learn the data; it amplifies the prejudices, gaps, and historical inequalities hidden within it.  The model perceives these biases as objective mathematical truths rather than human errors.

If the training data is imbalanced, incomplete, or skewed, the model internalizes those distortions and reflects them in predictions.

Examples:

1. A facial recognition project. If the training dataset contains a disproportionate number of lighter-skinned faces, the model may achieve very high overall accuracy but perform significantly worse on darker-skinned individuals. The bias reduces subgroup accuracy even if global metrics look acceptable. The issue is not the neural network architecture itself but the imbalance in representation within the dataset.

2. In credit scoring systems, bias can emerge when historical data reflects past discriminatory lending practices. If a model is trained on such data, it may learn correlations between geographic areas or demographic proxies and loan defaults. This can result in lower approval rates for certain communities and degraded fairness, even if the model performs well against historical validation data.

3. In natural language processing, bias can appear when models are trained predominantly on formal language. A sentiment analysis system trained on standard English may misinterpret slang, dialects, or informal phrasing as negative sentiment. In a moderation system, this could lead to disproportionate flagging of certain user groups. Technically, this reduces precision and recall for those subpopulations.

How to mitigate the Impact:

1. Diverse Data Collection: Ensuring the training set reflects the actual population.

2. Algorithmic Auditing: Testing the model against specific subgroups (Intersectional Analysis) rather than just looking at the overall accuracy score.

3. Adversarial Debiasing: Training a second model to "catch" the first model using protected attributes to make decisions.

Note: A model can be 99% accurate on paper but 0% fair in practice. Accuracy is a measure of how well a model matches its training, not how well it matches justice or reality.

Bias alters the probability distribution the model learns. It affects not only fairness but predictive robustness. To mitigate this, practitioners must use representative sampling, subgroup evaluation metrics, stratified validation, fairness-aware training techniques, and continuous monitoring after deployment. A model is only as reliable as the data foundation it is built upon.

External sources:

1. [https://www.researchgate.net/publication/385694931\_Bias\_and\_Its\_Consequences\_A\_Study\_of\_Machine\_Learning\_Performance](https://www.researchgate.net/publication/385694931_Bias_and_Its_Consequences_A_Study_of_Machine_Learning_Performance)

2. [https://scholarsmine.mst.edu/cgi/viewcontent.cgi?article=1030&context=peer2peer](https://scholarsmine.mst.edu/cgi/viewcontent.cgi?article=1030&context=peer2peer)

3. [https://www.crescendo.ai/blog/ai-bias-examples-mitigation-guide](https://www.crescendo.ai/blog/ai-bias-examples-mitigation-guide)

[https://github.com/Trusted-AI/AIF360](https://github.com/Trusted-AI/AIF360)

(An open-source library that provides +10 bias mitigation algorithms)

*Dr. Haba:*

*Interesting answer. Bias in training data affects not only the perceived accuracy of an AI model but also the relevance and fairness of its outputs. Consequently, even if your quality assurance (QA) team confirms that the model meets specific accuracy criteria, real-world users may still encounter problematic results due to these inherent biases.*

*For example, AI models like DALL-E3 have been noted for frequently depicting doctors as men and nurses as women, despite their ability to accurately generate images of both genders in both professions. This bias stems from patterns in the training data, which often reflect societal stereotypes rather than the reality that both men and women are equally qualified to be doctors or nurses.*

*Such biases in the training data can lead to outputs that reinforce outdated stereotypes, rather than offering a fair and accurate representation of the world. This bias highlights the critical importance of carefully evaluating the composition and quality of training data to ensure that AI models operate effectively and fairly in real-world scenarios.*
