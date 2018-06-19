---
title: HL7 版本 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HL7, standards
- HL7, versions
ms.assetid: 47299c6f-55c3-4434-8170-5ad73fe9a84c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c7edcfa6c44467c0660efd8a9b4b02df7010de6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204821"
---
# <a name="hl7-versions"></a>HL7 版本
HL7 版本 2 是一系列的密切相关的标准，而不是单个标准。 HL7 组织已设计为向上兼容的 HL7 版本间的兼容性规则的应用程序通过这些标准。 这些规则保证，范围内的版本 2 的接口定义的 HL7 版本的规则下仍可正常工作的定义后续版本中。 以便接收系统将能够接受来自更高版本的消息而不会破坏其实现和发送系统将能够继续将消息发送给支持更高版本的接收者。  
  
 务必请注意， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]):  
  
-   支持从版本 2.5 通过 2.1 版的所有实时 HL7 版本  
  
-   提供功能需要 HL7 版本之间进行映射，并启用在单一站点的多个版本的互操作性  
  
-   通过支持 Z 段支持本地化和启用备用解释之间的映射或使用的标准的消息  
  
 请务必要注意的消息的标准版本之间的差异：  
  
-   版本 1 作为概念证明工作正常  
  
-   版本 2 提供要支持应用程序之间的消息交换的消息规范的集合  
  
-   版本 3 将提供基于模型的集成的一组规范以支持各种互操作性需求  
  
 从本质上讲，版本 2 侧重于向用户提供他们需要执行指定的任务，虽然版本 3 着重介绍确保一致性和正文的消息的规范作为长期扩展性的规范的实用方法常规首选项。  
  
 通过引入临床文档使用 XML 的表示形式的标准，临床文档体系结构提供了 HL7 标准的重要扩展。  
  
 下表显示 HL7 标准开发前进。  
  
|事件|Year|详细信息|  
|-----------|----------|-------------|  
|HL7 成立|1987|在第一个会议在斯坦福，CA 中，包含 12 与会者。|  
|V1.0|1987|提供给 HL7 全体会议的草稿。|  
|2.0 版|1988|提供给 HL7 全体会议的草稿。|  
|2.1 版发布|1990|第一个广泛实现版本|  
|V2.2 发布|1994||  
|V.2.3 发布|1997|ANSI 批准|  
|V2.3.1 发布|1999|ANSI 批准|  
|V2.4 发布|2000|ANSI 批准|  
|临床文档体系结构|2000|ANSI 批准|  
|V2.5 发布|2003|完成批准内 HL7，为 ANSI 提交以供审批。|  
|正在进行的 V3.0|2003||  
  
## <a name="see-also"></a>另请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [消息模式](../../adapters-and-accelerators/accelerator-hl7/message-modes.md)   
 [HL7 消息传送](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)