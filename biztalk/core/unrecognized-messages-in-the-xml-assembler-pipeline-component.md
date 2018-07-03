---
title: 无法识别的消息中 XML 组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.AllowUnrecognizedMessage property
- XML Assembler [pipeline component], unrecognized messages
- pipeline components, XML Assembler
ms.assetid: dd98512a-33a4-4b2e-977e-1b3a30747c6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de9f072fc09126d56397725f93505afaca46adf4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974814"
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="102ff-102">XML 组装器管道组件中无法识别的消息</span><span class="sxs-lookup"><span data-stu-id="102ff-102">Unrecognized Messages in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="102ff-103">如果消息符合以下情况，则 XML 组装器组件将该消息视为“无法识别”：</span><span class="sxs-lookup"><span data-stu-id="102ff-103">The XML Assembler component treats a message as "unrecognized" if a message has:</span></span>  
  
-   <span data-ttu-id="102ff-104">没有正文部分。</span><span class="sxs-lookup"><span data-stu-id="102ff-104">No body part.</span></span>  
  
-   <span data-ttu-id="102ff-105">正文部分为空。</span><span class="sxs-lookup"><span data-stu-id="102ff-105">An empty body part.</span></span>  
  
-   <span data-ttu-id="102ff-106">正文部分中没有数据。</span><span class="sxs-lookup"><span data-stu-id="102ff-106">No data in the body part.</span></span>  
  
-   <span data-ttu-id="102ff-107">没有部署关联的架构。</span><span class="sxs-lookup"><span data-stu-id="102ff-107">No associated schema deployed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="102ff-108">非 XML 消息始终被视为无法识别的消息。</span><span class="sxs-lookup"><span data-stu-id="102ff-108">Non-XML messages are always treated as unrecognized.</span></span>  
  
 <span data-ttu-id="102ff-109">XML 组装器处理无法识别的消息的方式受**XMLNorm.AllowUnrecognizedMessage**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="102ff-109">The manner in which the XML Assembler handles an unrecognized message is controlled by the **XMLNorm.AllowUnrecognizedMessage** message context property.</span></span>  
  
 <span data-ttu-id="102ff-110">当**XMLNorm.AllowUnrecognizedMessage**设置为**True**，XML 组装器处理 XML 文档，如下所示：</span><span class="sxs-lookup"><span data-stu-id="102ff-110">When **XMLNorm.AllowUnrecognizedMessage** is set to **True**, the XML Assembler handles XML documents as follows:</span></span>  
  
- <span data-ttu-id="102ff-111">没有正文部分、正文部分为空或正文部分中数据为空的消息将原封不动地通过组装器。</span><span class="sxs-lookup"><span data-stu-id="102ff-111">A message with no body part or with an empty body part or empty data in the body part passes unchanged through the assembler.</span></span>  
  
- <span data-ttu-id="102ff-112">未部署关联架构的文档将原封不动地通过组装器。</span><span class="sxs-lookup"><span data-stu-id="102ff-112">A document that does not have a deployed schema associated with it passes unchanged through the assembler.</span></span>  
  
- <span data-ttu-id="102ff-113">部署了关联架构的文档将由组装器进行处理（无论是组件属性中显式引用了架构还是在架构解析过程中找到了架构）。</span><span class="sxs-lookup"><span data-stu-id="102ff-113">A document with an associated deployed schema is processed by the assembler (regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process).</span></span>  
  
  <span data-ttu-id="102ff-114">如果**XMLNorm.AllowUnrecognizedMessage**设置为**False**，XML 组装器处理 XML 文档，如下所示：</span><span class="sxs-lookup"><span data-stu-id="102ff-114">If **XMLNorm.AllowUnrecognizedMessage** is set to **False**, the XML Assembler handles XML documents as follows:</span></span>  
  
- <span data-ttu-id="102ff-115">没有正文部分、正文部分为空或正文部分中数据为空的消息不进行处理。</span><span class="sxs-lookup"><span data-stu-id="102ff-115">A message with no body part or with an empty body part or empty data in the body part is not processed.</span></span> <span data-ttu-id="102ff-116">组装器将报告错误并挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="102ff-116">An error is reported and the message is suspended.</span></span>  
  
- <span data-ttu-id="102ff-117">未部署关联架构的消息不进行处理。</span><span class="sxs-lookup"><span data-stu-id="102ff-117">A message that does not have a deployed schema associated with it is not processed.</span></span> <span data-ttu-id="102ff-118">组装器将报告错误并挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="102ff-118">An error is reported and the message is suspended.</span></span>  
  
- <span data-ttu-id="102ff-119">部署了关联架构的文档将由组装器进行处理（无论是组件属性中显式引用了架构还是在架构解析过程中找到了架构）。</span><span class="sxs-lookup"><span data-stu-id="102ff-119">A document with an associated deployed schema is processed by the assembler (regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process).</span></span>  
  
- <span data-ttu-id="102ff-120">默认情况下，XML 组装器组件不允许无法识别的消息 (即**XMLNorm.AllowUnrecognizedMessages**被视为**False**如果未设置在消息上下文)。</span><span class="sxs-lookup"><span data-stu-id="102ff-120">By default, the XML Assembler component does not allow unrecognized messages (that is, **XMLNorm.AllowUnrecognizedMessages** is considered **False** if it is not set on the message context).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="102ff-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="102ff-121">See Also</span></span>  
 <span data-ttu-id="102ff-122">[XML 组装器管道组件](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="102ff-122">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="102ff-123">[如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="102ff-123">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="102ff-124">Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="102ff-124">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)