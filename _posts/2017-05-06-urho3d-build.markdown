---
layout:     post
title:      "Urho3D游戏引擎搭建"
subtitle:   " \"Hello World, Hello Blog\""
date:       2017-05-06
author:     "xiaolbj"
#header-img: "img/post-bg-2015.jpg"
tags:
    - Urho3D
---

> “Urho3D是一个轻量级、跨平台的2D和3D渲染的c++实现开源游戏引擎,在MIT许可协议下发布。利用OpenGL渲染或是3D9（Shader Model 2和OpenGL 2），是受到OGRE 和horde3d极大的鼓舞而延生。本文将描述Urho3D在Linux下的搭建。”

#下载Urho3D

Urho3D的项目地址是<https://github.com/urho3d/Urho3D>。
首先使用git将源代码克隆到本地，当然你也可以到项目主页直接[download](https://github.com/urho3d/Urho3D)。

	git clone https://github.com/urho3d/Urho3D Urho3d

#编译Urho3D

0. 安装开发工具包

	Debian-based的使用如下命令安装

		sudo apt-get install build-essential manpages-dev
		sudo apt-get install cmake

	RedHat-based的使用如下命令安装

		yum groupinstall 'Development Tools'
		yum -y install cmake

1. 安装Display server

	Debian-based的使用如下命令安装

		sudo apt-get install libx11-dev, libxcursor-dev, libxext-dev, libxi-dev, libxinerama-dev, libxrandr-dev, libxrender-dev, libxss-dev, and libxxf86vm-dev

	RedHat-based的使用如下命令安装

		sudo yum install libX11-devel, libXcursor-devel, libXext-devel, libXi-devel, libXinerama-devel, libXrandr-devel, libXrender-devel, libXScrnSaver-devel, and libXxf86vm-devel

2. 安装Sound server

	Debian-based的使用如下命令安装

		sudo apt-get install libpulse-dev

	RedHat-based的使用如下命令安装

		sudo yum install pulseaudio-libs-devel

3. 编译安装Urho3d

	切换到Urho3d的源码目录，里面有对应不同系统的sh或者bat脚本，根据你的系统选择适当的脚本文件。

		cd Urho3d
		./cmake_generic.sh my_urho3d_build

	执行完毕会在my_urho3d_build下生成很多文件，我们到里面执行

		cd my_urho3d_build
		cmake .
		make install

	接下来是漫长的等待，安装完成后就可以在命令行下
		
		Urho3DPlayer

	就能看到Urho3D自带的demo跑起来了。

4. 编译文档

	在my_urho3d_build目录执行

		make doc

	如果有提示缺少包，把缺少的包安装上，然后再次执行，等带编译完成，用浏览器运行my_urho3d_build/Docs/html/index.html，就能看到文档了。

	
