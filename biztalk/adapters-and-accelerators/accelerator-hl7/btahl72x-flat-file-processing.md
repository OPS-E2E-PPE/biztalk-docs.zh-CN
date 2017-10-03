---
title: "BTAHL72X 平面文件处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ACKs
- 2.X messages, disassembler
- property promotion, MSH-header schemas
- disassembler, validating messages
- HL7, errors
- 2.X messages, validating headers
- acknowledgements, generating
- assembler, validating messages
- messages, multi-part messages
- property promotion, property schemas
- generating aknowledgements
- messages, 2.X messages
- schemas, MSH-header schemas
- 2.X messages, validating message bodies
- 2.X messages
- schemas, property schemas
- message modes, 2.X messages
- errors, HL7 error format
- flat files
- validating, messages
- schemas, property promotion
- headers, validating
- 2.X messages, message modes
- 2.X messages, header validation
- 2.X messages, parsing flat files
ms.assetid: c92e2f70-0bfa-4bc8-8044-4a6e62cabee3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b15d21653b9f0d6109487677484506c7a5d6bcc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="btahl72x-flat-file-processing"></a>BTAHL72X 平面文件处理
中的以下组件[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 处理 HL7 2.X （HL7 编码） 消息：  
  
-   管道和核心库： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。PipelineCommon.dll 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。PipelineMessageCore.dll  
  
-   汇编程序和反汇编程序库： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL72fAsm.dll 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL72fDAsm.dll  
  
-   用于双向 MLLP 确认 (ACK) 验证库发送适配器： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL7ACKHelper.dll  
  
## <a name="hl7-message-modes"></a>HL7 消息模式  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]支持以下的消息模式的 2.X 消息：  
  
-   发布服务器订阅服务器 （发布-订阅） 模式  
  
     为订阅服务器，为声明性或一个未经请求方广播发布服务器更新。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]提供灵活地此模式下，因为你可以在设计时后管理订阅和方。  
  
-   请求-响应模式  
  
     来自特定实体的特定请求导致响应消息 interrogative 或查询消息交换。  
  
## <a name="flat-file-parsing"></a>分析的平面文件  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析 HL7 2.X 多个部分的消息数分为三个部分：  
  
-   标头 MSH 一部分  
  
-   正文部分  
  
-   Z 一部分  
  
## <a name="hl7-header-validation"></a>HL7 标头验证  
 HL7 反汇编程序和汇编程序执行 2.X 消息，以验证它可以处理该消息的标头的结构化和示意图验证。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]窗体的常见标头架构 MSH_25_GLO_DEF 的示意图验证。  
  
 例如，该分析器会认为 MSH1 和 MSH2 字段的格式正确。 MSH1 必须只有一个字符。 MSH2 必须介于两个和第四个字符之间，并且没有的字符可以重复。  
  
## <a name="hl7-body-validation"></a>HL7 正文验证  
 HL7 反汇编程序和汇编程序执行 2.X 消息正文的基本结构验证和示意图验证，如果你启用它。  
  
 正文的基本结构验证其[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]始终执行，包括验证以下：  
  
-   段中有三个字符  
  
-   段分隔符是\<CR > 或\<CR >\<LF > （可选择的最后一段）  
  
-   字段分隔符是适当  
  
-   未声明的 Z 段中有任何声明的段 （与定义的三个字符段标记）  
  
 正文的更广泛的架构验证过程包括以下：  
  
-   尾随字段分隔符  
  
     标头 MSH 段和正文段中  
  
-   Z 段  
  
-   XSD 支持和自定义数据类型  
  
     支持的 XSD 和非 XSD 类型 （TS （时间戳）、 DT （日期）、 TM （时间） 和 TN （电话号码）  
  
-   枚举  
  
     ID （HL7 定义表） 和 IS （用户定义表）  
  
-   Optionality  
  
     必选和可选  
  
-   重复  
  
     段和字段  
  
-   转义序列  
  
     字符进行编码、 格式和字符集  
  
 启用或禁用的所有消息从接收或发送到特定方 （源方反汇编程序、 目标为汇编程序的参与方） 的示意图验证。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]直接对此处理，根据 MSH9.3 消息结构标头字段、 MSH12 版本 ID 字段 （2.3.1、 2.4 或 2.5） 和命名空间设置的使用 HL7 2.X 架构[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
## <a name="hl7-disassembler-processing"></a>HL7 反汇编程序处理  
 HL7 反汇编程序分析到 XML 段，用来处理传入的 HL7 消息。 它会分析消息，拆装器执行以下任务：  
  
-   句柄转义序列  
  
-   处理检查必需/可选属性  
  
-   句柄定义线段而未定义或意外 Z 线段 (Z 段的说明，请参阅[Z 对象通过自定义消息](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md))。  
  
-   将忽略意外的段数实例的末尾 （变得未声明的 Z 段）  
  
## <a name="error-reporting"></a>错误报告  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]报告标准 HL7 错误格式，其中包括段、 序列、 字段和错误代码的大多数错误。 但是，错误条件中的可能是这样的： 不是所有这些都可用，例如，如果没有架构，则存在。 若要处理这种情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以报告中备用的错误[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]错误格式。 在消息中的错误段包括两个部分： 一个用于 HL7 错误，一个可选[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]错误。  
  
## <a name="ack-generation"></a>ACK 生成  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X 消息支持以下类型的确认 (Ack)。 HL7 错误类型和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用 （备用） 错误类型：  
  
-   将原始消息和 ACK 映射  
  
-   HL7 原始确认  
  
-   HL7 增强确认  
  
     提交接受和应用程序接受  
  
-   静态/代理 ACK  
  
     ACK 或否认  
  
## <a name="property-promotion"></a>属性提升  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]升级以下 2.X 属性的支持：  
  
-   属性架构  
  
-   MSH 标头架构  
  
## <a name="in-this-section"></a>本节内容  
  
-   [HL7 2.X 反汇编程序中的架构确定](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)  
  
-   [架构确定在 HL7 2.X 汇编程序](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)  
  
## <a name="see-also"></a>另请参阅  
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)