---
title: XML 汇编程序管道组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: 3adfd603-0577-49c2-ae9d-445d62fed385
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22348b61ca32567190fa99e103fe536f5199af58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289485"
---
# <a name="xml-assembler-pipeline-component"></a><span data-ttu-id="c5eb9-102">XML 汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="c5eb9-102">XML Assembler Pipeline Component</span></span>
<span data-ttu-id="c5eb9-103">XML 组装器管道组件将 XML 序列化和组装合并到一个组件中。</span><span class="sxs-lookup"><span data-stu-id="c5eb9-103">The XML Assembler pipeline component combines XML serializing and assembling in one component.</span></span> <span data-ttu-id="c5eb9-104">其主要功能是将属性从消息上下文传输回信封和文档。</span><span class="sxs-lookup"><span data-stu-id="c5eb9-104">Its primary function is to transfer properties from the message context back into envelopes and documents.</span></span>  
  
 <span data-ttu-id="c5eb9-105">在接收一批消息形成交换后，在 XML 组装器组件中将会出现以下操作：</span><span class="sxs-lookup"><span data-stu-id="c5eb9-105">The following actions occur in the XML Assembler component after receiving a batch of messages to form an interchange:</span></span>  
  
1.  <span data-ttu-id="c5eb9-106">组装器通过使用指定的信封规范创建信封。</span><span class="sxs-lookup"><span data-stu-id="c5eb9-106">The assembler creates the envelope by using the specified envelope specification.</span></span>  
  
2.  <span data-ttu-id="c5eb9-107">该组件通过使用预定义的 XPath（编码为与消息相关联的 XSD 架构中的批注）将内容属性放入消息实例中。</span><span class="sxs-lookup"><span data-stu-id="c5eb9-107">The component puts the content properties on the message instances by using the predefined XPaths coded as annotations in the XSD schemas associated with the message.</span></span>  
  
3.  <span data-ttu-id="c5eb9-108">该组件将消息附加到信封。</span><span class="sxs-lookup"><span data-stu-id="c5eb9-108">The component appends the message to the envelope.</span></span>  
  
4.  <span data-ttu-id="c5eb9-109">该组件通过使用预定义的 XPath（编码为与信封相关联的 XSD 架构中的批注）将内容属性放入信封中。</span><span class="sxs-lookup"><span data-stu-id="c5eb9-109">The component puts the content properties on the envelope by using the predefined XPaths coded as annotations in the XSD schemas associated with envelopes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5eb9-110">XML 组装器管道组件不填充缺少的属性字段，但如果空元素字段为可选字段但不具有默认值或固定值，则将填充这些空元素字段。</span><span class="sxs-lookup"><span data-stu-id="c5eb9-110">The XML Assembler pipeline component does not populate missing attribute fields, but does populate empty element fields when the fields are optional but do not have default or fixed values.</span></span>  
  
 <span data-ttu-id="c5eb9-111">有关配置 XML 汇编程序管道组件的信息，请参阅[如何将 XML 汇编程序管道组件配置](../core/how-to-configure-the-xml-assembler-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="c5eb9-111">For information about configuring the XML Assembler pipeline component, see [How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c5eb9-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="c5eb9-112">In This Section</span></span>  
  
-   [<span data-ttu-id="c5eb9-113">XML 汇编程序管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="c5eb9-113">Character Encoding in the XML Assembler Pipeline Component</span></span>](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="c5eb9-114">处理 XML 汇编程序管道组件中的说明</span><span class="sxs-lookup"><span data-stu-id="c5eb9-114">Processing Instructions in the XML Assembler Pipeline Component</span></span>](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="c5eb9-115">无法识别的消息中 XML 汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="c5eb9-115">Unrecognized Messages in the XML Assembler Pipeline Component</span></span>](../core/unrecognized-messages-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="c5eb9-116">XML 信息集 XML 汇编程序管道组件中的元素</span><span class="sxs-lookup"><span data-stu-id="c5eb9-116">XML Information Set Elements in the XML Assembler Pipeline Component</span></span>](../core/xml-information-set-elements-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="c5eb9-117">XML 汇编程序管道组件中的文档结构强制</span><span class="sxs-lookup"><span data-stu-id="c5eb9-117">Document Structure Enforcement in the XML Assembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-xml-assembler-pipeline-component.md)