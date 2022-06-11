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

a 1×1 convolution called a pointwise convolution.

## Model Compression

A different approach for obtaining small networks is shrinking, factorizing or compressing pretrained networks. Compression based on product quantization [36], hashing [2], and pruning, vector quantization and Huffman coding [5] have been proposed in the literature. Additionally various factorizations have been proposed to speed up pretrained networks [14, 20]. Another method for training small networks is distillation [9] which uses a larger network to teach a smaller network. (MobileNets paper)

##### Huffman coding?

<img src="https://github.com/sandokim/Reference/blob/main/images/huffman coding.JPG" width="80%">
