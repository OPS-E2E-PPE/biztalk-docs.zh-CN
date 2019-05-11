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
# <a name="parsing-escape-characters"></a>解析转义字符
当分析器遇到常规字符 （即，一个不是分隔符或其他特殊字符） 前缀的转义字符时，将忽略转义符。 例如，给定的字符串"abc\d"其中"\\"转义符，输出为"abcd"。  
  
 如果分析程序遇到了双转义符 (例如，"abc\\\d")，输出包括单个转义符 ("abc\d")。  
  
 如果分析程序遇到三个转义符 (例如，abc\\\\\d)，输出将是"abc\d"，因为第一个的两个转义符将被解析到"\\"第三个转义符将被忽略。  
  
 分析器将位置错误的分隔符视为常规字符。 例如，如果收到"Record，Field1，Field，2"，则输出 XML 是\<Field1\> \<Field，2\>。  
  
## <a name="see-also"></a>请参阅  
 [使用平面文件解析引擎](../core/using-the-flat-file-parsing-engine.md)