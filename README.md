# SRTP
轨道交通门控

## 环境配置
1. conda 创建虚拟环境 <br>
* conda 的安装与使用可见文章：http://t.csdn.cn/BY2vj <br>
* 安装深度学习框架（Pytorch）和d2l软件包见：http://zh-v2.d2l.ai/chapter_installation/index.html <br>
2. 虚拟环境所需安装包（除上面过程已安装的部份外）**注意一定要安装到自己的虚拟环境中** <br>
* 安装sklearn: `conda install scikit-learn`
* 安装pandas: `conda install pandas`
* 安装numpy: `conda install numpy`
* 备注懒人方法（需要PyCharm，不推荐，后续跑代码可能出问题）:<br>
在 PyCharm 选择你创建的虚拟环境作为 Python Interpreter,然后打开代码看 import 项哪些缺失，PyCharm 可以帮你 install
3. jupyter notebook 配置 <br>
* 安装jupyter notebook（建议直接安装到自己电脑的base环境）: `win+r` -> `cmd` -> `pip install jupyter` 或 `pip3 install jupyter`
* 配置 jupyter 虚拟环境见文章：http://t.csdn.cn/w15dy
4. GPU 版本 Pytorch 安装（可选）<br>
* 见文章：http://t.csdn.cn/znhUM

## 模型介绍
保留全部标签：99\*256，256\*256，256\*40 的全连接神经网络 <br>
合并部分标签后：99\*256，256\*256，256\*28 的全连接神经网络

## 代码运行
**如果你想自己试着训练一下模型，可以运行前四个；如果只是想看模型效果，只需要运行第五个**
* `demo.ipynb` 用CPU训练模型
* `demo_gpu.ipynb` 用GPU训练模型
* `demo_gpu_label_only_normal.ipynb` 合并标签为两类：故障或非故障，使用线性分类器，效果极差
* `demo_gpu_unite_label.ipynb` 合并部分标签，只保留故障类型，舍弃列车编号。这部分训练出来的模型效果最好，所以保存了模型
* `load_model_and_eval.ipynb` 加载上面所提到的模型，并使用模型进行标签预测 <br>
