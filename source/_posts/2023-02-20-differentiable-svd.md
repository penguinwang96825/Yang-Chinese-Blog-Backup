---
title: SVD的微分推導
mathjax: false
password: d64aeb91367f
cover: /cover/wallhaven-4gmgkd.jpg
categories:
  - - 科研
tags:
  - SVD
  - 矩陣分解
abbrlink: b8597833
date: 2023-02-20 17:41:21
---

最近剛好做的研究題目跟SVD有關，需要把SVD應用在神經網路裡面。所以就想說手推一下SVD的導數，並把它紀錄下來，以免之後老年癡呆都忘光光。想要看懂這篇的人也要有一點心理準備，等等的數學真的很不友善，我也是花了好久的時間才整理完這篇文章。

# 奇異值分解

奇異值分解(Singular Value Decomposition, SVD)是線性代數裡邊一個重要的主題，主要就是在進行任意矩陣分解。在信號處理、圖像修復、數據壓縮、降噪、統計學有重要應用。

## SVD分解

設$A$為一個$m \times n$的實矩陣，且$rank(A) = r$，則full SVD具有以下形式：

\begin{equation}
   A = U \Sigma V^T
   \label{eq:svd}
\end{equation}

其中$U \in \mathbb{R}^{m \times m}$、$\Sigma \in \mathbb{R}^{m \times n}$、$V \in \mathbb{R}^{n \times n}$。方陣$U$和$V$都是實正交矩陣(orthogonal matrix)。這邊我只考慮compact SVD，也就是$A = U_r \Sigma_r V^T_r$。現在的三個矩陣維度分別為$U \in \mathbb{R}^{m \times r}$、$\Sigma \in \mathbb{R}^{r \times r}$、$V \in \mathbb{R}^{r \times n}$。矩陣的秩(rank)代表的是對存儲在矩陣$A$中的獨特信息的量，rank越高則信息越多。

## SVD求導

既然我們知道了$rank(A) = r$，則$r \leq min(m, n)$。我們還知道$U$和$V$都是實正交，則

\begin{equation}
	U^T U = V^T V = I_r
	\label{eq:constraint}
\end{equation}

現在$A$的導數可以寫成

\begin{equation}
   dA = dU \Sigma V^T + U d\Sigma V^T + U \Sigma dV^T
   \label{eq:diff-svd}
\end{equation}

在限制式$\ref{eq:constraint}$中，我們可以先對$U$求導，得到

\begin{equation}
   dU^T U + U^T dU = 0
\end{equation}

並且假設一個新的矩陣$d\Omega_U = U^T dU$。因為$d\Omega_U = U^T dU = - dU^T U$，所以我們可以知道$d\Omega$是一個反對稱矩陣(skew-symmetric)。類似地，我們可以得到$d\Omega_V = V^T dV = - dV^T V$，所以$d\Omega_V$也是一個反對稱矩陣。

對矩陣$A$左乘$U^T$並且右乘$V$，我們可以得到

\begin{equation}
\begin{aligned}
	U^T dA V &= U^T dU \Sigma V^T V + U^T U d\Sigma V^T V + U^T U \Sigma dV^T V \\\\
	         &= d\Omega_U \Sigma + d\Sigma + \Sigma d\Omega_V^T
\end{aligned}
\label{eq:diff-svd-dp}
\end{equation}

現在我們定義$dP \equiv U^T dA V$，且使用$X \circ Y$來表示$X$和$Y$的Hadamard product。我們現在要分別去算$dP$斜對角元素和非斜對角元素的值。首先，我們求得$dP$斜對角元素為

\begin{equation}
   I_r \circ dP = d\Sigma
   \label{eq:diff-svd-diagonal}
\end{equation}

且$dP$的非斜對角元素為

\begin{equation}
\begin{aligned}
   \bar{I_r} \circ dP &= d\Omega_U \Sigma + \Sigma d\Omega_V^T \\\\
   					  &= d\Omega_U \Sigma - \Sigma d\Omega_V
