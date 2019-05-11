---
title: POP3 适配器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f799175e-e9e7-4937-93bd-aaec1c43b75a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87aaff170c75395b96b8d8d36d6efec6693e38ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394918"
---
# <a name="pop3-adapter-performance-counters"></a>POP3 适配器性能计数器
性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。 性能计数器可以帮助您确定和解决服务器性能问题。  
  
 以下性能计数器都可以访问每个主机实例下**BizTalk:POP3 Receive Adapter**性能对象类别：  
  
|**类别**|**计数器**|**说明**|  
|------------------|-----------------|---------------------|  
|BizTalk:POP3 Receive Adapter|Active sessions|同时管理 POP3 适配器的打开 POP3 连接的数目。|  
||接收的字节数|POP3 适配器从邮件服务器下载的字节的总数。|  
||接收的字节数/秒|POP3 适配器从邮件服务器每秒下载的字节数。|  
||接收的消息|POP3 适配器从邮件服务器下载的电子邮件消息的总数。|  
||收到的消息数/秒|POP3 适配器每秒从邮件服务器下载的电子邮件消息数。|  
  
## <a name="to-access-performance-counters"></a>若要访问性能计数器  
 请执行以下步骤访问 POP3 适配器的性能计数器：  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的 Windows 2008  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。  
  
2.  在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**BizTalk:POP3 Receive Adapter**性能计数器对象，然后选择要进行的计数器监视  
  
4.  在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。  
  
5.  添加计数器之后, 单击**确定**。  
  
     所选的性能计数器随即显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>请参阅  
 [监视 BizTalk Server](../core/monitoring-biztalk-server.md)  
 [使用 POP3 适配器处理多部分消息](../core/processing-multi-part-messages-with-the-pop3-adapter.md)   
 [在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)