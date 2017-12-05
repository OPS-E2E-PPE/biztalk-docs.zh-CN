---
title: "HL7 2.X 和 2.XML 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, schema types
- HL7-encoded messages
- 2.X schemas
- schemas, HL7 organization
- BTAHL7, HL7 schemas
- HL7, 2.XML schemas
- Update2XMLSchema tool
- schemas, common schemas
- 2.X schemas, about 2.X schemas
- 2.X schemas, compatibility
- 2.XML schemas, compatibility
- messages, HL7-encoded messages
- HL7 Schema Selector
- schemas, 2.XML schemas
- 2.XML schemas
- 2.XML schemas, about 2.XML schemas
- HL7, 2.X schemas
- schemas, compatibility
- common schemas
- schemas, 2.X schemas
ms.assetid: 02532d72-1948-48d8-a8ef-6b5a814eb573
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a02c8451dc0dc07b81a824f692203809d52b588
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="hl7-2x-and-2xml-schemas"></a>HL7 2.X 和 2.XML 架构
HL7 组织发布的架构的两个集： HL7 2.X 架构，用于 HL7 编码消息和 HL7 2.XML 架构，用于 XML 编码的消息。  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]本机配合 HL7 2.X 架构。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装程序加载 HL7 2.X 架构文件到\<*驱动器*\>: \program files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>HL7\Templates\ 快捷键Schemas\2.X。 因此，HL7 2.X 架构是 HL7 架构选择器中可用。 在中运行 HL7 架构选择器[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
 BTAHL7 配合 HL7 2.XML 架构，但 BTAHL7 安装程序不会加载和 BTAHL7 程序文件，HL7 2.XML 架构和你需要修改某些即可使用 BTAHL7 的 HL7 2.XML 架构。 要使它们可 HL7 架构选择器中，并使所需的修改，HL7 组织的网站中，从下载 2.XML 架构，然后运行**Update2XMLSchema**工具 (有关详细信息，请参阅[Update2XMLSchema 工具](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md))。 根据需要来处理，该工具将修改 HL7 2.XML 架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，然后将其放置在和\<*驱动器*\>: \program files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<版本\>HL7\Templates\Schemas 快捷键。  
  
 每个架构这些组包含一系列的版本。 HL7 2.X 实时架构版本包括通过 2.5 2.1 (有关详细信息，请参阅[HL7 版本](../../adapters-and-accelerators/accelerator-hl7/hl7-versions.md))。 HL72。XML 架构版本包括 2.3.1、 2.4 和 2.5。 HL7 2.X 架构版本是向后兼容。 HL7 2.XML 架构版本不向后兼容。  
  
> [!NOTE]
>  因为 2.XML 版本 2.4 不向后符合 2.XML 的 2.3.1，可能发生错误如果部署 2.XML 架构，2.4 版本，然后提交消息符合 2.3.1 的实例版本。 若要纠正此问题，你可能需要创建一个不同的目标命名空间，以应对 2.3.1 消息。  
  
 当你创建多个部分组成的 HL7 2.X 消息，必须将正文部分的类型设置为特定的架构。 如果没有，序列化程序将拒绝该消息。  
  
 下表介绍 BTAHL7 的工作的架构的两个基本类型。  
  
|架构类型|Description|  
|-----------------|-----------------|  
|HL7FF – ER7 编码 (2.X) 架构|BTAHL7 提供 HL7 2.X 架构派生自 HL7 Access 数据库中，包括：<br /><br /> -一组基于版本、 消息类型或事件的所有特定架构<br />的有关段、 数据类型、 表、 标头，和确认 (Ack) 通用架构<br /><br /> BTAHL7 支持以下架构模板：<br /><br /> -2.1 版<br />-V2.2<br />-V2.3<br />-V2.3.1<br />-V2.4<br />-V2.5<br /><br /> BTAHL7 安装程序安装 V2。X 中的架构\<*驱动器*\>\Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7\Templates\Schemas。|  
|HL7XML – 2.XML 编码|BTAHL7 支持以下架构：<br /><br /> -V2.3.1<br />-V2.4<br />-V2.5<br /><br /> BTAHL7 安装程序不会安装 2.XML 架构。 若要安装它们，并修改即可运行使用 BizTalk 编辑器，请参阅[Update2XMLSchema 工具](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md)。|  
  
## <a name="common-schemas"></a>通用架构  
 BTAHL7 使用特定于消息类型 HL7 架构来创建并验证该消息类型的实例的正文。 它还使用常见的架构，除了特定的架构。 BTAHL7 使用通用 HL7 架构来验证 HL7 消息标头和确认。 这些文件是 MSH_25_GLO_DEF.xsd 有关标头和 ACK_24_GLO_DEF 的确认。  
  
 BTAHL7 还使用通用架构来验证数据类型、 线段和表值。 这些架构是特定于每个版本的 HL7 标准。 例如，V2.2 消息的常见架构是 datatype_22.xsd、 segments_22.xsd 和 tablevalues_22.xsd。 BTAHL7 使用这些架构来验证数据类型、 线段和表值的所有 V2.2 消息。  
  
## <a name="see-also"></a>另请参阅  
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [BTAHL72X 平面文件处理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)   
 [BTAHL72XML 处理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)   
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)