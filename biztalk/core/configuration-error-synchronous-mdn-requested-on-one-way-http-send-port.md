---
title: 配置错误。 在单向 HTTP 上请求了同步 MDN 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bd38eb3-321f-4738-b35e-390f4f54673e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1e52f0d7107a09357af0b6ab35db15ad0a8514c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391529"
---
# <a name="configuration-error-synchronous-mdn-requested-on-one-way-http-send-port"></a>配置错误。 在单向 HTTP 上请求了同步 MDN 发送端口
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
 此错误/警告/信息事件表明在发送 AS2 消息后 BizTalk Server 无法接收同步 MDN，因为发送 AS2 消息的 HTTP 发送端口是单向端口。 处理为了响应端口发送的 AS2 消息而返回的同步 MDN，需要双向要求-响应发送端口。 这种情况下，必须同步返回 MDN，因为在 AS2 消息接收方的参与方的配置中，选中了“请求 MDN”属性，但清除了“请求异步 MDN”属性。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请将发送 AS2 消息的发送端口更改为静态要求-响应发送端口，而不是单向发送端口。 将要求-响应发送端口的接收管道设置为 AS2EdiReceive（针对 EDI 交换）或 AS2Receive（针对非 EDI 交换）。