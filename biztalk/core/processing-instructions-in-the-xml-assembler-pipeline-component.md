---
title: "处理 XML 汇编程序管道组件中的说明 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XMLNorm.ProcessingInstructionOption property
- envelopes, processing instructions
- XML Assembler [pipeline component], processing instructions
- Processing instruction scope property
- XMLNorm.ProcessingInstruction property
- envelopes, XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: d8ea453e-3b20-417d-bf25-9d424b0150fd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85ac6045084c0aea672b0c1e9d6dfb1b4a742d55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-instructions-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="c17dc-102">处理 XML 汇编程序管道组件中的说明</span><span class="sxs-lookup"><span data-stu-id="c17dc-102">Processing Instructions in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="c17dc-103">处理指令向处理 XML 文档的应用程序提供信息。</span><span class="sxs-lookup"><span data-stu-id="c17dc-103">Processing instructions provide information to the application that processes an XML document.</span></span> <span data-ttu-id="c17dc-104">这些信息可能包括有关如何处理文档、如何显示文档等的指令。</span><span class="sxs-lookup"><span data-stu-id="c17dc-104">Such information may include instructions about how to process the document, how to display it, and so on.</span></span>  
  
 <span data-ttu-id="c17dc-105">处理指令添加到 XML 文档由**添加处理指令**属性 (或同等**XMLNorm.ProcessingInstructionOption**消息上下文属性)。</span><span class="sxs-lookup"><span data-stu-id="c17dc-105">Processing instructions are added to an XML document by the **Add processing instructions** property (or the equivalent **XMLNorm.ProcessingInstructionOption** property on the message context).</span></span> <span data-ttu-id="c17dc-106">处理指令文本的情况下指定**添加处理指令文本**属性 (或同等**XMLNorm.ProcessingInstruction**消息上下文属性)。</span><span class="sxs-lookup"><span data-stu-id="c17dc-106">Processing instruction text is specified with the **Add processing instructions text** property (or the equivalent **XMLNorm.ProcessingInstruction** property on the message context).</span></span>  
  
 <span data-ttu-id="c17dc-107">**添加处理指令**属性 (或**XMLNorm.ProcessingInstructionOption**属性) 具有三个可能的值，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="c17dc-107">The **Add processing instructions** property (or **XMLNorm.ProcessingInstructionOption** property) has three possible values, which are described in the following table.</span></span>  
  
