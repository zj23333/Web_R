# python虚拟环境

## 软件选择

venv, virtualenv, virtualenvwrapper, pipenv, pyenv, conda

## virtualenv 使用

### 创建环境

进入项目目录  
$ virtualenv myenv   创建虚拟环境  

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

$ source myenv/bin/activate  
$ deactivate  
