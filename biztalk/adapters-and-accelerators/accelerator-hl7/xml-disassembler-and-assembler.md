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
ms.openlocfilehash: ccf8b71b08c35e94f710af12562060d477bf4abb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285141"
---
# <a name="xml-disassembler-and-assembler"></a><span data-ttu-id="d1a92-102">XML 拆装器和组装器</span><span class="sxs-lookup"><span data-stu-id="d1a92-102">XML Disassembler and Assembler</span></span>
<span data-ttu-id="d1a92-103">XML 拆装器和组装器，请确保 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 不仅支持 HL7 编码的消息，但也支持传入和/或传出 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="d1a92-103">The XML disassembler and assembler ensure that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) not only supports HL7-encoded messages, but also supports incoming and/or outgoing XML messages.</span></span>  
  
## <a name="xml-disassembler"></a><span data-ttu-id="d1a92-104">XML 拆装器</span><span class="sxs-lookup"><span data-stu-id="d1a92-104">XML Disassembler</span></span>  
 <span data-ttu-id="d1a92-105">XML 拆装器将传入的 XML 消息分析为进行处理的 XML 段。</span><span class="sxs-lookup"><span data-stu-id="d1a92-105">The XML disassembler parses incoming XML messages into XML segments for processing.</span></span> <span data-ttu-id="d1a92-106">在分析消息，拆装器将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="d1a92-106">As it parses the messages, the disassembler performs the following tasks:</span></span>  
  
- <span data-ttu-id="d1a92-107">句柄转义序列</span><span class="sxs-lookup"><span data-stu-id="d1a92-107">Handles escape sequences</span></span>  
  
- <span data-ttu-id="d1a92-108">处理检查必需/可选属性</span><span class="sxs-lookup"><span data-stu-id="d1a92-108">Handles checks of required/optional properties</span></span>  
  
- <span data-ttu-id="d1a92-109">句柄声明的 Z 段</span><span class="sxs-lookup"><span data-stu-id="d1a92-109">Handles declared Z segments</span></span>  
  
  <span data-ttu-id="d1a92-110">在分析消息，拆装器执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="d1a92-110">As it parses the messages, the dissassembler performs the following:</span></span>  
  
- <span data-ttu-id="d1a92-111">语法验证</span><span class="sxs-lookup"><span data-stu-id="d1a92-111">Syntactic validation</span></span>  
  
- <span data-ttu-id="d1a92-112">架构验证 （如果启用）</span><span class="sxs-lookup"><span data-stu-id="d1a92-112">Schema validation (if enabled)</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="d1a92-113">XML 组装器</span><span class="sxs-lookup"><span data-stu-id="d1a92-113">XML Assembler</span></span>  
 <span data-ttu-id="d1a92-114">XML 组装器将传出 XML 消息序列化为 XML 段。</span><span class="sxs-lookup"><span data-stu-id="d1a92-114">The XML assembler serializes XML segments into an outgoing XML message.</span></span> <span data-ttu-id="d1a92-115">XML 组装器支持，并创建以下确认 (ACK) 消息：</span><span class="sxs-lookup"><span data-stu-id="d1a92-115">The XML assembler supports and creates the following acknowledgment (ACK) messages:</span></span>  
  
- <span data-ttu-id="d1a92-116">Static</span><span class="sxs-lookup"><span data-stu-id="d1a92-116">Static</span></span>  
  
- <span data-ttu-id="d1a92-117">原始模式</span><span class="sxs-lookup"><span data-stu-id="d1a92-117">Original mode</span></span>  
  
- <span data-ttu-id="d1a92-118">增强的模式</span><span class="sxs-lookup"><span data-stu-id="d1a92-118">Enhanced mode</span></span>  
  
  <span data-ttu-id="d1a92-119">XML 组装器还具有将延迟的确认消息路由功能。</span><span class="sxs-lookup"><span data-stu-id="d1a92-119">The XML assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a92-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1a92-120">See Also</span></span>  
 <span data-ttu-id="d1a92-121">[BTAHL72XML 处理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span><span class="sxs-lookup"><span data-stu-id="d1a92-121">[BTAHL72XML Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span></span>  
 [<span data-ttu-id="d1a92-122">BizTalk Accelerator for HL7 组件</span><span class="sxs-lookup"><span data-stu-id="d1a92-122">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)