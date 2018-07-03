---
title: 有关日志记录进程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- logging, about logging
- auditing, about auditing
- logging
- auditing
ms.assetid: 859ee1f5-aae4-4a47-ab39-8d2b4168a429
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 110c7d4505e6518836fa481ed268771aef72d4c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981054"
---
# <a name="about-the-logging-process"></a>有关日志记录进程
你的应用程序处理关键，因为时间敏感和货币数据，审核将成为应用程序的关键部分。 若要启用企业级可管理性和可用性，Microsoft[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]依赖以下共享运行的时和管理组件：  
  
- **日志记录**： 若要收集和路由的所有日志事件中指定的数据库的托管方法  
  
- **事件监视和调试服务**： 若要配置日志记录行为以及调查/管理面向系统管理员和其他 IT 专业人员收集的信息  
  
  与增强审核中的功能[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]，可以优化运营效率、 安全性和性能，以确保 HL7 法规符合性。  
  
## <a name="types-of-data"></a>类型的数据  
 本主题介绍不同类型的日志记录功能和存储此数据使用的日志记录数据：  
  
- 配置数据： 日志记录配置数据存储在配置数据库 （也称为 BizTalk 管理数据库） 中并包含审核信息和审核数据的 SQL ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]事件查看器中，集中式数据库 WMI) 位置。  
  
- 存档数据： 事件日志表中的 SQL 日志存储日志记录的数据。  
  
## <a name="how-logging-works"></a>日志记录的工作原理  
 本主题介绍三种类型的事件日志的软件，以及可以在其中存储日志的数据的三个位置。  
  
|组件|用途|  
|---------------|-------------|  
|配置编辑器|若要指定保存日志数据的位置。 BTAHL7 支持日志记录到以下任意组合： 事件查看器、 WMI 和 SQL Server 日志记录。|  
|事件代理|若要接收日志事件引发的其他组件，并记录基于配置数据的日志记录。|  
|日志记录 API|日志记录调用 BTAHL7 的所有程序集的接口。|  
  
### <a name="types-of-logging"></a>类型的日志记录  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 日志三种类型的错误：  
  
- 信息性事件、 启动或停止的服务或事件失败。  
  
- 警告事件，例如非严重错误和警告中的[!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]事件日志。 例如，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]挂起消息，因为数据验证失败。  
  
- 在组件中的严重故障的错误事件。 例如，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]挂起消息，因为分析器错误。  
  
  系统可以记录[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]到下列可配置的位置的事件：  
  
- [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] 事件查看器  
  
- WMI 事件  
  
- 集中式的数据库 （SQL 日志记录数据库）  
  
  事件代理接收所有[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]记录事件和，基于配置信息，请在将其发送到相应的位置。  
  
### <a name="overview-of-features"></a>功能概述  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]日志记录功能提供了：  
  
-   一种统一日志记录所有错误消息的方法  
  
-   用于存储所有事件的详细信息的集中式存储库  
  
-   日志记录消息流到离散的业务线应用程序一致的对象模型  
  
-   日志记录和跟踪来帮助的系统管理员将关联的组合记录了错误的文档  
  
## <a name="event-log-data"></a>事件日志数据  
 本主题介绍的格式和内容的事件日志数据。  
  
 下表显示适用于合作伙伴的典型记录的数据。  
  
|data|Description|  
|----------|-----------------|  
|日志数据|数据日志|  
|CategoryNumber|分类数|  
|EntryType|事件的类型|  
|存在 EventId|事件 ID|  
|MachineName|计算机名称|  
|消息|消息详细信息|  
|数据源|创建、 更新、 读取、 删除、 部署，或将数据存档|  
|TimeGenerated|成功或失败|  
|UserName|“用户名”|  
|MsgGuid|消息的 GUID|  
|SvcGuid|服务 GUID|  
|运算|操作详细信息|  
  
## <a name="see-also"></a>请参阅  
 [配置日志记录](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)