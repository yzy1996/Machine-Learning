English | [简体中文](./README.zh-CN.md)


#  Generative Adversarial Networks(GAN)


![country](https://img.shields.io/badge/country-China-red)

This is my  research summary on Generative Adversarial Networks and I sort them into:

- Traditional GAN
- Applicational GAN
- Multi-Objective GAN



**Introduction of GAN**

> 

If you want to know more about more details of the derivation or the difficult of GAN’s training, you can see the part of [Traditional GAN](#Traditional-GAN)



**Why Are GANs So Popular?**

GANs are popular partly because they tackle the important unsolved challenge of unsupervised learning.

If intelligence was a cake, unsupervised learning would be the cake, supervised learning would be the icing on the cake, and reinforcement learning would be the cherry on the cake. We know how to make the icing and the cherry, but we don’t know how to make the cake. – Yann LeCun, 2016.



**Why is there an “s” after GANs?**

> It means GAN and its variants



**Commonly used datasets**

> Mnist, CelebA, LSUN, and ImageNet



**Facing problem**

> - mode collapse: diversity the generator can only learn some limited patterns from the large-scale target datasets, or assigns all of its probability mass to a small region in the space.
> - vanishing gradient: 



**Evaluation metrics of GAN**

> paper: https://arxiv.org/pdf/1806.07755.pdf
>
> code: https://github.com/xuqiantong/GAN-Metrics
>
> blog: https://zhuanlan.zhihu.com/p/99375611



## [Traditional GAN](1-Traditional-GAN)

The development of some famous GAN models including <u>Vanilla GAN</u>, <u>DCGAN</u>, <u>WGAN</u>

## [Applicational GAN](2-Applicational-GAN)

Some applications of GAN including the use of defense

## [Multi-Objective GAN](3-Multi-Objective-GAN)

Add multi-objective and evolutionary algorithm into GAN





### objective functions of GANs



**vanilla GAN**
$$
\min _{G} \max _{D} V(D, G)=\mathbb{E}_{\boldsymbol{x} \sim p_{\mathrm{data}}(\boldsymbol{x})}[\log D(\boldsymbol{x})]+\mathbb{E}_{\boldsymbol{z} \sim p_{\boldsymbol{z}}(\boldsymbol{z})}[\log (1-D(G(\boldsymbol{z})))]
$$

$$
\min J^G = \mathbb{E}_{\boldsymbol{z} \sim p_{\boldsymbol{z}}(\boldsymbol{z})}[\log (1-D(G(\boldsymbol{z})))]
$$

where $J^G$ is the cost of for generator, $\log D(x)$ is the cross-entropy between $[D(x) \quad 1-D(x)]^T$ and $[1 \quad 0]^T$. Likewise,  $\log (1-D(G(z)))$ is the cross-entropy between $[1-D(G(z)) \quad D(G(z))]^T$ and $[1 \quad 0]^T$. It’s because that the cross-entropy 

For a fixed generator $G$, the optimal discriminator $D$ is:
$$
D^*(x)=\frac{p_{data}(x)}{p_{data}(x)+p_{g}(x)},
$$
For this optimal $D^*$, the optimal $G$ satisfies:
$$
p_g(x) =p_{data}(x).
$$

> Problem: 
>
> The cross-entropy of $G$ can be expressed as follow:
> $$
> H^G = 1 * \log(1-D(G(z))) + 0*log(D(G(z))) = \log(1-D(G(z)))
> $$
> In early training progress, D can easily distinguish fake samples from real samples ($D(G(z)) \rightarrow 0$). This results in G not having sufficient gradient to improve, which is called **training instability**. Rather than training G in the way of Equation (2), another way of Equation (6) could provides larger gradients in early training.
> $$
> \min J^G = \mathbb{E}_{\boldsymbol{z} \sim p_{\boldsymbol{z}}(\boldsymbol{z})}[-\log (D(G(\boldsymbol{z})))]
> $$
> So a new cross-entropy of $G$ can be expressed as:
> $$
> H = 1 * \log(-D(G(z))) + 0*log(1 + D(G(z)))
> $$
> 
>
> 



blog 

https://www.freecodecamp.org/news/an-intuitive-introduction-to-generative-adversarial-networks-gans-7a2264a81394/

https://wiki.pathmind.com/generative-adversarial-network-gan





some new work

https://github.com/hankhank10/fakeface

styleGAN

styleGAN2

https://thispersondoesnotexist.com/






