# LLM Powered Memory Consolidation for Ubiquitous Computing 
Large Language Models (LLMs) have achieved remarkable capabilities in reasoning and generation but lack the ability to retain and prioritize past information like humans do. This research introduces a memory consolidation framework for LLMs inspired by neurocognitive principles of recall and forgetting. Using multimodal data from wearable sensors in classroom environments, the system converts physiological signals—such as heart rate, stress, and movement—into semantic memories, which are then ranked by relevance, time, and recall frequency through a mathematical model of exponential decay. This enables the LLM to selectively strengthen or diminish memories over time, improving contextual reasoning and personalization. Applied to the En-Gage dataset, our memory-augmented GPT-4o model achieved higher alignment with ground-truth student engagement compared to the LLaSA + LLaMA-2 baseline. The study demonstrates how memory-driven LLMs can enhance human-centered applications, such as helping students understand their engagement across subjects to make better career choices. Future work will focus on comparing and optimizing diverse memory consolidation systems to build LLMs capable of long-term, efficient, and human-like reasoning.

**Authors:** [Parampuneet Kaur Thind](mailto:Parampuneet.thind@uniroma1.it) · [Vaibhav Kumar Katturu](mailto:vaibhavkumar651@gmail.com)  
*Accepted at UbiComp Companion 2025, Espoo, Finland*  
DOI: [10.1145/3714394.3750599](https://doi.org/10.1145/3714394.3750599)

## Overview  
This repository contains the **implementation and supporting material** for our paper:  
> **“LLM Powered Memory Consolidation for Ubiquitous Computing”**  
> Presented at **ACM UbiComp Companion 2025**.

Our research explores how **Large Language Models (LLMs)** can be enhanced with a **neuro-inspired memory consolidation mechanism** — allowing them to “remember and forget” information like humans do .  

We apply this framework in the **education domain**, using wearable sensor data from classrooms to model how students engage across different subjects.  
The system transforms physiological signals (e.g., stress, focus, movement) into **semantic memories**, ranks them by relevance and time, and helps generate **personalized engagement insights**.  

## Motivation  
Most students struggle to identify which subjects they’re truly engaged in — leading many adults to end up in jobs they don’t enjoy.  
This study proposes an AI model that helps students **understand their engagement across subjects**, potentially guiding better **career and learning decisions**.  

## Methodology  
### Step 1: Data Processing  
We use the **In-Gauge** and **En-Gage** datasets ([PhysioNet v1.0.0](https://physionet.org/content/in-gauge-and-en-gage/1.0.0/)) that capture real classroom physiological signals.  
Each record includes multimodal data such as:  
- Heart rate and stress indicators  
- Movement and fidget index  
- Thermal and comfort data  
- Time, subject, and context metadata  

### Step 2: Memory Construction  
- Data is converted into **natural language summaries** using GPT-based models.  
- Each summary becomes a **memory entry**, ranked by:  
  - *Time elapsed*  
  - *Contextual relevance*  
  - *Recall frequency*  

### Step 3: Mathematical Memory Consolidation  
We model recall probability using a **decaying memory function** inspired by neurocognitive recall models:  
\[
P_n(t) = \frac{1 - \exp(-r e^{-t/g(n)})}{1 - e^{-1}}
\]
This ensures that frequently recalled, semantically relevant memories strengthen over time — just like human long-term memory.

### Step 4: Engagement Scoring  
- Consolidated memory traces are aggregated to compute **engagement levels** (Low / Moderate / High).  
- Validation is performed against ground-truth student surveys.  

The proposed model (Memory + GPT-4o) achieved **higher correlation and F1-scores** than the baseline **LLaSA + LLaMA-2** model, showing improved interpretability and personalization.

## Core Idea  
| Concept | Human Analogy | LLM Equivalent |
|----------|----------------|----------------|
| Short-term memory | Working memory | Context window |
| Long-term memory | Consolidated memories | External structured memory |
| Forgetting | Decay over time | Exponential decay in relevance |
| Recall | Memory strengthening | Reinforcement via recurrence |

## Experimental Setup  
**Tech Stack:**  
- Python   
- PyTorch   
- Sentence-Transformers   
- OpenAI GPT-4o API  
- Pandas / NumPy / Matplotlib for analysis   

**Data:**  
- [In-Gauge / En-Gage (v1.0.0, PhysioNet)](https://physionet.org/content/in-gauge-and-en-gage/1.0.0/)   

## Results  
| Model | Correlation (r) | F1 Score |
|--------|-----------------|----------|
| **LLaSA + LLaMA-2** | 0.62 | 0.68 |
| **Ours (Memory + GPT-4o)** | **0.70** | **0.73** |

The improvement demonstrates that adding **temporal and contextual memory consolidation** helps the model interpret engagement patterns more faithfully.

## Future Work  
**Next research direction:**  
I aim to **study, compare, and optimize different types of memory consolidation systems in LLMs** — including retrieval-based, summarization-based, and neuro-inspired models — to build AI systems capable of **efficient, long-term reasoning and human-like understanding** across domains.

## Citation  
If you use this work, please cite our paper:  
```
@inproceedings{thind2025llm,
  title={LLM Powered Memory Consolidation for Ubiquitous Computing},
  author={Thind, Parampuneet Kaur and Katturu, Vaibhav Kumar},
  booktitle={Companion of the 2025 ACM International Joint Conference on Pervasive and Ubiquitous Computing (UbiComp Companion ’25)},
  year={2025},
  publisher={ACM},
  doi={10.1145/3714394.3750599}
}
```

## Acknowledgments  
This research uses the **In-Gauge and En-Gage datasets (PhysioNet)** and was supported by insights from **La Sapienza Università di Roma** and **independent contributions** from the authors.

## Contact  
📧 vaibhavkumar651@gmail.com  
🌐 [LinkedIn](https://www.linkedin.com/in/vaibhav-katturu-559787185/)
