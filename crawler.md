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


# 盲生发现了华点

用BBDown下载视频的时候，视频流编码选择HEVC或AVC就有画面，ffmpeg也能处理;AV1没有画面，ffmpeg会报错。VLC播放器用了ffmpeg所以他们一荣俱荣，一损俱损。
```
[ERROR:0@1324.386] global cap_ffmpeg_impl.hpp:1367 open Could not open codec av1, error: -1163346256                                                                            
[ERROR:0@1324.386] global cap_ffmpeg_impl.hpp:1375 open VIDEOIO/FFMPEG: Failed to initialize VideoCapture
```

# 用到的options

BBDown <url> [command] [options]

  -e, --encoding-priority <encoding-priority>    视频编码的选择优先级, 用逗号分割 例: "hevc,av1,avc"  
  -q, --dfn-priority <dfn-priority>              画质优先级,用逗号分隔 例: "8K 超高清, 1080P 高码率, HDR 真彩, 杜比视界"  
  -info, --only-show-info                        仅解析而不进行下载  
  --show-all                                     展示所有分P标题  
  -ia, --interactive                             交互式选择清晰度  
  --video-only                                   仅下载视频  
  --audio-only                                   仅下载音频  
  --danmaku-only                                 仅下载弹幕  
  --sub-only                                     仅下载字幕  
  --cover-only                                   仅下载封面  
  --debug                                        输出调试日志  
  --skip-mux                                     跳过混流步骤  
  -dd, --download-danmaku                        下载弹幕  
  -p, --select-page <select-page>                选择指定分p或分p范围: (-p 8 或 -p 1,2 或 -p 3-5 或 -p ALL 或 -p LAST 或 -p 3,5,LATEST)  

# 下载目标&命令

hevc编码，最高清晰度的音频和视频，下载弹幕，封面，字幕  

```
./BBDown https://www.bilibili.com/video/BV1EjdcY7EWf -e hevc,av1,avc -dd    # 优先下载hevc编码的视频，下载弹幕
./BBDown https://www.bilibili.com/video/BV1EjdcY7EWf --sub-only    # 下载字幕
./BBDown https://www.bilibili.com/video/BV1EjdcY7EWf --cover-only    # 下载封面
```
