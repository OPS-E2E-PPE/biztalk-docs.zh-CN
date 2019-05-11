---
title: 配置错误。 在单向 HTTP 上请求了同步 MDN 接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f140c7a4-46bf-4557-9679-cdaf2fbe66f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5bdd3f27fa8a4abe5cb9f2ff16310a6e0e85f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356522"
---
# <a name="configuration-error-synchronous-mdn-requested-on-a-one-way-http-receive-port"></a>配置错误。 在单向 HTTP 上请求了同步 MDN 接收端口
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |       配置错误。 在单向 HTTP 发送端口上请求了同步 MDN。        |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法后收到的 AS2 消息，因为 HTTP 接收处理传入的 AS2 消息的端口是单向端口返回同步 MDN。 双向请求-响应接收端口返回同步 MDN 以响应传入的 AS2 消息所需。 在这种情况下，必须同步返回 MDN，因为 AS2 消息包含的处置通知的标题，或作为 AS2 消息发送方，重写已签入站的消息属性的属性，生成的参与方的配置中MDN 属性被选中，并且传输 MDN 以异步方式属性为清除。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请更改接收端口接收 AS2 消息是请求响应接收端口，而不是一个单向接收端口。 设置发送管道的请求响应接收位置设置为非 EDI 交换的 EDI 交换的或 AS2Send 为 AS2EdiSend。