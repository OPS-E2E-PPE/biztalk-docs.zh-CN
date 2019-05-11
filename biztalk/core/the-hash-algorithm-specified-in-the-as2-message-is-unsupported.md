---
title: 不支持 AS2 消息中指定的哈希算法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b292238-f964-4275-bbfa-e21c9150abf7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8ac08333b5506e342fe84a2e7a950610bcdd1b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258617"
---
# <a name="the-hash-algorithm-specified-in-the-as2-message-is-unsupported"></a>不支持 AS2 消息中指定的哈希算法
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                            UnsupportedAS2HashAlgorithmError                            |
|  消息正文   |            不支持在 AS2 消息中指定的哈希算法。             |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法生成指定的 MDN，因为所收到 AS2 消息的 signed-receipt-micalg 标头中指定的 MIC 哈希算法具有无效的值。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让消息的发送方将算法更改为 MD5 或 SHA1 并再次发送消息。