# Style_Transfer的教程
## 环境配置
对于已经熟练使用Miniconda/Anaconda的人来说，环境配置相对简单，注意到文件中的environment.yml文件  
只需在终端键入```conda env create -f environment.yml```即可，conda会根据environment.yml进行环境配置

### 安装miniconda
如果不熟悉Miniconda，可以在[这里](https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/) 进行下载并完成安装

### 配置镜像源
为了加快下载速度，可以配置conda使用国内的镜像源。以下是配置方法：

1. 打开终端（Windows用户可以使用Anaconda Prompt）。
2. 输入以下命令来配置清华大学的镜像源：
    ```sh
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
    conda config --set show_channel_urls yes
    ```
3. 验证配置是否成功：
    ```sh
    conda config --show channels
    ```
    你应该能看到刚刚添加的镜像源。

### 创建并激活环境
1. 在终端中导航到包含 `environment.yml` 文件的目录。
2. 创建环境：
    ```sh
    conda env create -f environment.yml
    ```
3. 激活环境：
    ```sh
    conda activate your_environment_name
    ```
    将 `your_environment_name` 替换为 `environment.yml` 文件中定义的环境名称。

## 运行文件
有 **.ipynb** 和 **.py**两种文件可供选择  
### 使用jupyter notebook(.ipynb)
在VS Code中运行文件,选择内核为刚才创建的 **sty_trans**  

修改第二代码块中的 `content_path` 以及 `style_path` 为你图片的路径

然后在每个代码块左侧依次点击运行按钮  

如果没有报错说明这个代码块正常运行  

### 使用python脚本(.py)

暂未填写

### 常见问题  


#### Question 1
Q:为什么显示我的设备是CPU? 我有GPU和CUDA  
A:你需要**安装和你的CUDA版本相应**的PyTorch&TorchVision

#### Question 2
Q:为什么最后一个代码框运行了很久?  
A:在使用CPU的情况下,需要运行相对久(5-10min)的时间才能完成2000轮

#### Question 3
Q:可以**修改代码参数**吗?  
A:当然可以,学习率(lr),内容损失和风格损失的权重(weight)都可以手动调整