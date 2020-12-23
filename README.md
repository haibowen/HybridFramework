# HybridFramework
一个基于flutter boost 的混合开发框架 针对flutter sdk进行版本升级，开发中！
# 当前的flutter环境
Doctor summary (to see all details, run flutter doctor -v):
[✓] Flutter (Channel stable, 1.22.5, on macOS 11.1 20C69 darwin-x64, locale zh-Hans-CN)
 
[✓] Android toolchain - develop for Android devices (Android SDK version 30.0.2)
[✓] Xcode - develop for iOS and macOS (Xcode 11.6)
[✓] Android Studio (version 4.0)
[✓] Connected device (2 available)

# 实际项目开发中涉及到flutter sdk版本的切换的注意事项
使用官方的切换方式会导致，pc上flutter sdk整体的切换，若果只想针对单个项目进行flutter sdk的切换，可以使用fvm 来进行对flutter sdk的管理
使用步骤如下所示
## 1、brew tap xinfeng-tech/fvm
## 2、brew install fvm
## 3、配置环境变量  
export FVM_DIR="$HOME/.fvm" <br>
source "/usr/local/opt/fvm/init.sh"
## 4、切换到需要更改sdk的项目下
执行 fvm use 1.22.5 --local 即可<br>
fvm use version --local
## 5、安装新的sdk执行如下命令
fvm install 1.17.4  <br>
fvm install version

# 切换为flutter的最新版本的时候，Android模拟器 运行flutter boost会出现如下报错，运行ios模拟器暂未发先报错的地方
~~~


/Users/edz/AndroidStudioProjects/new/flutter_boost/android/src/main/java/com/idlefish/flutterboost/XFlutterTextureView.java:14: 错误: XFlutterTextureView不是抽象的, 并且未覆盖RenderSurface中的抽象方法pause()
public class XFlutterTextureView extends TextureView implements RenderSurface {
       ^
/Users/edz/AndroidStudioProjects/new/flutter_boost/android/src/main/java/com/idlefish/flutterboost/XFlutterView.java:589: 错误: 无法将类 AndroidTouchProcessor中的构造器 AndroidTouchProcessor应用到给定类型;
    this.androidTouchProcessor = new AndroidTouchProcessor(this.flutterEngine.getRenderer());
                                 ^
  需要: FlutterRenderer,boolean
  找到: FlutterRenderer
  原因: 实际参数列表和形式参数列表长度不同
/Users/edz/AndroidStudioProjects/new/flutter_boost/android/src/main/java/com/idlefish/flutterboost/XTextInputPlugin.java:89: 错误: <匿名com.idlefish.flutterboost.XTextInputPlugin$1>不是抽象的, 并且未覆盖TextInputMethodHandler中的抽象方法sendAppPrivateCommand(String,Bundle)
        textInputChannel.setTextInputMethodHandler(new TextInputChannel.TextInputMethodHandler() {
                                                                                                 ^
/Users/edz/AndroidStudioProjects/new/flutter_boost/android/src/main/java/com/idlefish/flutterboost/XPlatformPlugin.java:36: 错误: <匿名com.idlefish.flutterboost.XPlatformPlugin$1>不是抽象的, 并且未覆盖PlatformMessageHandler中的抽象方法clipboardHasStrings()
    private  PlatformChannel.PlatformMessageHandler mPlatformMessageHandler = new PlatformChannel.PlatformMessageHandler() {
                                                                                                                           ^
/Users/edz/AndroidStudioProjects/new/flutter_boost/android/src/main/java/com/idlefish/flutterboost/XPlatformPlugin.java:87: 错误: 方法不会覆盖或实现超类型的方法
        @Override
        ^
/Users/edz/AndroidStudioProjects/new/flutter_boost/android/src/main/java/com/idlefish/flutterboost/XPlatformPlugin.java:92: 错误: 方法不会覆盖或实现超类型的方法
        @Override
        ^
# 针对android版本做了简单的修复，目前可以正常使用
