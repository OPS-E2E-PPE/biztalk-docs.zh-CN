---
title: 向外扩展发送主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80fcc73aa4d0f2d65a097bd47d06fc75305abdc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309068"
---
# <a name="scaled-out-sending-hosts"></a>向外扩展发送主机
向外扩展发送主机可确保的发送功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高度可用。 如果用于发送消息，可以向主机添加多台计算机，可以运行多个发送主机实例以实现冗余和高可用性。  
  
 下图显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过在两台计算机上运行的发送主机实例以确保发送主机提供高可用性的部署。 请注意，在此图中的接收和处理主机并不高度可用。  
  
 ![缩放&#45;扩展发送主机](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")  
  
## <a name="high-availability-for-sending-hosts"></a>发送主机的高可用性  
 发送功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]类似于处理意义上说，这些活动都不需要主机和数据之间的关联中的功能。 正如任何处理主机实例可以从 MessageBox 数据库中检索消息和处理它们，任何发送主机实例可以从 MessageBox 数据库中检索消息并将其发送。 因此，发送主机提供高可用性意味着使用确保处理主机高度可用的相同方法。  
  
## <a name="scaling-the-biztalk-server-send-adapters"></a>扩展 BizTalk Server 发送适配器  
  
### <a name="high-availability-for-the-msmq-send-adapter"></a>发送适配器在 msmq 的高可用性  
 MSMQ 发送适配器应群集 MSMQ 服务、 群集与群集的 MSMQ 服务位于同一组中的 BizTalk 主机和配置为提供高可用性 MSMQ 发送处理程序在此群集的 BizTalk 主机中运行。 这应进行以确保 MSMQ 适配器启动的事务发送的一致性。 有关详细信息请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
### <a name="high-availability-for-the-windows-sharepoint-services-send-adapter"></a>发送适配器的 Windows SharePoint Services 的高可用性  
 若要为 Windows SharePoint Services 发送适配器提供高可用性，请向引用相同的文档库的每台主机计算机上的发送端口与发送主机添加多台计算机。 Windows SharePoint Services 适配器通过调入 SharePoint 计算机上安装 BizTalk 的 Windows SharePoint Services web 服务将消息发送到 SharePoint。 有关 SharePoint 允许将消息推送到同一 HTTP URL 指向 SharePoint NLB 安装的多个主机实例运行同一个发送端口的发送适配器，BizTalk Server 提供高可用性。  
  
## <a name="see-also"></a>请参阅  
 [为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)   
 [在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)