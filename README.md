# Common-ToM

This is the repository corresponding to [Views Are My Own, But Also Yours: Benchmarking Theory of Mind using Common Ground](https://arxiv.org/abs/2403.02451) which was accepted to ACL 2024 Findings. It contains the code and data used to generate Common-ToM, a theory of mind (ToM) question answering corpus based on common ground. It also contains the scripts used for the zero-shot experiments reported.

## Installation
Supposing [conda](https://docs.conda.io/en/latest/) and [poetry](https://python-poetry.org) are installed, the project dependencies can be setup using the following commands.

```
conda create -n common-tom python=3.10
conda activate common-tom
poetry install
```

By default, all scripts will log their output to `/home/{username}/scratch/logs/`. To change this behavior see ~line 40 of `src/core/context.py`.

## Content
The common ground corpus which Common-ToM is based on ([Markowska et al., 2023](https://aclanthology.org/2023.findings-emnlp.551/)) can be found in `data/cg` while Common-ToM itself is in `data/questions`. The script used for zero-shot experiments and its prompt are located in `bin/openai_zero_shot.py` and `data/prompts/`, respectively. The logic used for generating Common-ToM is located in `bin/generate_yn_questions.py`. This is summarized below.

```
common-tom/
|- bin/
|  |- generate_yn_questions.py - generates the common-tom corpus.
|  |- openai_zero_shot.py      - runs zero-shot experiments.
|- data/
|  |- cg/                      - base common ground corpus.
|  |- prompts/                 - prompts for zero-shot experiments.
|  |- questions/               - the common-tom corpus questions.
|- src/                        - additional utilities.
|  |- ...
```

## Citation

```
@misc{soubki2024views,
      title={Views Are My Own, But Also Yours: Benchmarking Theory of Mind using Common Ground}, 
      author={Adil Soubki and John Murzaku and Arash Yousefi Jordehi and Peter Zeng and Magdalena Markowska and Seyed Abolghasem Mirroshandel and Owen Rambow},
      year={2024},
      eprint={2403.02451},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```
