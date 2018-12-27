---
layout: post
title: "创建线程的三种方式"
subtitile: "创建线程的三种方式."
date: 2018-12-20 11:00:00
author: "乱码人生"
header-img: ""
tags:
     - Java
     - JavaSE
     - Thread
---

### 方法一：继承Thread类创建线程类
1. 定义Thread类的子类，并重写该类的run()方法，该run()方法的方法体就代表了线程需要完成的任务。
2. 创建Thread子类的实例，即创建线程对象。
3. 调用线程对象的start()方法来启动该线程。
### 方法二：实现Runnable接口创建线程类
1. 定义Runnable接口的实现类，并重写接口的run()方法，该run()方法的方法体就是线程的执行体。
2. 创建Runnable实现类的实例，并以此实例作为Thread的参数来创建Thread对象，该Thread对象才是真正的线程对象。
### 方法三：使用Callable和Future创建线程
1. 创建Callable接口的实现类，并实现call()方法，该call()方法将作为线程执行体，且该call()方法有返回值，再创建Callable实现类的实例。*java8 开始，可以直接使用Lambda表达式创建Callable对象* 
2. 使用FutureTask类来包装Callable对象，调用FutureTask对象的get()方法可以得到Callable对象call()方法的返回值。
3. 使用FutureTask对象作为Thread的参数创建并启动新线程。
4. 调用FutureTask对象的get()方法获取子线程执行结束后的返回值。