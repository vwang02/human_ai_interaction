
---
layout: default
title: "AI Use Across the Day"
---

# AI Use Across the Day

**Team:** Iris Lang, Yunchuan Wang, Mengyuan Dong, Ning Ding

This project explores how English-language ChatGPT prompt topics vary across different times of day in California. Using the WildChat-1M dataset, we examine when people submit prompts and plan to compare what they ask about. Our preliminary analysis identified 1,091 eligible first user prompts, with the highest number occurring in the evening.

## Research question and motivation

**Research question:** How do English-language ChatGPT prompt topics vary by local time in California?

People use ChatGPT for many different purposes, including studying, working, and asking everyday questions. We want to understand whether the topics people discuss with AI change depending on the time of day.

This question matters because it may help us understand how AI fits into people's daily routines. For example, people might use AI for work-related tasks during the day and personal questions in the evening. We want to explore whether patterns like these appear in real conversations.

We divide the day into four time periods and compare the types of prompts submitted during each period.

## Data

- **Source:** [WildChat-1M Dataset](https://huggingface.co/datasets/allenai/WildChat-1M)
- **Unit of analysis:** One eligible first user prompt per conversation.
- **Coverage:** Our preliminary analysis examined 100,000 WildChat-1M training records from April 8 to May 16, 2023. After filtering for English-language first prompts recorded in California, excluding empty prompts, and removing duplicate conversation hashes, 1,091 eligible prompts were included.
- **Access and ethics:** WildChat-1M is publicly available for research, but some conversations may contain sensitive or identifying information. We will not publish raw sensitive prompts or personal details. Location information may also be incomplete or inaccurate, and the dataset does not represent all California residents.

We filtered conversations using both conversation-level and first-user-message location information. We also checked the language of the first user message, removed empty prompts, and kept one eligible prompt per conversation hash.

All 1,091 eligible first user messages had missing timestamps. Therefore, we used the first assistant response completion time as a proxy for when each prompt was submitted.

## Methods

We used **descriptive frequency analysis** to examine how English-language ChatGPT prompts were distributed across different times of day in California.

Our preliminary analysis included the following steps:

1. Loaded 100,000 records from the WildChat-1M training dataset.
2. Selected the first English-language user prompt from conversations recorded in California.
3. Checked both conversation-level and first-message location information.
4. Removed empty prompts and duplicate conversation hashes.
5. Used the first assistant response completion time because the first user timestamps were missing.
6. Converted timestamps to Pacific Time using `America/Los_Angeles`.
7. Divided prompts into four time periods:
   - **Night:** 00:00–05:59
   - **Morning:** 06:00–11:59
   - **Afternoon:** 12:00–17:59
   - **Evening:** 18:00–23:59
8. Calculated the number and percentage of prompts in each period.

We also performed a validation check by comparing the first assistant response timestamp with the conversation's last-turn timestamp. Using the last-turn timestamp would change the assigned time period for 51 out of 1,091 prompts (4.7%).

For the next stage, we plan to use text analysis to compare common words and prompt topics across the four time periods. We will focus on topic proportions within each period rather than only comparing raw counts.

## Findings

### Finding 1: Distribution of Prompts by Time of Day

Our preliminary analysis identified **1,091 eligible first user prompts** from 100,000 training records.

The following table shows the number and percentage of prompts in each time period.

| Time Period | Count | Share |
|---|---:|---:|
| Night (00:00–05:59) | 175 | 16.0% |
| Morning (06:00–11:59) | 313 | 28.7% |
| Afternoon (12:00–17:59) | 281 | 25.8% |
| Evening (18:00–23:59) | 322 | 29.5% |
| **Total** | **1,091** | **100%** |

Evening had the highest number of prompts (322, 29.5%), closely followed by morning (313, 28.7%). Afternoon accounted for 25.8%, while night had the fewest prompts (175, 16.0%).

These results show that prompt counts differ across the four time periods in our preliminary sample. However, the difference between evening and morning is relatively small, and we cannot yet conclude that these patterns represent broader ChatGPT usage.

The preliminary analysis focuses on when prompts were submitted. It does not yet tell us whether the topics of the prompts change throughout the day.

### Finding 2: Topic Differences Across Time Periods

**Analysis in progress.**

Our next step is to examine whether different types of prompts are more common during different times of day.

We plan to use text analysis to compare common words, phrases, and topics across night, morning, afternoon, and evening.

We will first compare word and phrase frequencies, then apply a topic analysis method covered in class. We also plan to inspect sample prompts to help interpret the results.

Because each time period contains a different number of prompts, we will compare topic percentages within each period instead of relying only on raw counts.

This analysis will help us answer our main research question about how AI prompt topics vary throughout the day.

## Interpretation and limitations

- **Strongest claim supported:** In our preliminary sample of 1,091 prompts, evening had the largest share (29.5%), closely followed by morning (28.7%). Night had the smallest share (16.0%). All four time periods contained eligible observations.

- **Claim not supported:** We cannot conclude that California residents generally use ChatGPT more frequently in the evening. We also cannot conclude that prompt topics differ across time periods because the topic analysis has not yet been completed.

- **Important limitations:** All 1,091 first user timestamps were missing, so we used the first assistant response completion time as a proxy. This may introduce timing errors, especially when a response crosses a time-period boundary. Our validation check showed that 51 prompts (4.7%) would be assigned to different periods if we used the conversation's last-turn timestamp. The dataset may also contain imperfect location information, repeated users, and sampling bias.

- **Social-science implications:** Understanding how people interact with AI at different times of day may help us learn how AI fits into everyday routines. Our preliminary findings provide a starting point, but further text analysis is needed to understand whether the purposes of AI use change throughout the day.

Our current limitation is that we have only completed the descriptive time analysis, not the topic comparison.

Our next steps are:

1. **Iris Lang:** Continue preparing and checking the filtered dataset.
2. **Yunchuan Wang:** Validate the timestamp proxy and review the time-period distribution.
3. **Mengyuan Dong:** Compare common words and prompt topics across time periods.
4. **Ning Ding:** Create visualizations, update the project website, and help present the findings.

All team members will review the interpretation, limitations, and privacy concerns before the final submission.

## Reproducibility

- **Repository:** [Add GitHub repository URL]
- **Environment:** Run `uv sync --frozen` from the repository folder.
- **Run order:** Run `import.ipynb` to load the WildChat-1M dataset, filter eligible conversations, convert timestamps, calculate time-period counts, and generate the preliminary visualization. Additional text analysis notebooks will be linked as they are completed.
- **Data access:** The original WildChat-1M dataset is available through Hugging Face. Researchers can access the training dataset and reproduce our analysis by applying the same language, location, deduplication, and timestamp-processing steps.

Our current preliminary analysis uses 100,000 training records. We will document any additional data cleaning or analysis decisions in the repository as the project develops.

## References

1. [WildChat-1M Dataset — Hugging Face](https://huggingface.co/datasets/allenai/WildChat-1M)
2. [WildChat: 1M ChatGPT Interaction Logs in the Wild](https://arxiv.org/abs/2405.01470)
