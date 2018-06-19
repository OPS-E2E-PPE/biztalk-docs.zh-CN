---
title: XML 信息在 XML 反汇编程序管道组件中设置元素 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], information set
- XML Disassembler [pipeline component], processing instructions
- pipeline components, XML Disassembler
ms.assetid: cc82344c-6c4b-4154-a662-0b7ae5caad30
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90b3140cbe23637160aafabdccb37104efd1d318
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289293"
---
# <a name="xml-information-set-elements-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="59f79-102">XML 信息集 XML 反汇编程序管道组件中的元素</span><span class="sxs-lookup"><span data-stu-id="59f79-102">XML Information Set Elements in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="59f79-103">XML 拆装器按如下方式处理 XML 信息集合元素：</span><span class="sxs-lookup"><span data-stu-id="59f79-103">The XML Disassembler handles XML information set elements as follows.</span></span>  
  
|<span data-ttu-id="59f79-104">元素</span><span class="sxs-lookup"><span data-stu-id="59f79-104">Element</span></span>|<span data-ttu-id="59f79-105">Description</span><span class="sxs-lookup"><span data-stu-id="59f79-105">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59f79-106">comment</span><span class="sxs-lookup"><span data-stu-id="59f79-106">comment</span></span>|<span data-ttu-id="59f79-107">注释保留在文档中；但不保留 XML 信封中的任何注释。</span><span class="sxs-lookup"><span data-stu-id="59f79-107">Comments are preserved in the document; however, any comments in XML envelopes are not preserved.</span></span>|  
|<span data-ttu-id="59f79-108">CDATA</span><span class="sxs-lookup"><span data-stu-id="59f79-108">CDATA</span></span>|<span data-ttu-id="59f79-109">CDATA 保留在文档中。</span><span class="sxs-lookup"><span data-stu-id="59f79-109">CDATA is preserved in the document.</span></span> <span data-ttu-id="59f79-110">但不保留显示在文档外部（如信封中）的 CDATA 元素。</span><span class="sxs-lookup"><span data-stu-id="59f79-110">CDATA elements appearing outside of a document (for example, in an envelope) are not preserved.</span></span>|  
|<span data-ttu-id="59f79-111">处理指令</span><span class="sxs-lookup"><span data-stu-id="59f79-111">processing instructions</span></span>|<span data-ttu-id="59f79-112">XML 拆装器保留显示在 XML 文档中或 XML 文档之前的处理指令。</span><span class="sxs-lookup"><span data-stu-id="59f79-112">The XML Disassembler preserves processing instructions appearing in or before an XML document.</span></span> <span data-ttu-id="59f79-113">不保留显示在 XML 文档之后或信封前后的处理指令。</span><span class="sxs-lookup"><span data-stu-id="59f79-113">Processing instructions appearing after an XML document or before or after an envelope are not preserved.</span></span>|  
|<span data-ttu-id="59f79-114">XML 声明</span><span class="sxs-lookup"><span data-stu-id="59f79-114">XML declaration</span></span>|<span data-ttu-id="59f79-115">删除所有传入 XML 消息的 XML 声明元素。</span><span class="sxs-lookup"><span data-stu-id="59f79-115">The XML declaration element of any incoming XML message is removed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59f79-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59f79-116">See Also</span></span>  
 <span data-ttu-id="59f79-117">[XML 反汇编程序管道组件](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="59f79-117">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="59f79-118">如何将 XML 反汇编程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="59f79-118">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)