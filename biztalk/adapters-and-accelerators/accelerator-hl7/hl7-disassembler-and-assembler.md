---
title: HL7 反汇编程序和汇编程序 |Microsoft 文档
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
ms.openlocfilehash: e81d621656fc678196f7f6fb709b29de87a3aaf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204925"
---
# <a name="hl7-disassembler-and-assembler"></a><span data-ttu-id="3480e-102">HL7 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="3480e-102">HL7 Disassembler and Assembler</span></span>
<span data-ttu-id="3480e-103">HL7 反汇编程序和汇编程序为 HL7 编码消息提供支持。</span><span class="sxs-lookup"><span data-stu-id="3480e-103">The HL7 disassembler and assembler provide support for HL7-encoded messages.</span></span> <span data-ttu-id="3480e-104">由于[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]处理以本机方式在 XML 格式的消息[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用 HL7 反汇编程序和汇编程序以使[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]HL7 集成引擎。</span><span class="sxs-lookup"><span data-stu-id="3480e-104">Since [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] processes messages natively in XML format, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses the HL7 disassembler and assembler to make [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] an HL7 integration engine.</span></span>  
  
## <a name="hl7-disassembler"></a><span data-ttu-id="3480e-105">HL7 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="3480e-105">HL7 Disassembler</span></span>  
 <span data-ttu-id="3480e-106">HL7 反汇编程序以进行处理的 XML 分成分析传入 HL7 编码消息。</span><span class="sxs-lookup"><span data-stu-id="3480e-106">The HL7 disassembler parses incoming HL7-encoded messages into XML segments for processing.</span></span> <span data-ttu-id="3480e-107">它将执行验证的消息头和正文的基本验证。</span><span class="sxs-lookup"><span data-stu-id="3480e-107">It performs validation of the message header, and basic validation of the body.</span></span> <span data-ttu-id="3480e-108">它将确定它使用来分析 HL7 消息的架构 (请参阅[HL7 中的架构确定 2.X 反汇编程序](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md))，确定该消息的源方，并执行其他验证正文的 (如果为启用当事方）。</span><span class="sxs-lookup"><span data-stu-id="3480e-108">It determines the schema that it uses to parse the HL7 message (see [Schema Determination in the HL7 2.X Disassembler](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)), determines the source party for the message, and performs additional validation of the body (if enabled for the party).</span></span>  
  
## <a name="hl7-assembler"></a><span data-ttu-id="3480e-109">HL7 汇编程序</span><span class="sxs-lookup"><span data-stu-id="3480e-109">HL7 Assembler</span></span>  
 <span data-ttu-id="3480e-110">HL7 汇编程序传出的 HL7 消息序列化为 XML 段。</span><span class="sxs-lookup"><span data-stu-id="3480e-110">The HL7 assembler serializes XML segments into an outgoing HL7 message.</span></span> <span data-ttu-id="3480e-111">它将确定它用于序列化 HL7 消息的架构 (请参阅[HL7 中的架构确定 2.X 汇编程序](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md))，确定目标参与方的消息，并执行验证的正文 （如果启用当事方）。</span><span class="sxs-lookup"><span data-stu-id="3480e-111">It determines the schema that it uses to serialize the HL7 message (see [Schema Determination in the HL7 2.X Assembler](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)), determines the destination party for the message, and performs validation of the body (if enabled for the party).</span></span>  
  
 <span data-ttu-id="3480e-112">汇编程序可以序列化下面的确认 (ACK) 消息：</span><span class="sxs-lookup"><span data-stu-id="3480e-112">The assembler can serialize the following acknowledgment (ACK) messages:</span></span>  
  
-   <span data-ttu-id="3480e-113">静态</span><span class="sxs-lookup"><span data-stu-id="3480e-113">Static</span></span>  
  
-   <span data-ttu-id="3480e-114">原始模式</span><span class="sxs-lookup"><span data-stu-id="3480e-114">Original mode</span></span>  
  
-   <span data-ttu-id="3480e-115">增强的模式</span><span class="sxs-lookup"><span data-stu-id="3480e-115">Enhanced mode</span></span>  
  
 <span data-ttu-id="3480e-116">HL7 汇编程序还能够将延迟的 ACK 消息路由。</span><span class="sxs-lookup"><span data-stu-id="3480e-116">The HL7 assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3480e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3480e-117">See Also</span></span>  
 <span data-ttu-id="3480e-118">[BTAHL72X 平面文件处理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) </span><span class="sxs-lookup"><span data-stu-id="3480e-118">[BTAHL72X Flat File Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) </span></span>  
 [<span data-ttu-id="3480e-119">BizTalk Accelerator for HL7 组件</span><span class="sxs-lookup"><span data-stu-id="3480e-119">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)