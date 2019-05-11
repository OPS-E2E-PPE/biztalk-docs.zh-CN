---
title: 该节点名称字符进行编码 |Microsoft Docs
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
ms.openlocfilehash: 810476ccd640b33ecf5996bc351947a8bceb0ad4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394787"
---
# <a name="which-node-name-characters-get-encoded"></a><span data-ttu-id="bbd4c-102">节点名称字符进行编码</span><span class="sxs-lookup"><span data-stu-id="bbd4c-102">Which Node Name Characters Get Encoded</span></span>
<span data-ttu-id="bbd4c-103">XML 将置于可在 XML 名称，例如元素的名称，包括一些特殊限制 XML 名称的第一个字符的字符的一些限制。</span><span class="sxs-lookup"><span data-stu-id="bbd4c-103">XML places some restrictions on the characters that can be used in XML names, such as element names, including some special restrictions on the first character of an XML name.</span></span> <span data-ttu-id="bbd4c-104">确定允许哪些字符以及排除合法 XML 名称中使用哪些字符概念的目标是：</span><span class="sxs-lookup"><span data-stu-id="bbd4c-104">The conceptual goals in determining which characters to allow and which characters to exclude from legal XML names are:</span></span>  
  
- <span data-ttu-id="bbd4c-105">如果适用，是包含而非排除，以便新的文字系统可以以 Unicode 进行编码一样容纳。</span><span class="sxs-lookup"><span data-stu-id="bbd4c-105">Wherever applicable, be inclusive rather than exclusive, so that new writing systems can be accommodated as they are encoded in Unicode.</span></span>  
  
- <span data-ttu-id="bbd4c-106">排除可能或者用作分隔符的字符，以便 XML 名称可以更轻松地将显示在非 XML 分隔的上下文。</span><span class="sxs-lookup"><span data-stu-id="bbd4c-106">Exclude characters that may be or are used as delimiters, so that XML names can more easily appear in a non-XML, delimited context.</span></span>  
  
  <span data-ttu-id="bbd4c-107">下表显示了可以在 XML 名称中，在任何位置在名称中，或位于第一个以外的任何位置使用的字符。</span><span class="sxs-lookup"><span data-stu-id="bbd4c-107">The following table shows which characters can be used in an XML name, either in any position within the name, or in any position other than the first.</span></span> <span data-ttu-id="bbd4c-108">某些允许的字符不在名称中的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="bbd4c-108">Some allowable characters are excluded from being the first character in the name.</span></span> <span data-ttu-id="bbd4c-109">带引号的原义字符，并且范围显示在方括号内。</span><span class="sxs-lookup"><span data-stu-id="bbd4c-109">Literal characters are quoted, and ranges are shown within square brackets.</span></span>  
  
|<span data-ttu-id="bbd4c-110">名称中的位置</span><span class="sxs-lookup"><span data-stu-id="bbd4c-110">Position in name</span></span>|<span data-ttu-id="bbd4c-111">允许的字符</span><span class="sxs-lookup"><span data-stu-id="bbd4c-111">Allowed characters</span></span>|  
|----------------------|------------------------|  
|<span data-ttu-id="bbd4c-112">任何位置</span><span class="sxs-lookup"><span data-stu-id="bbd4c-112">Any position</span></span>|<span data-ttu-id="bbd4c-113">["A"-"Z"], ["a"-"z"], "_", [0x00C0-0x02FF], [0x0370-0x037D], [0x037F-0x1FFF], [0x200C-0x200D], [0x2070-0x218F], [0x2C00-0x2FEF], [0x3001-0xD7FF], [0xF900-0xEFFF]</span><span class="sxs-lookup"><span data-stu-id="bbd4c-113">["A"-"Z"], ["a"-"z"], "_", [0x00C0-0x02FF], [0x0370-0x037D], [0x037F-0x1FFF], [0x200C-0x200D], [0x2070-0x218F], [0x2C00-0x2FEF], [0x3001-0xD7FF], [0xF900-0xEFFF]</span></span>|  
|<span data-ttu-id="bbd4c-114">除第一个任何位置</span><span class="sxs-lookup"><span data-stu-id="bbd4c-114">Any position except first</span></span>|<span data-ttu-id="bbd4c-115">"-"，"。"，["0"-"9"]，0x00B7、 [0x0300-0x036F] [0x203F-0x2040]</span><span class="sxs-lookup"><span data-stu-id="bbd4c-115">"-", ".", ["0"-"9"], 0x00B7, [0x0300-0x036F], [0x203F-0x2040]</span></span>|  
  
 <span data-ttu-id="bbd4c-116">在英语中的元素或属性名称 （架构树视图中的节点名称） 的最佳做法可归纳如下：</span><span class="sxs-lookup"><span data-stu-id="bbd4c-116">Best practice in English for an element or attribute name (a node name in the schema tree view) can be summarized as:</span></span>  
  
-   <span data-ttu-id="bbd4c-117">使用字母数字字符，但不要以数字开头的名称。</span><span class="sxs-lookup"><span data-stu-id="bbd4c-117">Use alphanumeric characters, except do not begin a name with a numeral.</span></span>  
  
-   <span data-ttu-id="bbd4c-118">使用下划线 (_)、 连字符 （-）、 句点 （.） 和中间点 （配置）。</span><span class="sxs-lookup"><span data-stu-id="bbd4c-118">Use the underscore (_),hyphen (-), period (.), and middle dot (·).</span></span>  
  
-   <span data-ttu-id="bbd4c-119">不要使用空格。</span><span class="sxs-lookup"><span data-stu-id="bbd4c-119">Do not use white space.</span></span>  
  
-   <span data-ttu-id="bbd4c-120">自然语言中使用有意义的词或词组。</span><span class="sxs-lookup"><span data-stu-id="bbd4c-120">Use meaningful words or combinations of words in natural languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbd4c-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbd4c-121">See Also</span></span>  
 <span data-ttu-id="bbd4c-122">[节点名称属性](../core/node-name-property.md) </span><span class="sxs-lookup"><span data-stu-id="bbd4c-122">[Node Name Property](../core/node-name-property.md) </span></span>  
 [<span data-ttu-id="bbd4c-123">如何对节点名称字符进行编码</span><span class="sxs-lookup"><span data-stu-id="bbd4c-123">How Node Name Characters Get Encoded</span></span>](../core/how-node-name-characters-get-encoded.md)