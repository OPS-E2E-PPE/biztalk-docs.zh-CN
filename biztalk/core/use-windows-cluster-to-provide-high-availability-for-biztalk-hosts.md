---
title: "使用 Windows Server 群集以提供高可用性的 BizTalk Server Hosts2 |Microsoft 文档"
ms.custom: 
ms.date: 2016-01-04
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 338f9fd39208f85ce5748f5ebe5548fa9487c9df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-windows-server-cluster-to-provide-high-availability-for-biztalk-server-hosts2"></a><span data-ttu-id="8f5e1-102">Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性</span><span class="sxs-lookup"><span data-stu-id="8f5e1-102">Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8f5e1-103">提供允许你将 BizTalk 主机配置为 Windows Server 故障转移群集组中的群集资源的功能。</span><span class="sxs-lookup"><span data-stu-id="8f5e1-103"> provides functionality that allows you to configure a BizTalk host as a clustered resource within a  Windows Server failover cluster group.</span></span> <span data-ttu-id="8f5e1-104">使用主机群集支持，可以确保那些不应同时运行于多个主机实例中的集成 BizTalk 适配器（例如 FTP 接收处理程序，或在某些情况下的 POP3 接收处理程序）高度可用。</span><span class="sxs-lookup"><span data-stu-id="8f5e1-104">Host cluster support is provided to support high availability for integrated BizTalk adapters that should not be run in multiple host instances simultaneously, such as the FTP receive handler or, under certain circumstances, the POP3 receive handler.</span></span> <span data-ttu-id="8f5e1-105">另外，在需要群集 MSMQ 服务的方案中，主机群集支持还可确保 MSMQ 适配器发送或接收的消息的事务一致性。</span><span class="sxs-lookup"><span data-stu-id="8f5e1-105">Host cluster support is also provided to ensure transactional consistency for messages sent or received by the MSMQ adapter in scenarios that require that the MSMQ service is clustered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f5e1-106">主机群集时才可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="8f5e1-106">Host clustering is only available with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise Edition.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f5e1-107">您可以进行群集 BizTalk 主机之前，你必须配置至少两个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组作为 Windows Server 故障转移群集的成员。</span><span class="sxs-lookup"><span data-stu-id="8f5e1-107">Before you can cluster a BizTalk host, you must have configured at least two [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group as members of a Windows Server Failover cluster.</span></span> <span data-ttu-id="8f5e1-108">有关配置 Windows Server 故障转移群集的详细信息，请参阅 Windows Server 联机帮助。</span><span class="sxs-lookup"><span data-stu-id="8f5e1-108">For more information about configuring a Windows Server Failover cluster, please see the Windows Server online help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f5e1-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="8f5e1-109">In This Section</span></span>  
  
-   [<span data-ttu-id="8f5e1-110">在 Windows Server 群集上安装 BizTalk Server 的注意事项</span><span class="sxs-lookup"><span data-stu-id="8f5e1-110">Considerations for Installing BizTalk Server on a Windows Server Cluster</span></span>](../core/considerations-for-installing-biztalk-server-on-a-windows-server-cluster2.md)  
  
-   [<span data-ttu-id="8f5e1-111">如何将 BizTalk 主机配置为群集资源</span><span class="sxs-lookup"><span data-stu-id="8f5e1-111">How to Configure a BizTalk Host as a Cluster Resource</span></span>](../core/how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)  
  
-   [<span data-ttu-id="8f5e1-112">运行在群集主机内的适配器处理程序的注意事项</span><span class="sxs-lookup"><span data-stu-id="8f5e1-112">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)