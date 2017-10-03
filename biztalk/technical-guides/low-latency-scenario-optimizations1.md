---
title: "低延迟方案 Optimizations1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd2a891a-ee4b-4542-b3ce-434e2a6474be
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2957888253826845ea9a941ad7fce8fd7a2ed7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="low-latency-scenario-optimizations"></a>低延迟方案优化
默认情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对吞吐量，而不是低延迟进行了优化。 下列优化已应用到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]测试方案用于本指南。  
  
> [!NOTE]  
>  这些优化将提高延迟，但可能在执行此操作对整体吞吐量一些成本。  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a>增加的 BizTalk Server 主机内部消息队列大小  
 每个 BizTalk 主机有其自己的内部内存中队列。 增加此队列从 100 到 1000，以提高性能的低延迟方案的默认值的大小。 有关修改的内部消息队列大小的值的详细信息，请参阅"如何为修改默认主机限制设置"中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]在帮助[http://go.microsoft.com/fwlink/?LinkID=120225](http://go.microsoft.com/fwlink/?LinkID=120225)。  
  
## <a name="reduce-the-maxreceiveinterval-value-in-the-admserviceclass-table-of-the-biztalk-server-management-database"></a>减小 BizTalk Server 管理数据库的 adm_ServiceClass 表中的 MaxReceiveInterval 值  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用轮询机制从 Messagebox 中其主机队列接收消息。 **MaxReceiveInterval** BizTalk 管理 (BizTalkMgmtDb) 数据库 adm_ServiceClass 表中的值是以每个 BizTalk 主机实例将等待的毫秒为单位的最大值之前它轮询 MessageBox。 Adm_ServiceClass 表包含以下服务类型的记录包含：  
  
-   **XLANG/S** – 表示 BizTalk 业务流程主机实例  
  
-   **消息传送 InProcess** – 进程内主机实例  
  
-   **MSMQT** – MSMQT 适配器主机实例  
  
-   **消息传送 Isolated** – 用于外进程主机实例，使用 HTTP、 SOAP、 和某些 WCF 接收适配器处理程序  
  
 默认情况下，此值设置为 500 毫秒，针对吞吐量，而不是低延迟进行了优化。 在某些情况下，可以通过减小此值进行改进延迟。  
  
> [!NOTE]  
>  为此值的更改影响所有类型的实例关联的服务，因此，请小心谨慎以更改此值之前评估所有主机实例上的影响。  
  
> [!NOTE]  
>  仅当 Messagebox 不具有任何剩余的未处理的消息，才能使用此值。 如果没有在消息框中，未处理消息的常量囤积[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将尝试处理消息，而无需等到上轮询延迟。 在处理所有消息之后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将开始轮询使用 MaxReceiveInterval 为指定的值。  
  
> [!NOTE]  
>  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 Messagebox 数据库实例，减小值 MaxReceiveInterval 可能会保存 Messagebox 数据库实例的 SQL Server 计算机上的 CPU 使用率过高的主机实例的比值较高的环境。 例如，如果 MaxReceiveInterval 减小到较低的值 (\< 100) 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中的使用单个消息框和 > 50 主机实例，SQL Server 上的 CPU 使用率可能攀升超过 50%。 由于与不断轮询主机队列关联的开销很重要，则可能出现这种现象。 如果你 MaxReceiveInterval 的值减小至小于 100，你还应该评估这对 SQL Server 计算机的 CPU 使用率的影响。