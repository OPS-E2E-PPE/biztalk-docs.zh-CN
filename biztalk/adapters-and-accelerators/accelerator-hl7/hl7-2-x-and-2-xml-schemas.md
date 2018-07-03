---
title: HL7 2.X 和 2.xml 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69dc39b3f61dbb564fc3ef128405b8721633dd2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994182"
---
# <a name="hl7-2x-and-2xml-schemas"></a>HL7 2.X 和 2.xml 架构
HL7 组织发布的架构的两个集： HL7 2.X 架构，用于 HL7 编码的消息和 HL7 2.xml 架构，用于 XML 编码的消息。  

 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]本机配合 HL7 2.X 架构。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 安装程序到加载 HL7 2.X 架构文件\<*驱动器*\>: \program files\\Microsoft BizTalk\<版本\>HL7\Templates\Schemas\2.X 的加速器。 因此，HL7 2.X 架构均位于 HL7 架构选择器。 在 Microsoft 中运行 HL7 架构选择器[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  

 BTAHL7 处理 HL7 2.xml 架构，但 BTAHL7 安装程序将不会加载 HL7 2.xml 架构 BTAHL7 的程序文件，并且你必须修改某些使其可 BTAHL7 HL7 2.xml 架构。 若要使其可在 HL7 架构选择器和所需的修改，HL7 组织网站上，下载 2.xml 架构，然后运行**Update2XMLSchema**工具 (有关详细信息，请参阅[Update2XMLSchema 工具](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md))。 该工具将 HL7 2.xml 架构根据需要修改以处理[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，然后将其放\<*驱动器*\>: \program files\\Microsoft BizTalk\<版本\>Accelerator for HL7\Templates\Schemas。  

 每个这些集架构包含一系列的版本。 HL7 2.X 实时架构版本包括通过 2.5 2.1 (有关详细信息，请参阅[HL7 版本](../../adapters-and-accelerators/accelerator-hl7/hl7-versions.md))。 HL72。XML 架构版本包括 2.3.1、 2.4 和 2.5。 HL7 2.X 架构版本为向后兼容。 HL7 2.XML 架构版本不向后兼容。  

> [!NOTE]
>  因为 2.4 版本 2.XML 不是向后与 2.XML 的 2.3.1 兼容，可能会出错如果部署 2.XML 架构，2.4 版本，并提交消息符合 2.3.1 的实例版本。 若要更正此问题，可能需要创建不同的目标命名空间 2.3.1 处理消息。  

 当你创建多个部分组成的 HL7 2.X 消息，必须将正文部分的类型设置为特定的架构。 如果没有，序列化程序将拒绝该消息。  

 下表介绍 BTAHL7 的工作的架构的两种基本类型。  


|            架构类型            |                                                                                                                                                                                                                                                                                                   Description                                                                                                                                                                                                                                                                                                    |
|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| HL7FF – ER7 编码 (2.X) 架构 | BTAHL7 提供 HL7 2.X 架构派生自 HL7 访问数据库，包括：<br /><br /> 的基于版本、 消息类型或事件的所有特定架构一组<br />的段、 数据类型、 表、 标头和确认 (Ack) 通用架构<br /><br /> BTAHL7 支持以下架构模板：<br /><br /> -2.1 版<br />-V2.2<br />-V2.3<br />-适用于版本 V2.3.1<br />-于 V2.4<br />-版本 2.5<br /><br /> BTAHL7 安装程序安装 V2。中的架构 0x \<*驱动器*\>\Program Files\\Microsoft BizTalk Accelerator for HL7\Templates\Schemas。 |
|      HL7XML – 2.XML 编码      |                                                                                                                                            BTAHL7 支持以下架构：<br /><br /> -适用于版本 V2.3.1<br />-于 V2.4<br />-版本 2.5<br /><br /> BTAHL7 安装程序不安装 2.XML 架构。 若要安装它们，修改它们以使用 BizTalk 编辑器，请参阅[Update2XMLSchema 工具](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md)。                                                                                                                                            |

## <a name="common-schemas"></a>常见的架构  
 BTAHL7 使用 HL7 架构特定于消息类型来创建并验证该消息类型的实例的正文。 它还使用常见的架构，除了特定的架构。 BTAHL7 使用常见的 HL7 架构来验证 HL7 消息标头和确认。 这些文件是 MSH_25_GLO_DEF.xsd 标头和 ACK_24_GLO_DEF 确认。  

 BTAHL7 还使用常见的架构来验证数据类型、 段，以及表值。 这些架构是特定于每个版本的 HL7 标准。 例如，V2.2 消息的常见架构是 datatype_22.xsd、 segments_22.xsd 和 tablevalues_22.xsd。 BTAHL7 使用这些架构来验证数据类型、 段，以及对于所有消息都 V2.2 表值。  

## <a name="see-also"></a>请参阅  
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [BTAHL72X 平面文件处理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)   
 [BTAHL72XML 处理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)   
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)