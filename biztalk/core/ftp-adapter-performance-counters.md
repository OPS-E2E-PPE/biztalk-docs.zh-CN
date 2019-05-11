---
title: FTP 适配器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca5cbe67-9aa3-4194-816e-fab4eb551c07
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7710f0dc5cff707aee60892c833ad178eadb9f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387816"
---
# <a name="ftp-adapter-performance-counters"></a>FTP 适配器性能计数器
性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。 性能计数器可以帮助您确定和解决服务器性能问题。  
  
 以下性能计数器都可以访问每个主机实例下**biztalk: Ftp Receive Adapter**并**biztalk: Ftp Send Adapter**性能对象类别：  
  
|**类别**|**计数器**|**说明**|  
|------------------|-----------------|---------------------|  
|Biztalk: Ftp 接收适配器|接收的字节数|接收适配器通过 FTP 接收的字节总数。 此计数器递增 FTP 完全读取消息后接收适配器从 FTP 服务器。|  
||接收的字节数/秒|Ftp 接收的字节数接收适配器每秒。 计数器只计入消息已完全读取的 FTP 接收适配器从 FTP 服务器。|  
||接收的消息|接收适配器接收到的 FTP 消息的总数。 此计数器递增 FTP 完全读取消息后接收适配器从 FTP 服务器。|  
||收到的消息数/秒|适配器每秒接收的 ftp 接收的消息数。 计数器只计入消息已完全读取的 FTP 接收适配器从 FTP 服务器。|  
|Biztalk: Ftp 发送适配器|发送的字节数|发送适配器通过 FTP 发送的字节总数。 已写入目标 FTP 服务器的消息才是增加计数器的数值。|  
||发送的字节数/秒|Ftp 发送的字节数发送适配器每秒。 计数器仅应用于已写入目标 FTP 服务器的消息。|  
||发送的消息|发送适配器通过 FTP 发送的消息的总数。 已写入目标 FTP 服务器的消息才是增加计数器的数值。|  
||发送的消息数/秒|适配器每秒发送的 ftp 发送的消息数。 计数器仅应用于已写入目标 FTP 服务器的消息。|  
  
## <a name="to-access-performance-counters"></a>若要访问性能计数器  
 使用以下步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的 Windows 2008  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。  
  
2.  在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**biztalk: Ftp**性能计数器对象，然后选择要监视的计数器  
  
4.  在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。  
  
5.  添加计数器之后, 单击**确定**。  
  
     所选的性能计数器随即显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>请参阅  
 [监视 BizTalk Server](../core/monitoring-biztalk-server.md) [运行适配器处理程序在群集主机内的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)