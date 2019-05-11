---
title: 收到的 AS2 消息不包含 AS2-To 标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 343a9b41-fcd9-4508-ac65-9b6e05ec6496
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8bee1ee759a8aefb83aa3045808b6ce22689a6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359239"
---
# <a name="an-as2-message-was-received-that-did-not-contain-the-as2-to-header"></a>收到的 AS2 消息不包含 AS2-To 标头
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |           收到的 AS2 消息不包含 AS2-To 标头           |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法处理传入的 AS2 消息，因为该消息不包含指明消息源的 AS2-To 标头。 AS2 消息必须有 AS2-To 标头。 如果消息没有 AS2-To 标头，则会挂起该消息。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
-   确保在发送之前发送参与方向 AS2 消息的 HTTP、AS2 和 MIME 标头中添加 AS2-To 标头。