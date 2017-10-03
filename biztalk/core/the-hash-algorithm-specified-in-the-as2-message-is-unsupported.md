---
title: "AS2 消息中指定的哈希算法是不受支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b292238-f964-4275-bbfa-e21c9150abf7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6d16c7a3336a798c18b484bc50ff3e2f0c69764
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-hash-algorithm-specified-in-the-as2-message-is-unsupported"></a>不支持在 AS2 消息中指定的哈希算法
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|UnsupportedAS2HashAlgorithmError|  
|消息正文|不支持在 AS2 消息中指定的哈希算法。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法生成指定的 MDN，因为所收到 AS2 消息的 signed-receipt-micalg 标头中指定的 MIC 哈希算法具有无效的值。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让消息的发送方将算法更改为 MD5 或 SHA1 并再次发送消息。