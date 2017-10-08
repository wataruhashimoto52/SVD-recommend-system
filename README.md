# SVD-recommend-system


## 本実装の特徴
本実装では,特異値分解に基づくレコメンドシステムを実装した.特異値分解とは,与えられた行列 R を U,Σ, V の 3 つに分解する手法である.本実装において行列 R はユーザー,映画間の行列になっているので,U はユーザーに 関する特徴が詰まった行列,V は映画に関する特徴が詰まった行列,そして Σ はそれらに与える重み,に相当する.  

$$  
\begin{equation}  
    R \approx U\Sigma V^{T}  
\end{equation}  
$$  

Eq.(1) において ≈ としているのは,特異値分解の際に行列のランクを任意の K に下げているためである.する
と,K ランクの分解された行列によって,もとの行列 R の近似行列 Rˆ を作成することができる.  

$$
\begin{equation}  
\hat {R} = U\Sigma V^{T}  
\end{equation}  
$$

行列のランク数を下げることによって，実質的に似たユーザーをクラスタリングしたとみなして扱うことができるようになり，アイテムベースやユーザーベースの協調フィルタリングで問題であった，ほとんど何の映画も見ていないユーザーであっても，似たクラスタ（主成分）のユーザーを参照することができ，その結果として映画をレコメンドできる，ということになる．