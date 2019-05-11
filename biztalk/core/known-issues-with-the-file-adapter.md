---
title: 使用文件适配器的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aaf448c-0035-4648-910b-ae2f15106342
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef5da0b47efc357da7b3e85f3ceb48f93f3845b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380780"
---
# <a name="known-issues-with-the-file-adapter"></a>文件适配器的已知的问题
本部分包含可能帮助您避免错误的信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="a-file-receive-location-is-disabled"></a>文件接收位置被禁用  
  
##### <a name="problem"></a>问题  
 File 接收位置将被禁用。  
  
##### <a name="cause"></a>原因  
 如果发生以下任一情况，文件接收适配器将禁用接收位置：  
  
-   文件接收适配器无法访问文件系统上的接收位置或网络共享，因为指定的路径不存在。 对于网络共享，文件接收适配器已用完所有重试次数后禁用接收位置。  
  
-   文件接收适配器无法访问文件系统上的接收位置或网络共享，因为关联的主机实例使用的帐户没有对该位置的读写权限。 对于网络共享，文件接收适配器已用完所有重试次数后禁用接收位置。  
  
-   在接收位置遇到文件的名称长度超过 256 个字符。  
  
##### <a name="resolution"></a>解决方法  
  
-   请确保指定的路径或共享已存在。  
  
-   确保为所使用的帐户**登录：** 帐户文件接收处理程序主机实例具有读取和写入权限到指定接收位置。  
  
-   请确保接收适配器写入到该文件所监视的文件夹的文件不包含超过 256 个字符的文件名称。  
  
#### <a name="files-are-not-being-read-from-the-specified-receive-location"></a>从读取文件指定的接收位置  
  
##### <a name="problem"></a>问题  
 文件接收适配器不会读取从指定文件接收位置。 当文件接收适配器遇到此类文件时，它将事件日志中记录错误并将该文件留在接收位置。  
  
##### <a name="cause"></a>原因  
 如果任意下列条件为 true，则文件接收适配器不会从接收位置读取文件：  
  
-   文件为只读文件。  
  
-   该文件具有系统属性。  
  
-   文件接收适配器没有权限读取和写入文件。  
  
-   在接收位置遇到文件的名称长度超过 256 个字符。  
  
##### <a name="resolution"></a>解决方法  
  
-   请确保在指定文件接收位置未标记为"只读"。  
  
-   请确保在指定文件接收位置未标有系统属性。  
  
-   确保为所使用的帐户**登录：** 帐户文件接收处理程序主机实例具有读取和写入权限到指定接收位置。  
  
-   请确保接收适配器写入到该文件所监视的文件夹的文件不包含超过 256 个字符的文件名称。  
  
#### <a name="messages-are-not-being-sent-by-the-file-send-adapter"></a>不通过 File 发送适配器发送消息  
  
##### <a name="problem"></a>问题  
 文件发送适配器无法将消息发送到指定的目录或文件共享。  
  
 如果消息无法写入到指定的目录或文件共享，错误写入到 BizTalk server 计算机的事件日志并发生以下事件序列：  
  
1.  文件发送适配器将重试写入操作。  
  
2.  文件适配器将尝试传送文件使用备份传输 （如果已配置）。  
  
3.  该消息将写入到挂起队列。  
  
##### <a name="cause"></a>原因  
  
-   文件发送适配器无法访问文件会从文件系统或网络共享因为不存在指定的路径的目录。  
  
-   文件发送适配器无法写入到目标位置中的文件在文件系统或网络共享上因为关联的主机实例不具有该文件或对该位置的写权限。  
  
-   文件发送适配器无法写入文件指定，因为它是只读的或标有**系统**文件属性。  
  
##### <a name="resolution"></a>解决方法  
  
-   请确保指定的路径或共享已存在。  
  
-   确保为所使用的帐户**登录：** 文件发送处理程序主机实例帐户具有读取和写入到指定的目录或文件共享的权限。  
  
-   请确保指定的目录或文件共享中的现有文件不具有系统属性。  
  
#### <a name="sending-a-file-using-the-file-adapter-is-very-slow"></a>发送文件使用文件适配器时速度缓慢  
  
##### <a name="problem"></a>问题  
 文件发送适配器的性能条件时速度较慢**允许写入时缓存**属性设置为**False**。 **允许写入时缓存**属性设置为**False**默认情况下。  
  
##### <a name="cause"></a>原因  
 设置**允许写入时缓存**属性设置为**False**可以降低性能，因为此设置不允许使用内存中缓存的文件由操作系统。  
  
##### <a name="resolution"></a>解决方法  
 若要提高性能的文件发送适配器更改**允许写入时缓存**属性设置为**True** （选中复选框）。 有关详细信息**允许写入时缓存**属性，请参阅[如何配置 File 发送端口](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9)。  
  
> [!NOTE]
>  设置**允许写入时缓存**属性设置为**True**增加可能会丢失数据的情况在操作系统发生故障。 在此方案中，存储在内存中文件缓存中的任何数据将会丢失。  
  
#### <a name="zero-byte-files-received-by-the-file-adapter-are-deleted"></a>文件适配器接收到的零字节文件将被删除  
  
##### <a name="problem"></a>问题  
 如果为空 （零个字节） 文件将提取该文件接收适配器、 删除文件和 BizTalk server 的应用程序日志中写入类似于以下警告：  
  
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
 按照设计，文件接收适配器删除零字节文件。  
  
##### <a name="resolution"></a>解决方法  
 不不需要任何操作，此行为是有意设计。