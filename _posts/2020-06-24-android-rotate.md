---
layout: post
title: 安卓加载旋转效果
date: 2020-06-24
Author: 石强 
tags: [安卓]
comments: true
# toc: true  添加目录
# pinned: true 置顶
# categories: JavaScript
---

列表下拉，页面等待加载都可以使用。  
在res下创建drawable文件夹，在drawable下创建progress.xml文件，代码如下:  

\<?xml version="1.0" encoding="utf-8"?>  
\<animated-rotate xmlns:android="http://schemas.android.com/apk/res/android"  
android:drawable="@drawable/ab"  
android:pivotX="50%"   
android:pivotY="50%" /> 

在layout布局文件里写入:  

\<ProgressBar  
android:layout_width="wrap_content"  
android:layout_height="wrap_content"  
android:indeterminateBehavior="repeat"  
android:indeterminateDuration="100"  
android:layout_centerInParent="true"  
android:indeterminateDrawable="@drawable/progress"  
android:indeterminateOnly="true" />  
其中android:pivotX="50%" 和android:pivotY="50%" 图片为中心旋转，ab为旋转的图片。
