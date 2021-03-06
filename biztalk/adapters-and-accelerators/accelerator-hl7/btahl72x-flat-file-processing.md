---
title: BTAHL72X 平面文件处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd0755b31e56474a4cfde05264b0e1696d3aece7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251486"
---
# <a name="btahl72x-flat-file-processing"></a>BTAHL72X 平面文件处理
Microsoft BizTalk Accelerator for HL7 中的以下组件 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 处理 HL7 2.X （HL7 编码） 消息：  
  
- 管道和核心库： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。PipelineCommon.dll 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。PipelineMessageCore.dll  
  
- 组装器和拆装器库： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL72fAsm.dll 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL72fDAsm.dll  
  
- 确认 (ACK) 验证库用于双向 MLLP 发送适配器： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL7ACKHelper.dll  
  
## <a name="hl7-message-modes"></a>HL7 消息模式  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 支持以下的消息模式的 2.X 消息：  
  
- 发布服务器的订阅服务器 （发布-订阅） 的模式  
  
   发布服务器将广播到参与方订阅服务器，以声明性或一个未经请求的更新。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]提供到此模式下，大的灵活性，因为可以在设计时后管理订阅和参与方。  
  
- 请求-响应模式  
  
   来自特定实体的特定请求导致响应消息 interrogative 或查询消息交换。  
  
## <a name="flat-file-parsing"></a>平面文件解析  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 为三个部分的分析 HL7 2.X 多部分消息：  
  
-   标头 MSH 部分  
  
-   正文部分  
  
-   Z 部分  
  
## <a name="hl7-header-validation"></a>HL7 标头验证  
 HL7 反汇编程序和汇编程序执行 2.X 消息，以确认它可以处理该消息的标头的结构化和示意性验证。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 窗体上常见标头架构 MSH_25_GLO_DEF 示意图的验证。  
  
 例如，分析器会认为格式正确的 MSH1 和 MSH2 字段。 MSH1 必须只有一个字符。 MSH2 必须是介于两个到四个字符之间并且不含字符可以重复。  
  
## <a name="hl7-body-validation"></a>HL7 正文验证  
 HL7 反汇编程序和汇编程序执行 2.X 消息正文的基本结构验证和示意图验证，如果启用该功能。  
  
 正文的基本结构验证其[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]始终执行，包括验证以下：  
  
- 在段中有三个字符  
  
- 段分隔符是\<CR\>或\<CR\>\<LF\> （对于最后一个段是可选的）  
  
- 字段分隔符是相应  
  
- 未声明的 Z 段中有任何声明的段 （与定义的三个字符段标记）  
  
  正文的更广泛的架构验证过程包括以下：  
  
- 尾部字段分隔符  
  
   标头 MSH 段和正文段中  
  
- Z 段  
  
- XSD 支持和自定义数据类型  
  
   支持的 XSD 和非 XSD 类型 （TS （时间戳）、 DT (date)、 TM （时间） 和 TN （电话号码）  
  
- 枚举  
  
   ID （HL7 定义表） 和 IS （用户定义表）  
  
- 可选性  
  
   必需和可选  
  
- 重复  
  
   段和字段  
  
- 转义序列  
  
   对字符进行编码、 格式和字符集  
  
  启用或禁用所有消息从接收或发送给特定参与方 （源参与方的拆装器，则组装器的目标参与方） 的示意性验证。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 使用 HL7 2.X 架构直接对此处理，MSH9.3 消息结构标头字段、 MSH12 版本 ID 字段 （2.3.1、 2.4 或 2.5） 和命名空间设置确定[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
## <a name="hl7-disassembler-processing"></a>HL7 拆装器处理  
 HL7 拆装器将传入的 HL7 消息分析为进行处理的 XML 段。 在分析消息，拆装器将执行以下任务：  
  
-   句柄转义序列  
  
-   处理检查必需/可选属性  
  
-   句柄定义段和未定义或意外的 Z 段 (的 Z 段的说明，请参阅[通过 Z 对象自定义消息](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md))。  
  
-   将忽略意外的段末尾的实例 （它们将变成未声明的 Z 段）  
  
## <a name="error-reporting"></a>错误报告  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 报告标准 HL7 错误格式，其中包括段、 序列、 字段和错误代码的大多数错误。 但是，错误条件可能是这样不是所有这些都可用，例如，如果存在任何架构。 若要处理这种情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以在中报告错误备用[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]错误格式。 在消息中的错误段包括两个部分： 一个用于 HL7 错误，一个可选[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]错误。  
  
## <a name="ack-generation"></a>确认生成  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 对于 2.X 消息支持以下类型的确认 (Ack)。 HL7 错误类型和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用 （备用） 的错误类型：  
  
-   映射原始消息和确认  
  
-   HL7 原始 Ack  
  
-   HL7 增强 Ack  
  
     提交接受和应用程序接受  
  
-   静态/代理 ACK  
  
     ACK 或 NAK  
  
## <a name="property-promotion"></a>属性升级  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 支持升级以下 2.X 属性：  
  
-   属性架构  
  
-   MSH 标头架构  
  
## <a name="in-this-section"></a>本节内容  
  
-   [HL7 2.X 反汇编程序的架构确定](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)  
  
-   [HL7 2.X 汇编程序的架构确定](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)  
  
## <a name="see-also"></a>请参阅  
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)