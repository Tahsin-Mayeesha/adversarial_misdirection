# MisdirectVQA-200

A 200-question benchmark for testing whether vision-language models can be misdirected by text-only prompt attacks. The image never changes; only the prompt does.

**Dataset:** [huggingface.co/datasets/Tahsin-Mayeesha/MisdirectVQA-200](https://huggingface.co/datasets/Tahsin-Mayeesha/MisdirectVQA-200)

## Usage

```python
from datasets import load_dataset

ds = load_dataset("Tahsin-Mayeesha/MisdirectVQA-200", split="test")
```
![Figure](./images/dataset.png)


Run the experiment:

```bash
pip install -r requirements.txt
export OPENAI_API_KEY="your-key-here"
jupyter notebook notebooks/Misdirection_Attack.ipynb
```

## Results (GPT-4o-mini)

| Category   | Baseline | Attack | Attack Success Rate |
|------------|----------|--------|---------------------|
| Counting   | 50.0%    | 48.0%  | 10.0%               |
| Comparison | 10.0%    | 12.0%  | 6.0%                |
| Relational | 42.0%    | 42.0%  | 2.0%                |
| Spatial    | 70.0%    | 54.0%  | 20.0%               |
| **Overall**| **43.0%**| **39.0%** | **9.5%**         |

Spatial reasoning is the most vulnerable category. With 50 questions per category, treat per-category differences as directional.

![Figure](./images/counting.png)
![Figure](./images/spatial.png)

## Paper 

[Adversarial Misdirection: Probing & Visualizing Cross-Modal Reasoning Vulnerabilities in Vision-Language Models](https://ieeexplore.ieee.org/abstract/document/11402081)

## Citation

```bibtex
@INPROCEEDINGS{11402081,
  author={Mayeesha, Tasmiah Tahsin and Ovi, Pretom Roy and Sharma, Sharad},
  booktitle={2025 IEEE International Conference on Big Data (BigData)}, 
  title={Adversarial Misdirection: Probing & Visualizing Cross-Modal Reasoning Vulnerabilities in Vision-Language Models}, 
  year={2025},
  volume={},
  number={},
  pages={7899-7907},
  keywords={Visualization;Accuracy;Systematics;Perturbation methods;Linguistics;Cognition;Robustness;Planning;Artificial intelligence;Surface treatment;Vision-Language Models;Adversarial Attacks;Visual Reasoning;Prompt Injection;VLM Agents;Trustworthy AI;Visualization},
  doi={10.1109/BigData66926.2025.11402081}}
```


