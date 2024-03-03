# How You Prompt Matters! Even Task-Oriented Constraints in Instructions Affect LLM-Generated Text Detection
[![arXiv](https://img.shields.io/badge/arXiv-2311.08369-b31b1b.svg)](https://arxiv.org/abs/2311.08369)
[![LICENSE](https://img.shields.io/badge/License-Apache--2.0-green.svg)](https://github.com/ryuryukke/OUTFOX?tab=Apache-2.0-1-ov-file)

### This is the official repository for our [preprint](https://arxiv.org/abs/2311.08369), "How You Prompt Matters! Even Task-Oriented Constraints in Instructions Affect LLM-Generated Text Detection"

<p align="center">
  <img src="https://github.com/ryuryukke/HowYouPromptMatters/assets/61570900/33aa87d9-b594-4a56-89b3-b39e82061d72" width="900"/>
</p>

## 📖 Introduction
To combat the misuse of Large Language Models (LLMs), many recent studies have presented LLM-generated-text detectors with promising performance.
When users instruct LLMs to generate texts, the instruction can include different constraints depending on the user’s need.
However, most recent studies do not cover such diverse instruction patterns when creating datasets for LLM detection.

In this paper, we find that **even _task-oriented_ constraints --- constraints that would naturally be included in an instruction and are not related to detection-evasion --- cause existing detectors to have a large variance in detection performance**.
We focus on student essay writing as a realistic domain and manually create task-oriented constraints based on several factors for essay quality.

Our experiments and analysis show that:
- A task-oriented constraint has a more significant effect on the detection performance than the baseline randomness caused by generating texts multiple times (via sampling) or paraphrasing the instruction.
  - The standard deviation (SD) of current detector performance on texts generated by an instruction with such a constraint reaches up to 14.4 points in the F1-score.
- The high instruction-following ability of LLMs fosters the large impact of such constraints on detection performance.


## 📢 Updates
- **March 2024**: Our essay datasets are now available!

## :page_facing_up: Dataset Info
Our dataset is based on 500 pairs of essay problem statements and human(native-student)-written essays that are part of [OUTFOX dataset](https://github.com/ryuryukke/OUTFOX).
The native students range from 6th to 12th grade in the U.S.

We instruct three LMs to generate essays: GPT-4(`gpt-4-0613`), ChatGPT(`gpt-3.5-turbo-0613`), and GPT-3(`davinci-002`).

`data/llm_essays/Multiple/` includes essays in the Multiple setting: generating texts multiple times (via sampling).

`data/llm_essays/Paraphrase/` includes essays in the Paraphrase setting: generating texts via each paraphrased instruction.

`data/llm_essays/Constraint/` includes essays in the Constraint setting: generating texts via instruction with each different constraint.


## 📚 Citation
#### If our work inspires you, please consider citing our work as follows:
```
@misc{koike2024prompt,
      title={How You Prompt Matters! Even Task-Oriented Constraints in Instructions Affect LLM-Generated Text Detection}, 
      author={Ryuto Koike and Masahiro Kaneko and Naoaki Okazaki},
      year={2024},
      eprint={2311.08369},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```