---
title: "HTTP 适配器性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d85473f1-1d67-4990-8d2f-fc7fe0e80108
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21ae11dfb3ecd9a2b5e63449961af70aa3bc6f7d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-performance-counters"></a>HTTP 适配器性能计数器
使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。 性能计数器能够帮助您标识和解决有关服务器性能的问题。  
  
 以下性能计数器进行访问每个主机实例下**BizTalk:HTTP 接收适配器**和**BizTalk:HTTP 发送适配器**性能对象类别：  
  
|**类别**|**计数器**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:HTTP Receive Adapter|内存队列大小|HTTP 接收适配器的内部内存队列中的传入消息数。|  
||接收到的消息|HTTP 接收适配器收到的 HTTP 请求的总数。 HTTP 接收适配器从 HTTP 客户端完整读取一个请求消息后，该计数器的值才会增加。|  
||每秒接收的消息数|HTTP 接收适配器每秒收到的 HTTP 请求数。 该计数器只计入 HTTP 接收适配器已从 HTTP 客户端完整读取的请求消息。|  
||发送的消息|HTTP 接收适配器发送的 HTTP 响应的总数。 此计数器递增只对已成功地发送到 HTTP 客户端的响应消息中。|  
||每秒发送的消息数|HTTP 接收适配器每秒发送的 HTTP 响应数。 该计数器只计入已成功发送到 HTTP 客户端的响应消息。|  
||将消息添加到批中的时间|从 IIS 将消息发送到 HTTP 接收适配器，到将消息添加到批次，这之间的平均时间。|  
||生成批的时间|HTTP 接收适配器生成批消息所花费的平均时间。|  
|BizTalk:HTTP Send Adapter|内存队列大小|HTTP 发送适配器的内部内存队列中的传出消息数。|  
||收到的消息|HTTP 发送适配器收到的 HTTP 响应消息总数。 HTTP 发送适配器从 HTTP 服务器完整读取一个响应消息后，该计数器的值才会增加。|  
||每秒接收消息|HTTP 发送适配器每秒收到的 HTTP 响应数。 该计数器只计入 HTTP 发送适配器已从 HTTP 服务器完整读取的响应消息。|  
||发送的消息|HTTP 发送适配器发送的 HTTP 请求的总数。 此计数器只对已到达目标 URL 的请求消息时递增。|  
||每秒发送的消息数|HTTP 发送适配器每秒发送的 HTTP 请求数。 该计数器只计入已到达目标 URL 的请求消息。|  
  
## <a name="to-access-performance-counters"></a>访问性能计数器  
 依照下述步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的是 Windows 2008  
  
1.  单击**启动**，指向**管理工具**，然后单击**性能监视器**。  
  
2.  在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:HTTP**性能计数器对象，然后选择要监视的计数器  
  
4.  在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，选择\<**所有实例**>。  
  
5.  添加计数器后, 单击**确定**。  
  
     所选的性能计数器显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>另请参阅  
 [监视 BizTalk Server](../core/monitoring-biztalk-server.md)   
 [HTTP 适配器配置和优化参数](../core/http-adapter-configuration-and-tuning-parameters.md)   
 [运行在群集主机内的适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)