---
title: 对目标 URL 属性的限制 |Microsoft Docs
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98220fbc5ec99780d230c46751b903cf34167d8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254873"
---
# <a name="restrictions-on-the-destination-url-property"></a>对目标 URL 属性的限制
目标 URL 是一个字符串，指定你想要使用 HTTP 协议发送消息的 HTTP 服务器的地址。  
  
 目标 URL 属性适用以下规则和限制：  
  
-   始终必须采用以下格式指定目标 URL 属性：  
  
     http[s]://\<host\>[:\<port\>][/\<path\>[/\<file\>[?\<query-string\>]]]  
  
-   整个字符串可能会或可能不采用 URI 编码。  
  
-   整个字符串，除了查询字符串中，不能包含任何以下字符： \< \> : \ &#124; "？ *.  
  
-   该属性不区分大小写。  
  
-   字符串的长度不得超过 256 个字符。  
  
## <a name="see-also"></a>请参阅  
 [配置 HTTP 发送端口](../core/configuring-an-http-send-port.md)