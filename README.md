# 神经网络里的mini-batch算法

## 在梯度下降中需要对所有样本进行处理过后然后走一步，那么如果样本规模的特别大的话效率就会比较低。假如有500万，甚至5000万个样本的话走一轮迭代就会非常的耗时。这个时候的梯度下降叫做full batch。 

## 所以为了提高效率，可以把样本分成等量的子集。 例如把100万样本分成1000份， 每份1000个样本， 这些子集就称为mini batch。然后分别用一个for循环遍历这1000个子集。 针对每一个子集做一次梯度下降。 然后更新参数w和b的值。接着到下一个子集中继续进行梯度下降。 这样在遍历完所有的mini batch之后相当于在梯度下降中做了1000次迭代。 将遍历一次所有样本的行为叫做一个 epoch，也就是一个世代。 在mini batch下的梯度下降中做的事情其实跟full batch一样，只不过训练的数据不再是所有的样本，而是一个个的子集。 这样在mini batch在一个epoch中就能进行1000次的梯度下降，而在full batch中只有一次。 这样就大大的提高了算法的运行速度。

## 既然有了mini batch，那就会有一个batch size的超参数，也就是块大小。代表着每一个mini batch中有多少个样本。 我们一般设置为2的n次方。 例如64,128,512,1024. 一般不会超过这个范围。不能太大，因为太大了会无限接近full batch的行为，速度会慢。 也不能太小，太小了以后可能算法永远不会收敛。 当然如果我们的数据比较小， 但也用不着mini batch了。 full batch的效果是最好的。
