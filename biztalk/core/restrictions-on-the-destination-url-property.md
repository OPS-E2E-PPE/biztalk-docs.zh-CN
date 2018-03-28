---
title: 在目标 URL 属性上的限制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [HTTP adapters], restrictions
- HTTP adapters, restrictions
ms.assetid: 982a5122-e43d-4730-a8b9-ceb1ff88638c
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f7966fccca324a1453f0ea84e79cd7d9d3d55ad
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="restrictions-on-the-destination-url-property"></a>在目标 URL 属性上的限制
目标 URL 是指定要在其中使用 HTTP 协议发送消息的 HTTP 服务器地址的字符串。  
  
 目标 URL 属性适用以下规则和限制：  
  
-   必须始终采用以下格式指定目标 URL 属性：  
  
     http [s]://\<主机\>[:\<端口\>] [/\<路径\>[/\<文件\>[？\<查询字符串\>]]]  
  
-   整个字符串可以采用 URI 编码，也可不采用 URI 编码。  
  
-   整个字符串，除查询字符串中，不能包含任何以下字符： \< \> : \ &#124; "？ *.  
  
-   该属性不区分大小写。  
  
-   字符串的长度不得超过 256 个字符。  
  
## <a name="see-also"></a>另请参阅  
 [配置 HTTP 发送端口](../core/configuring-an-http-send-port.md)