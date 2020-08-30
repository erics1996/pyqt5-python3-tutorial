##### 1. PyQt5基础
###### 1.1 GUI编程学什么
- 大致了解你所选择的GUI库
- 基本的程序的结构：使用这个GUI库来运行你的GUI程序
- 各种控件的特性和如何使用
- 控件的样式
- 资源的加载
- 控件的布局
- 事件和信号
- 动画特效
- 界面跳转
- 设计工具的使用
###### 1.2 PyQT是什么
QT是跨平台C++库的集合，它实现高级API来访问现代桌面和移动系统的许多方面。这些服务包括定位和定位服务、多媒体、NFC和蓝牙连接、基于Chromium的web浏览器以及传统的UI开发。PyQt5是Qt v5的一组完整的Python绑定。它被实现为超过35个扩展模块，并使Python在所有支持的平台（包括IOS和Android）上被用作C++的替代应用程序开发语言。PyQT5也可以嵌入在基于C++的应用程序中，以允许这些应用程序的用户配置或增强这些应用程序的功能。
###### 1.3 PyQT的优势
- 简单好用
- 功能强大
- 跨平台支持
- 性能高
- 文档齐全：PyQT本身就是对QT库Python的绑定，在绑定的时候保持了原有的QT库的API。也就是说，PyQT除了自己的文档外，也几乎可以通用QT文档。
- 稳定性高：面向对象、信号与槽的机制、界面设计与业务代码完全隔离
- 生态支持：QU Designer进行图形界面设计、ui转换成py文件、资源处理
- 开源免费：PyQT是双重许可的，开发人员可以在GPL和商业许可之间进行选择。采用GPL协议，软件著作权属于开发者本人所有，受国际相关版权法保护，允许其他用户对原作者软件进行复制和发行，也可以更改后发型自己的软件。
###### 1.4 开发环境的安装
首先，基本的 Python3 环境和 PyCharm 开发工具的安装，由于比较简单，博主在这里不再详细演示了！实在有问题的可以自行Google或者百度。其次就是GUI开发环境的安装，也就是安装PyQT5。这里演示在Python的虚拟环境中来安装PyQT5（Ubuntu Linux系统）：
```js
# 在Python全局环境中安装pipenv
$ pip3 install pipenv -i https://pypi.tuna.tsinghua.edu.cn/simple

# 创建项目目录
$ mkdir pyqt5-pro

# 进入项目目录
$ cd pyqt5-pro/

# 创建虚拟环境
$ pipenv --three

# 激活虚拟环境(激活环境后会自动创建Pipfile文件)
$ pipenv shell

# 为加速安装，将源改为国内源
(pyqt5-pro) $ vim Pipfile
url = "https://pypi.tuna.tsinghua.edu.cn/simple"

# 安装pyqt5库
(pyqt5-pro) $ pipenv install pyqt5
```
这个时候我们使用Pycharm打开这个项目文件夹：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200109234253112.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1RoYW5sb24=,size_16,color_FFFFFF,t_70)
可以从设置中看到该项目依赖的Python环境：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200109234314228.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1RoYW5sb24=,size_16,color_FFFFFF,t_70)
###### 1.5 第一个pyqt5桌面应用
**`示例代码：`**
```py
from PyQt5.Qt import *
import sys

if __name__ == '__main__':
    # 创建QApplication类的实例
    app = QApplication(sys.argv)
    # 创建一个窗口
    window = QWidget()
    # 设置窗口标题
    window.setWindowTitle('Hello World!')
    # 设置窗口尺寸
    window.resize(400, 400)
    # 移动窗口位置
    window.move(1000, 300)
    # 创建label控件
    label = QLabel(window)
    # 为控件设置文本
    label.setText('Hello World!')
    # 移动空间的位置
    label.move(160, 160)
    # 显示窗口
    window.show()
    # 进入程序的主循环，并通过exit函数确保主循环安全结束
    sys.exit(app.exec_())
```
**`效果图[在windows平台中显示有差别于Linux(注意我这不是Mac OS系统，只是ubuntu linux系统使用了Mac OS的主题)]：`**
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200110090054186.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1RoYW5sb24=,size_16,color_FFFFFF,t_70)