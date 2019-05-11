---
title: 为 AS2 解决方案配置端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715358b1-4226-476b-b0de-2b91434aa24c
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b045a18893153d6c2982b7b6214b7eea6e1852fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390862"
---
# <a name="configuring-ports-for-an-as2-solution"></a>为 AS2 解决方案配置端口
您可以使用以下接收和发送端口通过 AS2 传输 EDI 和非 EDI 消息：  
  
 **接收端口**  
  
|若要接收|若要发送|端口类型|  
|----------------|-------------|------------------|  
|EDI 或非 EDI 消息或确认|MDN 响应 （如果处于同步模式） 或 HTTP 响应 （如果处于异步模式）|双向请求-响应 HTTP 接收端口|  
|MDN 响应|-|单向 HTTP 接收端口|  
  
 **发送端口**  
  
|若要发送|若要接收|端口类型|  
|-------------|----------------|------------------|  
|EDI 或非 EDI 消息或确认<br /><br /> （基于协议的路由）|-|静态单向 HTTP 发送端口|  
|EDI 或非 EDI 消息或确认<br /><br /> （基于内容的路由）|MDN 响应|动态双向要求-响应 HTTP 发送端口|  
|EDI 或非 EDI 消息或确认<br /><br /> （基于内容的路由）|-|动态单向 HTTP 发送端口|  
|异步 MDN 响应<br /><br /> （基于内容的路由）|-|动态单向发送端口|  
|异步 MDN 响应|-|静态单向发送端口|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置 AS2 消息的接收端口](../core/configuring-a-receive-port-for-messages-over-as2.md)  
  
-   [配置传入 MDN 的接收端口](../core/configuring-a-receive-port-for-incoming-mdns.md)  
  
-   [配置 AS2 消息的静态发送端口](../core/configuring-a-static-send-port-for-messages-over-as2.md)  
  
-   [配置 AS2 消息的动态发送端口](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)  
  
-   [配置用于通过 AS2 发送异步 MDN 的静态发送端口](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)  
  
-   [配置用于通过 AS2 发送异步 MDN 的动态发送端口](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)  
  
## <a name="see-also"></a>请参阅  
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)