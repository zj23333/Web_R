# python虚拟环境

## 软件选择

venv, virtualenv, virtualenvwrapper, pipenv, pyenv, conda

## virtualenv 使用

### 创建环境

进入项目目录  
`$ virtualenv myenv`   创建虚拟环境  

### 文件结构

在项目目录下  

```
myenv/                  # 虚拟环境根目录
│── bin/                # 可执行文件目录（包含 python、pip 等）
│   ├── activate        # 激活脚本（Linux/macOS）
│   ├── python          # 虚拟环境的 Python 解释器
│   ├── pip             # 该环境下的 pip
│── lib/                # 依赖库目录
│   ├── pythonX.X/      # Python 版本目录
│   │   ├── site-packages/  # 该虚拟环境的 Python 库
│── include/            # C 头文件（扩展模块）
│── pyvenv.cfg          # 记录 Python 版本信息
```


### 激活/退出环境

`$ source myenv/bin/activate`  
激活后，终端会变成`(myenv) user@host:~/project$`  
然后照常使用pip,库会安装到`myenv/lib/pythonX.X/site-packages/`  
`$ deactivate`  
终端恢复  

# 安装python库

```
pip install pyppeteer
pip install paddlepaddle
pip install paddleocr
pip install yt-dlp
pip install ffmpeg
pip install --upgrade setuptools
```

# 使用PaddleOCR

运行PaddleOCR会自动下载**预训练模型**（.tar文件）。

# Linux部分屏幕截图

Shift + PrtSc

# 下载B站视频的命令行工具

yt-dlp：可以下很多网站的视频，但是下B站的视频有些只有声音没有图像  
<https://github.com/yt-dlp/yt-dlp>  
you-get：可以下很多网站的视频/图片/文字，但是不用cookie下B站的视频只能下480p的  
<https://github.com/soimort/you-get>  
BBDown：专门下B站的工具，功能强大，可以下1080p的，每一个视频都能下，能下列表/弹幕/字幕/封面etc  
<https://github.com/nilaoda/BBDown>  
lux：可以下很多网站的视频/图片/文字，还没试  
<https://github.com/iawia002/lux>  
youtube-dl：可以下很多网站的视频，还没试  
<https://github.com/ytdl-org/youtube-dl>  
bilix:专门下B站的工具，还没试  
<https://github.com/HFrost0/bilix>  
