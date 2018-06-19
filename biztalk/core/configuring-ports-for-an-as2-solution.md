---
title: 配置端口以便为 AS2 解决方案 |Microsoft 文档
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
ms.openlocfilehash: f8f02c5de0edd7956f00e10ce8782e4865033076
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233581"
---
# <a name="configuring-ports-for-an-as2-solution"></a>为 AS2 解决方案配置端口
可以使用以下接收和发送端口传送 AS2 上的 EDI 和非 EDI 消息：  
  
 **接收端口**  
  
|若要接收|发送|端口类型|  
|----------------|-------------|------------------|  
|EDI 或非 EDI 消息或确认|MDN 响应（如果处于同步模式）或 HTTP 响应（如果处于异步模式）|双向请求-响应 HTTP 接收端口|  
|MDN 响应|-|单向 HTTP 接收端口|  
  
 **发送端口**  
  
|发送|若要接收|端口类型|  
|-------------|----------------|------------------|  
|EDI 或非 EDI 消息或确认<br /><br /> （基于协议的路由）|-|静态单向 HTTP 发送端口|  
|EDI 或非 EDI 消息或确认<br /><br /> （基于内容的路由）|MDN 响应|动态双向要求-响应 HTTP 发送端口|  
|EDI 或非 EDI 消息或确认<br /><br /> （基于内容的路由）|-|动态单向 HTTP 发送端口|  
|异步 MDN 响应<br /><br /> （基于内容的路由）|-|动态单向发送端口|  
|异步 MDN 响应|-|静态单向发送端口|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置通过 AS2 消息接收端口](../core/configuring-a-receive-port-for-messages-over-as2.md)  
  
-   [配置传入 Mdn 的接收端口](../core/configuring-a-receive-port-for-incoming-mdns.md)  
  
-   [通过 AS2 消息配置静态发送端口](../core/configuring-a-static-send-port-for-messages-over-as2.md)  
  
-   [通过 AS2 消息配置动态发送端口](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)  
  
-   [通过 AS2 异步 Mdn 的配置静态发送端口](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)  
  
-   [通过 AS2 异步 Mdn 的配置动态发送端口](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)  
  
## <a name="see-also"></a>另请参阅  
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)