|<span data-ttu-id="c17dc-108">值</span><span class="sxs-lookup"><span data-stu-id="c17dc-108">Value</span></span>|<span data-ttu-id="c17dc-109">值</span><span class="sxs-lookup"><span data-stu-id="c17dc-109">Value</span></span>|<span data-ttu-id="c17dc-110">Description</span><span class="sxs-lookup"><span data-stu-id="c17dc-110">Description</span></span>|  
|-----------|-----------|-----------------|  
|<span data-ttu-id="c17dc-111">追加</span><span class="sxs-lookup"><span data-stu-id="c17dc-111">Append</span></span>|<span data-ttu-id="c17dc-112">0</span><span class="sxs-lookup"><span data-stu-id="c17dc-112">0</span></span>|<span data-ttu-id="c17dc-113">将 XML 组装器中的新处理指令附加到文档开头处的处理指令。</span><span class="sxs-lookup"><span data-stu-id="c17dc-113">New processing instructions from the XML Assembler are appended to the processing instructions at the beginning of the document.</span></span>|  
|<span data-ttu-id="c17dc-114">创建新的</span><span class="sxs-lookup"><span data-stu-id="c17dc-114">Create new</span></span>|<span data-ttu-id="c17dc-115">1</span><span class="sxs-lookup"><span data-stu-id="c17dc-115">1</span></span>|<span data-ttu-id="c17dc-116">XML 组装器中的新处理指令将覆盖文档开头处的现有处理指令。</span><span class="sxs-lookup"><span data-stu-id="c17dc-116">New processing instructions from the XML Assembler overwrite existing processing instructions at the beginning of the document.</span></span>|  
|<span data-ttu-id="c17dc-117">Ignore</span><span class="sxs-lookup"><span data-stu-id="c17dc-117">Ignore</span></span>|<span data-ttu-id="c17dc-118">2</span><span class="sxs-lookup"><span data-stu-id="c17dc-118">2</span></span>|<span data-ttu-id="c17dc-119">将删除文档开头处的处理指令。</span><span class="sxs-lookup"><span data-stu-id="c17dc-119">Processing instructions at the beginning of the document are removed.</span></span>|  
  
 <span data-ttu-id="c17dc-120">消息上下文中指定的处理指令对（或消息上下文属性）的优先级高于管道设计器中指定的属性对。</span><span class="sxs-lookup"><span data-stu-id="c17dc-120">The pair of processing instructions (or message context properties) specified on a message context take precedence over the property pair specified in Pipeline Designer.</span></span> <span data-ttu-id="c17dc-121">例如，如果**XMLNorm.ProcessingInstructionOption**指定为**新建**(1) 和**XMLNorm.ProcessingInstruction**未指定，空处理指令将替换现有的处理指令。</span><span class="sxs-lookup"><span data-stu-id="c17dc-121">For example, if **XMLNorm.ProcessingInstructionOption** is specified as **Create new** (1) and **XMLNorm.ProcessingInstruction** is not specified, an empty processing instruction will replace an existing processing instruction.</span></span>  
  
 <span data-ttu-id="c17dc-122">再举一例，如果**XMLNorm.ProcessingInstruction**指定但**XMLNorm.ProcessingInstructionOption**不，没有从消息上下文属性使用。</span><span class="sxs-lookup"><span data-stu-id="c17dc-122">As another example, if **XMLNorm.ProcessingInstruction** is specified but **XMLNorm.ProcessingInstructionOption** is not, none of the properties from the message context are used.</span></span> <span data-ttu-id="c17dc-123">在这种情况下，将使用管道设计器中的处理指令。</span><span class="sxs-lookup"><span data-stu-id="c17dc-123">In this case, the processing instructions from Pipeline Designer are used.</span></span>  
  
 <span data-ttu-id="c17dc-124">默认情况下，**添加处理指令**设置为**追加**，和**添加处理指令文本**为空。</span><span class="sxs-lookup"><span data-stu-id="c17dc-124">By default, **Add processing instructions** is set to **Append**, and **Add processing instructions text** is empty.</span></span>  
  
## <a name="processing-properties-and-envelopes"></a><span data-ttu-id="c17dc-125">处理属性和信封</span><span class="sxs-lookup"><span data-stu-id="c17dc-125">Processing Properties and Envelopes</span></span>  
 <span data-ttu-id="c17dc-126">由于对信封不保留处理指令，因此以下组合的平面文件组装器设置导致只有最外层信封才具有处理指令：</span><span class="sxs-lookup"><span data-stu-id="c17dc-126">Because processing instructions are not preserved for the envelopes, the following combination of flat file assembler settings results in only the outermost envelope having the processing instruction:</span></span>  
  
-   <span data-ttu-id="c17dc-127">**处理指令作用域**属性设置为"封套"。</span><span class="sxs-lookup"><span data-stu-id="c17dc-127">**Processing instruction scope** property set to "Envelope."</span></span>  
  
-   <span data-ttu-id="c17dc-128">**添加处理指令**属性设置为"追加"。</span><span class="sxs-lookup"><span data-stu-id="c17dc-128">**Add processing instructions** property set to "Append."</span></span>  
  
 <span data-ttu-id="c17dc-129">信封的情况下将使用的汇编中指定的处理指令**添加处理指令文本**属性。</span><span class="sxs-lookup"><span data-stu-id="c17dc-129">The envelope would use the processing instruction specified in the assembler's **Add Processing instructions text** property.</span></span>  
  
 <span data-ttu-id="c17dc-130">传入消息中所指定的外层信封或内层信封中的任何现有处理指令都不会出现在输出消息中。</span><span class="sxs-lookup"><span data-stu-id="c17dc-130">Any existing processing instructions in either the outer or inner envelope(s), as specified in the incoming message, will not be present in the output message(s).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c17dc-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c17dc-131">See Also</span></span>  
 <span data-ttu-id="c17dc-132">[XML 汇编程序管道组件](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c17dc-132">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="c17dc-133">[如何将 XML 汇编程序管道组件配置](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c17dc-133">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="c17dc-134">管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="c17dc-134">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)