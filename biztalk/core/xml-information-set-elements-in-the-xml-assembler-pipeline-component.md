---
title: XML 组装器管道组件中的 XML 信息集合元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], processing instructions
- Add XML declaration property
- XMLNorm.AddXMLDeclaration property
- pipeline components, XML Assembler
- XML Assembler [pipeline component], XML information set
ms.assetid: 5a262763-838e-476b-8117-30c94bc1d64a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c6662f65c82a79fb174fe3b97c10fc24351255b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246398"
---
# <a name="xml-information-set-elements-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="fb3ae-102">XML 组装器管道组件中的 XML 信息集合元素</span><span class="sxs-lookup"><span data-stu-id="fb3ae-102">XML Information Set Elements in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="fb3ae-103">XML 组装器组件，如下所示处理 XML 信息集合元素。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-103">The XML Assembler component handles XML information set elements as follows.</span></span>  
  
|<span data-ttu-id="fb3ae-104">元素</span><span class="sxs-lookup"><span data-stu-id="fb3ae-104">Element</span></span>|<span data-ttu-id="fb3ae-105">Description</span><span class="sxs-lookup"><span data-stu-id="fb3ae-105">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fb3ae-106">comment</span><span class="sxs-lookup"><span data-stu-id="fb3ae-106">comment</span></span>|<span data-ttu-id="fb3ae-107">打开和关闭文档中的 XML 标记之间保留注释。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-107">Comments are preserved between opening and closing XML tags in the document.</span></span>|  
|<span data-ttu-id="fb3ae-108">CDATA</span><span class="sxs-lookup"><span data-stu-id="fb3ae-108">CDATA</span></span>|<span data-ttu-id="fb3ae-109">CDATA 保留之间打开和关闭文档中的 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-109">CDATA is preserved between opening and closing XML tags in the document.</span></span> <span data-ttu-id="fb3ae-110">CDATA 值不用于属性升级或可分辨字段。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-110">CDATA values are not used for property promotion or distinguished fields.</span></span>|  
|<span data-ttu-id="fb3ae-111">处理指令</span><span class="sxs-lookup"><span data-stu-id="fb3ae-111">processing instructions</span></span>|<span data-ttu-id="fb3ae-112">处理指令位于文档 XML 标记进行处理之前根据它们的值 (有关详细信息，请参阅[XML 组装器管道组件中处理指令](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md))。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-112">Processing instructions located before the document XML tag are handled based on their value (for more information, see [Processing Instructions in the XML Assembler Pipeline Component](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)).</span></span> <span data-ttu-id="fb3ae-113">文档打开和关闭之间的处理指令将保留标记。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-113">Processing instructions between document open and close tags are preserved.</span></span> <span data-ttu-id="fb3ae-114">XML 结束标记后的处理指令被忽略，因为之前，在中，或信封之后是任何说明。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-114">Processing instructions after the closing XML tag are ignored, as are any instructions before, in, or after the envelope.</span></span>|  
|<span data-ttu-id="fb3ae-115">XML 声明</span><span class="sxs-lookup"><span data-stu-id="fb3ae-115">XML declaration</span></span>|<span data-ttu-id="fb3ae-116">XML 声明字符串，如`<?xml version='1.0'? encoding='UTF-8'>`，可能会保留 XML 组装器管道组件。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-116">The XML declaration string, such as `<?xml version='1.0'? encoding='UTF-8'>`, may be preserved by the XML Assembler pipeline component.</span></span> <span data-ttu-id="fb3ae-117">这由控制**添加 XML 声明**属性或在消息上下文，其等效**XMLNorm.AddXMLDeclaration**。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-117">This is controlled by the **Add XML declaration** property, or its equivalent on the message context, **XMLNorm.AddXMLDeclaration**.</span></span><br /><br /> <span data-ttu-id="fb3ae-118">如果此选项设置为 **，则返回 True**则会向文档添加 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-118">If this option is set to **True** then the XML declaration will be added to the document.</span></span> <span data-ttu-id="fb3ae-119">如果已在 XML 声明已存在，它将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-119">If the XML declaration already existed, it will be overwritten.</span></span><br /><br /> <span data-ttu-id="fb3ae-120">如果此选项设置为**False**，将添加任何 XML 声明，并且将删除任何现有的 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-120">If this option is set to **False**, no XML declaration will be added and any existing XML declaration will be removed.</span></span> <span data-ttu-id="fb3ae-121">在消息上下文中此属性的值优先于在管道设计器中指定的值。</span><span class="sxs-lookup"><span data-stu-id="fb3ae-121">The value of this property in the message context takes precedence over the value specified in Pipeline Designer.</span></span><br /><br /> <span data-ttu-id="fb3ae-122">默认值：**True** （始终添加 XML 声明）</span><span class="sxs-lookup"><span data-stu-id="fb3ae-122">Default value: **True** (the XML declaration is always added)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb3ae-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb3ae-123">See Also</span></span>  
 <span data-ttu-id="fb3ae-124">[XML 组装器管道组件](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="fb3ae-124">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="fb3ae-125">[如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="fb3ae-125">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="fb3ae-126">Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="fb3ae-126">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)