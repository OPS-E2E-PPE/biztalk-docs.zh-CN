---
title: XML 组装器管道组件 |Microsoft Docs
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
ms.openlocfilehash: 7ed0d334539ae013a87d8caa293b55288e24becd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295603"
---
# <a name="xml-assembler-pipeline-component"></a><span data-ttu-id="bed97-102">XML 组装器管道组件</span><span class="sxs-lookup"><span data-stu-id="bed97-102">XML Assembler Pipeline Component</span></span>
<span data-ttu-id="bed97-103">XML 组装器管道组件将 XML 序列化和组装中有一个组件相结合。</span><span class="sxs-lookup"><span data-stu-id="bed97-103">The XML Assembler pipeline component combines XML serializing and assembling in one component.</span></span> <span data-ttu-id="bed97-104">其主要功能是将属性从消息上下文传输回信封和文档。</span><span class="sxs-lookup"><span data-stu-id="bed97-104">Its primary function is to transfer properties from the message context back into envelopes and documents.</span></span>  
  
 <span data-ttu-id="bed97-105">接收一批消息形成交换后，XML 组装器组件中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bed97-105">The following actions occur in the XML Assembler component after receiving a batch of messages to form an interchange:</span></span>  
  
1.  <span data-ttu-id="bed97-106">在组装器通过使用指定的信封规范创建信封。</span><span class="sxs-lookup"><span data-stu-id="bed97-106">The assembler creates the envelope by using the specified envelope specification.</span></span>  
  
2.  <span data-ttu-id="bed97-107">组件属性放入内容的消息实例通过使用预定义的 Xpath 编码为与消息关联的 XSD 架构中的批注。</span><span class="sxs-lookup"><span data-stu-id="bed97-107">The component puts the content properties on the message instances by using the predefined XPaths coded as annotations in the XSD schemas associated with the message.</span></span>  
  
3.  <span data-ttu-id="bed97-108">该组件将消息附加到信封中。</span><span class="sxs-lookup"><span data-stu-id="bed97-108">The component appends the message to the envelope.</span></span>  
  
4.  <span data-ttu-id="bed97-109">该组件通过使用预定义的 Xpath 编码为与信封相关联的 XSD 架构中的批注在信封上将内容属性。</span><span class="sxs-lookup"><span data-stu-id="bed97-109">The component puts the content properties on the envelope by using the predefined XPaths coded as annotations in the XSD schemas associated with envelopes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bed97-110">XML 组装器管道组件不会填充缺少的属性字段，但填充空元素字段时的字段是可选的但不是具有默认值或固定值。</span><span class="sxs-lookup"><span data-stu-id="bed97-110">The XML Assembler pipeline component does not populate missing attribute fields, but does populate empty element fields when the fields are optional but do not have default or fixed values.</span></span>  
  
 <span data-ttu-id="bed97-111">有关配置 XML 组装器管道组件的信息，请参阅[如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="bed97-111">For information about configuring the XML Assembler pipeline component, see [How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bed97-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="bed97-112">In This Section</span></span>  
  
-   [<span data-ttu-id="bed97-113">XML 汇编程序管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="bed97-113">Character Encoding in the XML Assembler Pipeline Component</span></span>](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="bed97-114">XML 汇编程序管道组件中的处理指令</span><span class="sxs-lookup"><span data-stu-id="bed97-114">Processing Instructions in the XML Assembler Pipeline Component</span></span>](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="bed97-115">XML 汇编程序管道组件中无法识别的消息</span><span class="sxs-lookup"><span data-stu-id="bed97-115">Unrecognized Messages in the XML Assembler Pipeline Component</span></span>](../core/unrecognized-messages-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="bed97-116">XML 汇编程序管道组件中的 XML 信息集元素</span><span class="sxs-lookup"><span data-stu-id="bed97-116">XML Information Set Elements in the XML Assembler Pipeline Component</span></span>](../core/xml-information-set-elements-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="bed97-117">XML 汇编程序管道组件中的文档结构强制规定</span><span class="sxs-lookup"><span data-stu-id="bed97-117">Document Structure Enforcement in the XML Assembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-xml-assembler-pipeline-component.md)