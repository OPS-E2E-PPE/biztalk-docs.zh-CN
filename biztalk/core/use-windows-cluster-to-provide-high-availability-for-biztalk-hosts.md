---
title: 使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 2016-01-04
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Passive configuration [Master Secret server]
- Active configuration [Master Secret server]
- clustering, about clustering
- high availability
- Windows Server cluster, warnings
- installation, high availibility planning
- Master Secret server
- installation, configuring
- Master Secret server, configuring
- installation, Windows Server cluster
- clustering
ms.assetid: 4d7f0842-561e-49e0-ab08-504256b9294f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8893bcd043ca046c310ee52276eb28476be4ea9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001174"
---
# <a name="using-windows-server-cluster-to-provide-high-availability-for-biztalk-server-hosts2"></a>使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了功能，可将 BizTalk 主机配置为 Windows Server 故障转移群集组内的群集资源。 使用主机群集支持，可以确保那些不应同时运行于多个主机实例中的集成 BizTalk 适配器（例如 FTP 接收处理程序，或在某些情况下的 POP3 接收处理程序）高度可用。 另外，在需要群集 MSMQ 服务的方案中，主机群集支持还可确保 MSMQ 适配器发送或接收的消息的事务一致性。  
  
> [!NOTE]
>  主机群集时才可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Enterprise Edition。  
> 
> [!NOTE]
>  在可以群集 BizTalk 主机之前，你必须配置至少两台[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组作为 Windows Server 故障转移群集的成员。 有关配置 Windows Server 故障转移群集的详细信息，请参阅 Windows Server 联机帮助。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在 Windows Server 群集上安装 BizTalk Server 的注意事项](../core/considerations-for-installing-biztalk-server-on-a-windows-server-cluster2.md)  
  
-   [如何将 BizTalk 主机配置为群集资源](../core/how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)  
  
-   [在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)