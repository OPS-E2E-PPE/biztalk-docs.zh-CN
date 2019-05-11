---
title: HTTP 适配器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d85473f1-1d67-4990-8d2f-fc7fe0e80108
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd3fa6a9dbb49edd5bbeee20230d1ccef2ac6baa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382845"
---
# <a name="http-adapter-performance-counters"></a>HTTP 适配器性能计数器
性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。 性能计数器可以帮助您确定和解决服务器性能问题。  
  
 以下性能计数器都可以访问每个主机实例下**biztalk: Http Receive Adapter**并**biztalk: Http Send Adapter**性能对象类别：  
  
|**类别**|**计数器**|**说明**|  
|------------------|-----------------|---------------------|  
|Biztalk: Http 接收适配器|内存队列大小|传入消息在 HTTP 接收适配器的内部内存队列。|  
||接收消息|接收适配器收到的 HTTP 的 HTTP 请求的总数。 此计数器递增后请求消息完全读取的 HTTP 接收适配器从 HTTP 客户端。|  
||收到的消息数/秒|适配器每秒接收的 http 接收到 HTTP 请求数。 该计数器仅适用于请求消息已完全读取的 HTTP 接收适配器从 HTTP 客户端。|  
||发送的消息|接收适配器通过 HTTP 发送的 HTTP 响应的总数。 仅对已成功发送到 HTTP 客户端的响应消息是增加计数器的数值。|  
||发送的消息数/秒|适配器每秒接收的 http 发送的 HTTP 响应数。 计数器仅应用于已成功发送到 HTTP 客户端的响应消息。|  
||若要将消息添加到批的时间|当消息发送到 HTTP 之间的平均时间接收适配器的 IIS 和时将消息添加到批处理。|  
||生成批处理的时间|HTTP 的平均占用时间接收适配器生成批消息。|  
|Biztalk: Http 发送适配器|内存队列大小|发送适配器的内部内存队列在 HTTP 的传出消息数。|  
||接收的消息|发送适配器通过 HTTP 接收 HTTP 响应消息的总数。 HTTP 发送适配器从 HTTP 服务器完整读取的响应消息后，计数器将递增。|  
||收到的消息数/秒|适配器每秒发送的 http 接收到的 HTTP 响应数。 计数器仅应用于已完全读取的 HTTP 发送适配器从 HTTP 服务器的响应消息。|  
||发送的消息|发送适配器通过 HTTP 发送的 HTTP 请求的总数。 仅对已到达目标 URL 的请求消息是增加计数器的数值。|  
||发送的消息数/秒|适配器每秒发送的 http 发送的 HTTP 请求数。 计数器仅应用于已到达目标 URL 的请求消息。|  
  
## <a name="to-access-performance-counters"></a>若要访问性能计数器  
 使用以下步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的 Windows 2008  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。  
  
2.  在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**biztalk: Http**性能计数器对象，然后选择要监视的计数器  
  
4.  在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。  
  
5.  添加计数器之后, 单击**确定**。  
  
     所选的性能计数器随即显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>请参阅  
 [监视 BizTalk Server](../core/monitoring-biztalk-server.md)   
 [HTTP 适配器配置和优化参数](../core/http-adapter-configuration-and-tuning-parameters.md)   
 [在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)