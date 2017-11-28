---
title: "XML 反汇编程序和汇编程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler, XML
- assembler, XML
ms.assetid: 242a7a96-2342-4ab5-9d3f-1acbcc7ffd14
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4978484f888290377986ee4ae8bf049c14a1b31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xml-disassembler-and-assembler"></a><span data-ttu-id="d293a-102">XML 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="d293a-102">XML Disassembler and Assembler</span></span>
<span data-ttu-id="d293a-103">XML 反汇编程序和汇编程序确保[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 不仅支持 HL7 编码消息，但也支持传入和/或传出的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="d293a-103">The XML disassembler and assembler ensure that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) not only supports HL7-encoded messages, but also supports incoming and/or outgoing XML messages.</span></span>  
  
## <a name="xml-disassembler"></a><span data-ttu-id="d293a-104">XML 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="d293a-104">XML Disassembler</span></span>  
 <span data-ttu-id="d293a-105">XML 反汇编程序分析到 XML 段，用来处理传入的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="d293a-105">The XML disassembler parses incoming XML messages into XML segments for processing.</span></span> <span data-ttu-id="d293a-106">它会分析消息，拆装器执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="d293a-106">As it parses the messages, the disassembler performs the following tasks:</span></span>  
  
-   <span data-ttu-id="d293a-107">句柄转义序列</span><span class="sxs-lookup"><span data-stu-id="d293a-107">Handles escape sequences</span></span>  
  
-   <span data-ttu-id="d293a-108">处理检查必需/可选属性</span><span class="sxs-lookup"><span data-stu-id="d293a-108">Handles checks of required/optional properties</span></span>  
  
-   <span data-ttu-id="d293a-109">声明 Z 段的句柄</span><span class="sxs-lookup"><span data-stu-id="d293a-109">Handles declared Z segments</span></span>  
  
 <span data-ttu-id="d293a-110">它会分析消息，如 dissassembler 执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="d293a-110">As it parses the messages, the dissassembler performs the following:</span></span>  
  
-   <span data-ttu-id="d293a-111">语法验证</span><span class="sxs-lookup"><span data-stu-id="d293a-111">Syntactic validation</span></span>  
  
-   <span data-ttu-id="d293a-112">架构验证 （如果启用）</span><span class="sxs-lookup"><span data-stu-id="d293a-112">Schema validation (if enabled)</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="d293a-113">XML 汇编程序</span><span class="sxs-lookup"><span data-stu-id="d293a-113">XML Assembler</span></span>  
 <span data-ttu-id="d293a-114">XML 汇编程序传出的 XML 消息序列化为 XML 段。</span><span class="sxs-lookup"><span data-stu-id="d293a-114">The XML assembler serializes XML segments into an outgoing XML message.</span></span> <span data-ttu-id="d293a-115">XML 汇编程序支持，并创建以下确认 (ACK) 消息：</span><span class="sxs-lookup"><span data-stu-id="d293a-115">The XML assembler supports and creates the following acknowledgment (ACK) messages:</span></span>  
  
-   <span data-ttu-id="d293a-116">静态</span><span class="sxs-lookup"><span data-stu-id="d293a-116">Static</span></span>  
  
-   <span data-ttu-id="d293a-117">原始模式</span><span class="sxs-lookup"><span data-stu-id="d293a-117">Original mode</span></span>  
  
-   <span data-ttu-id="d293a-118">增强的模式</span><span class="sxs-lookup"><span data-stu-id="d293a-118">Enhanced mode</span></span>  
  
 <span data-ttu-id="d293a-119">XML 汇编程序还能够将延迟的 ACK 消息路由。</span><span class="sxs-lookup"><span data-stu-id="d293a-119">The XML assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d293a-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d293a-120">See Also</span></span>  
 <span data-ttu-id="d293a-121">[BTAHL72XML 处理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span><span class="sxs-lookup"><span data-stu-id="d293a-121">[BTAHL72XML Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span></span>  
 [<span data-ttu-id="d293a-122">BizTalk Accelerator for HL7 组件</span><span class="sxs-lookup"><span data-stu-id="d293a-122">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)