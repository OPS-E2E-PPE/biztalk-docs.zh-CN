---
title: 回执送达选项值无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eed306b-0912-4694-a55c-976128117c02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f69a1f396b6b788f3aee446b5feb501eb2f59e4f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398227"
---
# <a name="receipt-delivery-option-value-is-invalid"></a>回执送达选项值无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                           InvalidReceiptDeliveryOptionError                            |
|  消息正文   |                 回执送达选项值:"{0}"无效。  {1}                  |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明所接收 AS2 消息中的回执送达选项不是有效的 URL 和不符合 AS2 RFC 4130 中的规范。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请更改为包含有效的 URL 并符合 AS2 RFC 4130 第 7.3 节中的规范，然后重新发送 AS2 消息的 AS2 消息中具有回执送达选项。