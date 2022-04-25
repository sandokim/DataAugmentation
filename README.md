### Data Augmentation 논문

[GAN Augmentation: Augmenting Training Data using Generative Adversarial Networks](https://arxiv.org/pdf/1810.10863.pdf)

#### 본 논문에서 MR은 CT보다 higher observed variance가 존재하여 CT보다 더 많이 실험을 진행했다.

All segmentation experiments on CT were repeated 8 times, while those on MR were repeated 14 times to compensate for a higher observed variance.

<img src="https://github.com/Hyeseong0317/DataAugmentation/blob/main/images/synthesisbrain.JPG" width="60%">

#### GAN을 training distribution에서 interpolate할 수는 있지만 일반적인 rotation과 같은 augmentation처럼 tranining distribution의 끝을 넘어서 하는 extrapolate는 할 수 없다. Traditional augmentation과 GAN Augmentation을 둘다 썼을 때가 둘 중 하나의 Augmentation만 썼을 때보다 성능이 우수했다.

It is interesting to note that the improvements given by using both traditional and GAN augmentation, as seen in Table 3, are consistently more than the sum of the improvements given by using the two methods separately. This provides strong evidence that the additional information provided by the two augmentation methods are independent. It also suggests that when used together they are potentially synergistic, an observation which agrees with the results in [5]. This could be due to the two methods acting in different ways, with GANs providing an effective alternative to traditional augmentation when attempting to interpolate within the training distribution, but cannot extrapolate beyond its extremes without the aid of traditional augmentation like rotation.

#### 확률분포상에서 GAN은 discrete data distribution의 안쪽을 채우는 역할을 한다.
One major advantage that traditional augmentation has over GAN augmentation is the ability to extrapolate. GANs can provide an effective way to fill in gaps in the discrete training data distribution and augment sources of variance which are difficult to augment in other ways, but will not extend the distribution beyond the extremes of the training data. In general, appropriate traditional augmentation procedures should be used to extrapolate and extend the manifold of semantically viable images. GANs can then be used to interpolate between the discrete points on this manifold, providing an additional data driven source of augmentation.

#### GAN은 training case가 적을수록 training data와 비슷한 이미지를 generate한다. 당연하다. GAN이 Training data로부터 배운 내용이 적기 때문이다. 반면에 training case가 증가할수록 생성한 이미지의 해부학적구조와 병변의 위치가 다양하게 나타난다. 이는 segmentation에서 data의 해부학적구조와 병변의 위치정보를 추가로 제공할 수 있으므로 모델 성능향상에 유리하다.

[Progressive growing of GANs for improved quality, stability, and variation](https://arxiv.org/pdf/1710.10196.pdf)

PGGAN was chosen on the basis of its training stability at large image sizes and apparent robustness to hyperparameter selection.

[Are GANs created equal?](https://arxiv.org/pdf/1711.10337.pdf)

Whether the choice of GAN architecture will affect the quality of the augmentation is unclear, however there is evidence [14] to suggest that different GAN architectures produce results which are, on average, not significantly different from each other.

[MRI augmentation via elastic registration for brain lesions segmentation](https://link.springer.com/chapter/10.1007/978-3-319-75238-9_32)

