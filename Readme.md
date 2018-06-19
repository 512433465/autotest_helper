# Lvmama Ui Automator Viewer使用帮助(夜神模拟器，OPPO真机亲测可用，其他设备未做测试，欢迎尝试)

## 1，安装准备

1. 打开手机模拟器，安装驴妈妈测试App （或者你的APP）

2. 复制LvmamaXmlKit.jar到本地D盘根目录下，打开命令行窗口执行命令：

   adb push D:\LvmamaXmlKit.jar /data/local/tmp/

3. 打开手机文件管理，到 /data/local/tmp/目录下，检查确保LvmamaXmlKit.jar是否复制到手机中

   ![1524477949570](https://github.com/512433465/autotest_helper/blob/master/11111.jpg)

4. 模拟器中安装ADBKeyBoard.apk并设置设置默认输入法为ADBKeyBoard，并关闭硬件物理键盘。

   ![1524478068333](https://github.com/512433465/autotest_helper/blob/master/22222.jpg)

   5.重命名自己电脑SDK目录的  \android-sdk-windows\tools\lib 下面的uiautomatorviewer.jar==》uiautomatorviewer.zip。复制共享目录\自动化\个人\autotest_helper\下面的uiautomatorviewer.jar到自己电脑SDK目录的  \android-sdk-windows\tools\lib 下

   6.点击uiautomatorviewer.bat 开启生成代码之旅。


## 2，使用说明

本工具基于安装自带的uiautomatorviewer进行二次开发，主要优化xpth提取，支持选取短的相对xpath，同时支持全部索引xpath定位，以及基于UiSelector的定位。选取元素后，增加右键菜单，提供了，常用的点击，输入，长按，等待，查找元素，按键等代码的生成。使用本工具前请先确认adb 是否能连上您的设备，如未连上，请百度自行解决谢谢！

1.使用示例

![1524479147962](https://github.com/512433465/autotest_helper/blob/master/33333.jpg)

如上图，点击门票后，右击，弹出菜单，选择Click时，弹出ClickBy菜单，选择xpth 时，会生成driver.findElement("//android.widget.ImageView[@content-desc='门票']","xpath").click();

2，同步点击手机，选择Click（Reshot），或者Longpress（Reshot）菜单时，会同步点击模拟器，并重新截取屏幕。

3，同步输入，选择input时，会在手机控件同步输入。更多使用方法期待您的发现，如使用中有任何问题，欢迎讨论交流！


测试交流论坛：https://testerhome.com/
工具交流QQ群：610460807
