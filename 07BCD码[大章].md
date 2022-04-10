# 总览

![](https://pic.imgdb.cn/item/62444e1327f86abb2a7c4c71.png)

<br><br>

# BCD码

***

我们使用4个bit来代表一个十进制
但是这样的话我们就有2^4^=16种表达方式，显然表示0-9是绰绰有余,而且还有6种冗余

<br><br>

## 8421码

***

![](https://pic.imgdb.cn/item/62451c5d27f86abb2ab0ca40.png)

可以看到，我们对应的权重

![](https://pic.imgdb.cn/item/62451c8d27f86abb2ab11e49.png)

> 例子 保存数字985

$$
\overbrace{1001}^\text {9},
\overbrace{1000}^\text {8},
\overbrace{0101}^\text {5}=985^{十进制}
$$

<br><br>

### 8421码的加法

***

![](https://pic.imgdb.cn/item/62451dff27f86abb2ab3b508.png)

$$
\left\{
\begin{align*}
    & 十进制:5 + 8 = 13\\
    \\
    & 8421码:0101 + 1000 = 1101\\
\end{align*}
\right.
$$

二进制的加法之前有提到，可以去前面寻找

(`07进位计数制度[大章]`)

![](https://pic.imgdb.cn/item/62451f5727f86abb2ab63961.png)

此时我们计算出来的值为1101，但是在8421码中1010-1111(10-15)这部分没有定义

==所以我们在这个范围里面的数字，我们统一加上一个6==

![](https://pic.imgdb.cn/item/62451fc027f86abb2ab6fa45.png)

$$
\begin{align*}
1101 + 0110^{(十进制里的6)} &= 1\;0011^{可以看到又符合8421码了}\\
&=0001 \; 0011
\end{align*}
$$

<br><br>

## 余3码

***

![](https://pic.imgdb.cn/item/6245267127f86abb2ac33147.png)

我们余3码就是在8421码的基础上都+3(0011)变化而来的
但也因此，我们的余3码没有固定的权重

<br><br>

## 2421码 改变权值定义

***

![](https://pic.imgdb.cn/item/6245275827f86abb2ac4afb9.png)

和8421码一样，我们2421码改变了权值
比如5

$$
1011 = 1*2 + 0*4 + 1*2 + 1*1 = 5
$$

!!! note 注意
    0到4所有的开头都是0
    5到9所有的开头都是1

# 总结

![](https://pic.imgdb.cn/item/62459fe327f86abb2ab7c99d.png)