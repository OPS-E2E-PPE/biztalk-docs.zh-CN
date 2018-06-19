---
title: 群集接收主机 |Microsoft 文档
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
ms.openlocfilehash: 488a87539228a90ac427339e260653a141eb7121
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008302"
---
# <a name="clustering-receiving-hosts"></a>群集接收主机
BizTalk Server 提供功能，您可以将 BizTalk 主机配置中的群集资源为[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集组。 若要支持集成 BizTalk 的高可用性收到适配器不应运行在多个主机实例同时，如 FTP 接收处理程序，或者，在某些情况下，POP3 接收处理程序提供了主机群集支持。 另外，在需要群集 MSMQ 服务的方案中，主机群集支持还可确保 MSMQ 适配器发送或接收的消息的事务一致性。  
  
> [!NOTE]  
>  主机群集时仅使用 BizTalk Server Enterprise Edition。  
  
> [!NOTE]  
>  您可以进行群集 BizTalk 主机之前，必须配置为至少两个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk 组中的成员的计算机[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集。 有关配置的详细信息[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集，请参阅[Windows Server 2008 群集文档、 白皮书、 网络广播、 组](http://go.microsoft.com/fwlink/?LinkId=156818)(http://go.microsoft.com/fwlink/?LinkId=156818)。  
  
 BizTalk 主机群集支持是可用于为五个集成的 BizTalk 适配器提供高可用性： FTP 适配器、 MSMQ 适配器、 POP3 适配器、 SQL 适配器和 SAP 适配器。 使用主机群集支持还可以确保在为实现按序送达而运行适配器的单个实例时具有高可用性。  
  
 所有的 BizTalk 适配器处理程序可以运行在群集主机，但不在群集主机除外如下所示中运行适配器处理程序会带来好处。 如果你处理的要求包括任何下面的部分中所述的方案，然后应在群集主机运行适配器处理程序。 有关设置的详细步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]群集，请参阅[通过使用 Windows Server 2008 故障转移群集或 Windows Server 2003 服务器群集的 BizTalk Server 中改进容错功能](http://go.microsoft.com/fwlink/?LinkId=156819)(http://go.microsoft.com/fwlink/?LinkId=156819)。  
  
## <a name="scenarios-for-running-adapter-handlers-in-clustered-hosts"></a>在群集主机中运行适配器处理程序的方案  
 如果你处理的要求包括任何下面列出的方案，然后应在群集主机运行适配器处理程序。  
  
-   在群集的 BizTalk 主机内运行 FTP 适配器接收处理程序  
  
-   运行在群集 BizTalk 主机内的 MSMQ 适配器处理程序  
  
-   在群集的 BizTalk 主机内运行 POP3 适配器接收处理程序  
  
-   运行支持通过群集的 BizTalk 主机进行按序送达的接收适配器  
  
 有关这些方案的详细信息，请参阅[在群集主机内运行适配器处理程序的注意事项](http://go.microsoft.com/fwlink/?LinkId=151284)(http://go.microsoft.com/fwlink/?LinkId=151284)。  
  
## <a name="see-also"></a>另请参阅  
 [向外扩展接收主机](../technical-guides/scaling-out-receiving-hosts.md)   
 [向外扩展处理主机](../technical-guides/scaling-out-processing-hosts.md)   
 [横向扩展发送主机](../technical-guides/scaling-out-sending-hosts.md)