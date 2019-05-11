---
title: 低延迟方案 Optimizations1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd2a891a-ee4b-4542-b3ce-434e2a6474be
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dc842715be4e2ad97733c144302a52704865b57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266151"
---
# <a name="low-latency-scenario-optimizations"></a>低延迟方案优化
默认情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对吞吐量而不是低延迟进行了优化。 以下优化应用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]本指南中使用测试方案。  
  
> [!NOTE]  
>  这些优化将改善延迟，但可能会在执行此操作对总体吞吐量一些费用。  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a>增加 BizTalk Server 主机内部消息队列大小  
 每个 BizTalk 主机具有其自己的内部内存中队列。 增加此队列从 100 到 1000，以提高性能的低延迟方案的默认值的大小。 有关修改的内部消息队列大小值的详细信息，请参阅"如何为修改默认主机阻止设置的"BizTalk Server 帮助中在[ http://go.microsoft.com/fwlink/?LinkID=120225 ](http://go.microsoft.com/fwlink/?LinkID=120225)。  
  
## <a name="reduce-the-maxreceiveinterval-value-in-the-admserviceclass-table-of-the-biztalk-server-management-database"></a>减少 BizTalk Server 管理数据库的 adm_ServiceClass 表中的 MaxReceiveInterval 值  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用轮询机制从 Messagebox 中其主机队列接收消息。 **MaxReceiveInterval** BizTalk 管理 (BizTalkMgmtDb) 数据库的 adm_ServiceClass 表中的值是以每个 BizTalk 主机实例将等待的毫秒为单位的最大值直到轮询 MessageBox。 Adm_ServiceClass 表包含以下服务类型的记录：  
  
- **XLANG/S** – 表示 BizTalk 业务流程主机实例  
  
- **消息传送 InProcess** – 进程内主机实例  
  
- **MSMQT** – 对于 MSMQT 适配器主机实例  
  
- **消息传送独立**– 带进程主机实例，使用 HTTP、 SOAP 和某些 WCF 接收适配器处理程序  
  
  默认情况下，此值设置为 500 毫秒，这适用于吞吐量而不是低延迟。 在某些情况下，可以通过减少此值改进延迟。  
  
> [!NOTE]
>  为此值的更改影响所有类型的实例关联的服务，因此，请务必更改此值之前，请评估所有主机实例上的影响。  
> 
> [!NOTE]
>  如果 Messagebox 已没有剩余的未处理的消息，则仅使用此值。 如果没有常量积压在 Messagebox 中的未处理消息的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将尝试处理消息，而无需等待轮询延迟。 所有消息经过都处理后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将开始轮询使用 MaxReceiveInterval 为指定的值。  
> 
> [!NOTE]
>  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高比率的主机实例到 Messagebox 数据库实例，MaxReceiveInterval 可能会导致包含 Messagebox 数据库实例的 SQL Server 计算机上的 CPU 使用率过高的减小值的环境。 例如，如果 MaxReceiveInterval 缩小到较低的值 (\< 100) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中的单个 Messagebox 和 > 50 主机实例，SQL Server 上的 CPU 使用率可能会高于 50%攀升。 由于与不断轮询的主机队列相关的开销很重要，可能出现这种现象。 如果 MaxReceiveInterval 减少为小于 100 的值时，还应评估这对 SQL Server 计算机的 CPU 利用率的影响。