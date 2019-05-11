---
title: XML 拆装器管道组件中的字符编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], character encoding
- XMLNorm.SourceCharset property
ms.assetid: 37962bdc-cbcb-4559-9ae8-6c4be49b4822
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d299ac6a1261160cbd3844c3f0201e55affa5655
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391668"
---
# <a name="character-encoding-in-xml-disassembler-pipeline-component"></a><span data-ttu-id="29e06-102">XML 拆装器管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="29e06-102">Character Encoding in XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="29e06-103">XML 拆装器使用以下算法来确定要用于处理传入消息使用的编码：</span><span class="sxs-lookup"><span data-stu-id="29e06-103">The XML Disassembler uses the following algorithm to determine which encoding to use for processing incoming messages:</span></span>  
  
1. <span data-ttu-id="29e06-104">如果数据中存在字节顺序标记，它从确定编码信息。</span><span class="sxs-lookup"><span data-stu-id="29e06-104">If a byte order mark exists in the data, encoding information is determined from it.</span></span>  
  
2. <span data-ttu-id="29e06-105">否则为如果**IBaseMessagePart.Charset**属性设置，则使用指定的编码。</span><span class="sxs-lookup"><span data-stu-id="29e06-105">Otherwise, if the **IBaseMessagePart.Charset** property is set, the encoding specified there is used.</span></span>  
  
3. <span data-ttu-id="29e06-106">或者如果 XML 文档中存在 XML 声明，则指定的编码则使用，提供的 XML 声明为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="29e06-106">Otherwise if the XML declaration is present in the XML document, the encoding specified there is used, provided the XML declaration is ANSI.</span></span>  
  
4. <span data-ttu-id="29e06-107">否则，使用 utf-8 编码。</span><span class="sxs-lookup"><span data-stu-id="29e06-107">Otherwise, UTF-8 encoding is used.</span></span>  
  
   <span data-ttu-id="29e06-108">对于上述情况下，2、 3 和 4 中，XML 拆装器将确定编码后，它将其保存的消息上下文中**XMLNorm.SourceCharset**属性。</span><span class="sxs-lookup"><span data-stu-id="29e06-108">For the preceding cases 2, 3, and 4, after the XML Disassembler determines the encoding, it saves it on the message context in **XMLNorm.SourceCharset** property.</span></span> <span data-ttu-id="29e06-109">消息始终由 XML 拆装器管道组件使用 utf-8 编码。</span><span class="sxs-lookup"><span data-stu-id="29e06-109">Messages produced by the XML Disassembler pipeline component always use UTF-8 encoding.</span></span> <span data-ttu-id="29e06-110">针对情况 1，不保留从字节顺序标记确定的编码。</span><span class="sxs-lookup"><span data-stu-id="29e06-110">For case 1, encoding determined from the byte order mark is not preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e06-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="29e06-111">See Also</span></span>  
 <span data-ttu-id="29e06-112">[XML 拆装器管道组件](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="29e06-112">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="29e06-113">如何配置 XML 拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="29e06-113">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)