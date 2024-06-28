---
noteId: "2876e19034fb11ef94da49bbb3095ec1"
tags: []

---



步骤1：下载Anaconda安装程序
打开浏览器，访问清华大学开源软件镜像站.
找到适合你的操作系统（Windows）的安装程序，然后点击下载。例如，对于64位Windows系统，下载Anaconda3-2022.05-Windows-x86_64.exe。
步骤2：运行安装程序
下载完成后，双击运行安装程序（例如：Anaconda3-2022.05-Windows-x86_64.exe）。
在安装向导中，点击“Next”继续。
阅读许可协议，然后选择“I Agree”以继续安装。
选择安装类型，一般建议选择“Just Me”，然后点击“Next”。
选择安装路径，默认安装路径是 C:\Users\YourUsername\Anaconda3。你可以根据需要更改安装路径，然后点击“Next”。
在“Advanced Installation Options”中，建议勾选“Register Anaconda as my default Python 3.9”，不勾选“Add Anaconda to my PATH environment variable”，然后点击“Install”开始安装。
安装完成后，点击“Next”，然后点击“Finish”完成安装。
步骤3：配置清华大学镜像源
打开“Anaconda Prompt”（可以通过开始菜单找到并选择Anaconda Prompt）。
在命令提示符中运行以下命令，配置Conda使用清华大学镜像源：

conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
配置完成后，可以使用以下命令验证：

conda config --show
你应该会看到已配置的清华大学镜像源。

步骤4：更新conda

conda update conda

步骤5：创建虚拟环境并安装PyTorch
创建虚拟环境：

conda create -n pytorch_env python=3.8
以上命令将创建一个名为pytorch_env的虚拟环境，并安装Python 3.8。你可以根据需要调整Python版本。

激活虚拟环境：

conda activate pytorch_env


安装PyTorch：
首先，确认你的CUDA版本。然后根据PyTorch官网提供的安装命令来安装GPU版本。以下是一个示例（假设你使用的是CUDA 11.1）：

安装CPU版本的PyTorch

conda install pytorch torchvision torchaudio cpuonly -c pytorch

安装GPU版本的PyTorch

conda install pytorch torchvision torchaudio cudatoolkit=11.1 -c pytorch -c nvidia

请根据你的CUDA版本调整cudatoolkit=11.1部分，例如cudatoolkit=10.2表示CUDA 10.2。
步骤6：验证安装
安装完成后，验证PyTorch是否安装成功。运行以下命令来启动Python交互式环境：

python

然后在Python交互式环境中运行以下代码：

import torch
# 检查PyTorch版本
print("PyTorch version:", torch.__version__)

# 检查CUDA是否可用
print("CUDA available:", torch.cuda.is_available())

# 如果CUDA可用，打印GPU信息
if torch.cuda.is_available():
    print("GPU device name:", torch.cuda.get_device_name(0))
如果输出PyTorch的版本号和相关信息，说明安装成功。

通过以上步骤，你可以在Windows上通过Anaconda成功安装和配置PyTorch。这种方法不仅能加快下载速度，还能保证安装过程的稳定性。如果遇到任何问题，可以参考Anaconda的文档或清华大学开源软件镜像站的帮助页面。










