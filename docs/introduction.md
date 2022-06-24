## Python入门
### 选择一个Python解释器

#### Python的现状 (2 vs 3)

[Python官网](https://www.python.org/)

~~当选择Python解释器的时候，一个首先要面对的问题是：“我应该选择Python 2还是Python 3？” 答案并不像人们想象的那么明显。~~
2022年了无脑选Python3


#### 实现

当人们谈论起 Python，他们不仅是在说语言本身，还包括其CPython实现。 Python 实际上是一个可以用许多不同的方式来实现的语言规范。

#### CPython

[CPython](https://github.com/python/cpython) 是Python的参考实现，用C编写。它把Python代码编译成 中间态的字节码，然后由虚拟机解释。CPython为Python包和C扩展模块提供了最大限度的兼容。

如果您正在写开源的Python代码，并希望有尽可能广泛的用户，用CPython是最好的。使用依赖C扩展的包，CPython是您唯一的选择。

所有版本的Python语言都用C实现，因为CPython是参考实现。

#### PyPy
[PyPy](https://www.pypy.org/) 是用RPython实现的解释器。RPython是Python的子集， 具有静态类型。这个解释器的特点是即时编译，支持多重后端（C, CLI, JVM）。

PyPy旨在提高性能，同时保持最大兼容性（参考CPython的实现）。

如果您正在寻找提高您的Python代码性能的方法，值得试一试PyPy。在一套的[基准测试](https://speed.pypy.org/)下， 它目前比CPython的速度快超过5倍 。

PyPy支持Python Python 2.7.18 和 3.7.10 

#### Jython
Jython 是一个将Python代码编译成Java字节码的实现， 运行在JVM (Java Virtual Machine) 上。另外，它可以像是用Python模块一样，导入 并使用任何Java类。

如果您需要与现有的Java代码库对接或者基于其他原因需要为JVM编写Python代码，那么 Jython是最好的选择。

Jython现在支持到Python 2.7 [3]。

#### IronPython
IronPython 是一个针对 .NET 框架的Python实现。它 可以用Python和.NET framework的库，也能将Python代码暴露给给.NET框架中的其他语言。

Python Tools for Visual Studio 直接集成了 IronPython到Visual Studio开发环境中，使之成为Windows开发者的理想选择。

IronPython支持Python 2.7 [4]。

#### PythonNet
Python for .NET 是一个近乎无缝集成的， 提供给本机已安装的Python .NET公共语言运行时（CLR）包。它采取与IronPython （见上文）相反的方法，与其说是竞争，不如说是互补。

PythonNet与Mono相结合使用，通过.NET框架，能使Python在非windows系统上（如OS X和Linux）完成操作。它可以在除外IronPython的环境中无冲突运行。

PythonNet支持Python 2.3到2.7 [5]。



### 安装指南

#### 下载
[官方下载页面](https://www.python.org/downloads/)

#### Pyenv
[Pyenv](https://github.com/pyenv/pyenv) 是一个允许多个Python解释器版本同时安装 于一台机器的工具。这解决了不同的项目需要不同版本的Python的问题。比如，为了兼容性， 可以很容易地为一个项目安装Python 2.7，而继续使用Python 3.4作为默认的编辑器。 pyenv不止限于CPython版本——它还能安装PyPy、Anaconda、miniconda、stackless、Jython 和IronPython解释器。

推荐使用 来管理Python版本
  

1. 安装 Python 3.10.4：
```
pyenv install 3.10.4
```

2. 创建一个新的虚拟环境：
```
pyenv virtualenv 3.10.4 example
```

3. 激活虚拟环境：
```
pyenv activate example
```
当前虚拟环境的名字会显示在提示符左侧（比如说 (venv)您的电脑:您的工程 用户名$） 以让您知道它是激活的。从现在起，任何您使用pip安装的包将会放在 `venv` 文件夹中， 与全局安装的Python隔绝开。

像平常一样安装包，比如：
```
pip install requests
```

4. 如果您在虚拟环境中暂时完成了工作，则可以停用它：
```
pyenv deactivate
```
这将会回到系统默认的Python解释器，包括已安装的库也会回到默认的。



### Python 开发环境

#### IDE

[PyCharm](http://www.jetbrains.com/pycharm/) 由JetBrains公司开发，此公司还以 IntelliJ IDEA闻名。它们都共享着相同的基础代码，PyCharm中大多数特性能通过免费的 Python 插件 带入到IntelliJ中。PyCharm由两个版本：专业版（Professional Edition）（30天试用）和 拥有相对少特性的社区版（Community Edition）（Apache 2.0 License）。
*以Python为主语言开发者的推荐使用PyCharm*

[Visual Studio Code](https://code.visualstudio.com/) 是一个免费的、轻量的、开源的IDE，支持Mac、Windows和Linux。它以诸如Node.js和Python等 开源技术构建，具有如Intellisense（自动补全）、本地和远程调试、linting（代码检查）等 引人注目的特性。MIT 许可证。