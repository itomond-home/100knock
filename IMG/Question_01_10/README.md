# Q. 1 - 10
## Q.8. Maxプーリング

ここでは平均値でなく最大値でプーリングせよ。

|入力 (imori.jpg)|出力 (answers_image/answer_8.jpg)|
|:---:|:---:|
|![](imori.jpg)|![](answers_image/answer_8.jpg)|

答え
- Python >> [answers_py/answer_8.py](answers_py/answer_8.py)
- C++ >> [answers_cpp/answer_8.cpp](answers_cpp/answer_8.cpp)

## Q.9. ガウシアンフィルタ

ガウシアンフィルタ(3x3、標準偏差1.3)を実装し、*imori_noise.jpg*のノイズを除去せよ。

ガウシアンフィルタとは画像の**平滑化**（滑らかにする）を行うフィルタの一種であり、**ノイズ除去**にも使われる。

ノイズ除去には他にも、メディアンフィルタ(Q.10)、平滑化フィルタ(Q.11)、LoGフィルタ(Q.19)などがある。

ガウシアンフィルタは注目画素の周辺画素を、ガウス分布による重み付けで平滑化し、次式で定義される。
このような重みは**カーネル**や**フィルタ**と呼ばれる。

ただし、画像の端はこのままではフィルタリングできないため、画素が足りない部分は0で埋める。これを**0パディング**と呼ぶ。
かつ、重みは正規化する。(sum g = 1)

重みはガウス分布から次式になる。

<img src='assets/gaussian_filter.png' width=200>

```bash
重み g(x,y,s) = 1/ (2 * pi * sigma * sigma) * exp( - (x^2 + y^2) / (2*s^2))
標準偏差s = 1.3による8近傍ガウシアンフィルタは
            1 2 1
K =  1/16 [ 2 4 2 ]
            1 2 1
```

|入力 (imori_noise.jpg)|出力 (answers_image/answer_9.jpg)|
|:---:|:---:|
|![](imori_noise.jpg)|![](answers_image/answer_9.jpg)|

答え 
- Python >> [answers_py/answer_9.py](answers_py/answer_9.py)
- C++ >> [answers_cpp/answer_9.cpp](answers_cpp/answer_9.cpp)

## Q.10 メディアンフィルタ

メディアンフィルタ(3x3)を実装し、*imori_noise.jpg*のノイズを除去せよ。

メディアンフィルタとは画像の平滑化を行うフィルタの一種である。

これは注目画素の3x3の領域内の、メディアン値(中央値)を出力するフィルタである。
これもゼロパディングせよ。

|入力 (imori_noise.jpg)|出力 (answers_image/answer_10.jpg)|
|:---:|:---:|
|![](imori_noise.jpg)|![](answers_image/answer_10.jpg)|

答え 
- Python >> [answers_py/answer_10.py](answers_py/answer_10.py)
- C++ >> [answers_cpp/answer_10.cpp](answers_cpp/answer_10.cpp)
