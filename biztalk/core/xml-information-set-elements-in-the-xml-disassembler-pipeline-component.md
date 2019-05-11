---
title: XML 拆装器管道组件中的 XML 信息集合元素 |Microsoft Docs
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
ms.openlocfilehash: 2b9d2b581a327f8d7009794338d431a2358db748
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298480"
---
# <a name="xml-information-set-elements-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="afa04-102">XML 拆装器管道组件中的 XML 信息集合元素</span><span class="sxs-lookup"><span data-stu-id="afa04-102">XML Information Set Elements in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="afa04-103">XML 拆装器处理 XML 信息集合元素，如下所示。</span><span class="sxs-lookup"><span data-stu-id="afa04-103">The XML Disassembler handles XML information set elements as follows.</span></span>  
  
|<span data-ttu-id="afa04-104">元素</span><span class="sxs-lookup"><span data-stu-id="afa04-104">Element</span></span>|<span data-ttu-id="afa04-105">Description</span><span class="sxs-lookup"><span data-stu-id="afa04-105">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="afa04-106">comment</span><span class="sxs-lookup"><span data-stu-id="afa04-106">comment</span></span>|<span data-ttu-id="afa04-107">注释保留在文档;但是，不会保留 XML 信封中的任何注释。</span><span class="sxs-lookup"><span data-stu-id="afa04-107">Comments are preserved in the document; however, any comments in XML envelopes are not preserved.</span></span>|  
|<span data-ttu-id="afa04-108">CDATA</span><span class="sxs-lookup"><span data-stu-id="afa04-108">CDATA</span></span>|<span data-ttu-id="afa04-109">CDATA 保留在文档中。</span><span class="sxs-lookup"><span data-stu-id="afa04-109">CDATA is preserved in the document.</span></span> <span data-ttu-id="afa04-110">不保留显示在文档 （例如，在一个信封） 外部的 CDATA 元素。</span><span class="sxs-lookup"><span data-stu-id="afa04-110">CDATA elements appearing outside of a document (for example, in an envelope) are not preserved.</span></span>|  
|<span data-ttu-id="afa04-111">处理指令</span><span class="sxs-lookup"><span data-stu-id="afa04-111">processing instructions</span></span>|<span data-ttu-id="afa04-112">XML 拆装器保留显示中或之前的 XML 文档的处理指令。</span><span class="sxs-lookup"><span data-stu-id="afa04-112">The XML Disassembler preserves processing instructions appearing in or before an XML document.</span></span> <span data-ttu-id="afa04-113">不保留处理指令，使其不显示在 XML 文档或之前或之后信封。</span><span class="sxs-lookup"><span data-stu-id="afa04-113">Processing instructions appearing after an XML document or before or after an envelope are not preserved.</span></span>|  
|<span data-ttu-id="afa04-114">XML 声明</span><span class="sxs-lookup"><span data-stu-id="afa04-114">XML declaration</span></span>|<span data-ttu-id="afa04-115">删除所有传入 XML 消息的 XML 声明元素。</span><span class="sxs-lookup"><span data-stu-id="afa04-115">The XML declaration element of any incoming XML message is removed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="afa04-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="afa04-116">See Also</span></span>  
 <span data-ttu-id="afa04-117">[XML 拆装器管道组件](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="afa04-117">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="afa04-118">如何配置 XML 拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="afa04-118">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)