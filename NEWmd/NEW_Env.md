# 环境配置
## 安装Pytorch、CUDA
注：YOLOv8源码中写了安装要求，python>=3.8，PyTorch>=1.8 。
检查是否安装成功，在命令行中的python编译器中验证：
```bash
python
import torch # 如果pytorch安装成功即可导入
print(torch.cuda.is_available()) # 查看CUDA是否可用
print(torch.cuda.device_count()) # 查看可用的CUDA数量
print(torch.version.cuda) # 查看CUDA的版本号
```

安装ultralytics：
```bash
pip install ultralytics -i https://pypi.tuna.tsinghua.edu.cn/simple
```
安装requirements.txt
```bash
pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
```

注：（存疑）matplotlib重新安装，为什么要重新安装？因为在训练结束之后，程序会用matplotlib对各种指标进行画图，如下所示。但是如果matplotlib版本过高就会导致错误：ImportError: Cannot load backend 'TkAgg' which requires the 'tk' interactive framework, as 'headless' is currently running。这个错误就会使得一些曲线图没法画出来，亲测呢！！！

卸载你的环境中matplotlib高版本，下载3.2.2版本。我是管用的。

```bash
pip uninstall matplotlib
pip install matplotlib==3.2.2 -i https://pypi.tuna.tsinghua.edu.cn/simple
```

