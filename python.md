###pyenv
> brew install pyenv

- 查看已安装版本：pyenv versions
- 查看可安装版本：pyenv install --list
- 安装特定版本的python：pyenv install \<version\>
- 安装完pyenv之后需要对数据库进行更新：pyenv rehash
- 设置全局Python环境：pyenv global 2.7.1
- 设置当前目录Python环境：pyenv local 2.7.1
- 在mac os下以framework形式安装Python：env PYTHON_CONFIGURE_OPTS="--enable-framework CC=clang" pyenv install 2.7.6

###pyenv-virtualenv
> brew install pyenv-virtualenv 

- pyenv virtualenv 3.3.0 env    #创建一个 Python 版本为 3.3.0 的环境, 环境叫做 env
- pyenv activate env_name       #激活 env 这个环境, 此时 Python 版本自动变为 3.3.0, 且是独立环境
- pyenv deactivate              #离开已经激活的环境

####可用链接
- [Anaconda](http://seisman.info/anaconda-scientific-python-distribution.html)
- [使用pyenv-virtual](http://ju.outofmemory.cn/entry/105367)
- [用pyenv搭建多版本Python虚拟环境](http://www.it165.net/pro/html/201405/13603.html)
- [Python多版本共存只pyenv](http://seisman.info/python-pyenv.html)
- [pyenv-virtualenv initialisation failing](https://github.com/yyuu/pyenv-virtualenv/issues/36#ref-commit-e0fa11e)

###virtualenv
> pip install virtualenv

- virtualenv test_env --no-site-packages #创建虚拟环境，不使用系统依赖库
- cd test_env & source ./bin/activate #启用虚拟环境
- deactivate #退出虚拟环境

####可用链接
- [virtualenv -- python虚拟沙盒](http://www.cnblogs.com/tk091/p/3700013.html)
- [VirtualEnv 和Pip 构建Python的虚拟工作环境](https://www.v2ex.com/t/42760)

###安装Python3.5.0问题
在mac上安装3.5.0版本Python，出现can't decompress data zlib not available mac，应该是系统刚升级Xcode命令行工具没安装好，可通过以下两种方案解决：
- xcode-select --install #输入改命令之后再安装
- CFLAGS="-I$(brew --prefix openssl)/include -I$(xcrun --show-sdk-path)/usr/include" \
LDFLAGS="-L$(brew --prefix openssl)/lib" \
pyenv install -v 3.5.0

####可用链接
- [OSX下的Python多版本管理器pyenv的安装设置](http://python.jobbole.com/84621/)

####安装问题解决
- [unknown locale: UTF-8解决方法](https://www.phodal.com/blog/unknown-locale-utf-8/)
- [building framework variants of Python on MacOS X](https://github.com/yyuu/pyenv/issues/99)
