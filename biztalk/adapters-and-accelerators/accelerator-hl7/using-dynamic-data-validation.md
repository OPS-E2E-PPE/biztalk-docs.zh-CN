---
title: "使用动态数据验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic data validation
- validating, dynamic data
ms.assetid: 8dac7f74-92a7-447c-97bf-b1f3ce39b614
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c08393b8e6d4b2563d6fb7ccdf49559943538ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-dynamic-data-validation"></a>使用动态数据验证
动态数据验证的一个重要部分正在验证针对动态数据，其中包括验证的消息格式和消息内容的消息内容。 文档架构，其中[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] XSD 文件中实现、 定义和验证消息格式。 业务规则定义消息内容，其中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]通过业务规则引擎策略验证。 内容验证可以包括确认消息实例中的数据与可能随相对频率发生变化的数据匹配。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]以动态方式实现这种类型的验证，以便你可以更新在生产环境中，此数据，而无需重新编译代码，或关闭服务。  
  
## <a name="validate-and-expose-data"></a>验证和公开这样的数据  
 在执行动态数据验证 (DDV) 有两个步骤：  
  
-   公开的数据。  
  
-   将使用该数据的验证规则的应用。  
  
 DDV 提供用于存储、 公开，和缓存动态数据的以下支持：  
  
-   业务规则引擎或消息类执行验证。  
  
-   业务规则引擎公开数据通过数据库表列词汇。 业务规则引擎通过实现从管道或业务流程中运行的规则集验证针对消息此动态数据。  
  
-   现有的 SQL 接口，如 SQL 企业管理器和查询分析器中，在设计时是被动的公开动态数据。  
  
-   业务规则引擎数据库表列词汇定义显示在运行时动态数据。  
  
-   业务规则引擎在运行时公开消息实例数据。  
  
-   业务规则引擎 XML 文档词汇定义在设计时显示消息实例数据。  
  
-   您可将规则在设计时在业务规则编辑器用户界面或直接在业务规则语言 (BRL) XML 文本编辑器中。  
  
 有关业务规则和业务规则引擎的详细信息，请参阅"开发与业务规则"中[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。  
  
## <a name="extending-ddv"></a>扩展 DDV  
 如果您更改 HL7 基于跨字段验证或数据类型验证，则必须将记录以下两项操作：  
  
-   如果修改现有规则，你不需要重新部署。  
  
-   如果你创建或删除管道组件会影响新规则，然后你必须重新编译。  
  
## <a name="see-also"></a>另请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [消息扩充教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)