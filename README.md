# 危险驾驶行为检测系统（Driver-Monitoring System）

该系统提供了通过摄像头实时监测、通过视频录像后期检测两大功能，检测范围包括双手离开方向盘、闭眼、哈欠、低头共四类行为。

## 系统特色

该系统采用了 __PERCLOS__ 疲劳程度评价指标来评价驾驶员的疲劳程度，并提供参考值供使用者分析驾驶员的疲劳状态。
<br>此外，该系统在实时监测驾驶员行为期间，会记录各个危险驾驶行为的出现时间，并通过可互动的图表展现驾驶员的总体状态。使用者可以通过五大图表充分了解到驾驶员的驾驶状态，并及时作出相应调整，避免事故的发生。

## 环境配置

本项目的运行环境为 __Python 3.9.13__，项目仓库内已经提供了 __requirements.txt__ 文件，但是为了预防万一，请在安装前先阅读下列两点
+ __Dlib__ 库的安装需要通过下载特定的 whl 文件才能完成！如果直接通过在终端输入命令 
    ```
    pip install dlib
    ```
  将无法正常安装并有报错信息。
  <br>你需要自行前往[ Dlib 官网](http://dlib.net/)并根据网站提供的[教程](http://dlib.net/compile.html)下载 __Dlib__ 的 whl 文件，在当前环境中安装。
+ 在安装 __Dlib__ 库之前，还需要安装 __cmake__ 库和 __boost__ 库，并需要有可用的 __C++__ 编译器，而执行下列命令则可以安装 __cmake__ 库和 __boost__ 库
    ```
    pip install cmake
    pip install boost
    ```
  这两个库被写入到了 __requirements.txt__ 中，你也可以直接执行下列命令，一样可以完成安装
    ```
    pip install -r requirements.txt
    ```

## 运行环境

如果你的用户文件夹包含中文字符，那么本项目就会无法正常运行。<br>
例如，你的用户文件夹路径为 C:\Users\中文用户名<br>
请在代码文件 main.py 开头加入下列代码
```python
import os
os.environ['HUB_HOME'] = './module'
```
其中 './module' 指定了本项目目录下的文件夹 module，该文件夹可以自行指定，但不能包含中文。<br>
此代码只需要在当前用户的用户文件夹包含中文字符时添加，如果用户文件夹名称为纯英文，则不需要添加。