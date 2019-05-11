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
ms.openlocfilehash: f5f633383b4e57133fc3b39bec804e376e1c6542
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266168"
---
# <a name="consolidate-the-biztalk-server-databases2"></a>合并 BizTalk Server 数据库 2
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装可能需要在 Microsoft 中最多 13 个单独的数据库创建[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]用作数据存储为各种[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能。 由于管理和维护这些数据库所需的开销[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可容纳多个这些数据库的合并到单个数据库。 本部分介绍如何完成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库合并，并讨论了实现的注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库合并。  

> [!NOTE]
>  有关所有安装时所需的数据库的完整列表[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[BizTalk Server 中的数据库](../core/databases-in-biztalk-server.md)。  

## <a name="implementing-biztalk-database-consolidation"></a>实现 BizTalk 数据库合并  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装后执行数据库整合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。 请按照下列步骤来实现[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库合并：  

1. 单击**启动**，依次指向**程序**，指向[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后单击**BizTalk Server 配置**。 如果系统提示选择配置类型，请单击**自定义配置**。  

2. 输入相同[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]**服务器名称**并**数据库名称**(例如*BizTalkConsolidatedDb*) 对于一个或多个以下数据存储：  

   |功能名称|数据存储区名称|  
   |------------------|---------------------|  
   |企业 SSO|SSO 数据库|  
   |Group|BizTalk 管理数据库|  
   |Group|BizTalk MessageBox 数据库|  
   |Group|BizTalk 跟踪数据库|  
   |业务规则引擎|规则引擎数据库|  

    请注意以下数据存储应**不**配置为共享[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库：  


   | 功能名称 |       数据存储区名称       |
   |--------------|-----------------------------|
   |  BAM 工具   | BAM 主导入数据库 |
   |  BAM 工具   |    BAM 存档数据库     |


3. 设置剩余的配置选项，并将应用配置。 配置工具将在共享中创建表[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]为其指定了相同的数据存储的数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]**服务器名称**并**数据库名称**。  

## <a name="considerations-for-implementing-biztalk-database-consolidation"></a>实现 BizTalk 数据库合并的注意事项  
 合并 BizTalk 数据库时, 考虑以下方面：  

1. 数据库合并可降低与管理和维护关联的开销[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，但只应在适当的环境中实现。 实现之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的数据库在生产环境中，影响合并[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应在过渡环境中测量的持续的性能。 请考虑实施[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库合并，以简化数据库管理和维护以下方案中：  

   - 小型、 低容量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库性能不会成为性能瓶颈的可能性非常小的生产环境。  

   - 中型、 中等容量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如果合并不包含 BizTalk 跟踪数据库的生产环境，理想情况下，如果从合并数据库的单独物理磁盘上创建 BizTalk 跟踪数据库。  

   - 大型、 高容量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生产环境如果共享[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库以物理方式位于其中的数据库成为性能瓶颈的可能性是非常高性能存储区域网络 (SAN) 设备非常低。  

   - 概念证明或开发环境，其中数据库性能是次要问题。  

2. 总体[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能所依赖的性能通常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 因此数据库整合不都应在任何实现[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生产环境采用或将要采用高容量。 一个例外情况是如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库位于其中的数据库成为性能瓶颈的可能性是非常低的性能非常高存储区域网络 (SAN) 设备上。 如果数据库磁盘不位于高性能 SAN，分布式的数据库提供优异的性能与合并数据库，尤其是在负载下。  

3. 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理数据库包含在数据库合并和合并数据库不是**BizTalkMgmtDb**，那么必须将 BizTalk 管理控制台配置为指向合并数据库。 按照中的步骤[如何连接到现有组](../core/how-to-connect-to-an-existing-group.md)并配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来指向合并数据库，以便管理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  

4. 详细了解可承受[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能，请参阅[规划可持续性能](../core/planning-for-sustained-performance.md)。  

   有关与维护相关的活动详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[维护 BizTalk Server1](../core/maintaining-biztalk-server1.md)。