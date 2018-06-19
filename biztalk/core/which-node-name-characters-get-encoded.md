---
title: 该节点名称字符获取编码 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a581d2-48fa-4c36-b5c2-fe87c328a7f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3895fd74ac63380d5502a05eed7c145e13bfd681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289181"
---
# <a name="which-node-name-characters-get-encoded"></a><span data-ttu-id="cd486-102">已编码的节点名称字符</span><span class="sxs-lookup"><span data-stu-id="cd486-102">Which Node Name Characters Get Encoded</span></span>
<span data-ttu-id="cd486-103">XML 对可用于 XML 名称（例如元素名称）的字符进行了限制，包括对 XML 名称的第一个字符的一些特殊限制。</span><span class="sxs-lookup"><span data-stu-id="cd486-103">XML places some restrictions on the characters that can be used in XML names, such as element names, including some special restrictions on the first character of an XML name.</span></span> <span data-ttu-id="cd486-104">确定在合法 XML 名称中允许使用哪些字符以及不允许使用哪些字符的概念目标为：</span><span class="sxs-lookup"><span data-stu-id="cd486-104">The conceptual goals in determining which characters to allow and which characters to exclude from legal XML names are:</span></span>  
  
-   <span data-ttu-id="cd486-105">如果适用，包含而非排除，这样可以容纳新的文字系统，就像以 Unicode 进行编码一样。</span><span class="sxs-lookup"><span data-stu-id="cd486-105">Wherever applicable, be inclusive rather than exclusive, so that new writing systems can be accommodated as they are encoded in Unicode.</span></span>  
  
-   <span data-ttu-id="cd486-106">排除可能是分隔符或者用作分隔符的字符，这样 XML 名称可以更容易地显示在非 XML 分隔的上下文中。</span><span class="sxs-lookup"><span data-stu-id="cd486-106">Exclude characters that may be or are used as delimiters, so that XML names can more easily appear in a non-XML, delimited context.</span></span>  
  
 <span data-ttu-id="cd486-107">下表显示了 XML 名称中可以使用的字符，可在名称中的任何位置使用，或者可在除第一个位置之外的任何位置使用。</span><span class="sxs-lookup"><span data-stu-id="cd486-107">The following table shows which characters can be used in an XML name, either in any position within the name, or in any position other than the first.</span></span> <span data-ttu-id="cd486-108">某些允许的字符不能作为名称的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="cd486-108">Some allowable characters are excluded from being the first character in the name.</span></span> <span data-ttu-id="cd486-109">文本字符带引号，范围显示在方括号中。</span><span class="sxs-lookup"><span data-stu-id="cd486-109">Literal characters are quoted, and ranges are shown within square brackets.</span></span>  
  
|<span data-ttu-id="cd486-110">名称中的位置</span><span class="sxs-lookup"><span data-stu-id="cd486-110">Position in name</span></span>|<span data-ttu-id="cd486-111">允许的字符</span><span class="sxs-lookup"><span data-stu-id="cd486-111">Allowed characters</span></span>|  
|----------------------|------------------------|  
|<span data-ttu-id="cd486-112">任何位置</span><span class="sxs-lookup"><span data-stu-id="cd486-112">Any position</span></span>|<span data-ttu-id="cd486-113">["A"-"Z"]、["a"-"z"]、"_"、[0x00C0-0x02FF]、[0x0370-0x037D]、[0x037F-0x1FFF]、[0x200C-0x200D]、[0x2070-0x218F]、[0x2C00-0x2FEF]、[0x3001-0xD7FF]、[0xF900-0xEFFF]</span><span class="sxs-lookup"><span data-stu-id="cd486-113">["A"-"Z"], ["a"-"z"], "_", [0x00C0-0x02FF], [0x0370-0x037D], [0x037F-0x1FFF], [0x200C-0x200D], [0x2070-0x218F], [0x2C00-0x2FEF], [0x3001-0xD7FF], [0xF900-0xEFFF]</span></span>|  
|<span data-ttu-id="cd486-114">除第一个位置之外的任何位置</span><span class="sxs-lookup"><span data-stu-id="cd486-114">Any position except first</span></span>|<span data-ttu-id="cd486-115">"-"、"."、["0"-"9"]、0x00B7、[0x0300-0x036F]、[0x203F-0x2040]</span><span class="sxs-lookup"><span data-stu-id="cd486-115">"-", ".", ["0"-"9"], 0x00B7, [0x0300-0x036F], [0x203F-0x2040]</span></span>|  
  
 <span data-ttu-id="cd486-116">元素或属性名称（架构树视图中的节点名称）以英文表示的最佳实践可概括为以下几点：</span><span class="sxs-lookup"><span data-stu-id="cd486-116">Best practice in English for an element or attribute name (a node name in the schema tree view) can be summarized as:</span></span>  
  
-   <span data-ttu-id="cd486-117">使用字母数字字符，但名称不要以数字开头。</span><span class="sxs-lookup"><span data-stu-id="cd486-117">Use alphanumeric characters, except do not begin a name with a numeral.</span></span>  
  
-   <span data-ttu-id="cd486-118">使用下划线 (_)、 连字符 （-）、 句点 （.） 和中间点 （·）。</span><span class="sxs-lookup"><span data-stu-id="cd486-118">Use the underscore (_),hyphen (-), period (.), and middle dot (·).</span></span>  
  
-   <span data-ttu-id="cd486-119">不要使用空格。</span><span class="sxs-lookup"><span data-stu-id="cd486-119">Do not use white space.</span></span>  
  
-   <span data-ttu-id="cd486-120">使用以自然语言表示的有意义单词或单词的组合。</span><span class="sxs-lookup"><span data-stu-id="cd486-120">Use meaningful words or combinations of words in natural languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd486-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd486-121">See Also</span></span>  
 <span data-ttu-id="cd486-122">[节点名称属性](../core/node-name-property.md) </span><span class="sxs-lookup"><span data-stu-id="cd486-122">[Node Name Property](../core/node-name-property.md) </span></span>  
 [<span data-ttu-id="cd486-123">节点名称字符获取编码方式</span><span class="sxs-lookup"><span data-stu-id="cd486-123">How Node Name Characters Get Encoded</span></span>](../core/how-node-name-characters-get-encoded.md)