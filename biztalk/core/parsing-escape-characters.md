---
title: 分析转义字符 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- pipeline components [custom], escape characters
- pipeline components [custom], parsing
ms.assetid: 2b33f436-3c29-4ff5-8dfa-26d6591713bc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f200e7c68a43360dc9edbae42ebea196b884f577
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971971"
---
# <a name="parsing-escape-characters"></a><span data-ttu-id="d6238-102">分析转义字符</span><span class="sxs-lookup"><span data-stu-id="d6238-102">Parsing Escape Characters</span></span>
<span data-ttu-id="d6238-103">当解析程序遇到了作为常规字符（即，不是分隔符或其他特殊字符的字符）前缀的转义符时，将忽略该转义符。</span><span class="sxs-lookup"><span data-stu-id="d6238-103">When the parser encounters an escape character that prefixes a regular character (that is, one that is not a delimiter or other special character), the escape character is ignored.</span></span> <span data-ttu-id="d6238-104">例如，给定的字符串"abc\d"位置"\\"转义符，输出是"abcd"。</span><span class="sxs-lookup"><span data-stu-id="d6238-104">For example, given a string "abc\d" where "\\" is the escape character, the output is "abcd".</span></span>  
  
 <span data-ttu-id="d6238-105">如果分析器在遇到双重转义字符 (例如，"abc\\\d")，输出包括一个转义字符 ("abc\d")。</span><span class="sxs-lookup"><span data-stu-id="d6238-105">If the parser encounters a double escape character (for example, "abc\\\d"), the output includes a single escape character ("abc\d").</span></span>  
  
 <span data-ttu-id="d6238-106">如果分析器在遇到三个转义字符 (例如，abc\\\\\d)，输出将是"abc\d"，因为第一个的两个转义字符解析为"\\"第三个转义字符将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d6238-106">If the parser encounters three escape characters (for example, abc\\\\\d), the output is "abc\d" because the first two escape characters are parsed to "\\" and the third escape character is ignored.</span></span>  
  
 <span data-ttu-id="d6238-107">分析程序会将位置错误的分隔符视为常规字符。</span><span class="sxs-lookup"><span data-stu-id="d6238-107">The parser treats misplaced delimiters as regular characters.</span></span> <span data-ttu-id="d6238-108">例如，如果收到"记录，Field1，字段中，2"时，输出 XML 将是\<Field1\> \<字段，2\>。</span><span class="sxs-lookup"><span data-stu-id="d6238-108">For example, if "Record, Field1, Field,2" is received, the output XML is \<Field1\> \<Field,2\>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6238-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6238-109">See Also</span></span>  
 [<span data-ttu-id="d6238-110">使用平面文件解析引擎</span><span class="sxs-lookup"><span data-stu-id="d6238-110">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)