# Project title
Improving Language Model Alignment: Addressing Gaps in Preference Learning with Reward Model Optimization
# Project introduction
In general-domain language model applications, alignment with human values—such as helpfulness, honesty, and harmlessness—is essential. While pre-training and supervised fine-tuning enable strong performance across tasks, further alignment with human preferences is achieved through methods like Reinforcement Learning from Human Feedback (RLHF) and Direct Preference Optimization (DPO). However, recent research, such as "Preference Learning Algorithms Do Not Learn Preference Rankings, <https://arxiv.org/pdf/2405.19534>" reveals an alignment gap between observed and ideal ranking accuracies. Most preference-tuned models achieve less than 60% accuracy on common datasets, highlighting limitations in current methods. To address this, there is a need to develop a reward model specifically designed for learning preference rankings. Such a model could close the alignment gap, improving the accuracy of preference predictions and enhancing the alignment of language models with human values.
# Dataset description
The UltraFeedback dataset (<https://huggingface.co/datasets/openbmb/UltraFeedback>, <https://arxiv.org/pdf/2310.01377>) is one of the most widely used datasets for preference learning tasks. However, as demonstrated in the study "Preference Learning Algorithms Do Not Learn Preference Rankings," achieving high accuracy on this dataset presents significant challenges.

In response to these challenges, we focus on this dataset for further investigation. Since the original dataset contains only a training split, we have restructured it into three subsets: training (40,000 samples), validation (10,000 samples), and test (13,967 samples).

The modified version of the dataset, now split for convenience in experimentation, is available at <https://huggingface.co/datasets/JayHyeon/UFB_xai>. We encourage the use of this restructured dataset for benchmarking and performance evaluation in preference learning tasks.

# QnA
For any inquiries regarding this project, please contact the following email: bonin147@gmail.com.
