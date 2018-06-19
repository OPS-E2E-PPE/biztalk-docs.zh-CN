---
title: XML 信息在 XML 汇编程序管道组件中设置元素 |Microsoft 文档
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
ms.openlocfilehash: b194b85c88f63036cd74fcd9838aa99e73de6556
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289517"
---
# <a name="xml-information-set-elements-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="c7292-102">XML 信息集 XML 汇编程序管道组件中的元素</span><span class="sxs-lookup"><span data-stu-id="c7292-102">XML Information Set Elements in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="c7292-103">XML 组装器组件可处理 XML 信息集合元素，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c7292-103">The XML Assembler component handles XML information set elements as follows.</span></span>  
  
|<span data-ttu-id="c7292-104">元素</span><span class="sxs-lookup"><span data-stu-id="c7292-104">Element</span></span>|<span data-ttu-id="c7292-105">Description</span><span class="sxs-lookup"><span data-stu-id="c7292-105">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7292-106">comment</span><span class="sxs-lookup"><span data-stu-id="c7292-106">comment</span></span>|<span data-ttu-id="c7292-107">保留文档中打开与关闭 XML 标记之间的注释。</span><span class="sxs-lookup"><span data-stu-id="c7292-107">Comments are preserved between opening and closing XML tags in the document.</span></span>|  
|<span data-ttu-id="c7292-108">CDATA</span><span class="sxs-lookup"><span data-stu-id="c7292-108">CDATA</span></span>|<span data-ttu-id="c7292-109">保留文档中打开与关闭 XML 标记之间的 CDATA。</span><span class="sxs-lookup"><span data-stu-id="c7292-109">CDATA is preserved between opening and closing XML tags in the document.</span></span> <span data-ttu-id="c7292-110">CDATA 值不用于属性升级或可分辨字段。</span><span class="sxs-lookup"><span data-stu-id="c7292-110">CDATA values are not used for property promotion or distinguished fields.</span></span>|  
|<span data-ttu-id="c7292-111">处理指令</span><span class="sxs-lookup"><span data-stu-id="c7292-111">processing instructions</span></span>|<span data-ttu-id="c7292-112">处理指令前处理文档的 XML 标记基于其值 (有关详细信息，请参阅[处理 XML 汇编程序管道组件中的说明](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md))。</span><span class="sxs-lookup"><span data-stu-id="c7292-112">Processing instructions located before the document XML tag are handled based on their value (for more information, see [Processing Instructions in the XML Assembler Pipeline Component](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)).</span></span> <span data-ttu-id="c7292-113">文档打开标记与关闭标记之间的处理指令将保留，</span><span class="sxs-lookup"><span data-stu-id="c7292-113">Processing instructions between document open and close tags are preserved.</span></span> <span data-ttu-id="c7292-114">XML 结束标记后的处理指令被忽略，因为前后也是所有说明操作，在中，信封。</span><span class="sxs-lookup"><span data-stu-id="c7292-114">Processing instructions after the closing XML tag are ignored, as are any instructions before, in, or after the envelope.</span></span>|  
|<span data-ttu-id="c7292-115">XML 声明</span><span class="sxs-lookup"><span data-stu-id="c7292-115">XML declaration</span></span>|<span data-ttu-id="c7292-116">XML 组装器管道组件可能会保留 XML 声明字符串（例如，`<?xml version='1.0'? encoding='UTF-8'>`）。</span><span class="sxs-lookup"><span data-stu-id="c7292-116">The XML declaration string, such as `<?xml version='1.0'? encoding='UTF-8'>`, may be preserved by the XML Assembler pipeline component.</span></span> <span data-ttu-id="c7292-117">这将由控制**添加 XML 声明**属性或在消息上下文中，它的等效项**XMLNorm.AddXMLDeclaration**。</span><span class="sxs-lookup"><span data-stu-id="c7292-117">This is controlled by the **Add XML declaration** property, or its equivalent on the message context, **XMLNorm.AddXMLDeclaration**.</span></span><br /><br /> <span data-ttu-id="c7292-118">如果此选项设置为**True**然后 XML 声明将添加到文档。</span><span class="sxs-lookup"><span data-stu-id="c7292-118">If this option is set to **True** then the XML declaration will be added to the document.</span></span> <span data-ttu-id="c7292-119">如果 XML 声明已存在，则会覆盖该声明。</span><span class="sxs-lookup"><span data-stu-id="c7292-119">If the XML declaration already existed, it will be overwritten.</span></span><br /><br /> <span data-ttu-id="c7292-120">如果此选项设置为**False**，没有 XML 声明将被添加，并且将删除任何现有的 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="c7292-120">If this option is set to **False**, no XML declaration will be added and any existing XML declaration will be removed.</span></span> <span data-ttu-id="c7292-121">消息上下文中此属性的值的优先级高于管道设计器中指定的值。</span><span class="sxs-lookup"><span data-stu-id="c7292-121">The value of this property in the message context takes precedence over the value specified in Pipeline Designer.</span></span><br /><br /> <span data-ttu-id="c7292-122">默认值： **True** （始终添加 XML 声明）</span><span class="sxs-lookup"><span data-stu-id="c7292-122">Default value: **True** (the XML declaration is always added)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7292-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7292-123">See Also</span></span>  
 <span data-ttu-id="c7292-124">[XML 汇编程序管道组件](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c7292-124">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="c7292-125">[如何将 XML 汇编程序管道组件配置](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c7292-125">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="c7292-126">管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="c7292-126">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)