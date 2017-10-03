---
title: "针对灾难恢复进行规划 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a33e8875-cfde-4a60-9dab-fc6bb3ac4f1c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f342030cd016dc0b1ea015a463e8777d498f860
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-disaster-recovery"></a>针对灾难恢复进行规划
本主题提供到灾难恢复要求的应用程序团队和过程指南[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。 Microsoft[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]配置和处理将信息存储在[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]可以通过的高可用性和灾难恢复功能来实现高可用性和灾难恢复[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
 BizTalk 组定义通过一组的数据库托管在[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 数据库中托管的一套[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]可通过 Windows Server 群集使用高可用。 在 BizTalk 环境中，运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供运行的计算机上的"运行时环境"和数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]为环境提供持久存储区。 因此，[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]备份、 还原和灾难恢复过程很大程度侧重于[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
## <a name="purpose"></a>用途  
 本主题将整合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从的核心文档、 多个 Microsoft Web 站点和中的信息的灾难恢复信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]产品团队定义的灾难恢复过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
 应用程序团队应全面测试备份、 还原和灾难恢复过程。 你还应该确保过程专门编写，来满足在进入生产前的应用程序。  
  
## <a name="scope"></a>范围  
 本部分重点的灾难恢复过程[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]和相关过程[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 本指南基于如何备份和还原 BizTalk Server 有关的相关文档。  
  
 有关备份和还原的详细信息，请参阅本文档并查看[备份和还原 BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154071) (http://go.microsoft.com/fwlink/?LinkID=154071) 中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]帮助。 每个应用程序团队必须增加与其他过程特定于其环境，如文档计算机名，驱动器号，本主题中的信息并群集配置中，以及的灾难恢复过程相关非 BizTalk 应用程序解决方案的一部分。  
  
 本主题不提供详细的灾难恢复过程对以下方面：  
  
-   非 BizTalk 应用程序  
  
-   应用程序源代码  
  
-   证书  
  
-   应用程序操作  
  
 可能有需要，上面未列出的应用程序的灾难恢复计划中的文档必须通过每个应用程序团队进行寻址的其他区域。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [灾难恢复最佳方案](../technical-guides/best-practices-for-disaster-recovery.md)  
  
-   [什么 BizTalk Server 日志传送？](../technical-guides/what-is-biztalk-server-log-shipping.md)