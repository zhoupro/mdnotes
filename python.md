## python开发工作流程
* create venv in project: python3 -m venv .venv
* source .venv/bin/activate
* install modules with pip3 and work with nvim using pyright
* deactivate

## 分享环境
* `pip3 freeze > requirements.txt`
* `pip3 install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple/`

## 调试
`import pdb; pdb.set_trace()`


## 避免使用共享目录

Windows file system doesn't support symbolic links, so if you're trying to create a virtual environment in a folder shared from the host machine, it's simply not going to work.
