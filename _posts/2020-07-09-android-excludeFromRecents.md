---
layout: post
title: android:excludeFromRecents属性
date: 2020-07-09
Author: 石强 
tags: [安卓]
comments: true
# toc: true  添加目录
# pinned: true 置顶
# categories: JavaScript
---

在 Android 系统中，如果我们不想某个 Activity 出现在 “Recent screens” 中，可以设置 <activity> 属性 android:excludeFromRecents 为 true。其中有些需要注意到的地方说明下。

android:excludeFromRecents 属性并不会仅仅影响被设置的 Activity。由此该 Activity 启动的后续同属一个 “Task” 的一系列 Activity 都不会出现在 Recent screens。也就是说该属性是对 Task 起作用的，而不仅仅是某个 Activity。

所以想要后续的 Activity 能够出现在 Recent screens 中，就必须让后续 Activity 在新的 Task 中。

但是如果设置上面属性的 Activity 正是当前正在使用的，切换到 Recent screens 也是可以看到的。但是退到后台运行后，比如按下 Home 键，属性就会发生作用。

官方文档如下：

是否应将该 Activity 启动的任务排除在最近使用的应用列表（即概览屏幕）之外。 也就是说，当该 Activity 是新任务的根 Activity 时，此属性确定任务是否应出现在最近使用的应用列表中。 如果应将任务排除在列表之外，请设置“true”；如果应将其包括在内，则设置“false”。 默认值为“false”。

所以要想属性生效设置该属性的 Activity 必须是 Task 的根 Activity。如果在某个 Task 非根 Activity 中设置 android:excludeFromRecents 是没有任何效果的。