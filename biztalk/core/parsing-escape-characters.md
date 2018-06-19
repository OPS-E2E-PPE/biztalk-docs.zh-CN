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
# <a name="parsing-escape-characters"></a>分析转义字符
当解析程序遇到了作为常规字符（即，不是分隔符或其他特殊字符的字符）前缀的转义符时，将忽略该转义符。 例如，给定的字符串"abc\d"位置"\\"转义符，输出是"abcd"。  
  
 如果分析器在遇到双重转义字符 (例如，"abc\\\d")，输出包括一个转义字符 ("abc\d")。  
  
 如果分析器在遇到三个转义字符 (例如，abc\\\\\d)，输出将是"abc\d"，因为第一个的两个转义字符解析为"\\"第三个转义字符将被忽略。  
  
 分析程序会将位置错误的分隔符视为常规字符。 例如，如果收到"记录，Field1，字段中，2"时，输出 XML 将是\<Field1\> \<字段，2\>。  
  
## <a name="see-also"></a>另请参阅  
 [使用平面文件解析引擎](../core/using-the-flat-file-parsing-engine.md)