---
layout: default
title: Nginx
nav_order: 3
has_children: true
permalink: docs/nginx
---

# Nginx
{: .no_toc }

Nginx介绍与理解.
{: .fs-6 .fw-300 }

## 需求分析

Nginx是由伊戈尔·赛索耶夫为俄罗斯访问量第二的Rambler.ru站点开发。由此我们可以猜测一下伊戈尔当时面对的情况，访问量巨大，部署更新会中断服务，某请求错误导致进程崩溃进而影响其他请求，代码耦合度高。
针对不同的需求的解决方案：
	• 访问量巨大
	高并发处理能力强
	• 部署更新
	master-woker
	• 崩溃
	master-worker
	• 代码耦合度
	模块化

## master-worker模式

master责任：
	管理worker进程，也就是向worker发送命令，具体来说包含：接受来自外界的信号，向worker发送信号，监控worker进程。
worker责任：
         接收、处理、响应请求。
管理：
master管理监控worker，那么master与worker直接需要通信，假定我们以多进程的方式运行，则可供选择的方式有

## 码源文件结构
文件目录："/assets/images/nginx_code_struct.png"