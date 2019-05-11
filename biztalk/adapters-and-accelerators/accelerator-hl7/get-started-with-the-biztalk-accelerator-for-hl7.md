---
title: 开始使用 BizTalk Accelerator for HL7 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.gettingstarted
helpviewer_keywords:
- BizTalk Accelerator for HL7
- BizTalk Accelerator for HL7, getting started
- getting started
ms.assetid: e842d501-2037-4fd6-a518-d29b25877250
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e1d4b8d33824d6eca25c52207b8aaa9473df5e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255316"
---
# <a name="get-started-with-the-biztalk-accelerator-for-hl7"></a>开始使用 BizTalk Accelerator for HL7
使用 Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)]，可以在医疗保健计算机系统之间开发业务流程。 通过使用[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]，开发人员、 IT 专业人员和接口分析师可以在常见环境来开发跨保健应用程序的端到端集成基于 BTAHL7 的解决方案下工作。  
  
 更具体地说，[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]你可以：  
  
- **简化卫生保健应用程序集成**。 生成、 管理和跟踪分布式的业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]开发环境。  
  
- **标准化医疗应用程序之间的临床数据交换**。 转换到的应用程序之间的现有数据传输[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]标准。  
  
- **提高效率**。 自动执行最少的手动干预的医疗应用程序之间的所有通信流程。  

本部分提供有关如何使用特定于角色的信息[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]便于企业应用程序集成 (EAI) 医院和医疗卫生领域来自动执行企业到企业医疗保健解决方案中.  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] 为每种类型的解决方案提供四种不同方案教程格式。 在开始这些教程之前，应了解基本概念[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]，以及工具和进程进行生成解决方案所需的[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]。  

> [!TIP] 
> 在开始这些课程之前[了解 HL7 加速器及可用的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)。  
  
 以下说明提供每个有一个大致了解[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]教程。  
  
## <a name="end-to-end-tutorial"></a>端到端教程  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]端到端教程提供了详细步骤，以便在订阅服务器和发布服务器方案中的业务流程。 这种情况下是发布服务器，例如，一个病人入院出院事项和传输系统将一条消息发送到特定的订阅服务器的情况。  
  
 该消息将路由到[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接口引擎，又接收进程，验证，将重新格式化，并随后将消息路由到订阅服务器。 在此方案中的订阅服务器是医院信息系统和药房系统。  
  
 此方案使用文件和最小的较低层协议 (MLLP) 适配器类型。 发布服务器不需要注意的订阅服务器，并[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接口引擎处理消息之后将相应的确认发送到发布服务器。  
  
## <a name="interrogative-tutorial"></a>询问教程  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]询问教程提供了详细步骤用于实现在组织内的子系统之间的查询响应系统。 在此方案中，业务 (LOB) 应用程序在病人入院，释放，并将传输系统将查询发送到医院信息系统以获得患者实验室的结果。 医院信息系统收到查询后，它将请求的数据发送回发出查询的系统。  
  
 此方案使用 MLLP 作为传输协议的所有消息，包括确认。  
  
## <a name="message-enrichment-tutorial"></a>消息充实教程  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]充实教程提供了解决特定业务问题的详细步骤： 消息收集方案。 消息扩充方案是需要添加或丰富的情况下，一条消息，不符合 HL7 和/或不完整。 这种情况下可能会出现应用程序，如患者注册应用程序，或将填充来自 XML 数据的消息时[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]。  
  
 在消息扩充方案中，捕获的消息与[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]，并提供任何缺失的数据，例如，从患者记录数据库。 然后将消息转换，并将其发送到实验室、 保險、 或任何旧的业务线 (LOB) 应用程序使用 MLLP 适配器。  
  
## <a name="batching-tutorial"></a>批处理教程  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]批处理教程提供了详细步骤，以接收和发送批处理的消息。 批处理为单个复合消息包括接收和/或发送的一组各个消息 （或确认）。  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] 支持以下三种消息批处理方案：  
  
- **零碎的入站的批处理**。 在此方案中，[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接收 HL7 消息批，，然后将各个消息路由到目标系统。  
  
- **在批处理 / 出站批处理**。[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接收 HL7 消息批，验证在批处理中的单个消息，然后将消息批路由到目标系统。  
  
- **创建批次 （或出站批处理）**。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] 接收单个消息并将它们路由到目标系统之前对其进行批量。  
  
## <a name="tutorial-links"></a>教程的链接  
  
-   [端到端教程](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)  
  
-   [询问教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)  
  
-   [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)  
  
-   [批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)
  
## <a name="see-also"></a>另请参阅
  
[为残障人士提供的辅助功能](../../adapters-and-accelerators/accelerator-hl7/accessibility-for-people-with-disabilities5.md)