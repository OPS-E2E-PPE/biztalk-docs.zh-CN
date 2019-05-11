---
title: 规划灾难恢复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a33e8875-cfde-4a60-9dab-fc6bb3ac4f1c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 415064960644356db37530b87ce0f591d5a23bb9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400711"
---
# <a name="planning-for-disaster-recovery"></a>规划灾难恢复
本主题提供灾难恢复要求的应用程序团队和 BizTalk Server 的过程指南。 Microsoft BizTalk Server 将存储在配置和处理信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 BizTalk Server 高可用性和灾难恢复通过的高可用性和灾难恢复功能[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
 由数据库托管在一组定义的 BizTalk 组[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 在托管的数据库集[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]可通过 Windows Server 群集使用高度可用。 在 BizTalk 环境中，运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供运行的计算机上的"运行时环境"和数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]为环境提供持久存储区。 因此，BizTalk Server 备份、 还原和灾难恢复过程很大程度侧重[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
## <a name="purpose"></a>用途  
 本主题将整合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]灾难恢复信息从核心文档、 各种 Microsoft Web 站点和中的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]产品团队定义的灾难恢复过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
 应用程序团队应该全面测试备份、 还原和灾难恢复过程。 您还应确保过程量身定制以符合在进入生产之前应用程序要求。  
  
## <a name="scope"></a>范围  
 本部分重点介绍灾难恢复过程的 BizTalk Server 和相关的过程[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 本指南基于如何备份和还原 BizTalk Server 的相关文档。  
  
 有关备份和还原的详细信息，请参阅此文档，请参阅[备份和还原 BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154071) (http://go.microsoft.com/fwlink/?LinkID=154071) BizTalk Server 帮助中。 每个应用程序团队必须使用其他过程特定于其环境，如文档计算机名，驱动器号，本主题中的信息做出补充和群集配置，以及的灾难恢复过程相关非 BizTalk 应用程序的解决方案的一部分。  
  
 本主题不提供详细的灾难恢复过程的以下几个方面：  
  
- 非 BizTalk 应用程序  
  
- 应用程序源代码  
  
- 证书  
  
- 应用程序操作  
  
  可能需要的上面未列出的应用程序的灾难恢复计划中的文档必须由每个应用程序团队的其他区域。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [灾难恢复的最佳做法](../technical-guides/best-practices-for-disaster-recovery.md)  
  
-   [BizTalk Server 日志传送概述](../technical-guides/what-is-biztalk-server-log-shipping.md)