\end{aligned}
\label{eq:diff-svd-dp-nondiagonal}
\end{equation}

由此可得$dP^T$的非斜對角元素為

\begin{equation}
   \bar{I_r} \circ dP^T = - \Sigma d\Omega_U + d\Omega_V \Sigma
   \label{eq:diff-svd-dpt-nondiagonal}
\end{equation}

現在我們對式子$\ref{eq:diff-svd-dp-nondiagonal}$右乘$\Sigma$，並對式子$\ref{eq:diff-svd-dpt-nondiagonal}$左乘$\Sigma$，然後做相加可得

\begin{equation}
\begin{aligned}
	\bar{I_r} \circ (dP \Sigma + \Sigma dP^T) &= (d\Omega_U \Sigma^2 + \Sigma d\Omega_V^T \Sigma) + (- \Sigma^2 d\Omega_U + \Sigma d\Omega_V \Sigma) \\\\
	&= (d\Omega_U \Sigma^2 - \Sigma^2 d\Omega_U) + (\Sigma d\Omega_V^T \Sigma + \Sigma d\Omega_V \Sigma) \\\\
	&= d\Omega_U \Sigma^2 - \Sigma^2 d\Omega_U
\end{aligned}
\end{equation}

最終可以得到

\begin{equation}
	d\Omega_U = F \circ (dP \Sigma + \Sigma dP^T)
	\label{eq:omega-u}
\end{equation}

其中

\begin{equation}
	F = 
	\begin{cases}
      \frac{1}{\sigma_j^2 - \sigma_i^2} & i \neq j \\\\
      0 & i = j
    \end{cases}       
\end{equation}

藉由類似的推導，我們也可以得到

\begin{equation}
	d\Omega_V = F \circ (\Sigma dP + dP^T \Sigma)
	\label{eq:omega-v}
\end{equation}

因為$d\Omega_U = U^T dU$，所以藉由左乘$U$我們得到$dU = U d\Omega_U$。

再繼續更深入的SVD導數推導之前，我們要先了解一些正交補餘(orthogonal complement)和投影矩陣(projection matrix)的性質。假設$U$的正交補餘矩陣為$U_{\bot}$且維度為$m \times (m-r)$，其中$U_{\bot}$可以藉由Gram-Schmidt process算出，這邊就不再詳細介紹這個算法。另外，投影矩陣$H$必須滿足$H^2 = H$和$H^T = H$，也就是自己的平方和自己的轉置都必須是自己。現在我們要來證明$U_{\bot} U_{\bot}^{T}$和$I - U U^{T}$都是投影矩陣。

\begin{equation}
	(U_{\bot} U_{\bot}^{T})^2 = U_{\bot} (U_{\bot}^{T} U_{\bot}) U_{\bot}^{T} = U_{\bot} U_{\bot}^{T}
\end{equation}

\begin{equation}
	(U_{\bot} U_{\bot}^{T})^T = (U_{\bot}^{T})^T (U_{\bot})^T = U_{\bot} U_{\bot}^{T}
\end{equation}

\begin{equation}
	(I - U U^{T})^2 = I - 2 U U^{T} + U U^{T} U U^{T} = I - U U^{T}
\end{equation}

\begin{equation}
	(I - U U^{T})^T = (I - U U^{T})
\end{equation}

除此之外，我們還必須了解$U$和$U_{\bot}$是否可以組成整個生成空間。我們先假設這句話為真，那麼對於任何一個向量空間都必須是$U$和$U_{\bot}$的線性組合，也就是$S = aU + bU_{\bot}$，其中$a, b$為純量、$S$為一矩陣。我們先將$S$透過投影向量$U U^T$映射到$U$的行空間：

\begin{equation}
	U U^T S = U U^T (aU + bU_{\bot}) = a U (U^T U)  + b U_{\bot} (U^T U_{\bot}) = a U
\end{equation}

其中$U^T U = I$($U$為正交矩陣)，還有$U^T U_{\bot} = 0$(因為$U$和$U_{\bot}$正交)。類似地，我們也可以將$S$透過投影向量$U_{\bot} U_{\bot}^T$映射到$U_{\bot}$的行空間：

