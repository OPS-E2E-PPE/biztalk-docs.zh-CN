---
title: "文件适配器的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aaf448c-0035-4648-910b-ae2f15106342
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2690803346efc5931a88acd70be9d24af107156f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-file-adapter"></a>文件适配器的已知的问题
本部分包含可帮助你避免出现错误的信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="a-file-receive-location-is-disabled"></a>文件接收位置被禁用  
  
##### <a name="problem"></a>问题  
 文件接收位置被禁用。  
  
##### <a name="cause"></a>原因  
 如果出现以下任一情况，文件接收适配器将禁用接收位置：  
  
-   由于指定路径不存在，文件接收适配器无法访问文件系统或网络共享上的接收位置。 对于网络共享，文件接收适配器在全部重新尝试次数均已耗尽后禁用该接收位置。  
  
-   文件接收适配器无法访问文件系统或网络共享上的接收位置，因为关联的主机实例使用的帐户不具有该位置的读写权限。 对于网络共享，文件接收适配器在全部重新尝试次数均已耗尽后禁用该接收位置。  
  
-   在接收位置上遇到文件名长度超过 256 个字符的文件。  
  
##### <a name="resolution"></a>解决方法  
  
-   请确保指定的路径或共享已存在。  
  
-   请确保帐户用作**登录：**帐户为 File 接收处理程序主机实例具有读取和写入权限指定接收位置。  
  
-   请确保写入由文件接收适配器监视的文件夹的文件的文件名长度不超出 256 个字符。  
  
#### <a name="files-are-not-being-read-from-the-specified-receive-location"></a>文件没有从指定的接收位置读取  
  
##### <a name="problem"></a>问题  
 文件接收适配器没有从指定的接收位置读文件。 如果文件接收适配器遇到这种文件，它将在事件日志中记录一个错误，并将该文件留在接收位置。  
  
##### <a name="cause"></a>原因  
 如果出现以下任一情况，则文件接收适配器无法从接收位置读取文件。  
  
-   文件为只读文件。  
  
-   文件具有系统属性。  
  
-   文件接收适配器没有读写该文件的权限。  
  
-   在接收位置上遇到文件名长度超过 256 个字符的文件。  
  
##### <a name="resolution"></a>解决方法  
  
-   请确保位于指定接收位置的文件没有被标记为“只读”。  
  
-   请确保位于指定接收位置的文件不具有系统属性。  
  
-   请确保帐户用作**登录：**帐户为 File 接收处理程序主机实例具有读取和写入权限指定接收位置。  
  
-   请确保写入由文件接收适配器监视的文件夹的文件的文件名长度不超出 256 个字符。  
  
#### <a name="messages-are-not-being-sent-by-the-file-send-adapter"></a>消息未被文件发送适配器发送  
  
##### <a name="problem"></a>问题  
 文件发送适配器无法将消息发送到指定的目录或文件共享。  
  
 如果消息无法写入指定的目录或文件共享，就会在 BizTalk Server 计算机的事件日志中写入一个错误，并发生以下事件序列：  
  
1.  文件发送适配器将重试写操作。  
  
2.  文件适配器将尝试使用备份传输（如果已配置）传送文件。  
  
3.  消息将写到挂起队列。  
  
##### <a name="cause"></a>原因  
  
-   由于指定路径不存在，文件发送适配器无法访问文件系统或网络共享上从中发送文件的目录。  
  
-   文件发送适配器无法写入文件系统或网络共享上的目标位置中的文件，因为关联的主机实例不具有该文件或该位置的写权限。  
  
-   File 发送适配器无法写入指定，因为它是只读的或用标记文件**系统**文件属性。  
  
##### <a name="resolution"></a>解决方法  
  
-   请确保指定的路径或共享已存在。  
  
-   请确保帐户用作**登录：**文件发送处理程序主机实例的帐户具有读取和写入到指定的目录或文件共享的权限。  
  
-   请确保位于指定目录或文件共享的现有文件不具有系统属性。  
  
#### <a name="sending-a-file-using-the-file-adapter-is-very-slow"></a>使用文件适配器发送文件速度很慢  
  
##### <a name="problem"></a>问题  
 File 发送适配器的性能速度较慢时**允许写入缓存**属性设置为**False**。 **允许写入缓存**属性设置为**False**默认情况下。  
  
##### <a name="cause"></a>原因  
 设置**允许写入缓存**属性**False**可以减小性能，因为此设置不允许使用内存中缓存文件的操作系统。  
  
##### <a name="resolution"></a>解决方法  
 若要提高性能的文件，将发送适配器更改**允许写入缓存**属性**True** （复选框）。 有关详细信息**允许写入缓存**属性，请参阅[如何配置文件发送端口](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9)。  
  
> [!NOTE]
>  设置**允许写入缓存**属性**True**增加可能出现数据丢失的事件中操作系统遇到失败。 在这种情况下，存储在内存中文件缓存的任何数据都会丢失。  
  
#### <a name="zero-byte-files-received-by-the-file-adapter-are-deleted"></a>删除文件适配器接收的零字节文件  
  
##### <a name="problem"></a>问题  
 如果文件接收适配器接收到一个空（零字节）文件，则该文件将被删除，并且在 BizTalk Server 的应用程序日志中将写入类似下面的警告：  
  
```  
Event Type:Warning  
Event Source:BizTalk Server 2009  
Event Category:BizTalk Server 2009   
Event ID:7182  
Date:8/30/2006  
Time:1:32:32 PM  
User:N/A  
Computer:BIZTALKSERVER  
Description:  
The FILE receive adapter deleted the empty file "C:\filesource\emptyfile.xml.BTS-WIP" without performing any processing.  
```  
  
##### <a name="cause"></a>原因  
 由于设计的结果，文件接收适配器删除零字节文件。  
  
##### <a name="resolution"></a>解决方法  
 无需任何操作，此行为是有意设计成这样的。