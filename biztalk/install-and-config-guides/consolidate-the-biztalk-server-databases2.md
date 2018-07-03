---
title: 合并 BizTalk Server 数据库 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7fc4fe6-3fc2-4164-9f16-90b6f473ba8c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 794558af8a6f947bb9ab8d9a29bd30dc3699e60c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975390"
---
# <a name="consolidate-the-biztalk-server-databases2"></a>合并 BizTalk Server 数据库2
安装 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可能需要在 Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 中创建多达 13 个单独的数据库，以用作各种 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 功能的数据库。 由于管理和维护这些数据库需要过多开销，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 允许将多个这样的数据库合并为一个数据库。 本部分介绍如何实现 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库合并，并讨论实现 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库合并的注意事项。  

> [!NOTE]
>  若要获取安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时需要的所有数据库的完整列表，请参阅 [BizTalk Server 中的数据库](../core/databases-in-biztalk-server.md)。  

## <a name="implementing-biztalk-database-consolidation"></a>实现 BizTalk 数据库合并  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库合并是在安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 后、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置期间执行的。 请遵循下列步骤实现 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库合并：  

1. 单击“开始”，依次指向“程序”和“[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]”，然后单击“BizTalk Server 配置”。 如果系统提示选择配置类型，请单击“自定义配置”。  

2. 为下列一个或多个数据存储输入相同的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]**服务器名称**和**数据库名称**（例如 *BizTalkConsolidatedDb*）：  

   |功能名称|数据存储区名称|  
   |------------------|---------------------|  
   |企业 SSO|SSO 数据库|  
   |分组|BizTalk 管理数据库|  
   |分组|BizTalk MessageBox 数据库|  
   |分组|BizTalk 跟踪数据库|  
   |业务规则引擎|规则引擎数据库|  

    请注意，**不**应将下列数据存储配置为共享 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 数据库：  


   | 功能名称 |       数据存储区名称       |
   |--------------|-----------------------------|
   |  BAM 工具   | BAM 主导入数据库 |
   |  BAM 工具   |    BAM 存档数据库     |


3. 设置剩余的配置选项，并应用配置。 对于为其指定了相同[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]**服务器名称**和**数据库名称**的数据存储，配置工具将在共享 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 数据库中为这样的数据存储创建表。  

## <a name="considerations-for-implementing-biztalk-database-consolidation"></a>实现 BizTalk 数据库合并的注意事项  
 合并 BizTalk 数据库时，应考虑下列几点：  

1. 数据库合并可降低与管理和维护 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库关联的开销，但只应在相应环境中实现。 在生产环境中实现 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库合并之前，应在过渡环境中测量合并对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可持续性能的影响。 请在下列各方案中考虑实现 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库合并，以简化数据库管理和维护：  

   - 小型、低容量的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生产环境，其中数据库性能不太可能成为性能瓶颈。  

   - 中型、中等容量的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生产环境，条件是：BizTalk 跟踪数据库不包含在合并中，并且该数据库最好在不同于合并数据库的单独物理磁盘上创建。  

   - 大型、高容量的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生产环境，条件是：共享 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 数据库物理位于性能非常高的存储区域网络 (SAN) 设备上，该设备上的数据库成为性能瓶颈的可能性非常低。  

   - 概念验证或开发环境，其中数据库性能是次要问题。  

2. 整个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的性能通常依赖于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库的性能。 因此，不能在采用或将要采用高容量的任何 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生产环境中实现数据库合并。 但此规则也有一个例外，即如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库位于性能非常高的存储区域网络 (SAN) 设备上，该设备上的数据库成为性能瓶颈的可能性非常低。 如果数据库磁盘不位于高性能 SAN 中，则分布式数据库与合并数据库相比，能提供更高的性能，特别是在负载条件下更是如此。  

3. 如果数据库合并包含 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理数据库，并且合并数据库的名称不是 **BizTalkMgmtDb**，那么必须将 BizTalk 管理控制台配置为指向合并数据库。 请遵循[如何连接到现有组](../core/how-to-connect-to-an-existing-group.md)中的步骤，并将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置为指向合并数据库，以便管理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组。  

4. 有关 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可持续性能的详细信息，请参考[规划可持续性能](../core/planning-for-sustained-performance.md)。  

   有关与维护 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库相关的活动的详细信息，请参考[维护 BizTalk Server1](../core/maintaining-biztalk-server1.md)。