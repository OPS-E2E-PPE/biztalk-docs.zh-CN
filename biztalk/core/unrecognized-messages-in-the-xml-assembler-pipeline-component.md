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
ms.openlocfilehash: c61a82f051349b69d72089093f4646325490a943
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292606"
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="7ac1d-102">XML 组装器管道组件中无法识别的消息</span><span class="sxs-lookup"><span data-stu-id="7ac1d-102">Unrecognized Messages in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="7ac1d-103">XML 组装器组件将作为"无法识别"如果消息具有一条消息：</span><span class="sxs-lookup"><span data-stu-id="7ac1d-103">The XML Assembler component treats a message as "unrecognized" if a message has:</span></span>  
  
-   <span data-ttu-id="7ac1d-104">没有正文部分。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-104">No body part.</span></span>  
  
-   <span data-ttu-id="7ac1d-105">正文部分为空。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-105">An empty body part.</span></span>  
  
-   <span data-ttu-id="7ac1d-106">正文部分中没有数据。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-106">No data in the body part.</span></span>  
  
-   <span data-ttu-id="7ac1d-107">部署没有关联的架构。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-107">No associated schema deployed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ac1d-108">非 XML 消息始终被视为无法识别。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-108">Non-XML messages are always treated as unrecognized.</span></span>  
  
 <span data-ttu-id="7ac1d-109">XML 组装器处理无法识别的消息的方式受**XMLNorm.AllowUnrecognizedMessage**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-109">The manner in which the XML Assembler handles an unrecognized message is controlled by the **XMLNorm.AllowUnrecognizedMessage** message context property.</span></span>  
  
 <span data-ttu-id="7ac1d-110">当**XMLNorm.AllowUnrecognizedMessage**设置为**True**，XML 组装器处理 XML 文档，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7ac1d-110">When **XMLNorm.AllowUnrecognizedMessage** is set to **True**, the XML Assembler handles XML documents as follows:</span></span>  
  
- <span data-ttu-id="7ac1d-111">为正文部分为空或空数据中将原封不动地通过组装器没有正文部分、 或的消息。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-111">A message with no body part or with an empty body part or empty data in the body part passes unchanged through the assembler.</span></span>  
  
- <span data-ttu-id="7ac1d-112">没有与它关联的已部署的架构的文档将原封不动通过组装器。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-112">A document that does not have a deployed schema associated with it passes unchanged through the assembler.</span></span>  
  
- <span data-ttu-id="7ac1d-113">（而不考虑是否显式组件属性中引用该架构或将其架构解析过程中找到） 组装器处理具有关联的已部署架构的文档。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-113">A document with an associated deployed schema is processed by the assembler (regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process).</span></span>  
  
  <span data-ttu-id="7ac1d-114">如果**XMLNorm.AllowUnrecognizedMessage**设置为**False**，XML 组装器处理 XML 文档，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7ac1d-114">If **XMLNorm.AllowUnrecognizedMessage** is set to **False**, the XML Assembler handles XML documents as follows:</span></span>  
  
- <span data-ttu-id="7ac1d-115">未处理的消息没有正文部分、 或正文部分为空或正文部分中的空数据。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-115">A message with no body part or with an empty body part or empty data in the body part is not processed.</span></span> <span data-ttu-id="7ac1d-116">报告错误并挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-116">An error is reported and the message is suspended.</span></span>  
  
- <span data-ttu-id="7ac1d-117">没有与它关联的已部署的架构的消息不处理。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-117">A message that does not have a deployed schema associated with it is not processed.</span></span> <span data-ttu-id="7ac1d-118">报告错误并挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-118">An error is reported and the message is suspended.</span></span>  
  
- <span data-ttu-id="7ac1d-119">（而不考虑是否显式组件属性中引用该架构或将其架构解析过程中找到） 组装器处理具有关联的已部署架构的文档。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-119">A document with an associated deployed schema is processed by the assembler (regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process).</span></span>  
  
- <span data-ttu-id="7ac1d-120">默认情况下，XML 组装器组件不允许无法识别的消息 (即**XMLNorm.AllowUnrecognizedMessages**被视为**False**如果未设置在消息上下文)。</span><span class="sxs-lookup"><span data-stu-id="7ac1d-120">By default, the XML Assembler component does not allow unrecognized messages (that is, **XMLNorm.AllowUnrecognizedMessages** is considered **False** if it is not set on the message context).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac1d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ac1d-121">See Also</span></span>  
 <span data-ttu-id="7ac1d-122">[XML 组装器管道组件](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="7ac1d-122">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="7ac1d-123">[如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="7ac1d-123">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="7ac1d-124">Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="7ac1d-124">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)