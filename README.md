# HS300_index_enhance
沪深300指数增强模型



模型结构：

包括数据预处理、单因子检验、收益预测模型及风险模型四部分，具体流程可参考图片“指数增强模型结构”。



代码框架：

因子预处理.py：因子预处理主文件；

factor_data_preprocess.py：因子预处理功能文件，用于对计算后的原始因子数据进行预处理，包括缺失值处理、中位数法去极值、标准化及相对行业和市值中性化处理。

单因子检验.py：单因子检验主文件；

single_factor_test.py：单因子检验功能文件，用于对标准化后的单因子进行回归IC法检验、分层回测法检验，对有效因子进行初步筛选。

指数增强模型.py：指数增强模型运行主文件；

index_enhance.py：指数增强模型功能文件，用于对有效单因子进行因子合成与正交，进行收益预测，并通过风险模型进行权重优化，最终生成回测结果。




参数设置：

模型采用月频方式调仓，根据历史月频横截面回归计算因子溢价，并在每个月末根据最新的因子暴露预测下个月全部指数成分股收益，并通过风险模型以最大化组合的预测收益为目标，同时控制组合相对基准指数的行业及市值暴露，实现对组合中个股的权重优化，以沪深300增强为例，每个月通过模型从300只成分股中选出约60-90只个股，以最优权重构建组合。



历史表现：

模型2011年至今每年均能实现相对沪深300指数的超额收益，平均年化超额收益9.54%，2019年1月至8月，获得收益36.01%，相对沪深300的超额收益达9.81%。
