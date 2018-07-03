---
title: HL7 版本 |Microsoft Docs
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
ms.openlocfilehash: b3806ed8db2272068ff60c6656b73cdf4a726bd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005894"
---
# <a name="hl7-versions"></a>HL7 版本
HL7 版本 2 是系列密切相关的标准，而不是单个标准。 HL7 组织经过设计，这些标准通过 HL7 版本间的兼容性规则的应用程序向上兼容。 这些规则保证，在版本 2 的篇幅所限，HL7 版本的规则下定义的接口仍可正常工作后续版本的定义中。 以便接收系统将能够接受来自更高版本的消息而不会破坏其实现并发送系统将能够继续将消息发送到接收方人员支持更高版本。  
  
 务必要注意的 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]):  
  
- 支持从版本 2.1 到版本 2.5 的所有实时 HL7 版本  
  
- 提供所需 HL7 版本之间进行映射的功能并使位于单个站点的多个版本的互操作性  
  
- 通过支持的 Z 段支持本地化和启用备用解释之间的映射或使用的标准消息  
  
  请务必要注意的消息传送标准版本之间的区别：  
  
- 版本 1 的职能的概念证明  
  
- 版本 2 提供了一系列消息规范，支持应用程序之间交换消息  
  
- 第 3 版将提供的基于模型的集成的一组规范支持范围的互操作性需求  
  
  从本质上讲，第 2 版侧重于向用户提供他们需要执行指定的任务，而版本 3 侧重于确保一致性和正文作为消息规范的长期可扩展性的规范的编程之法整体。  
  
  临床文档体系结构提供通过引入临床文档，使用 XML 的表示形式的标准 HL7 标准的重要扩展。  
  
  下表显示了 HL7 标准开发进度。  
  
|事件|Year|详细信息|  
|-----------|----------|-------------|  
|HL7 成立了|1987|第一次会议中，在斯坦福，CA 中，包含 12 位与会者。|  
|V1.0|1987|提供给 HL7 全体会议的草稿。|  
|V2.0|1988|提供给 HL7 全体会议的草稿。|  
|2.1 版发布|1990|第一个广泛的实施版本|  
|V2.2 发布|1994||  
|V.2.3 发布|1997|ANSI 批准|  
|适用于版本 V2.3.1 发布|1999|ANSI 批准|  
|发布于 V2.4|2000|ANSI 批准|  
|临床文档体系结构|2000|ANSI 批准|  
|已发布的版本 2.5|2003|完成审批中 HL7，为 ANSI 提交以供审核。|  
|正在进行中的 3.0 版|2003||  
  
## <a name="see-also"></a>请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [使用 HL7 2.xml 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [消息模式](../../adapters-and-accelerators/accelerator-hl7/message-modes.md)   
 [HL7 消息传送](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)