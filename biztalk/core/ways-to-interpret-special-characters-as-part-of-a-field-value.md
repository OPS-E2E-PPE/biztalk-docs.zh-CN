---
title: 如何解释的特殊字符作为字段值的一部分 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e19a202-4e4d-42e0-ba1e-fddc52792b21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b96a3c7502a47541e8e58ec3df3eccf6098e3abc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288381"
---
# <a name="ways-to-interpret-special-characters-as-part-of-a-field-value"></a><span data-ttu-id="221ae-102">如何解释的特殊字符作为字段值的一部分</span><span class="sxs-lookup"><span data-stu-id="221ae-102">Ways to Interpret Special Characters as Part of a Field Value</span></span>
<span data-ttu-id="221ae-103">位置记录和分隔记录中的字段均可包含不同类型的特殊字符，例如，填充字符、环绕符和转义符。</span><span class="sxs-lookup"><span data-stu-id="221ae-103">Fields in both positional and delimited records can contain special characters of different types, such as pad, wrap, and escape characters.</span></span> <span data-ttu-id="221ae-104">分隔记录还可以包含一个或多个不同的分隔符，这些字符用于将记录中的各字段分开以及分隔记录。</span><span class="sxs-lookup"><span data-stu-id="221ae-104">Delimited records can also contain one or more different delimiter characters that are used to separate the fields within a record and one record from another record.</span></span> <span data-ttu-id="221ae-105">有时，这些特殊字符是数据自身的一部分，在这种情况下，不应将其作为特殊字符进行解释。</span><span class="sxs-lookup"><span data-stu-id="221ae-105">Sometimes these special characters are part of the data itself, and are not meant to be interpreted as special in those cases.</span></span>  
  
 <span data-ttu-id="221ae-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 所使用的平面文件架构支持两种不同的技术，用于将原本是特殊字符的出现标记为字段所包含数据的简单部分。</span><span class="sxs-lookup"><span data-stu-id="221ae-106">The flat file schemas used by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] support two different techniques for flagging occurrences of otherwise special characters as simply part of the data contained by a field.</span></span> <span data-ttu-id="221ae-107">这两种技术分别使用了转义符和环绕符。</span><span class="sxs-lookup"><span data-stu-id="221ae-107">These two techniques employ escape characters and wrap characters, respectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="221ae-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="221ae-108">In This Section</span></span>  
  
-   [<span data-ttu-id="221ae-109">转义字符</span><span class="sxs-lookup"><span data-stu-id="221ae-109">Escape Characters</span></span>](../core/escape-characters.md)  
  
-   [<span data-ttu-id="221ae-110">自动换行字符</span><span class="sxs-lookup"><span data-stu-id="221ae-110">Wrap Characters</span></span>](../core/wrap-characters.md)