---
title: 入门 HL7 BizTalk 快捷键 |Microsoft 文档
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
ms.openlocfilehash: bebe61b152c7a74c2d45c0604e23b0a39bc6a4fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-the-biztalk-accelerator-for-hl7"></a>入门 HL7 BizTalk 快捷键
使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)]，你可以开发卫生保健的计算机系统之间的业务流程。 通过使用[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]，开发人员、 IT 专业人员和接口分析师可以在常见环境以开发跨卫生保健的应用程序的端到端集成的 BTAHL7 基于解决方案中工作。  
  
 更具体地说，使用[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]你可以：  
  
-   **简化卫生保健的应用程序集成**。 生成、 管理和跟踪使用的分布式的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]开发环境。  
  
-   **标准化医疗应用程序之间的临床数据交换**。 转换到的应用程序之间的现有数据传输[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]标准。  
  
-   **提高效率**。 自动执行以最少的手动干预的医疗应用程序之间的所有通信过程。  

本部分提供有关如何使用特定于角色的信息[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]便于企业应用程序集成 (EAI) 内医院和医疗保健的情景，来自动执行企业到企业医疗保健解决方案.  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]对于每个类型的解决方案提供教程格式的四种不同方案。 在开始这些教程之前，应了解中的基本概念[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]，和的工具和是开始使用构建的解决方案需要的进程[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]。  

> [!TIP] 
> 在开始这些课程之前[了解 HL7 快捷键和提供的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)。  
  
 以下说明提供每个大致了解[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]教程。  
  
## <a name="end-to-end-tutorial"></a>端到端教程  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]端到端教程为你提供方便在订阅服务器和发布服务器方案中的业务流程的详细步骤。 这种情况下是发布服务器，例如，许可放电并传输系统将一条消息发送到特定的订阅服务器的情况。  
  
 消息将路由到[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接口引擎，后者反过来接收进程，验证、 重新格式化，并随后将消息路由到订阅服务器。 在此方案中的订阅服务器是医院信息系统和药房系统。  
  
 此方案使用文件和最小较低层协议 (MLLP) 适配器类型。 发布服务器不需要注意的订阅服务器，与[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接口引擎处理消息之后将相应的确认发送到发布服务器。  
  
## <a name="interrogative-tutorial"></a>Interrogative 教程  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Interrogative 教程向你提供了详细步骤实现在组织内的子系统之间的查询响应系统。 在此方案中，在许可，-的业务线 (LOB) 应用程序释放，并将转移系统会将查询发送到医院信息系统，以获取患者实验室结果。 医院信息系统收到查询后，它会将所请求的数据发送回发出该查询的系统中。  
  
 这种情况下使用 MLLP 作为传输协议的所有消息，包括确认。  
  
## <a name="message-enrichment-tutorial"></a>消息扩充教程  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]扩充教程为你提供解决特定业务问题的详细步骤： 消息扩充方案。 消息扩充方案是在其中你必须将添加到，或丰富的情况下，一条消息，不符合 HL7 和/或不完整。 这种情况下可能会出现的应用程序，如患者注册应用程序，或将填充从 XML 数据的消息时[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]。  
  
 在消息扩充方案中，捕获与消息[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]，并提供任何缺少的数据，例如，从患者记录数据库。 然后将消息转换并将其发送到实验室、 保险或任何旧的业务线 (LOB) 应用程序使用 MLLP 适配器。  
  
## <a name="batching-tutorial"></a>批处理教程  
 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]批处理教程为你提供接收和发送批处理的消息的详细步骤。 批处理为单个复合消息涉及接收和/或发送的一组单个消息 （或确认）。  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]支持以下三种消息批处理方案：  
  
-   **零碎的入站的批处理**。 在此方案中，[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接收的 HL7 消息批次，并随后将各条消息路由到目标系统。  
  
-   **在批处理 / 批处理出**。[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接收的 HL7 消息批次，验证批处理中的单个消息，然后将消息批路由到目标系统。  
  
-   **创建批处理 （或出站批处理）**。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接收单个消息，并将它们路由到目标系统之前对它们进行批处理。  
  
## <a name="tutorial-links"></a>教程的链接  
  
-   [端到端教程](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)  
  
-   [Interrogative 教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)  
  
-   [消息扩充教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)  
  
-   [批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)
  
## <a name="see-also"></a>另请参阅
  
[针对残障人士的辅助功能](../../adapters-and-accelerators/accelerator-hl7/accessibility-for-people-with-disabilities5.md)