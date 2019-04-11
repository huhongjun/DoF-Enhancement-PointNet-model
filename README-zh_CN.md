2019.03.14 调通,走了5epoch

PointNet
=======================================================
wget https://shapenet.cs.stanford.edu/media/modelnet40_ply_hdf5_2048.zip

样本数据为手动下载解压放入data目录
单次训练时长大致为 3.5 小时。5epoch用时30分钟 =>默认250epoch

python源码中涉及linux脚本cp,rm,mv,wget

To see HELP for the training script:

python train.py -h
We can use TensorBoard to view the network architecture and monitor the training progress.

tensorboard --logdir log
After the above training, we can evaluate the model and output some visualizations of the error cases.
http://localhost:6006

python evaluate.py --visu

PointNet++:
=======================================================

2018年5月29日：

尝试按照自述文档中的用法一节，训练样本数据的 ModelNet40，并记录了日志（点击下载日志压缩包）。本次训练按照自述文档的建议，使用两个显卡同时训练。单次训练时长大约 2 小时 20 分。

样本数据分两部分，即 ModelNet40 和 ShapeNetCore。

其中 ShapeNetCore 初次输入太大，实验室并不具备运行条件，遂没有尝试。

日志查看方法
上述提到的日志压缩包均为训练全部过程的记录。查看前将其解压到某个位置，然后使用 tensorboard 指定日志目录并运行即可。