# 预测Spotify用户流失情况

根据用户注册的信息以及过往浏览的行为预测未来用户在Spotify平台留存还是流失。
项目的目标是根据预测的结果给予预测流失概率高的用户一些优惠措施以留住用户。

项目使用Spark完成数据的清理，分析，建模工作。使用F1 Score作为评估指标。


使用的环境与库
conda 4.6.14

pyspark                   2.4.3
pandas                    0.23.3
seaborn                   0.8.1
matplotlib                2.1.0
numpy                     1.12.1

pyspark基于Java虚拟机，需要安装Java 8

目录结构
README.md                 The top-level README for developers using this project.
Sparkify_Mini.ipynb       Jupyter notebooks
report                    The project report


项目发现
1 需要根据具体的应用场景设定评估指标的阈值，以平衡模型的性能与稳健性
2 综合考虑模型的稳健性，F1 Score与训练时间，选用RandomForest，设置numTrees=10, maxDepth=7,
其他为默认设置，最后模型在训练集与测试集上的F1 Score均在0.8左右
