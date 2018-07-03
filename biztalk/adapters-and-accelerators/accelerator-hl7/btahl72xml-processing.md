---
title: BTAHL72XML 处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML messages, processing
- acknowledgements, 2.XML messages
- 2.XML messages, message modes
- message modes, 2.XML message
- 2.XML messages
- validating, 2.XML messages
- 2.XML messages, acknowledgements
- 2.XML messages, validating
ms.assetid: 2f12cb44-816c-4773-9db0-9cbc3d1b1aee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77bf987966e7f52b103c205298d8bf07c1fc1a5e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977286"
---
# <a name="btahl72xml-processing"></a><span data-ttu-id="89ae5-102">BTAHL72XML 处理</span><span class="sxs-lookup"><span data-stu-id="89ae5-102">BTAHL72XML Processing</span></span>
<span data-ttu-id="89ae5-103">Microsoft BizTalk Accelerator for HL7 中的以下组件 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 处理 HL7 2.XML （XML 编码） 的消息：</span><span class="sxs-lookup"><span data-stu-id="89ae5-103">The following components in Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) process HL7 2.XML (XML-encoded) messages:</span></span>  
  
- <span data-ttu-id="89ae5-104">管道和核心库： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。PipelineCommon.dll 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。PipelineMessageCore.dll</span><span class="sxs-lookup"><span data-stu-id="89ae5-104">Pipelines and core libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineCommon.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineMessageCore.dll</span></span>  
  
- <span data-ttu-id="89ae5-105">组装器和拆装器库： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL72XmlAsm.dll 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL72XmlDAsm.dll</span><span class="sxs-lookup"><span data-stu-id="89ae5-105">Assembler and disassembler libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72XmlAsm.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72XmlDAsm.dll</span></span>  
  
- <span data-ttu-id="89ae5-106">确认 (ACK) 验证库用于双向 MLLP 发送适配器： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL7ACKHelper.dll</span><span class="sxs-lookup"><span data-stu-id="89ae5-106">The acknowledgment (ACK) validation library used for the two-way MLLP send adapter: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL7ACKHelper.dll</span></span>  
  
## <a name="xml-message-modes"></a><span data-ttu-id="89ae5-107">XML 消息模式</span><span class="sxs-lookup"><span data-stu-id="89ae5-107">XML Message Modes</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="89ae5-108"> 2.XML 消息支持以下消息模式：</span><span class="sxs-lookup"><span data-stu-id="89ae5-108"> supports the following message modes for 2.XML messages:</span></span>  
  
- <span data-ttu-id="89ae5-109">发布服务器的订阅服务器 （发布-订阅） 的模式</span><span class="sxs-lookup"><span data-stu-id="89ae5-109">Publisher-subscriber (pub-sub) mode</span></span>  
  
   <span data-ttu-id="89ae5-110">发布服务器将广播到参与方订阅服务器，以声明性或一个未经请求的更新。</span><span class="sxs-lookup"><span data-stu-id="89ae5-110">The publisher broadcasts to a party of subscribers, either as declarative or an unsolicited update.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="89ae5-111"> 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]提供到此模式下，大的灵活性，因为可以在设计时后管理订阅和参与方。</span><span class="sxs-lookup"><span data-stu-id="89ae5-111"> and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] provide flexibility to this mode, since you can manage subscriptions and parties after design time.</span></span>  
  
- <span data-ttu-id="89ae5-112">请求-响应模式</span><span class="sxs-lookup"><span data-stu-id="89ae5-112">Request-response mode</span></span>  
  
   <span data-ttu-id="89ae5-113">来自特定实体的特定请求导致响应消息 interrogative 或查询消息交换。</span><span class="sxs-lookup"><span data-stu-id="89ae5-113">An interrogative or query message exchange in which a specific request from a specific entity results in a responding message.</span></span>  
  
## <a name="xml-validation"></a><span data-ttu-id="89ae5-114">XML 验证</span><span class="sxs-lookup"><span data-stu-id="89ae5-114">XML Validation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="89ae5-115"> 提供以下 2.验证 XML 消息：</span><span class="sxs-lookup"><span data-stu-id="89ae5-115"> provides the following validation of 2.XML messages:</span></span>  
  
- <span data-ttu-id="89ae5-116">XML 读取器</span><span class="sxs-lookup"><span data-stu-id="89ae5-116">XML reader</span></span>  
  
- <span data-ttu-id="89ae5-117">示意图</span><span class="sxs-lookup"><span data-stu-id="89ae5-117">Schematic</span></span>  
  
   <span data-ttu-id="89ae5-118">启用或禁用示意验证参与方。</span><span class="sxs-lookup"><span data-stu-id="89ae5-118">You enable or disable schematic validation by the party.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="89ae5-119"> 使用 HL7 2.xml 架构直接为此处理，MSH9.3 消息结构标头字段和 MSH12 版本 ID 字段 （2.3.1、 2.4 或 2.5） 确定。</span><span class="sxs-lookup"><span data-stu-id="89ae5-119"> uses the HL7 2.XML schemas directly for this processing, as determined by the MSH9.3 message-structure header field and the MSH12 Version ID field (2.3.1, 2.4, or 2.5).</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="89ae5-120"> 使用中的标准 XML 处理功能[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="89ae5-120"> uses the standard XML processing capabilities in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="89ae5-121">Z 段</span><span class="sxs-lookup"><span data-stu-id="89ae5-121">Z segment</span></span>  
  
   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="89ae5-122"> 验证未声明的 Z 段中包含任何声明的段。</span><span class="sxs-lookup"><span data-stu-id="89ae5-122"> validates that no declared segments are included in an undeclared Z segment.</span></span>  
  
## <a name="ack-generation"></a><span data-ttu-id="89ae5-123">确认生成</span><span class="sxs-lookup"><span data-stu-id="89ae5-123">ACK Generation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="89ae5-124"> 2.XML 消息支持以下类型的确认 (Ack)。</span><span class="sxs-lookup"><span data-stu-id="89ae5-124"> supports the following types of acknowledgments (ACKs) for 2.XML messages.</span></span> <span data-ttu-id="89ae5-125">HL7 错误类型和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用 （备用） 的错误类型：</span><span class="sxs-lookup"><span data-stu-id="89ae5-125">Both the HL7 error type and the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (alternate) error type are used:</span></span>  
  
-   <span data-ttu-id="89ae5-126">HL7 原始 Ack</span><span class="sxs-lookup"><span data-stu-id="89ae5-126">HL7 original ACKs</span></span>  
  
-   <span data-ttu-id="89ae5-127">HL7 增强 Ack</span><span class="sxs-lookup"><span data-stu-id="89ae5-127">HL7 enhanced ACKs</span></span>  
  
     <span data-ttu-id="89ae5-128">提交接受和应用程序接受</span><span class="sxs-lookup"><span data-stu-id="89ae5-128">Commit Accept and Application Accept</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89ae5-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="89ae5-129">See Also</span></span>  
 <span data-ttu-id="89ae5-130">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="89ae5-130">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="89ae5-131">使用 HL7 2.XML 架构</span><span class="sxs-lookup"><span data-stu-id="89ae5-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)