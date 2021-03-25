# Multiobjective-Optimization
* 多目的最適化のプログラム

## リポジトリ構成
```
.
├── README.md                 READMEファイル
├── .dockerignore        
├── Dockerfile                Dockerファイル
├── docker-compose.yml
└── notebook                  jupyter notebook
```

## 環境構築

* Dockderfileがあるホスト側のフォルダへ移動（例：Desktop/Multiobjective-Optimization）
```
cd Desktop/Multiobjective-Optimization
```

* Dockerによる環境構築（フォルダをマウント：Desktop/Multiobjective_Optimization）
```
docker-compose up
```

* ブラウザーを立ち上げてlocalhost:8888へアクセス
* ローカルフォルダがマウントされている

## jupyter notebook説明
* NSGA_2_deep.ipynb : 多目的最適化(NSGA-2)のnotebook
* NSGA_3_deep.ipynb : 多目的最適化(NSGA-3)のnotebook

## 参考文献
* NSGA_2_deep : [http://repository.ias.ac.in/83498/1/2-a.pdf](http://repository.ias.ac.in/83498/1/2-a.pdf)
* NSGA_3_deep : [https://www.egr.msu.edu/~kdeb/papers/k2005012.pdf](https://www.egr.msu.edu/~kdeb/papers/k2005012.pdf)


## 動作環境
マシンスペック（Mac)
- MacBook Air (Retina, 13-inch, 2018)
- 1.6 GHz デュアルコアIntel Core i5
- 8 GB 2133 MHz LPDDR3
