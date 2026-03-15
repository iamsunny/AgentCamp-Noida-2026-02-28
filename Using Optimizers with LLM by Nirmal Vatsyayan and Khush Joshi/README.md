# Using Optimizers with LLM

**Speakers:** [Nirmal Vatsyayan](https://www.linkedin.com/in/nirmal-vatsyayan-65189016) & [Khush Joshi](https://www.linkedin.com/in/khush-joshi-b4501724b)
**Duration:** 11:00 AM – 1:00 PM IST (Hands-on Workshop)

## Key takeaways

- **LLM-as-a-Judge scales evaluation** — use a stronger model to score outputs when human annotation is impractical; the judge *is* the feedback signal
- **GEPA beats RL for prompt refinement** — reflective prompt evolution outperforms reinforcement learning at improving LLM task performance iteratively
- **Prompt optimization is systematic, not intuitive** — structured techniques (candidate generation, scoring, selection) consistently outperform manual prompt tweaking
- **Knowledge distillation shrinks cost** — large model outputs become training signal for smaller, cheaper models without losing quality
- **Write platform-agnostic prompts** — well-structured prompts generalize across OpenAI, Gemini, and local models; avoid provider lock-in from day one
- **Measure before and after** — without a defined eval, you can't tell if your optimization actually improved anything

## About this session

A hands-on workshop exploring optimization techniques for language models. You'll learn practical methods to improve LLM output quality, train closed-source models, and build prompts that work across different platforms.

### Topics covered

- LLM-as-a-Judge technique for output refinement
- Applying the GEPA methodology to enhance model performance
- Writing prompts that generalize across different LLM platforms
- Distilling knowledge from larger models to improve smaller model outputs

## Further reading & tools

| Resource | What it is |
|----------|------------|
| [GEPA Paper (arXiv)](https://arxiv.org/abs/2507.19457) | Reflective Prompt Evolution — the core methodology covered in this session |
| [OpenAI Evals](https://github.com/openai/evals) | Framework for evaluating LLMs — pairs well with LLM-as-a-Judge patterns |
| [Ragas](https://github.com/explodinggradients/ragas) | RAG evaluation library using LLM-as-a-Judge; useful for validating optimized pipelines |
| [Weights & Biases](https://wandb.ai/) | Experiment tracking for prompt optimization runs and model comparisons |
| [DSPy](https://github.com/stanfordnlp/dspy) | Used in the demo notebook to minimize boilerplate — not the focus of the session |

## About the speakers

**[Nirmal Vatsyayan](https://www.linkedin.com/in/nirmal-vatsyayan-65189016)** — Director of Research & AI at HROne. Two-time entrepreneur with patent credentials and Y Combinator background. Has led engineering teams across SaaS, HR tech, and AI startups.

**[Khush Joshi](https://www.linkedin.com/in/khush-joshi-b4501724b)** — ML specialist covering supervised/unsupervised learning and generative AI, with expertise in translating datasets into production-ready solutions.

## What's in this folder

- **[optimizers-demo.ipynb](optimizers-demo.ipynb)** — Hands-on notebook demonstrating LLM optimization techniques: LLM-as-a-Judge evaluation, prompt refinement, and knowledge distillation. DSPy is used in the demo to minimize boilerplate code.

### The notebook covers

1. **LLM-as-a-Judge setup** — Using a stronger model to evaluate and score outputs programmatically
2. **Prompt optimization** — Systematically generating, scoring, and selecting better prompts
3. **GEPA in practice** — Iterative prompt refinement through reflection rather than manual tweaking
4. **Knowledge distillation** — Capturing large model outputs as training signal for smaller models
5. **Evaluation** — Measuring and comparing results before and after optimization

## Prerequisites

```bash
pip install dspy python-dotenv pandas
```

You'll need an LLM API key (OpenAI examples are demonstrated in the workshop).

## Reference Paper

- **GEPA: Reflective Prompt Evolution Can Outperform Reinforcement Learning**
  - Authors: Lakshya A Agrawal, Shangyin Tan, Dilara Soylu, Noah Ziems, et al.
  - A method for improving LLM performance through iterative prompt refinement rather than traditional RL — directly relevant to the optimizer concepts covered in this session.
  - [Read the paper on arXiv](https://arxiv.org/abs/2507.19457)
