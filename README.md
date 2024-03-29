# Multiobjective-Optimization

- 多目的最適化のプログラム

## リポジトリ構成
```
.
├── Dockerfile
├── README.md
├── data
├── docker
│   ├── deap
│   │   ├── Dockerfile
│   │   └── requirements_deap.txt
│   ├── optuna
│   │   ├── Dockerfile
│   │   └── requirements_optuna.txt
│   ├── physbo
│   │   ├── Dockerfile
│   │   └── requirements_physbo.txt
│   ├── pymoo
│   │   ├── Dockerfile
│   │   └── requirements_pymoo.txt
│   └── requirements.txt
├── docker-compose-deap.yml
├── docker-compose-optuna.yml
├── docker-compose-physbo.yml
├── docker-compose-pymoo.yml
├── docs
│   ├── Multi-Optimization.md
│   └── Multi-Optimization.pdf
├── models
├── notebooks
│   ├── deap
│   │   ├── MOPSO-deap.ipynb
│   │   ├── NSGA-2-deap.ipynb
│   │   └── NSGA-3-deap.ipynb
│   ├── optuna
│   │   ├── MOTPESampler
│   │   │   ├── optuna-real-discrete.ipynb
│   │   │   ├── optuna-real.ipynb
│   │   │   ├── pareto_data_real-discrete.csv
│   │   │   ├── pareto_data_real.csv
│   │   │   ├── pareto_graph_real-discrete.png
│   │   │   └── pareto_graph_real.png
│   │   └── NSGAIISampler
│   │       ├── optuna-real-discrete.ipynb
│   │       ├── optuna-real.ipynb
│   │       ├── pareto_data_real-discrete.csv
│   │       ├── pareto_data_real.csv
│   │       ├── pareto_graph_real-discrete.png
│   │       └── pareto_graph_real.png
│   ├── physbo
│   │   └── physbo.ipynb
│   └── pymoo
│       ├── C-TAEA-pymoo.ipynb
│       ├── MOEAD-pymoo.ipynb
│       ├── NSGA-2-pymoo.ipynb
│       ├── NSGA-3-pymoo.ipynb
│       ├── R-NSGA-2-pymoo.ipynb
│       └── R-NSGA-3-pymoo.ipynb
├── pyproject.toml
├── requirements.txt
├── setup.cfg
├── src
│   └── __init__.py
├── tests
│   └── __init__.py
└── work
```

## 環境構築

- Dockderfileがあるホスト側のフォルダへ移動（例：Desktop/Multiobjective-Optimization）

```
cd Desktop/Multiobjective-Optimization
```

- Dockerによる環境構築（フォルダをマウント：Desktop/Multiobjective-Optimization）

```
docker-compose -f docker-compose-{*構築対象}.yml up --build
```

- ブラウザーを立ち上げてlocalhost:8888へアクセス
- ローカルフォルダがマウントされている

## jupyter notebook説明

- NSGA-2-deep.ipynb : 遺伝的アルゴリズム/NSGA-2（deap）のnotebook
- NSGA-3-deep.ipynb : 遺伝的アルゴリズム/NSGA-2（deap）のnotebook
- MOPSO-deap.ipynb : 粒子群最適化/MOPSO（deap）のnotebook
- NSGA-2-pymoo.ipynb : 遺伝的アルゴリズム/NSGA-2（pymoo）のnotebook
- NSGA-3-pymoo.ipynb : 遺伝的アルゴリズム/NSGA-3（pymoo）のnotebook
- R-NSGA-2-pymoo.ipynb : 遺伝的アルゴリズム/R-NSGA-2（pymoo）のnotebook
- R-NSGA-3-pymoo.ipynb : 遺伝的アルゴリズム/R-NSGA-3（pymoo）のnotebook
- C-TAEA-pymoo.ipynb : C-TAEA（pymoo）のnotebook
- MOEAD-pymoo.ipynb : MOEAD（pymoo）のnotebook
- physbo.ipynb : 多目的ベイズ最適化（physbo）のnotebook
- optuna-real.ipynb : 遺伝的アルゴリズム/NSGA-2（optuna）のnotebook
- optuna-real-discrete.ipynb : 遺伝的アルゴリズム/NSGA-2（optuna）のnotebook

## ライブラリー情報

- [deap](https://github.com/DEAP/deap)
- [pymoo](https://github.com/msu-coinlab/pymoo)
- [physbo](https://github.com/issp-center-dev/PHYSBO)
- [optuna](https://github.com/optuna/optuna)

## 参考文献

- NSGA_2_deep : [http://repository.ias.ac.in/83498/1/2-a.pdf](http://repository.ias.ac.in/83498/1/2-a.pdf)
- NSGA_3_deep : [https://www.egr.msu.edu/~kdeb/papers/k2005012.pdf](https://www.egr.msu.edu/~kdeb/papers/k2005012.pdf)

## Display notebooks

- [View Jupyter notebooks in nbviewer](https://nbviewer.jupyter.org/github/ykato27/Multiobjective-Optimization/tree/main/notebooks/)

## 動作環境
マシンスペック（Mac)
- MacBook Air (Retina, 13-inch, 2018)
- 1.6 GHz デュアルコアIntel Core i5
- 8 GB 2133 MHz LPDDR3