\begin{equation}
	U_{\bot} U_{\bot}^T S = U_{\bot} U_{\bot}^T (a U + b U_{\bot}) = a U_{\bot} (U_{\bot}^T U) + b U_{\bot} (U_{\bot}^T U_{\bot}) = b U_{\bot}
\end{equation}

合在一起看的話就是：

\begin{equation}
\begin{aligned}
	(U U^T + U_{\bot} U_{\bot}^T) S &= U U^T S + U_{\bot} U_{\bot}^T S \\\\
	                                &= a U + b U_{\bot} \\\\
	                                &= I S
\end{aligned}
\end{equation}

所以，我們可以得到$U U^T + U_{\bot} U_{\bot}^T$就是一個identity matrix。我們可以寫成以下恆等式：

\begin{equation}
	U_{\bot} U_{\bot}^T = I - U U^T
\end{equation}

回歸到SVD的求導。為了求$dA$(式子\ref{eq:diff-svd})，我們需要算出$dU$、$d\Sigma$、$dV^T$。可以想像把SVD視為一種函示映射$f$，然後對輸入矩陣$A$增加擾動$dA$。那也就相當於對生成$A$的行空間的$U$進行擾動$dU$、對生成$A$的列空間的$V$進行擾動$dV$。不失一般性的，我們先看$dU$。假設$dU$在$U$的整個行空間($m \times m$)進行擾動，其中還可以分解為在$m \times r$和$m \times (m-r)$的部分進行擾動。所以我們可以寫成以下式子：

\begin{equation}
	dU = U d\Omega_U + U_{\bot} dK_U
	\label{eq:du}
\end{equation}

其中我們已經求出$d\Omega_U$(式子\ref{eq:omega-u})，現在需要去解$dK_U$。我們對$dA$左乘一個$U_{\bot}^{T}$得到：

\begin{equation}
\begin{aligned}
	U_{\bot}^{T} dA &= U_{\bot}^{T} dU \Sigma V^T + U_{\bot}^{T} U d\Sigma V^T + U_{\bot}^{T} U \Sigma dV^T \\\\
                    &= U_{\bot}^{T} dU \Sigma V^T \\\\
                    &= U_{\bot}^{T} (U d\Omega_U + U_{\bot} dK_U) \Sigma V^T \\\\
                    &= (U_{\bot}^{T} U d\Omega_U + U_{\bot}^{T} U_{\bot} dK_U) \Sigma V^T \\\\
                    &= dK_U \Sigma V^T
\end{aligned}
\label{eq:compute-dk-u}
\end{equation}

整理一下式子\ref{eq:compute-dk-u}就可以得到$dK_U$：

\begin{equation}
	dK_U = U_{\bot}^{T} dA V \Sigma^{-1}
	\label{eq:dk-u}
\end{equation}

同理，我們可以去算$dV$

\begin{equation}
	dV = V d\Omega_V + V_{\bot} dK_V
	\label{eq:dv}
\end{equation}

然後得到$dK_V$

\begin{equation}
	dK_V = V_{\bot}^{T} dA^T U \Sigma^{-1}
	\label{eq:dk-v}
\end{equation}

把式子\ref{eq:omega-u}和式子\ref{eq:dk-u}代入\ref{eq:du}可以得到$dU$，把式子\ref{eq:omega-v}和式子\ref{eq:dk-v}代入\ref{eq:dv}可以得到$dV$。

\begin{equation}
	dU = U (F \circ (U^T dA V \Sigma + \Sigma V^T dA^T U)) + (I_m - U U^T) dA V \Sigma^{-1}
\end{equation}

\begin{equation}
	d\Sigma = I_r \circ (U^T dA V)
\end{equation}


\begin{equation}
	dV = V (F \circ (\Sigma U^T dA V + V^T dA^T U \Sigma)) + (I_n - V V^T) dA^T U \Sigma^{-1}
\end{equation}

# 主成分分析

