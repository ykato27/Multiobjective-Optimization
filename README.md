# Multiobjective_Optimization
* 多目的最適化のプログラム

## リポジトリ構成
```
.
├── README.md                 READMEファイル
├── Dockerfile                Dockerファイル
└── notebook                  jupyter notebook
```

## 環境構築
Dockderfileがあるホスト側のフォルダへ移動（例：Desktop/Multiobjective_Optimization）
```
cd Desktop/Multiobjective_Optimization
```
Dockerによる環境構築
```
docker build .
```
docker run実行（対象フォルダをマウントする／例：Desktop/Multiobjective_Optimization）
```
docker run -p 8888:8888 -v ~/Desktop/Multiobjective_Optimization/:/work --name Multiobjective_Optimization <docker image>
```
ブラウザーを立ち上げてlocalhost:8888へアクセス
workフォルダ内が対象フォルダにマウントされている

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