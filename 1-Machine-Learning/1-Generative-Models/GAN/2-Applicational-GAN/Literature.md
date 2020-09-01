==Browsing on Github is recommended==



**[`Domain-Adversarial Training of Neural Networks(DANN)`]**

**[`2016`]** **[`JMLR`]** **[[:memo:](./Defense-GAN.pdf)]** **[[:octocat:](https://github.com/kabkabm/defensegan)]**

<details><summary>Click to expand</summary><p>


**The main work:**

> To solve the problem of **Domain Adaptation**
>
> 
>

</p></details>

---



**[`Multi-Task Adversarial Network for Disentangled Feature Learning`]**

**[`2018`]** **[`CVPR`]** **[[:memo:](./EMOO-Driven-by-GAN.pdf)]** **[[:octocat:]()]** 



Main idea:

Using a GAN like architecture to disentangles different features

---





**[`Transforming and Projecting Images into Class-conditional Generative Networks`]**

**[`2020`]** **[`ECCV`]** [project page](https://minyoungg.github.io/pix2latent/) **[[:octocat:](https://github.com/minyoungg/pix2latent)]** 







---

**[`Disentangled Representation Learning GAN for Pose-Invariant Face Recognition`]**

**[`2017`]** **[`CVPR`]** **[[:octocat:](https://github.com/zhangjunh/DR-GAN-by-pytorch)]** 


<details><summary>Click to expand</summary><p>


![Generator-in-multi-image-DR-GAN-From-an-image-set-of-a-subject-we-can-fuse-the-features_W64](https://raw.githubusercontent.com/yzy1996/Image-Hosting/master/20200831160904.jpg)

![Comparison-of-previous-GAN-architectures-and-our-proposed-DR-GAN_W640](https://raw.githubusercontent.com/yzy1996/Image-Hosting/master/20200831161231.jpg)

**key words**: 

> Pose-Invariant Face Recognition (PIFR); 

**Problem:** 

> solve the problem of pose-invariant face recognition (PIFR), the goal is to extract the identity representation that is exclusive or invariant to pose and other variations.

**Related work:** 

> existing PIFR methods can be group into two categories - 1) employ face frontalization to synthesize a frontal face and then use traditional face recognition methods. 2) learn features directly from the non-frontal face.

**Impact:**

> help law enforcement practitioners identify suspects

**Main method:**

> - the input of $G_{enc}$ is **a face image** of any pose; the output is **a feature representation**.
> - the input of $G_{dec}$ is **a feature representation** above, **a pose code** $c$, and **a random noise vector** $z$; the output of $G_{dec}$ is **a synthetic face image** at a target pose
> - $D$ is trained to not only distinguish **real vs. fake** images, but also predict the **identity and pose** of a face.

**Mainly including three features:**

> - identity - represented by feature extracted by $G_{enc}$
> - pose - represented by pose code 
> - other facial feature (appearance variations) - represented by noise vector



The learning problem are twofold: 1) to learn a pose-invariant identity representation for PIFR, and 2) to synthesize a face image $\hat{x}$ with the same identity $y^d$ but a different pose specified by a pose code $c$.

The approach is to train a DR-GAN **conditioned** on the original image $x$ and the pose code $c$.



Given a face image with label $y = \{y^d, y^p\}$, where $y^d$ represents the label for identity and $y^p$ for pose.



$\hat{x} = G(\mathbf{x}, c, z)$

</p></details>

---
