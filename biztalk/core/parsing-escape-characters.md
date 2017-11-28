---
title: "分析转义字符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- pipeline components [custom], escape characters
- pipeline components [custom], parsing
ms.assetid: 2b33f436-3c29-4ff5-8dfa-26d6591713bc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50e65ccbe1a1197a3b85ec86a8ae9e11f25eaf61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="parsing-escape-characters"></a><span data-ttu-id="04a29-102">分析转义字符</span><span class="sxs-lookup"><span data-stu-id="04a29-102">Parsing Escape Characters</span></span>
<span data-ttu-id="04a29-103">当解析程序遇到了作为常规字符（即，不是分隔符或其他特殊字符的字符）前缀的转义符时，将忽略该转义符。</span><span class="sxs-lookup"><span data-stu-id="04a29-103">When the parser encounters an escape character that prefixes a regular character (that is, one that is not a delimiter or other special character), the escape character is ignored.</span></span> <span data-ttu-id="04a29-104">例如，给定的字符串"abc\d"位置"\\"转义符，输出是"abcd"。</span><span class="sxs-lookup"><span data-stu-id="04a29-104">For example, given a string "abc\d" where "\\" is the escape character, the output is "abcd".</span></span>  
  
 <span data-ttu-id="04a29-105">如果分析器在遇到双重转义字符 (例如，"abc\\\d")，输出包括一个转义字符 ("abc\d")。</span><span class="sxs-lookup"><span data-stu-id="04a29-105">If the parser encounters a double escape character (for example, "abc\\\d"), the output includes a single escape character ("abc\d").</span></span>  
  
 <span data-ttu-id="04a29-106">如果分析器在遇到三个转义字符 (例如，abc\\\\\d)，输出将是"abc\d"，因为第一个的两个转义字符解析为"\\"第三个转义字符将被忽略。</span><span class="sxs-lookup"><span data-stu-id="04a29-106">If the parser encounters three escape characters (for example, abc\\\\\d), the output is "abc\d" because the first two escape characters are parsed to "\\" and the third escape character is ignored.</span></span>  
  
 <span data-ttu-id="04a29-107">分析程序会将位置错误的分隔符视为常规字符。</span><span class="sxs-lookup"><span data-stu-id="04a29-107">The parser treats misplaced delimiters as regular characters.</span></span> <span data-ttu-id="04a29-108">例如，如果收到"记录，Field1，字段中，2"时，输出 XML 将是\<Field1 >\<字段，2 >。</span><span class="sxs-lookup"><span data-stu-id="04a29-108">For example, if "Record, Field1, Field,2" is received, the output XML is \<Field1> \<Field,2>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a29-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04a29-109">See Also</span></span>  
 [<span data-ttu-id="04a29-110">使用平面文件分析引擎</span><span class="sxs-lookup"><span data-stu-id="04a29-110">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)