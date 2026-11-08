
---
layout: default
title: "AI Use Across the Day"
---

# AI Use Across the Day

**Team:** Iris Lang, Yunchuan Wang, Mengyuan Dong, Ning Ding

This project explores how the topics of AI prompts vary across different times of day. Using the WildChat-1M dataset, we focus on English-language conversations with recorded locations in California. Our initial exploration suggests that the dataset contains useful language and location information, but we have not yet tested differences in prompt topics.

## Research question and motivation

**Research question:** How do English-language prompt topics vary by time of day among California-based users?

People use AI for many different purposes, such as studying, working, and asking everyday questions. We want to understand whether these uses change throughout the day.

This question matters because it may help us understand how AI fits into people's daily routines. We divide the day into four time periods and compare the types of prompts submitted during each period.

## Data

- **Source:** [WildChat-1M Dataset](https://huggingface.co/datasets/allenai/WildChat-1M)
- **Unit of analysis:** One first user message per conversation.
- **Coverage:** We plan to focus on English-language conversations with recorded locations in California. Our initial exploration used a sample of 10,000 conversations.
- **Access and ethics:** The dataset is publicly available for research, but prompts may contain sensitive information. We will not publish raw prompts with identifying details. Recorded locations may also be inaccurate, and the sample does not represent all California residents.

We plan to clean the dataset by checking missing values, duplicate records, language information, and timestamps. We will also convert timestamps to California local time to make comparisons across the day.

## Methods

Our project uses descriptive statistics and text analysis to compare AI prompts across different times of day.

We divide the day into four periods:

- **Night:** 12:00 AM – 5:59 AM
- **Morning:** 6:00 AM – 11:59 AM
- **Afternoon:** 12:00 PM – 5:59 PM
- **Evening:** 6:00 PM – 11:59 PM

Our planned analysis includes:

1. **Data cleaning:** Filter conversations by language and recorded location, and check missing or duplicate records.
2. **Time analysis:** Convert timestamps to America/Los_Angeles and compare the number of prompts across four time periods.
3. **Text analysis:** Compare word and phrase frequencies to identify common topics during each period.
4. **Topic analysis:** Apply a text analysis method from class and inspect sample prompts to help interpret the topics.
5. **Validation:** Check whether uneven sample sizes, repeated users, or weekday/weekend differences affect our results.

We will compare topic proportions within each time period rather than relying only on raw counts.

Relevant notebooks and scripts will be linked here as the analysis is completed.

## Findings

### Finding 1: Initial Dataset Exploration

We first explored a sample of 10,000 conversations from WildChat-1M.

| Measure | Count |
|---|---:|
| Total conversations sampled | 10,000 |
| English-language conversations | 4,648 |
| Conversations with California as the recorded state | 257 |

California was the third most common state or region label in our initial sample.

These results suggest that the dataset contains information that can support our filtering strategy. However, the number of conversations meeting both the English-language and California criteria still needs to be verified.

**Preliminary result:** Data exploration completed. Final filtered sample size and time-of-day comparisons are pending.

### Finding 2: Prompt Topics Across Time Periods

**Preliminary analysis pending.**

Our next step is to compare prompt topics across night, morning, afternoon, and evening.

We plan to create visualizations showing the distribution of prompts and the most common words or topics in each time period.

This will help us explore whether different types of AI requests are more common at different times of day.

## Interpretation and limitations

- **Strongest claim supported:** Our initial exploration shows that WildChat-1M includes language, location, and time information that may support our research question. We have not yet established differences in prompt topics.

- **Claim not supported:** We cannot conclude that people use AI for specific purposes at particular times of day based on the current results. We also cannot generalize our findings to all California residents.

- **Important limitations:** Location information may be incomplete or inaccurate. Some users may appear multiple times, and the number of conversations may differ across time periods. Our sample may not represent the broader population of AI users.

- **Social-science implications:** Understanding when and why people use AI may provide insight into how AI fits into daily activities. Our findings could help describe patterns of AI use, but they would not establish causal relationships.

## Reproducibility

- **Repository:** [Add GitHub repository link]
- **Environment:** Run `uv sync --frozen` from the repository folder.
- **Run order:** [Add notebook or script names after confirming the analysis workflow.]
- **Data access:** The WildChat-1M dataset is available through Hugging Face. Researchers can access the original dataset and apply the same language, location, and time filters described in our methods.

We will document the data cleaning and analysis steps in the repository so that others can reproduce our results.

## References

1. [WildChat-1M Dataset — Hugging Face](https://huggingface.co/datasets/allenai/WildChat-1M)
2. [WildChat: 1M ChatGPT Interaction Logs in the Wild](https://arxiv.org/abs/2405.01470)

