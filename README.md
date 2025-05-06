# yyl
此项目为解决nano模型tensorrt推理加速的环境配置问题的方法



由于jetson nano是arm64架构，从而导致相当数量的库不能直接pip，得用jetson nano自带的包下，但是nano又是老版本没有pycuda的包，可是更新的话nano硬件又不支持新版本，这就导致了一个矛盾，对于解决这个问题，我选择另辟蹊径，直接放弃本地下载pycuda的想法，用另一种方法：我们直接从英伟达官方拉取官方配置好的机器学习镜像，然后再从下载到本地的镜像里复制相应的环境配置到本地环境，这样既轻松的解决了各种库之间不相容的问题，又不用每次都上传文件到容器那么麻烦
接下来是具体怎么实施的教程

首先打开英伟达ngc网址：https://www.nvidia.com/en-us/gpu-cloud/
然后注册账号，此步骤省略自行完成

接下来登录到 NVIDIA NGC
登录后，在 API Key 页面 创建一个 API 密钥（相当于你的登录密码）：https://org.ngc.nvidia.com/setup/api-key
![image](https://github.com/user-attachments/assets/ca6f8447-49d1-4ad8-a7af-becf3776bd07)
