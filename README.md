# Test-Projrct
This is a simple fraud detection model, not yet fully mature, the following provides the current model construction situation.

## 1、数据清洗（Data Cleaning）<br>
对原始数据主要进行了以下操作：<br>
（1）过滤方差过低的特征因子：本实验过滤方差小于0.5的特征因子 <br>
（2）处理有空值的特征因子：可以采用删除、用其他值填充 <br>
本实验中“出院诊断LENTH_MAX”有空值存在，但由于特征重要性排序较高，采用该特征因子列中不为空的值的平均值填充空值<br>
（3）进行数据归一化：考虑有模型对数据有归一化要求，本实验将数据分为归一化和未归一化两份<br>
（该过程于Data Processing实现）

## 2、模型选择（Model Selection）<br>
（1）本数据实验是否采用下采样？<br>
下采样通常在正常数据与异常数据比例极为不平衡时使用，本实验正常数据与欺诈数据所占百分比分别为：95.04%，4.96% <br>
（2）本实验采用哪种模型更适合？<br>
选择进行效果预测的模型有：LR（逻辑回归）、SVC（支撑向量机）、KNN（K近邻）、DT（决策树）、RFC（随机森林）、<br>
Bagging（集成学习bagging）、SGD（随机梯度）、GBC（集成学习Gradient）、xgb（极限梯度提升树）<br>
选用初步预测结果最优的模型xgb（极限梯度提升树），在XGB基础选用更优的LightGBM算法，并进行优化调参<br>
（该过程于Model Selection实现）

## 3、参数调优（Parameter tuning）<br>
通过不断修改调整超参数的设置，修改循环次数来优化模型，最后选择最优的模型，输出结果表格xlsx（结果按原数据顺序输出的RES列）<br>
（该过程于Model Tuning实现）

