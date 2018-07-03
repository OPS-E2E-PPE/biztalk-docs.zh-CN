---
title: HL7 反汇编程序和汇编程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, HL7
- disassembler, HL7
ms.assetid: 54e83a04-86c8-482f-bea3-dbbdeb4584d6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d603e74defeac983b1287f16c7f562b706b8c54d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994990"
---
# <a name="hl7-disassembler-and-assembler"></a><span data-ttu-id="ac6c3-102">HL7 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="ac6c3-102">HL7 Disassembler and Assembler</span></span>
<span data-ttu-id="ac6c3-103">HL7 反汇编程序和汇编程序为 HL7 编码的消息提供支持。</span><span class="sxs-lookup"><span data-stu-id="ac6c3-103">The HL7 disassembler and assembler provide support for HL7-encoded messages.</span></span> <span data-ttu-id="ac6c3-104">因为 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]处理本机格式为 XML，Microsoft BizTalk Accelerator for HL7 消息 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用 HL7 反汇编程序和汇编程序进行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]HL7 集成引擎。</span><span class="sxs-lookup"><span data-stu-id="ac6c3-104">Since Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] processes messages natively in XML format, Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses the HL7 disassembler and assembler to make [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] an HL7 integration engine.</span></span>  
  
## <a name="hl7-disassembler"></a><span data-ttu-id="ac6c3-105">HL7 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="ac6c3-105">HL7 Disassembler</span></span>  
 <span data-ttu-id="ac6c3-106">HL7 拆装器将传入 HL7 编码的消息分析为进行处理的 XML 段。</span><span class="sxs-lookup"><span data-stu-id="ac6c3-106">The HL7 disassembler parses incoming HL7-encoded messages into XML segments for processing.</span></span> <span data-ttu-id="ac6c3-107">它将执行验证的消息头和正文的基本验证。</span><span class="sxs-lookup"><span data-stu-id="ac6c3-107">It performs validation of the message header, and basic validation of the body.</span></span> <span data-ttu-id="ac6c3-108">便可确定它使用来分析 HL7 消息架构 (请参阅[架构确定 HL7 2.X 拆装器](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md))，确定源参与方的消息，并执行其他验证的主体 (如果启用了参与方）。</span><span class="sxs-lookup"><span data-stu-id="ac6c3-108">It determines the schema that it uses to parse the HL7 message (see [Schema Determination in the HL7 2.X Disassembler](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)), determines the source party for the message, and performs additional validation of the body (if enabled for the party).</span></span>  
  
## <a name="hl7-assembler"></a><span data-ttu-id="ac6c3-109">HL7 组装器</span><span class="sxs-lookup"><span data-stu-id="ac6c3-109">HL7 Assembler</span></span>  
 <span data-ttu-id="ac6c3-110">HL7 组装器序列化到传出的 HL7 消息的 XML 段。</span><span class="sxs-lookup"><span data-stu-id="ac6c3-110">The HL7 assembler serializes XML segments into an outgoing HL7 message.</span></span> <span data-ttu-id="ac6c3-111">便可确定它使用序列化 HL7 消息架构 (请参阅[架构确定 HL7 2.X 汇编程序](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md))，确定目标参与方的消息，并执行验证的主体 （如果已启用的参与方）。</span><span class="sxs-lookup"><span data-stu-id="ac6c3-111">It determines the schema that it uses to serialize the HL7 message (see [Schema Determination in the HL7 2.X Assembler](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)), determines the destination party for the message, and performs validation of the body (if enabled for the party).</span></span>  
  
 <span data-ttu-id="ac6c3-112">在组装器可以序列化以下确认 (ACK) 消息：</span><span class="sxs-lookup"><span data-stu-id="ac6c3-112">The assembler can serialize the following acknowledgment (ACK) messages:</span></span>  
  
- <span data-ttu-id="ac6c3-113">静态</span><span class="sxs-lookup"><span data-stu-id="ac6c3-113">Static</span></span>  
  
- <span data-ttu-id="ac6c3-114">原始模式</span><span class="sxs-lookup"><span data-stu-id="ac6c3-114">Original mode</span></span>  
  
- <span data-ttu-id="ac6c3-115">增强的模式</span><span class="sxs-lookup"><span data-stu-id="ac6c3-115">Enhanced mode</span></span>  
  
  <span data-ttu-id="ac6c3-116">HL7 组装器还具有将延迟的确认消息路由功能。</span><span class="sxs-lookup"><span data-stu-id="ac6c3-116">The HL7 assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac6c3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac6c3-117">See Also</span></span>  
 <span data-ttu-id="ac6c3-118">[BTAHL72X 平面文件处理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) </span><span class="sxs-lookup"><span data-stu-id="ac6c3-118">[BTAHL72X Flat File Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) </span></span>  
 [<span data-ttu-id="ac6c3-119">BizTalk Accelerator for HL7 组件</span><span class="sxs-lookup"><span data-stu-id="ac6c3-119">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)