---
title: X12 EDI 字符集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76e7b327-b0bd-4f16-8bfe-6c0184059f2b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6fb92d0b8a20e9ca4e1a71aead55af21b1daeea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394785"
---
# <a name="x12-edi-character-set"></a>X12 EDI 字符集
使用 Ñ 字符或重读符号 （'） 时，指定以下项：  


|                                                                   |                                  字符集                                   |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------|
|             仅 Ñ EDI 文档中的字符              |                            使用扩展的字符集                            |
|           抑音符 (\`) 中的 EDI 文档 |                             使用 UTF8 字符集                              |
| Ñ 字符**并**抑音符 (\`) 在同一文档中: | 的入站的文档必须具有 UTF8 编码<br />-使用 UTF8 字符集 |

 以下链接提供了有关 EDI 字符集的详细信息：  

 [EDI 字符集](http://go.microsoft.com/fwlink/p/?LinkId=271249)  

 [EDI 字符集支持](http://go.microsoft.com/fwlink/p/?LinkId=271250)