# conda

## 命令

```bash
conda create --name <env-name> python==3.7
conda activate <env-name>

conda install <package-name> -y
conda install -c conda-forge <package-name>

conda config --set show_channel_urls yes
```

## 镜像

国内可以配置[清华镜像源](https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/)加速 package 的安装。

```bash
channels:
  - defaults
show_channel_urls: true
channel_alias: https://mirrors.tuna.tsinghua.edu.cn/anaconda
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/pro
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
```

## package 推荐

| package | introduction |
| :--- | :--- |
| numpy |  |
| scikit-learn |  |
| scikit-image |  |
| tensorflow | Deep Learning |
| pytorch | Deep Learning |
| pyside2 | Qt GUI Python Binding |
| jupyter |  |
| ipython |  |
| gensim | NLP |
| pypinpin/jieba |  |

