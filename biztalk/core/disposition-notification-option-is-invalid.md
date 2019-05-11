---
title: 是无效的处置通知选项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1b807a8-eec9-45a5-83cc-075c91b4bc9e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8956b6ef3dd583522bb142e646920d4731651391
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350999"
---
# <a name="disposition-notification-option-is-invalid"></a>处理设置通知选项无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |              处理设置通知选项值:"{0}"无效。 {1}              |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 AS2 接收管道无法生成 MDN，因为处理设置通知选项标头无效。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保在 AS2 消息处置通知选项标头符合 RFC 4130 中描述的语法"基于 MIME 的安全对等业务数据交换使用 HTTP、 Applicability Statement 2 (AS2")。 请确保签名回执协议标头设置为"可选"或"pcks7-签名"和 Signed-receipt-micalg 的标头已设置为"可选"、"MD5"或"SHA1"。 （这两个这些标头包含处置通知选项标头中。）