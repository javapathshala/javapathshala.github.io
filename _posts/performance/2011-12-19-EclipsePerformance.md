---
layout: page
sidebar: right
breadcrumb: true
comments: true
title: "Eclipse Performance Improvement"
teaser: "Basic performance tweak is to install the latest eclipse from eclispe.org site. To have rocket speed eclipse based development environment, tweak your eclipse IDE installation. Eclipse installation contains an excellent intelligent file that can take care of Eclipse performance famously known as eclipse.ini."
categories:
          - performance
tags:
          - performance
          - eclipse
---

Below are tweaks that can be performed:

1. Introduce the -vm parameter to point eclipse to jdk. This is required if you are doing Maven development. Some maven goals reject to perform in absence of jdk path. This should be the first line in the elcpise.ini
-vm <Java Installation Path>\bin/javaw.exe
2. If you are not using maven, then probably point your eclipse to JRE instead of JVM as
  -vm <Java JRE Installation Path>\jre\bin\client\jvm.dll
  Referring to JVM instead of JDK has advantages such as
  ·         Splash screen coming up sooner.
  ·         Eclipse.exe in the process list instead of java.exe.

3. Set the heap & perm size to increase the performance. Hint Formulae: Specify half the size of RAM in have in your system i.e. if RAM size is 2GB [2048 MB] specify half the size in Xms & 4 times less in Permsize. So for 2 GB of RAM
  -vmargs -Xms1024m -Xmx512m -XX:PermSize=512m -XX:MaxPermSize=512m
4. -Xverify:none to eclipse.ini. This will reduce the eclipse start-up time by 50 %.
5.Navigate to  Windows->Preferences->General->Startup and Shutdown
Minimize the number of plugins to be loaded on startup
6. Navigate to Windows->Preferences->Validation," and uncheck any validators you don't want.
7. Remove all plug-ins, you don’t use.
8. Create separate workspace for projects you change rarely and include them as JARs to your primary project.
9. Use debug mode only when you are debugging (it is slower and uses more memory).
10. Another performance boost can be gained by disabling label decorations. Navigate to Windows -> Preferences->General -> Appearance -> Label Decorations).
11. Get additional performance by choosing a different garbage collection strategy depending on your JVM.
12. Use JavaRebel from ZeroTurnaround. This tool will shorten time spend on server/client restarts.
