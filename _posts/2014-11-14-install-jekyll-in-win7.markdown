---
layout: post
category: mood
title:  "在 Windows 上安装 Jekyll"
tags: [jekyll]
summary: "在 Windows 上安装 Jekyll"
---
###在 Windows 上安装 Jekyll

安装 Ruby

1. 前往 http://rubyinstaller.org/downloads/

2. 在 “RubyInstallers” 部分，选择某个版本点击下载。
例如， Ruby 2.1.4 是适于32位 Windows 机器上的 Ruby 2.1.4 安装包。

3. 通过安装包安装

最好保持默认的路径 C:\Ruby21， 因为安装包明确提出 “请不要使用带有空格的文件夹 (如： Program Files)”。
勾选 “Add Ruby executables to your PATH”，这样执行程序会被自动添加至 PATH 而避免不必要的头疼。

打开一个命令提示行并输入以下命令来检测 Ruby 是否成功安装。
ruby -v

输出示例：

ruby 2.1.4p265 (2014-10-27 revision 48166) [i386-mingw32]

安装 DevKit

DevKit 是一个在 Windows 上帮助简化安装及使用 Ruby C/C++ 扩展如 RDiscount 和 RedCloth 的工具箱。 详细的安装指南可以在程序的 wiki 页面 阅读。

再次前往 http://rubyinstaller.org/downloads/

下载同系统及 Ruby 版本相对应的 DevKit 安装包。 例如，DevKit-mingw64-32-4.7.2-20130224-1151-sfx.exe 适用于32位 Windows 系统上的 Ruby 2.1.4。

下面列出了如何选择正确的 DevKit 版本：

Ruby 1.8.7 and 1.9.3: DevKit-tdm-32-4.5.2-20111229-1559-sfx.exe
Ruby 2.0 and 2.1 (32bits version only): DevKit-mingw64-32-4.7.2-20130224-1151-sfx.exe
Ruby 2.0 and 2.1 (x64 - 64bits only): DevKit-mingw64-64-4.7.2-20130224-1432-sfx.exe

运行安装包并解压缩至某文件夹，如 C:\DevKit

通过初始化来创建 config.yml 文件。在命令行窗口内，输入下列命令：

cd “C:\DevKit”
ruby dk.rb init
notepad config.yml

在打开的记事本窗口中，于末尾添加新的一行 - C:\Ruby200-x64，保存文件并退出。

回到命令行窗口内，审查（非必须）并安装。

ruby dk.rb review
ruby dk.rb install


在window 平台的cmd 中安装
http://lee2013.iteye.com/blog/1488626
Ruby更改gem source

需要先移除source：https://rubygems.org/ 速度太慢 
cd D:\software\DevKit
gem sources
gem source -r https://rubygems.org/
gem source -a http://ruby.taobao.org

gem install jekyll
jekyll -v

安装 Python
Windows x86 MSI Installer (2.7.8)
python --version

python ez_setup.py
easy_install --version

gem install wdm
