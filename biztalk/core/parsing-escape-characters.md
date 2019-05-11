---
title: 解析转义字符 |Microsoft Docs
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
ms.openlocfilehash: f16ddf0225c2b8ebaa1a934955a1a05f45f64ee0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395055"
---
# <a name="parsing-escape-characters"></a><span data-ttu-id="82f31-102">解析转义字符</span><span class="sxs-lookup"><span data-stu-id="82f31-102">Parsing Escape Characters</span></span>
<span data-ttu-id="82f31-103">当分析器遇到常规字符 （即，一个不是分隔符或其他特殊字符） 前缀的转义字符时，将忽略转义符。</span><span class="sxs-lookup"><span data-stu-id="82f31-103">When the parser encounters an escape character that prefixes a regular character (that is, one that is not a delimiter or other special character), the escape character is ignored.</span></span> <span data-ttu-id="82f31-104">例如，给定的字符串"abc\d"其中"\\"转义符，输出为"abcd"。</span><span class="sxs-lookup"><span data-stu-id="82f31-104">For example, given a string "abc\d" where "\\" is the escape character, the output is "abcd".</span></span>  
  
 <span data-ttu-id="82f31-105">如果分析程序遇到了双转义符 (例如，"abc\\\d")，输出包括单个转义符 ("abc\d")。</span><span class="sxs-lookup"><span data-stu-id="82f31-105">If the parser encounters a double escape character (for example, "abc\\\d"), the output includes a single escape character ("abc\d").</span></span>  
  
 <span data-ttu-id="82f31-106">如果分析程序遇到三个转义符 (例如，abc\\\\\d)，输出将是"abc\d"，因为第一个的两个转义符将被解析到"\\"第三个转义符将被忽略。</span><span class="sxs-lookup"><span data-stu-id="82f31-106">If the parser encounters three escape characters (for example, abc\\\\\d), the output is "abc\d" because the first two escape characters are parsed to "\\" and the third escape character is ignored.</span></span>  
  
 <span data-ttu-id="82f31-107">分析器将位置错误的分隔符视为常规字符。</span><span class="sxs-lookup"><span data-stu-id="82f31-107">The parser treats misplaced delimiters as regular characters.</span></span> <span data-ttu-id="82f31-108">例如，如果收到"Record，Field1，Field，2"，则输出 XML 是\<Field1\> \<Field，2\>。</span><span class="sxs-lookup"><span data-stu-id="82f31-108">For example, if "Record, Field1, Field,2" is received, the output XML is \<Field1\> \<Field,2\>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f31-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="82f31-109">See Also</span></span>  
 [<span data-ttu-id="82f31-110">使用平面文件解析引擎</span><span class="sxs-lookup"><span data-stu-id="82f31-110">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)