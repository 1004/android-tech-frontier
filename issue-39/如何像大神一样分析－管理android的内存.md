如何像大神一样分析－管理android的内存
---

> * 原文链接 : [How to Analyze & Manage Memory on Android Like a Boss](https://acadgild.com/blog/analyze-manage-android-devices-memory-allocation-through-ddms-mat/
)
* 原文作者 : [acadgild](https://acadgild.com/blog/)
* 译文出自 : [开发技术前线 www.devtf.cn](http://www.devtf.cn)
* 转载声明: 本译文已授权[开发者头条](http://toutiao.io/download)享有独家转载权，未经允许，不得转载!
* 译者 : [Juude](https://www.github.com/juude) 
* 校对者: [这里校对者的github用户名](github链接)  
* 状态 :  未完成


This Blog is all about memory management in Android. It provides information about how you can analyze & reduce memory usage while developing an Android app.

本文是关于Android内存管理的。告诉你在Android应用开发中，如何分析并且减少存的使用。

Memory management is a complex field of computer science and there are many techniques being developed to make it more efficient. This guide is designed to introduce you to some of the basic memory management issues that programmers face.

内存管理计算机科学中一个很复杂的领域，这方面正发展着许多高效的技术。本文将介绍程序员所遇到的一些基础性的内存管理问题。

###Memory Management in Android

###Android内存管理

Android is a Linux based operating system. It uses native open source C libraries which power Linux machines. All the basic operating system operations like I/O, memory management and so on are handled by the Linux kernel. Like Java and .NET, Android uses its own run time and virtual machine to manage application memory. Unlike either of these frameworks, the Android run time also manages the lifetime processes.

Andrid是一个基于Linux的操作系统。它使用了本地C库去管理Linux机器。所有的基本的操作系统操作，包括I/O, 内存管理等都是又Linux内核控制的。像Java和.Net一样，Android有自己的运行时和虚拟机去管理内存。然而和其他框架不同的是，Android的运行时也管理进程的生命周期。

Each Android application runs in a separate process within its own Dalvik instance, relinquishing all responsibility for memory and process management to the Android run time, which stops and kills processes, necessary to manage resources.  Dalvik is an open source, register-based virtual machine (VM) that is part of the Android Operating System. The Dalvik VM executes files in the Dalvik Executable (.dex) format. Resources are simple files in xml format.

每个Android应用运行在独立的进程中，并且有自己的Dalvik实例(译者注:5.0以后应该是ART),将内存与进程的管理功能都授权于Android运行时，Android运行时可以停止以及杀死进程，并且管理资源。Dalvik是一个开源的，基于寄存器的虚拟机，被内置于Android系统中。Dalvik虚拟机的可执行文件格式为Dalvik Excuteable的(.dex),资源文件则是简单的xml文件。

Dalvik and the Android run time sit on top of a Linux kernel that handles low-level hardware interaction including drivers and memory management, while a set of APIs provide access to all the under-lying services, features and hardware.

Dalvik和Android运行时基于可以管理内存和内存等底层操作的Linux内核，有一系列的API提供了对底层服务、特性以及硬件的访问。

A systematic examination and evaluation of data or information is very important so that we can manage the available memory in an effective way. For this we have DDMS in Android Studio IDE, using which we can analyze the memory being utilized. (IDE is Integrated Development Environment which provides the platform for developing an app in Android)

有一个对数据和信息系统性检查和评估机制是非常重要的，那样我们才能高效地管理可用的内存。因而Android在Android Studio中提供了DDMS，使用它我们可以分析Android的内存(IDE是Android开发app的集成开发环境)。

###DDMS

###DDMS