在多元統計分析中，主成分分析(Principal Components Analysis, PCA)是一種統計分析和數據降維的方法。數學定義上，PCA的基本思想是使用一個正交化線性轉換把原始數據(sample matrix)轉換到一個新的座標系統上，並且投影在新的座標後仍保留數據最大的變異。換句話說，這一數據的任何投影的第一大變異數在第一個坐標上，第二大變異數在第二個坐標上，依次類推。

## 預備知識

首先，我們要先了解怎麼對數據做中心化(centralisation)。

\begin{equation}
X_{n \times d} = 
	\begin{pmatrix}
			x_{11} & x_{12} & \cdots & x_{1d} \\\\ 
			x_{21} & x_{22} & \cdots & x_{2d} \\\\
			\vdots & \vdots & \ddots & \vdots \\\\
			x_{n1} & x_{n2} & \cdots & x_{nd}
	\end{pmatrix}
\end{equation}

\begin{equation}
\mu_{d \times 1} = 
	\begin{pmatrix}
			\frac{1}{n} \sum\limits_{i=1}^{n} x_{i1} \\\\
			\vdots \\\\
			\frac{1}{n} \sum\limits_{i=1}^{n} x_{in}
	\end{pmatrix}
\end{equation}

對每一行操作特徵零均值化：

\begin{equation}
\begin{aligned}
\tilde{X} 
	&= X - \mathbb{1}\_{n \times 1} \mu^T \\\\
	&= \begin{pmatrix} x_1 & \cdots & x_d \end{pmatrix} - \begin{pmatrix} \frac{1}{n} \sum\limits_{i=1}^{n} x_{i1} & \cdots & \frac{1}{n} \sum\limits_{i=1}^{n} x_{id} \end{pmatrix} \\\\
	&= \begin{pmatrix}
			x_{11} - \frac{1}{n} \sum\limits_{i=1}^{n} x_{i1} & \cdots & x_{1d} - \frac{1}{n} \sum\limits_{i=1}^{n} x_{id} \\\\ 
			\vdots & \ddots & \vdots \\\\
			x_{n1} - \frac{1}{n} \sum\limits_{i=1}^{n} x_{i1} & \cdots & x_{nd} - \frac{1}{n} \sum\limits_{i=1}^{n} x_{id}
		\end{pmatrix} \\\\
	&= \begin{pmatrix}
			(1 - \frac{1}{n}) x_{11} - \cdots - \frac{1}{n} x_{n1} & \cdots & (1 - \frac{1}{n}) x_{1d} - \cdots - \frac{1}{n} x_{nd} \\\\
			\vdots & \ddots & \vdots \\\\
			- \frac{1}{n} x_{11} - \cdots + (1 - \frac{1}{n}) x_{n1} & \cdots & - \frac{1}{n} x_{1d} - \cdots + (1 - \frac{1}{n}) x_{nd}
		\end{pmatrix} \\\\
	&= \begin{pmatrix}
			1 - \frac{1}{n} & - \frac{1}{n} & \cdots & - \frac{1}{n} \\\\
			- \frac{1}{n} & 1 - \frac{1}{n} & \cdots & - \frac{1}{n} \\\\
			\vdots & \vdots & \ddots & \vdots \\\\
			- \frac{1}{n} & - \frac{1}{n} & \cdots & 1 - \frac{1}{n}
		\end{pmatrix} \cdot \begin{pmatrix} x_1 & \cdots & x_d \end{pmatrix} \\\\
	&= (I_n - \frac{1}{n} \mathbb{1}\_{n \times n}) \cdot X_{n \times d} \\\\
	&= \tilde{I}\_{n \times n} \cdot X_{n \times d}
\end{aligned}
\end{equation}

