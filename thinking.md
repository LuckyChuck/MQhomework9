# Thinking1	为什么股票预测问题容易出现过拟合，也就是在训练时结果很好，在真实环境中结果没那么好 #
答：用arima来说，它的预测值是个点，虽然在训练过程中的loss会比较小，但是因为股市本质上来说并非是个线性问题，其中会有很多不确定因素，所以正常来说，它的预测范围应该是个置信区间，所以会产生过拟合的现象，像本节课学习的prophet来说，它的预测结果是个置信区间，在一定程度上避免了过拟合的现象。
其次arma会对所有的数据，包括一些突变点的数据都进行训练，所以容易产生过拟合现象。

# Thinking2	Prophet与ARMA/ARIMA相比，优势在哪些地方 #
1.arma预测的是个点值，而prophet预测的是个置信区间，更符合现实情况，避免过拟合。
2.arma处理线性问题，而prophet在非线性上有更好的体现。
3.arma要求数据等长，而如果数据缺失，则需要使用插值等方法来预估缺失值，这样会引入噪音，影响模型结果
4.prophet可以对节假日或特殊时间点进行建模。
5.arma对于所有的数据进行训练，包括突变点，所以容易产生过拟合。而prophet会对突变点进行设置。一定程度上保护模型。
6.prophet有对于领域知识的一些设置，更符合现实情况。
7.在应用上，prophet包装性更好，比如内置plot