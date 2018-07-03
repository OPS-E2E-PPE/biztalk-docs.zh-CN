---
title: XML 拆装器和组装器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, XML
- assembler, XML
ms.assetid: 242a7a96-2342-4ab5-9d3f-1acbcc7ffd14
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d8dfaf91d9b0d3d058c4d3e31cd67c652235eff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983038"
---
# <a name="xml-disassembler-and-assembler"></a><span data-ttu-id="9106a-102">XML 拆装器和组装器</span><span class="sxs-lookup"><span data-stu-id="9106a-102">XML Disassembler and Assembler</span></span>
<span data-ttu-id="9106a-103">XML 拆装器和组装器，请确保 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 不仅支持 HL7 编码的消息，但也支持传入和/或传出 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="9106a-103">The XML disassembler and assembler ensure that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) not only supports HL7-encoded messages, but also supports incoming and/or outgoing XML messages.</span></span>  
  
## <a name="xml-disassembler"></a><span data-ttu-id="9106a-104">XML 拆装器</span><span class="sxs-lookup"><span data-stu-id="9106a-104">XML Disassembler</span></span>  
 <span data-ttu-id="9106a-105">XML 拆装器将传入的 XML 消息分析为进行处理的 XML 段。</span><span class="sxs-lookup"><span data-stu-id="9106a-105">The XML disassembler parses incoming XML messages into XML segments for processing.</span></span> <span data-ttu-id="9106a-106">在分析消息，拆装器将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="9106a-106">As it parses the messages, the disassembler performs the following tasks:</span></span>  
  
- <span data-ttu-id="9106a-107">句柄转义序列</span><span class="sxs-lookup"><span data-stu-id="9106a-107">Handles escape sequences</span></span>  
  
- <span data-ttu-id="9106a-108">处理检查必需/可选属性</span><span class="sxs-lookup"><span data-stu-id="9106a-108">Handles checks of required/optional properties</span></span>  
  
- <span data-ttu-id="9106a-109">句柄声明的 Z 段</span><span class="sxs-lookup"><span data-stu-id="9106a-109">Handles declared Z segments</span></span>  
  
  <span data-ttu-id="9106a-110">在分析消息，拆装器执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="9106a-110">As it parses the messages, the dissassembler performs the following:</span></span>  
  
- <span data-ttu-id="9106a-111">语法验证</span><span class="sxs-lookup"><span data-stu-id="9106a-111">Syntactic validation</span></span>  
  
- <span data-ttu-id="9106a-112">架构验证 （如果启用）</span><span class="sxs-lookup"><span data-stu-id="9106a-112">Schema validation (if enabled)</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="9106a-113">XML 组装器</span><span class="sxs-lookup"><span data-stu-id="9106a-113">XML Assembler</span></span>  
 <span data-ttu-id="9106a-114">XML 组装器将传出 XML 消息序列化为 XML 段。</span><span class="sxs-lookup"><span data-stu-id="9106a-114">The XML assembler serializes XML segments into an outgoing XML message.</span></span> <span data-ttu-id="9106a-115">XML 组装器支持，并创建以下确认 (ACK) 消息：</span><span class="sxs-lookup"><span data-stu-id="9106a-115">The XML assembler supports and creates the following acknowledgment (ACK) messages:</span></span>  
  
- <span data-ttu-id="9106a-116">静态</span><span class="sxs-lookup"><span data-stu-id="9106a-116">Static</span></span>  
  
- <span data-ttu-id="9106a-117">原始模式</span><span class="sxs-lookup"><span data-stu-id="9106a-117">Original mode</span></span>  
  
- <span data-ttu-id="9106a-118">增强的模式</span><span class="sxs-lookup"><span data-stu-id="9106a-118">Enhanced mode</span></span>  
  
  <span data-ttu-id="9106a-119">XML 组装器还具有将延迟的确认消息路由功能。</span><span class="sxs-lookup"><span data-stu-id="9106a-119">The XML assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9106a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="9106a-120">See Also</span></span>  
 <span data-ttu-id="9106a-121">[BTAHL72XML 处理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span><span class="sxs-lookup"><span data-stu-id="9106a-121">[BTAHL72XML Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span></span>  
 [<span data-ttu-id="9106a-122">BizTalk Accelerator for HL7 组件</span><span class="sxs-lookup"><span data-stu-id="9106a-122">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)