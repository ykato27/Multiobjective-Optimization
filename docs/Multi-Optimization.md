---
marp: true
theme: gaia
---
<!-- $theme: gaia -->
<!-- $size: 16:9 -->
<!-- page_number: true -->
<!-- paginate: true -->

<!-- タイトル用書式：中央寄せ -->
<!-- _class: lead -->
# 多目的最適化の概要

---

## 目次

1. 多目的最適化とは
2. 多目的最適化手法（NSGA-Ⅱ）
3. 多目的最適化手法（NSGA-Ⅲ）

---

<!-- タイトル用書式：中央寄せ -->
<!-- _class: lead -->
# 1. 多目的最適化とは

---

## 多目的最適化の概要

- 多目的最適化とは、複数の評価基準に基づいて最適化を行うことを指す。

![w:600](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/9dda32b2-f496-0fc5-c784-cc77bff2b4ca.png)

---

## 多目的最適化における最適性とは

- 多目的最適化における最適性とは、優越されていないパレート最適解を見つけることを指す。
  - 優劣されていない：パレート最適解
  - 優劣されている　：劣解

---

<!-- タイトル用書式：中央寄せ -->
<!-- _class: lead -->
# 2. 多目的最適化手法（NSGA-Ⅱ、NSGA-Ⅲ）

---

## NSGA-Ⅱ の概要

- NSGA-Ⅱ(Elitist Non-dominated Sorting Genetic Algorithm)は、Deb らによって2002年に提案された多目的遺伝的アルゴリズム。
- 遺伝的アルゴリズム(Genetic Algorithm)を多目的最適化問題に拡張したもの。
- NSGA-Ⅱ の特徴は下記3点
  - 高速非優劣ソートによるランキング法
  - 混雑度ソートによる個体選択
  - 混雑度トーナメント選択による遺伝子操作

---

## NSGA-Ⅱ のアルゴリズム概要

- NSGA-Ⅱ では、親母集団$P_t$ と遺伝子操作（交叉・突然変異）を行って探索を行うための子母集団$Q_t$ の2つの独立した集団を用いて解探索を行う手法

---

## Step1

- サイズN の親母集団$P_t$ をランダムに生成し、サイズN の子母集団$Q_t$ を生成し、$P_t$ と$Q_t$ を組合せて集団$R_t$ を生成する

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/914407c3-ed80-a3da-371d-27ba5b9b1de7.png)

---

## Step2

- 集団$R_t$ に対して非優劣ソートを実施し、全個体をランク毎（$F_1$, $F_2$, ・・・）に分類する

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/01aacadb-aabd-3afd-3100-e034a357bf78.png)

---

## Step3

- 新たな空の親母集団$P_{t+1}$ を生成し、step2 の非優劣ソートでランクが上位の個体で親母集団$P_{t+1}$ を構成する

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/56294428-985d-4856-72a2-e458877f32eb.png)

---

## Step4

- step3 で親母集団$P_{t+1}$ を構成していく途中で、個体サイズがN を越える時、サイズN を越えるランクの個体に対して、混雑度ソートを実行し、混雑度の高い個体を個体サイズがN になるまで取り除く

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/deac6300-3082-e7be-d5f3-ee597401c150.png)

---

## Step5

- 親母集団$P_{t+1}$ に対して混雑度トーナメント選択により、交叉・突然変異すべき個体を選択し、遺伝子操作を行い新たな子集団$Q_{t+1}$ を生成する

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/2bfc30c1-d76e-fecf-8621-31d1861d4b24.png)

---

## Step6

- 親母集団$P_{t+1}$ と子集団$Q_{t+1}$ を組み合わせて新たな集団$R_{t+1}$ を生成する

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/d540cd9d-16c3-cee3-250a-c9d51d447a16.png)

---

## Step7

- step2 へ戻り、これまでの操作を終了条件が満たすまで繰り返し実施する

---

## 高速非優劣ソートのアルゴリズム概要（①）

- 各個体に対して、支配している個体の数と支配されている個体の数を同時に数える

![w:700](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/2aae023e-c953-33b7-3a08-8c693f63c4cc.png)

---

## 高速非優劣ソートのアルゴリズム概要（②）

- ランク1（支配されている個体：0）の個体のみをフロント1用のリストF_1 として纏める

![w:500](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/66020fa4-ba9f-ec98-4387-a8e69040c1b2.png)

---

## 高速非優劣ソートのアルゴリズム概要（③）

