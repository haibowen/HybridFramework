# HybridFramework
一个基于flutter boost 的混合开发框架 针对flutter sdk进行版本升级，开发中！

# 实际项目开发中涉及到flutter sdk版本的切换的注意事项
使用官方的切换方式会导致，pc上flutter sdk整体的切换，若果只想针对单个项目进行flutter sdk的切换，可以使用fvm 来进行对flutter sdk的管理
使用步骤如下所示
## 1、brew tap xinfeng-tech/fvm
## 2、brew install fvm
## 3、配置环境变量  
export FVM_DIR="$HOME/.fvm"
source "/usr/local/opt/fvm/init.sh"
## 4、切换到需要更改sdk的项目下
执行 fvm use 1.22.5 --local 即可
## 5、安装新的sdk执行
fvm install 1.17.4
