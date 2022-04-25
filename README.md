### Data Augmentation 논문

[GAN Augmentation: Augmenting Training Data using Generative Adversarial Networks](https://arxiv.org/pdf/1810.10863.pdf)

#### 본 논문에서 MR은 CT보다 higher observed variance가 존재하여 CT보다 더 많이 실험을 진행했다.

All segmentation experiments on CT were repeated 8 times, while those on MR were repeated 14 times to compensate for a higher observed variance.

<img src="https://github.com/Hyeseong0317/DataAugmentation/blob/main/images/synthesisbrain.JPG" width="60%">

#### GAN을 training distribution에서 interpolate할 수는 있지만 일반적인 rotation과 같은 augmentation처럼 tranining distribution의 끝을 넘어서 하는 extrapolate는 할 수 없다.

It is interesting to note that the improvements given by using both traditional and GAN augmentation, as seen in Table 3, are consistently more than the sum of the improvements given by using the two methods separately. This provides strong evidence that the additional information provided by the two augmentation methods are independent. It also suggests that when used together they are potentially synergistic, an observation which agrees with the results in [5]. This could be due to the two methods acting in different ways, with GANs providing an effective alternative to traditional augmentation when attempting to interpolate within the training distribution, but cannot extrapolate beyond its extremes without the aid of traditional augmentation like rotation.

[Progressive growing of GANs for improved quality, stability, and variation](https://arxiv.org/pdf/1710.10196.pdf)

PGGAN was chosen on the basis of its training stability at large image sizes and apparent robustness to hyperparameter selection.

[Are GANs created equal?](https://arxiv.org/pdf/1711.10337.pdf)

Whether the choice of GAN architecture will affect the quality of the augmentation is unclear, however there is evidence [14] to suggest that different GAN architectures produce results which are, on average, not significantly different from each other.

[MRI augmentation via elastic registration for brain lesions segmentation](https://link.springer.com/chapter/10.1007/978-3-319-75238-9_32)

