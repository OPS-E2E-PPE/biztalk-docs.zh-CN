---
title: "X12 EDI 字符集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76e7b327-b0bd-4f16-8bfe-6c0184059f2b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46bcf25317d38846c6376b1fa25572b926c92992
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="x12-edi-character-set"></a>X12 EDI 字符集
在使用 Ñ 字符或抑音符 （'），指定以下项：  
  
||字符集|  
|-|-------------------|  
|仅 Ñ EDI 文档中的字符|使用扩展字符集|  
|仅 EDI 文档中的重读符号 (`)|使用 UTF8 字符集|  
|Ñ 字符**和**抑音符 （'） 在同一文档中：|-入站的文档必须具有 UTF8 编码<br />-使用 UTF8 字符集|  
  
 以下链接提供了有关 EDI 字符集的详细信息：  
  
 [EDI 字符集](http://go.microsoft.com/fwlink/p/?LinkId=271249)  
  
 [EDI 字符集支持](http://go.microsoft.com/fwlink/p/?LinkId=271250)