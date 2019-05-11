---
title: 消息类型不允许作为协议的一部分 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 829f8230-33b8-4b5f-a56a-d0c1d3a17271
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d5bb18ad9a46150b45d6994182ad18eb4fa564
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394539"
---
# <a name="message-type-is-not-allowed-as-part-of-the-agreement"></a>消息类型不允许作为协议的一部分
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                          TransactionSetNotAllowedDescription                           |
|  消息正文   |               消息类型{0}不允许作为协议的一部分。                |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 能够处理文档，因为该文档的消息类型不允许作为协议的一部分。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请查看允许和不允许作为协议的一部分的消息类型。