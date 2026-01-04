# luci-app-openlist - for openwrt-18.06

一个支持多存储的文件列表程序。

## 如何构建

- 安装依赖：libfuse
  - ubuntu/debian:
    ```shell
    sudo apt update
    sudo apt install libfuse-dev
    ```

  - redhat:
    ```shell
    sudo yum install fuse-devel
    ```

  - arch:
    ```shell
    sudo pacman -S fuse2
    ```

- 进入你的OpenWrt目录

- Openwrt官方SnapShots

  *1. 需要Go 1.22.x或更高版本（用于修复旧版OpenWrt的构建问题）
  ```shell
  rm -rf feeds/packages/lang/golang
  git clone https://github.com/sbwml/packages_lang_golang -b 23.x feeds/packages/lang/golang
  ```

  *2. 获取luci-app-openlist源码并编译
  ```shell
  git clone https://github.com/lm379/luci-app-openlist -b lua package/openlist
  make menuconfig # choose LUCI -> Applications -> luci-app-openlist
  make package/openlist/luci-app-openlist/compile V=s # build luci-app-openlist
  ```

--------------

![](https://user-images.githubusercontent.com/16485166/190462187-5d54725e-1d9b-45f3-854f-403b882fb223.png)
