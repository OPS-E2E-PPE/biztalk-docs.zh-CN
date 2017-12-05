---
title: "MSMQ 适配器性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab8b0342-c6c2-4113-ae54-359df28e5d30
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be7580ae6551fca18ee0a3b9b14b194006efd62e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="msmq-adapter-performance-counters"></a>MSMQ 适配器性能计数器
使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。 性能计数器能够帮助您标识和解决有关服务器性能的问题。  
  
 以下性能计数器进行访问每个主机实例下**BizTalk:MSMQ 接收适配器**和**BizTalk:MSMQ 发送适配器**性能对象类别：  
  
|**类别**|**计数器**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:MSMQ Receive Adapter|Bytes received|MSMQ 接收适配器接收到的字节总数。 MSMQ 接收适配器从源队列中完整读取一个消息后，该计数器的值才会增加。|  
||Bytes received/Sec|MSMQ 接收适配器每秒接收到的字节数。 该计数器只计入 MSMQ 接收适配器从源队列中完整读取的消息。|  
||收到的消息|MSMQ 接收适配器接收到的消息总数。 MSMQ 接收适配器从源队列中完整读取一个消息后，该计数器的值才会增加。|  
||每秒接收的消息数|MSMQ 接收适配器每秒接收到的消息数。 该计数器只计入 MSMQ 接收适配器从源队列中完整读取的消息。|  
|BizTalk:MSMQ Send Adapter|Bytes sent|MSMQ 发送适配器发送的字节总数。 该计数器只计入已到达目标队列的消息。|  
||Bytes sent/Sec|MSMQ 发送适配器每秒发送的字节数。 计数器仅适用于已到达目标队列的消息。|  
||发送的消息|MSMQ 发送适配器发送的消息总数。 该计数器只计入已到达目标队列的消息。|  
||每秒发送的消息数|MSMQ 发送适配器每秒发送的消息数。 计数器仅适用于已到达目标队列的消息。|  
  
## <a name="to-access-performance-counters"></a>访问性能计数器  
 依照下述步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的是 Windows 2008  
  
1.  单击**启动**，指向**管理工具**，然后单击**性能监视器**。  
  
2.  在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:MSMQ**性能计数器对象，然后选择要监视的计数器  
  
4.  在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，选择\<**所有实例**\>。  
  
5.  添加计数器后, 单击**确定**。  
  
     所选的性能计数器显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>另请参阅  
 [使用 MSMQ LoadGen 2007](../core/using-loadgen-2007-with-msmq.md)   
 [优化 MSMQ 适配器的性能](../core/optimizing-performance-of-the-msmq-adapter.md)