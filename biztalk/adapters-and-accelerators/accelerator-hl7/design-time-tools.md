---
title: 设计时工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Adapter Framework
- BTAHL7, tools
- Starter Project
- Pipeline Designer
- BizTalk Editor
- Visual Studio Starter Project
- BizTalk Mapper
- design-time tools
- Orchestration Designer
ms.assetid: 709bd782-d2ad-49be-ba33-e957eba2a0cc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d60cf2a64863a842bb974fcce2d4217f9b8105f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997438"
---
# <a name="design-time-tools"></a>设计时工具
在 Microsoft BizTalk Accelerator for HL7 工作的开发人员 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 具有一组的 BizTalk Server 中内置的设计时工具使用。 这些工具已集成到[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 有关详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具，请参阅 MicrosoftBizTalk Server 帮助。  
  
## <a name="biztalk-editor"></a>BizTalk 编辑器  
 使用 BizTalk 编辑器来管理 HL7 XSD 架构。 你的解决方案开发的可以使用以下受支持的架构模板 （为 XSD 文件）：  
  
-   HL7: 2.1 （包括 37 事件）  
  
-   HL7: 2.2 （包括 56 事件）  
  
-   HL7: 2.3 （包括 182 事件）  
  
-   HL7: 2.3.1 （包括 189 事件）  
  
-   HL7: 2.4 （包括 288 事件）  
  
-   HL7: 2.5 （包括大约 390 架构）  
  
-   HL7: 2.XML （适用于版本 V2.3.1 和 2.4 包括大约 450 架构）  
  
## <a name="biztalk-mapper"></a>BizTalk 映射器  
 你可以使用 BizTalk 映射器来创建并自定义用以定义数据转换的映射。 使用 BizTalk 映射器将映射的入站和出站转换[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]消息类型。  
  
## <a name="biztalk-orchestration-designer"></a>BizTalk 业务流程设计器  
 你可以使用 BizTalk 业务流程设计器来设计和实现业务流程。  
  
## <a name="biztalk-pipeline-designer"></a>BizTalk 管道设计器  
 使用 BizTalk 管道设计器创建和配置的管道的定义和处理步骤的链接。 管道将划分为若干阶段，处理，并确定在其中执行每个类别的工作的顺序。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 接收和传输管道，以了解所有受支持的 HL7 版本均提供。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 提供了自定义 HL7 分析器和拆装器/组装器组件的管道模板。  
  
## <a name="biztalk-adapter-framework"></a>BizTalk 适配器框架  
 你可以使用带有终结点适配器的 BizTalk 适配器框架与合作伙伴及应用程序集成。  
  
## <a name="visual-studio-starter-project"></a>Visual Studio 初学者项目  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 包括[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]初学者项目，可以使用您的 HL7 解决方案实现的快速入门。 初学者项目包括以下项目：  
  
- **空**[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**项目**。     不包括任何架构。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] **V2XCommon 项目**。 包括标头和确认架构。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] **V21Common 项目**。 包括用于 HL7 版本 2.1 的常见架构。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] **V22Common 项目**。 包括 HL7 版本 2.2 的常见架构。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] **V23Common 项目**。 包括常见 HL7 版本 2.3 所在的架构。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] **V231Common 项目**。 包括 HL7 版本 2.3.1 的常见架构。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] **V24Common 项目**。 包括 HL7 版本 2.4 的常见架构。  
  
- BTAHL7**V25Common 项目**。 包括 HL7 版本 2.5 的常见架构。  
  
## <a name="see-also"></a>请参阅  
 [工具和功能](../../adapters-and-accelerators/accelerator-hl7/tools-and-features.md)   
 [分析工具](../../adapters-and-accelerators/accelerator-hl7/analysis-tools2.md)