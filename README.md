# Multiobjective-Optimization
* 多目的最適化のプログラム

## リポジトリ構成
```
.
├── README.md                 READMEファイル
├── .dockerignore        
├── Dockerfile                Dockerファイル
├── docker-compose.yml
├── requirements.txt          requirementsファイル
└── notebook                  jupyter notebook
 ├── deap
 ├── optuna
 ├── physbo
 └── phmoo
```

## 環境構築

* Dockderfileがあるホスト側のフォルダへ移動（例：Desktop/Multiobjective-Optimization）
```
cd Desktop/Multiobjective-Optimization
```

* Dockerによる環境構築（フォルダをマウント：Desktop/Multiobjective_Optimization）
```
docker-compose up --build
```

* ブラウザーを立ち上げてlocalhost:8888へアクセス
* ローカルフォルダがマウントされている

## jupyter notebook説明
* NSGA-2-deep.ipynb : 遺伝的アルゴリズム/NSGA-2（deap）のnotebook
* NSGA-3-deep.ipynb : 遺伝的アルゴリズム/NSGA-2（deap）のnotebook
* MOPSO-deap.ipynb : 粒子群最適化/MOPSO（deap）のnotebook
* NSGA-2-pymoo.ipynb : 遺伝的アルゴリズム/NSGA-2（pymoo）のnotebook
* NSGA-3-pymoo.ipynb : 遺伝的アルゴリズム/NSGA-3（pymoo）のnotebook
* R-NSGA-2-pymoo.ipynb : 遺伝的アルゴリズム/R-NSGA-2（pymoo）のnotebook
* R-NSGA-3-pymoo.ipynb : 遺伝的アルゴリズム/R-NSGA-3（pymoo）のnotebook
* C-TAEA-pymoo.ipynb : C-TAEA（pymoo）のnotebook
* MOEAD-pymoo.ipynb : MOEAD（pymoo）のnotebook
* physbo.ipynb : 多目的ベイズ最適化（physbo）のnotebook
* optuna_real.ipynb : 遺伝的アルゴリズム/NSGA-2（optuna）のnotebook
* optuna_real-discrete.ipynb : 遺伝的アルゴリズム/NSGA-2（optuna）のnotebook

## ライブラリー情報
* [deap](https://github.com/DEAP/deap)
* [pymoo](https://github.com/msu-coinlab/pymoo)
* [physbo](https://github.com/issp-center-dev/PHYSBO)

## 参考文献
* NSGA_2_deep : [http://repository.ias.ac.in/83498/1/2-a.pdf](http://repository.ias.ac.in/83498/1/2-a.pdf)
* NSGA_3_deep : [https://www.egr.msu.edu/~kdeb/papers/k2005012.pdf](https://www.egr.msu.edu/~kdeb/papers/k2005012.pdf)


## 動作環境
マシンスペック（Mac)
- MacBook Air (Retina, 13-inch, 2018)
- 1.6 GHz デュアルコアIntel Core i5
- 8 GB 2133 MHz LPDDR3
