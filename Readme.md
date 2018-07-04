# Lvmama Ui Automator Viewer使用帮助（兼容支持IOS，安卓）

#### 项目介绍
二次开发 uiautomatorviewer 优化定位符生成，支持生成Java，Python自动化代码，修复自带工具画面有动态加载时截图失败问题，优化自带工具截图速度 ，实现类似录制脚本功能。兼容IOS安卓。

#### 软件架构
本工具以安卓SDK自带uiautomatorviewer为源码基础，在此上进行深度二次开发。
- 优化定位符Xpath生成，提取相对短的Xpath，解决自带工具Xpath太长不友好的问题
- 修复自带uiautomatorviewer截图报错，无法截图的Bug
- 优化截图速度优化获取Xml速度，至少减少原截图耗时的一半
- 支持生成Java，Python自动化代码，实现类似录制脚本功能,生成后只需Ctrl+C，Ctrl+V到自己的代码中即可运行
- 兼容IOS，安卓，支持真机以及模拟器,你无需要换工具安卓平台和Mac平台都可以使用此工具
- 优化删除IOS的Xml中的垃圾空节点，定位元素更清爽

#### 安装教程

1. 本工具和SDK自带Jar相同无需安卓。前提是您Mac或者Windows系统中已经安装并且配置好了Java1.8环境
2. Windows环境，复制该jar到您SDK安装目录uiautomatorviewer.jar所在的目录下(请先备份你原来的jar，一般目录在SDK的tools\lib下：\android-sdk-windows\tools\lib)
3. Mac环境，复制该jar到任意目录即可
4. 安卓自动化：
- 复制LvmamaXmlKit.jar到本地D盘根目录下，打开命令行窗口执行命令：adb push D:\LvmamaXmlKit.jar /data/local/tmp/
- 打开手机文件管理，到 /data/local/tmp/目录下，检查确保LvmamaXmlKit.jar是否复制到手机中（如图1）
- 模拟器中安装ADBKeyBoard.apk并设置设置默认输入法为ADBKeyBoard，并关闭硬件物理键盘（如图2）
- 打开您的app，点击uiautomatorviewer.bat 开启生成代码之旅。

图1：LvmamaXmlKit.jar推送成功与否检查示例

   ![1524477949570](https://github.com/512433465/autotest_helper/blob/master/11111.jpg)

图2：硬件物理键盘关闭与否检查示例

   ![1524478068333](https://github.com/512433465/autotest_helper/blob/master/22222.jpg)




## 2，使用说明

本工具基于安装自带的uiautomatorviewer进行二次开发，主要优化xpth提取，支持选取短的相对xpath，同时支持全部索引xpath定位，以及基于UiSelector的定位。选取元素后，增加右键菜单，提供了，常用的点击，输入，长按，等待，查找元素，按键等代码的生成。使用本工具前请先确认adb 是否能连上您的设备，如未连上，请百度自行解决谢谢！
1. Windows环境，和自带的uiautomatorviewer启动方式相同，找到您SDK安装目录的uiautomatorviewer.bat(一般目录在SDK的tools下：\android-sdk-windows\tools)双击启动即可
2. Mac环境，打开shell终端，1，输入cd xxx 进入你uiautomatorviewer.jar所放置的目录，回车,2：输入命令：java -XstartOnFirstThread -jar uiautomatorviewer.jar即可启动
3. 根据您项目需要，选择您要生成代码的语言（如图3）

图3：语言选择示例
![1524478068333](https://github.com/512433465/autotest_helper/blob/master/java_python.jpg)


## Python代码生成示例
- 选择Python，选中画面元素![1524479147962](https://github.com/512433465/autotest_helper/blob/master/python1.png)
- 选择Click-->id:![1524479147962](https://github.com/512433465/autotest_helper/blob/master/pyt222.png)
类似不再重复截图，欢迎尝试
选择Xpath：driver.find_element_by_xpath("//android.widget.ImageView[@content-desc='国内游']").click()
选择ID：driver.find_element_by_id("com.gift.android:id/search_edit").click()
选择desc：driver.find_element_by_accessibility_id("境外门票").click()
选择class：driver.find_element_by_class_name("android.widget.TextView").click()
选择text：driver.find_element_by_name("玩水季").click()

## Java代码生成示例

- ![1524479147962](https://github.com/512433465/autotest_helper/blob/master/33333.jpg)

- 如上图，点击门票后，右击，弹出菜单，选择Click时，弹出ClickBy菜单，选择xpth 时，会生成driver.findElement("//android.widget.ImageView[@content-desc='门票']","xpath").click();

- 同步点击手机，选择Click（Reshot），或者Longpress（Reshot）菜单时，会同步点击模拟器，并重新截取屏幕。

- 同步输入，选择input时，会在手机控件同步输入。更多使用方法期待您的发现，如使用中有任何问题，欢迎讨论交流！

测试交流论坛：https://testerhome.com/
工具交流QQ群：610460807
