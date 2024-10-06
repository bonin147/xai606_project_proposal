# Project title
Improving Language Model Alignment: Addressing Gaps in Preference Learning with Reward Model Optimization
# Project introduction
In general-domain language model applications, alignment with human values—such as helpfulness, honesty, and harmlessness—is essential. While pre-training and supervised fine-tuning enable strong performance across tasks, further alignment with human preferences is achieved through methods like Reinforcement Learning from Human Feedback (RLHF) and Direct Preference Optimization (DPO). However, recent research, such as "Preference Learning Algorithms Do Not Learn Preference Rankings, <https://arxiv.org/pdf/2405.19534>" reveals an alignment gap between observed and ideal ranking accuracies. Most preference-tuned models achieve less than 60% accuracy on common datasets, highlighting limitations in current methods. To address this, there is a need to develop a reward model specifically designed for learning preference rankings. Such a model could close the alignment gap, improving the accuracy of preference predictions and enhancing the alignment of language models with human values.
# Dataset description
The UltraFeedback dataset (<https://huggingface.co/datasets/openbmb/UltraFeedback>, <https://arxiv.org/pdf/2310.01377>) is one of the most widely used datasets for preference learning tasks. However, as demonstrated in the study "Preference Learning Algorithms Do Not Learn Preference Rankings," achieving high accuracy on this dataset presents significant challenges.

In response to these challenges, we focus on this dataset for further investigation. Since the original dataset contains only a training split, we have restructured it into three subsets: training (40,000 samples), validation (10,000 samples), and test (13,967 samples).

The modified version of the dataset, now split for convenience in experimentation, is available at <https://huggingface.co/datasets/JayHyeon/UFB_xai>. We encourage the use of this restructured dataset for benchmarking and performance evaluation in preference learning tasks.
# Baseline
The baseline implementation is available at <https://github.com/RLHFlow/RLHF-Reward-Modeling>. he Hugging Face model repository can be accessed at <https://huggingface.co/Ray2333/reward-model-Mistral-7B-instruct-Unified-Feedback>.

This baseline utilizes the Mistral-7B model as the pre-trained architecture and further fine-tunes it using the UltraFeedback dataset through supervised learning. The implementation builds upon the <https://github.com/huggingface/trl>.

The objective is to surpass the performance of this baseline reward model by leveraging a 7B reward model. The reason for utilizing the 7B model is that most labs, including our, are unable to support models larger than 7B.


To evaluate whether our model is well-trained, we typically create train, validation, and test datasets. However, empirical evidence suggests that performance on this type of data split does not always align with the model's real-world performance. As a result, we employ alternative methods to assess model performance, such as using Reward-Bench <https://huggingface.co/spaces/allenai/reward-bench>. Therefore, we recommend using the split dataset only as a preliminary check to ensure that the model is adequately trained.


| Model                                                 | Average | Chat  | Hard  | Safety | Reasoning | Prior Sets |
|-------------------------------------------------------|---------|-------|-------|--------|-----------|------------|
| berkeley-nest/Starling-RM-34B (34B)                   | 81.5    | 96.9  | 59    | 89.9   | 90.3      | 71.4       |
| **Ray2333/reward-model-Mistral-7B-instruct-Unified-Feedback (7B)** | 78.75   | 97.84 | 52.85 | 85.94  | 87.02     | 73.92      |
| berkeley-nest/Starling-RM-7B-alpha (7B)               | 74.6    | 98    | 43.4  | 88.6   | 74.6      | 68.6       |
| openbmb/UltraRM-13b (13B)                             | 71.3    | 96.1  | 55.3  | 45.8   | 82        | 77.2       |
| IDEA-CCNL/Ziya-LLaMA-7B-Reward (7B)                   | 66      | 88    | 41.3  | 62.5   | 73.7      | 64.6       |
| OpenAssistant/oasst-rm-2.1-pythia-1.4b-epoch-2.5 (1.4B) | 65.1    | 88.5  | 47.9  | 62.1   | 61.4      | 65.8       |
| OpenAssistant/oasst-rm-2-pythia-6.9b-epoch-1 (7B)     | 64      | 94.4  | 36.6  | 59.4   | 70        | 59.4       |
| llm-blender/PairRM-hf (0.4B)                          | 60.9    | 90.2  | 53    | 31.5   | 60        | 69.6       |


# QnA
For any inquiries regarding this project, please contact the following email: bonin147@gmail.com.