- リストF_1 に含まれる各個体（i）が支配している個体（j）に対して、支配されている数を1ずつ引く

---

## 高速非優劣ソートのアルゴリズム概要（④）

- ランク1（最良のフロント）の個体のみをフロント2用のリストF_2 として纏める

![w:500](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/17422647-19b7-214a-9d2e-982aaea00d5c.png)

---

## 高速非優劣ソートのアルゴリズム概要（⑤）

- ③〜④を繰り返し、全ての個体が無くなるまで実施

---

## 混雑度とは

- 各ランク内の個体集合を目的関数でソートし、隣接する個体を調べる。
- 全個体それぞれの隣接する個体間の距離を求め、個体間の和の数値が低いものほど、その個体は混雑している事とし、それを混雑度と呼ぶ。

![w:500](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/16b85325-f96f-df81-c870-9ee22919357d.png)

---

## 混雑度ソートとは

- 選択個体群$M$ が母集団の数$N$ を超えない場合は、ランク順に個体を選択。
- 選択個体群$M$ が母集団の数$N$ を超える場合は、混雑度を考慮して個体を選択。

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/0346b0af-b6f7-9c22-f27d-9614bfeb269e.png)

---

## NSGA-Ⅲ の概要

- NSGA-Ⅲ は、NSGA-Ⅱ を改良した手法
- NSGA-Ⅲ の特徴は下記2点
  - Reference point（参照点）の導入
  - Reference line を活用した個体選択

---

## NSGA-Ⅲ のアルゴリズム概要

- NSGA-Ⅲ では、親母集団$P_t$ と遺伝子操作（交叉・突然変異）を行って探索を行うための子母集団$Q_t$ の2つの独立した集団を用いて解探索を行う手法

---

## Step1

- サイズN の親母集団$P_t$ をランダムに生成し、サイズN の子母集団$Q_t$ を生成し、$P_t$ と$Q_t$ を組合せて集団$R_t$ を生成する

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/914407c3-ed80-a3da-371d-27ba5b9b1de7.png)

---

## Step2

- 集団$R_t$ に対して非優劣ソートを実施し、全個体をランク毎（$F_1$, $F_2$, ・・・）に分類する

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/01aacadb-aabd-3afd-3100-e034a357bf78.png)

---

## Step3

- 新たな空の親母集団$P_{t+1}$ を生成し、step2 の非優劣ソートでランクが上位の個体で親母集団$P_{t+1}$ を構成する

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/56294428-985d-4856-72a2-e458877f32eb.png)

---

## Step4

- step3 で親母集団$P_{t+1}$ を構成していく途中で、個体サイズがN を越える時、サイズN を越えるランクの個体に対して、Reference line を参照して個体を選択する

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/deac6300-3082-e7be-d5f3-ee597401c150.png)

---

## Step5

- 親母集団$P_{t+1}$ に対してReference line を活用して適合度評価により、交叉・突然変異すべき個体を選択し、遺伝子操作を行い新たな子集団$Q_{t+1}$ を生成する

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/2bfc30c1-d76e-fecf-8621-31d1861d4b24.png)

---

## Step6

- 親母集団$P_{t+1}$ と子集団$Q_{t+1}$ を組み合わせて新たな集団$R_{t+1}$ を生成する

![w:900](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/d540cd9d-16c3-cee3-250a-c9d51d447a16.png)

---

## Step7

- step2 へ戻り、これまでの操作を終了条件が満たすまで繰り返し実施

---

## Reference line を活用した適合度の計算方法の概要（①）

- 各個体と各reference line とのベクトルの直交距離を計算し、各個体の最近傍のreference line を決定する

---

## Reference line を活用した適合度の計算方法の概要（②）

- 近傍個体数の最も少ないreference line を選び、対象ランクの個体集合でそのreference line に最も直交距離の近い個体を次世代個体として選択する

![w:400](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/743453/8871a518-7ef1-78a5-ffa8-a7c1d413d74b.png)

---

## NSGA-Ⅱ とNSGA-Ⅲ の比較表

|手法|特徴|
|:---|:---|
|NSGA-Ⅱ|・目的変数の数が少ないと良好な結果が得られる <br> ・目的変数が多く高次元になると混雑距離で解の優劣が付けにくくなり、収束性が悪くなる　|
|NSGA-Ⅲ|・reference lineで解の探索方向を予め定めておくことで、目的変数が多く高次元になっても高い収束性を実現できる。　|
