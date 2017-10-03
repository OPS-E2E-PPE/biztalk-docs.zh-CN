---
title: "向外扩展发送主机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- hosts, sending
- FTP adapters, high availability
- EDI adapters, high availability
- hosts, high availability
- hosts, availability
- Windows SharePoint Services adapters, high availability
- scaling, hosts
- hosts, clustering
- scaling, adapters
- high availability, hosts
- clustering, hosts
- MSMQ adapters, high availability
- hosts, planning
- hosts, scaling
- adapters, scaling
ms.assetid: a3d79e0b-8c1e-471c-88e2-623600dfd81a
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1fb8ac3fe3752702ed3e1aa2795e521d7173618
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-out-sending-hosts"></a>扩展的发送主机
向外扩展的发送主机可确保中的发送功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高度可用。 如果向发送消息的主机添加多台计算机，您就可以运行多个发送主机实例以实现冗余和高可用性。  
  
 下图显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送主机通过在两台计算机正在运行的发送主机的实例提供高可用性的部署。 请注意，此图中的接收主机和处理主机并不高度可用。  
  
 ![缩放 &#45; 出发送主机](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")  
  
## <a name="high-availability-for-sending-hosts"></a>发送主机的高可用性  
 发送功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]类似于处理在这些活动都不需要任何主机和数据之间的关联的意义上的功能。 正如任何处理主机实例可从 MessageBox 数据库中检索消息并处理这些消息一样，任何发送主机实例也可以从 MessageBox 数据库中检索消息并发送这些消息。 因此，若要确保发送主机的高可用性，则需要使用确保处理主机的高可用性的相同方法。  
  
## <a name="scaling-the-biztalk-server-send-adapters"></a>扩展 BizTalk Server 发送适配器  
  
### <a name="high-availability-for-the-msmq-send-adapter"></a>MSMQ 发送适配器的高可用性  
 为确保 MSMQ 发送适配器的高可用性，您应群集 MSMQ 服务、群集与群集的 MSMQ 服务位于同一组中的 BizTalk 主机，并将 MSMQ 发送处理程序配置为在此群集的 BizTalk 主机中运行。 您应完成以上操作以确保 MSMQ 适配器启动的事务发送的一致性。 有关详细信息请参阅[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
### <a name="high-availability-for-the-windows-sharepoint-services-send-adapter"></a>Windows SharePoint Services 发送适配器的高可用性  
 为确保 Windows SharePoint Services 发送适配器的高可用性，请向发送主机添加多台计算机，并且每台主机计算机上的发送端口需要引用同一个文档库。 Windows SharePoint Services 适配器通过调入 SharePoint 计算机上安装 BizTalk 的 Windows SharePoint Services web 服务将消息发送到 SharePoint。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]为 SharePoint 由让多个消息推送到相同的 SharePoint NLB 安装所指向的 HTTP URL 的主机实例运行相同的发送端口发送适配器提供高可用性。  
  
## <a name="see-also"></a>另请参阅  
 [为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)   
 [运行在群集主机内的适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)