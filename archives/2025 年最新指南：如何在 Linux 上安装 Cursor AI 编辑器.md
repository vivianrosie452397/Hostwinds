# 2025 年最新指南：如何在 Linux 上安装 Cursor AI 编辑器

Cursor 是一款以 AI 为核心的代码编辑器，支持 Windows、Mac 和 Linux 平台。它专为与 AI 协同编程设计，旨在帮助开发者更快速、高效地编写代码。我在 Mac 上成功安装并使用了 Cursor，但在 Ubuntu Linux 上安装却遇到了一些困难。经过一番研究，我终于成功在 Linux 上安装了 Cursor。以下是详细的安装步骤，帮助你在 Linux 上顺利运行 Cursor。

## 第一步：下载 Cursor

访问 [Cursor 官网](https://cursor.so)，点击 **"Download"** 按钮，下载适用于 Linux 的版本。

![Cursor AI 编辑器](https://bbtdd.com/img/99091797.webp)

## 第二步：检查下载文件

下载完成后，你会在下载文件夹中看到一个以 **.AppImage** 结尾的文件。

**什么是 .AppImage 文件？**

> **AppImage** 是一种通用软件包格式，无需传统的安装方法即可在 Linux 上运行。

## 第三步：使文件可执行

不要立即点击运行！首先，我们需要使该文件**可执行**。在终端中执行以下命令：

bash
chmod +x cursor-0.42.4x86_64.AppImage


**注意**：文件名可能会有所不同，请根据你下载的文件名进行调整。

## 第四步：解决 FUSE 错误

在运行 `.AppImage` 文件时，你可能会遇到以下错误：

bash
./cursor-0.42.4x86_64.AppImage
dlopen(): error loading libfuse.so.2

AppImages require FUSE to run. 
You might still be able to extract the contents of this AppImage 
if you run it with the --appimage-extract option. 
See https://github.com/AppImage/AppImageKit/wiki/FUSE 
for more information


**原因分析**

> 该错误提示 `.AppImage` 需要 FUSE 才能运行。FUSE 是一种机制，允许非特权用户在 Unix 类操作系统中创建自己的文件系统，而无需编辑内核代码。

**解决方案**

bash
sudo apt install libfuse2


## 第五步：启动 Cursor

安装 `libfuse2` 后，再次运行以下命令启动 Cursor：

bash
./cursor-0.42.4x86_64.AppImage


## 第六步：将 Cursor 添加到应用程序列表

### 将 Cursor 移动到 /opt 目录

bash
sudo mv cursor-0.42.4x86_64.AppImage /opt/cursor.appimage


### 创建桌面快捷方式

bash
sudo nano /usr/share/applications/cursor.desktop


在打开的文件中输入以下内容：

bash
[Desktop Entry]
Name=Cursor
Exec=/opt/cursor.appimage
Icon=/opt/cursor.png
Type=Application
Categories=Development;


保存并退出编辑器：

bash
ctl + x


### 添加图标

将一张 `.png` 图片文件命名为 `cursor.png` 并放入 `/opt` 目录中，这样应用程序列表中就会显示图标。

![Cursor 启动并显示自定义图标](https://bbtdd.com/img/336690510481462.webp)

**注意**：如果图标未显示，请尝试**注销后重新登录**。

---

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bbtdd.com/WildCard)