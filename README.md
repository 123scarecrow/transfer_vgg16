# transfer_vgg16
vgg16迁移学习实现识别花
迁移学习，训练识别花的模型
该程序在windows下pyhton3 TensorFlow环境下可用

首先运行get_features.py获取特征值。//这一步可以线下完成，提前完成
  --get_feature.py中调用vgg16计算每一个花的特征值，
  --把计算得到的特征值存到codes.npy文件中保存起来和图片的标签存在labels中。
ftrain.py中定义了一个一层256全链接层和5全链接层，损失函数等
运行transfer_train.py 训练模型。//这一步可以线下完成，提前完成
  --保存模型到文件checkpoints，其中模型参数存在flowers.ckpt.meta中
运行transfer_test.py 进行测试，返回精确值。//这一步可以线下完成，提前完成
  --会先读取图片的特征值再加载训练好的模型。
运行app.py 提示输入一张图片，返回该花的名称。//程序入口
  --会先通过VGG16计算出该图片的特征，再加载训练好的模型。

#vgg16文件
vgg16.py中定义了vgg16的模型
vgg16.npy中存储了训练好的模型参数
utils.py是对图片的预处理
