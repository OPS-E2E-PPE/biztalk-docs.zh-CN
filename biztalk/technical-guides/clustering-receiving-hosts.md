---
title: 接收主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93544f39-836f-4a4f-9587-230bfa3a9d4e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f2d00960a2b09c692c1bc333d66d5bf72621259
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020664"
---
# <a name="clustering-receiving-hosts"></a>接收主机
BizTalk Server 提供了功能，可将 BizTalk 主机配置中的群集资源[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集组。 若要支持集成 BizTalk 的高可用性的接收适配器不应运行多个主机实例中同时，例如 FTP 接收处理程序，或在某些情况下，POP3 接收处理程序提供主机群集支持。 另外，在需要群集 MSMQ 服务的方案中，主机群集支持还可确保 MSMQ 适配器发送或接收的消息的事务一致性。  
  
> [!NOTE]
>  仅随 BizTalk Server Enterprise Edition 提供了主机群集。  
> 
> [!NOTE]
>  在可以群集 BizTalk 主机之前，必须配置至少两个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为成员的 BizTalk 组中计算机[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集。 有关配置详细信息[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集，请参阅[Windows Server 2008 聚类分析文档、 白皮书、 网络广播、 组](http://go.microsoft.com/fwlink/?LinkId=156818)(<http://go.microsoft.com/fwlink/?LinkId=156818>)。  
  
 BizTalk 主机群集支持，可用于为五个集成的 BizTalk 适配器提供高可用性： FTP 适配器、 MSMQ 适配器、 POP3 适配器、 SQL 适配器和 SAP 适配器。 使用主机群集支持还可以确保在为实现按序送达而运行适配器的单个实例时具有高可用性。  
  
 所有 BizTalk 适配器处理程序可以运行在群集主机，但从群集主机中除下面所述运行适配器处理程序并无好处。 如果您的处理要求包括任何以下部分中所述的方案，则应在群集主机中运行适配器处理程序。 有关设置的详细步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]群集，请参阅[通过使用 Windows Server 2008 故障转移群集或 Windows Server 2003 服务器群集的 BizTalk Server 中改进容错能力](http://go.microsoft.com/fwlink/?LinkId=156819)(<http://go.microsoft.com/fwlink/?LinkId=156819>)。  
  
## <a name="scenarios-for-running-adapter-handlers-in-clustered-hosts"></a>有关在群集主机中运行适配器处理程序的方案  
 如果您的处理要求包括任何下面列出的方案，则应在群集主机中运行适配器处理程序。  
  
- 在群集的 BizTalk 主机内运行 FTP 适配器接收处理程序  
  
- 在群集 BizTalk 主机内运行 MSMQ 适配器处理程序  
  
- 在群集的 BizTalk 主机内运行 POP3 适配器接收处理程序  
  
- 运行支持通过群集的 BizTalk 主机进行按序送达的接收适配器  
  
  有关这些方案的详细信息，请参阅[群集主机内运行适配器处理程序的注意事项](http://go.microsoft.com/fwlink/?LinkId=151284)(http://go.microsoft.com/fwlink/?LinkId=151284)。  
  
## <a name="see-also"></a>请参阅  
 [向外扩展接收主机](../technical-guides/scaling-out-receiving-hosts.md)   
 [横向扩展处理主机](../technical-guides/scaling-out-processing-hosts.md)   
 [横向扩展发送主机](../technical-guides/scaling-out-sending-hosts.md)