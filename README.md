# Reference

### CNN

[EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks](https://arxiv.org/abs/1905.11946) --> In this paper, we systematically study model scaling and identify that carefully balancing network depth, width, and resolution can lead to better performance.

--> Related Work --> Reference

[MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications](https://arxiv.org/abs/1704.04861) --> We introduce two simple global hyperparameters that efficiently trade off between latency and accuracy.

--> [Depth-wise Convolution and Depth-wise Separable Convolution](https://medium.com/@zurister/depth-wise-convolution-and-depth-wise-separable-convolution-37346565d4ec) / Having so much parameters increases the chance of over-fitting.

[Xception: Deep Learning with Depthwise Separable Convolutions](https://openaccess.thecvf.com/content_cvpr_2017/html/Chollet_Xception_Deep_Learning_CVPR_2017_paper.html)

#### input, conv_layer, output formula example, for the simplicity omit batch dimension
<img src="https://github.com/sandokim/Reference/blob/main/images/Conv_formula.JPG" width="80%">

## Computer Vision Trend

In many real world applications such as robotics, self-driving car and augmented reality, the recognition tasks need to be carried out in a timely fashion on a computationally limited platform.

### Convolution operation

[[Deep Learning] 딥러닝에서 사용되는 다양한 Convolution 기법들](https://eehoeskrap.tistory.com/m/431)

* Covolution
* Dilated Convolution (atrous, Deconvolution) -> 적은 계산 비용으로 Receptive Field를 늘리는 방법, Contextual Information이 중요한 분야에 유리
* Transposed Convolution (Deconvolution or fractionally strided convolution) -> Super resolution에 사용, 이미지 크기를 복원하는 방법은 Transposed convolution 이외에도 Bilinear interpolation과 같은 보간이 있다.
* Separable Convolution -> 커널 작업을 여러 단계로 나눈다.
* Depthwise Convolution -> 각 단일 채널에 대해서만 수행되는 필터를 사용, 연산량 급감, 채널 방향의 Convolution은 진행X, 공간 방향의 Convolution만 진행
* Depthwise Separable Convolution -> 채널의 출력 값이 하나로 합쳐지는 특징, Spatial feature와 Channel-wise Feature를 모두 고려하여 네트워크를 경량화한다. Depthwise Convolution을 진행한 것을 1개의 채널로 압축하는 추가적인 Convolution 진행.
* Pointwise Convolution-> 공간방향의 컨볼루션은 진행하지 않고, 채널방향의 컨볼루션만 진행, Channel Reduction에 주로 사용, 연산속도 향상 but 정보손실 발생, Inception/Xception/SqueezeNet/MobileNet에서 경량화와 성능 개선의 효능이 입증됨.
* Grouped Convolution -> 입력 값의 채널들을 여러 개의 그룹으로 나누어 독립적으로 Convolution 연산 수행, 낮은 파라미터수와 연산량, 각 그룹에 높은 Correlation을 가지는 채널이 학습될 수 있다.
* Deformable Convolution -> 기존 CNN에서 사용하는 연산(conv/pooling/roi pooling/etc..)은 기하학적으로 일정한 sampling grid를 가지므로 복잡한 Transformation에 유연하게 대처하기 어렵다는 한계가 있다. Deformable Convolution은 convolution에 사용하는 sampling grid에 2D offset을 더하여 다향한 패턴으로 변형시켜 사용한다. 일정하게 sampling pattern 이 고정되어있지 않고, 큰 object 에 대해서는 receptive field 가 더 커진 것을 확인 할 수 있다.

<img src="https://github.com/sandokim/Reference/blob/main/images/deformable_convolution.PNG" width="80%">

fractional number : 분수

a 1×1 convolution called a pointwise convolution.

## Model Compression

A different approach for obtaining small networks is shrinking, factorizing or compressing pretrained networks. Compression based on product quantization [36], hashing [2], and pruning, vector quantization and Huffman coding [5] have been proposed in the literature. Additionally various factorizations have been proposed to speed up pretrained networks [14, 20]. Another method for training small networks is distillation [9] which uses a larger network to teach a smaller network. (MobileNets paper)

##### Huffman coding?

<img src="https://github.com/sandokim/Reference/blob/main/images/huffman coding.JPG" width="80%">
