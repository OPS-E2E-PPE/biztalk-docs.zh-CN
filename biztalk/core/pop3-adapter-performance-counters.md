---
title: "POP3 适配器性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f799175e-e9e7-4937-93bd-aaec1c43b75a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c53bd0a487924a50155f388b6a657541ebe8fd3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="pop3-adapter-performance-counters"></a>POP3 适配器性能计数器
使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。 性能计数器能够帮助您标识和解决有关服务器性能的问题。  
  
 以下性能计数器进行访问每个主机实例下**BizTalk:POP3 接收适配器**性能对象类别：  
  
|**类别**|**计数器**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:POP3 Receive Adapter|Active sessions|POP3 适配器同时管理的 POP3 打开连接的数量。|  
||Bytes received|POP3 适配器从邮件服务器下载的总字节数。|  
||Bytes receive/Sec|POP3 适配器每秒从邮件服务器下载的字节数。|  
||收到的消息|POP3 适配器从邮件服务器下载的电子邮件总数。|  
||每秒接收的消息数|POP3 适配器每秒从邮件服务器下载的电子邮件数。|  
  
## <a name="to-access-performance-counters"></a>访问性能计数器  
 依照下述步骤访问 POP3 适配器的性能计数器：  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的是 Windows 2008  
  
1.  单击**启动**，指向**管理工具**，然后单击**性能监视器**。  
  
2.  在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:POP3 接收适配器**性能计数器对象，然后选择要将的计数器监视  
  
4.  在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，选择\<**所有实例**\>。  
  
5.  添加计数器后, 单击**确定**。  
  
     所选的性能计数器显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>另请参阅  
 [监视 BizTalk Server](../core/monitoring-biztalk-server.md)  
 [处理与 POP3 适配器的多部分消息](../core/processing-multi-part-messages-with-the-pop3-adapter.md)   
 [在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)