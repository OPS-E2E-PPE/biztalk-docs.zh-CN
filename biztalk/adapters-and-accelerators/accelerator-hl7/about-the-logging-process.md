---
title: "有关日志记录流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- logging, about logging
- auditing, about auditing
- logging
- auditing
ms.assetid: 859ee1f5-aae4-4a47-ab39-8d2b4168a429
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07dba617358d6ad451c53eeb75dbe5d1986f9066
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-logging-process"></a>有关日志记录流程
你的应用程序处理关键的因为时间敏感数据和货币数据，审核将成为应用程序的关键部分。 若要启用企业级别的可管理性和可用性， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]依赖于以下共享的运行的时和管理组件：  
  
-   **日志记录**： 收集和路由的所有日志事件中指定的数据库的托管方法  
  
-   **事件监视和服务调试**： 配置日志记录行为以及调查/管理系统管理员和其他 IT 专业人士收集的信息  
  
 与增强审核中的功能[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]，你可以优化你的运营效率、 安全性和性能，以确保 HL7 法规的合规性。  
  
## <a name="types-of-data"></a>类型的数据  
 本主题介绍了不同类型的使用日志记录功能和存储此数据的日志记录数据：  
  
-   配置数据： 日志记录配置数据存储在配置数据库 （也称为 BizTalk 管理数据库） 中并包含审核信息和审核数据的 SQL ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]事件查看器中，集中数据库 WMI) 位置。  
  
-   存档数据： 事件日志中的 SQL 日志的表存储日志记录数据。  
  
## <a name="how-logging-works"></a>日志记录的工作原理  
 本主题介绍三种类型的事件日志的软件，以及你可以在其中存储记录的数据的三个位置。  
  
|组件|用途|  
|---------------|-------------|  
|配置编辑器|若要指定保存的日志数据的位置。 BTAHL7 支持记录到以下的任意组合： 事件查看器、 WMI 和 SQL Server 日志记录。|  
|事件代理|若要接收日志事件引发的其他组件并将它们记录基于日志记录配置数据。|  
|日志记录 API|由所有 BTAHL7 程序集的日志记录接口。|  
  
### <a name="types-of-logging"></a>类型的日志记录  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]日志三种类型的错误：  
  
-   信息性事件，启动或停止服务或事件失败。  
  
-   如非严重错误和警告中的警告事件[!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]事件日志。 例如，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]挂起消息，因为数据验证失败。  
  
-   组件中的严重故障的错误事件。 例如，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]挂起消息，因为分析器错误。  
  
 系统可以记录[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]到下列可配置的位置的事件：  
  
-   [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]事件查看器  
  
-   WMI 事件  
  
-   集中的数据库 （SQL 日志记录数据库）  
  
 事件 broker 接收所有[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]日志记录事件，基于的配置信息、 将它们发送到的适当位置。  
  
### <a name="overview-of-features"></a>功能概述  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]日志记录功能提供了：  
  
-   日志记录所有错误消息的统一的方法  
  
-   集中式存储库用于存储所有的事件详细信息  
  
-   日志记录消息流到离散的业务线应用程序一致的对象模型  
  
-   日志记录和跟踪来帮助的系统管理员关联的组合的文档记录错误  
  
## <a name="event-log-data"></a>事件日志数据  
 本主题介绍的格式和内容的事件日志数据。  
  
 下表显示了有关合作伙伴的典型记录的数据。  
  
|data|Description|  
|----------|-----------------|  
|日志数据|数据日志|  
|CategoryNumber|类别号|  
|EntryType|事件的类型|  
|EventId|事件 ID|  
|MachineName|计算机名称|  
|消息|消息详细信息|  
|数据源|创建、 更新、 读取、 删除、 部署，或将数据存档|  
|TimeGenerated|成功或失败|  
|UserName|用户名|  
|MsgGuid|消息 GUID|  
|SvcGuid|服务 GUID|  
|运算|操作详细信息|  
  
## <a name="see-also"></a>另请参阅  
 [配置日志记录](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)