其中[居中矩陣](https://en.wikipedia.org/wiki/Centering_matrix)(centering matrix)是一個正交投影矩陣(orthogonal projection matrix)滿足：

\begin{equation}
	\tilde{I} = \tilde{I}^2 = \tilde{I}^T
\end{equation}

第二個要會的是算一下斜方差矩陣(sample covariance matrix)。

\begin{equation}
\begin{aligned}
	C &= \frac{1}{n} \sum_{i=1}^{n} (x_i - \mu) (x_i - \mu)^T \\\\
	  &= \frac{1}{n} \tilde{X}^T \tilde{X} \\\\
	  &= \frac{1}{n} (\tilde{I} X)^T (\tilde{I} X) \\\\
	  &= \frac{1}{n} X^T \tilde{I}^T \tilde{I} X \\\\
	  &= \frac{1}{n} X^T \tilde{I} X
\end{aligned}
\end{equation}

## PCA思想

假如原始的樣本$X \in \mathbb{R}^{n \times d}$($n$個數據點且特徵維度是$d$)。單看其中一筆數據$x_i$在座標$v \in \mathbb{R}^{d}$上做投影，則會得到

\begin{equation}
	proj_{v} x_i = \frac{v^{T} x_{i}}{\lVert v \rVert^2} v
\end{equation}

不失一般性，我們假設$v$是單位向量，則可以得到投影後的數據點是$(v^T x_i) v$。那麼我們可以得到去中心化後的數據的方差為：

\begin{equation}
\begin{aligned}
	\frac{1}{n} \sum_{i=1}^{n} (\tilde{x}\_i^T v - 0)^2 
		&= \frac{1}{n} \sum_{i=1}^{n} (\tilde{x}\_i^T v)^T (\tilde{x}\_i^T v) \\\\
		&= \frac{1}{n} \sum_{i=1}^{n} v^T \tilde{x}\_i \tilde{x}\_i^T v \\\\
		&= v^T (\frac{1}{n} \sum_{i=1}^{n} \tilde{x}\_i \tilde{x}\_i^T) v \\\\
		&= v^T (\frac{1}{n} \tilde{X}^T \tilde{X}) v \\\\
		&= v^T C v
\end{aligned}
\end{equation}

我們希望可以最大化投影後的數據方差，則可以利用拉格朗日函數建立目標函數：

\begin{equation}
	\mathcal{L}(v) = - v^T C v + \lambda (v^T v - 1)
\end{equation}

對$v$求導可以得到：

\begin{equation}
	\frac{\partial \mathcal{L}}{\partial v} = -2 C v + 2 \lambda v = 0
\end{equation}

最終得到：

\begin{equation}
	C v = \lambda v
\end{equation}

所以，我們可以得到$v$是$C$的特徵向量，$\lambda$是對應的特徵向量的特徵值。要是想要最大化$v^T C v$，那就必須要最大化$\lambda$，因為$v^T C v = v^T \lambda v = \lambda v^T v = \lambda$。

這裡還需要證明一下另外一個重要的性質。對於$X$的第$j$個主要成分$v_{j}$會是斜方差矩陣$C$第$j$大的特徵向量，對應的$\lambda_{j}$是第$j$大的特徵值。這邊會證明$j=2$的例子：

\begin{equation}
	v_2 = \underset{\lVert v \rVert^2 = 1, v_1^T v = 0}{\operatorname{arg max}} v^T C v
\end{equation}

一樣列出拉格朗日函數的目標函數

\begin{equation}
	\mathcal{L}(v) = - v^T C v + \alpha_1 (v^T v - 1) + \alpha_2 (v_{1}^{T} v)
\end{equation}

最小化$\mathcal{L}(v)$可以得到

\begin{equation}
	-2 C v + 2 \alpha_1 v + \alpha_2 v_1 = 0
\end{equation}

所以$\alpha_2 = 0$且$C v = \alpha_1 v$。想要最大化$v^T C v$的話，$v_2$就必須是第二大的特徵向量且$\alpha_1 = \lambda_2$。

# 總結

基本上，如果能從頭看到這邊應該就已經腦死的差不多了。之後我投的paper有成功上岸我再來這邊分享。

# References

1. Edelman et al., The geometry of algorithms with orthogonality constraints, 1998
2. Townsend, Differentiating the singular value decomposition, 2016
3. Wang et al., Robust Differentiable SVD, 2021