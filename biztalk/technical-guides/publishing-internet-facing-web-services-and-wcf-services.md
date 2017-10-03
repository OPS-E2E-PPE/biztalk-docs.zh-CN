---
title: "发布的面向 Internet 的 Web 服务和 WCF 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7553608-f57a-470e-91d4-75504b3fd52b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38ee916aaa5e158160f2096b0ba9b2678dd6b8d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-internet-facing-web-services-and-wcf-services"></a>发布的面向 Internet 的 Web 服务和 WCF 服务
可将多个方法用于发布[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务和 WCF 服务添加到 Internet:  
  
-   在外围网络 （也称为 DMZ、 外围安全区域和外围子网） 中使用反向代理规则。  
  
-   将运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，发布到外围网络域的 Web 服务或 WCF 服务。  
  
-   使用[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]云启用程序功能，以将 Web 服务或 WCF 服务发布为 Azure AppFabric Service Bus 中继终结点。  
  
## <a name="using-a-reverse-proxy"></a>使用反向代理  
 这已发布的传统方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务和 WCF 服务。 外围网络中使用反向代理规则了需要具有位于外围网络中的 BizTalk server。 反向代理规则只需 HTTP 和 SOAP 请求转发从外围网络到运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]intranet 域中。  
  
 有关使用反向代理的详细信息，请参阅中的以下主题[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]帮助：  
  
-   ["示例体系结构： HTTP 和 SOAP 适配器"](http://go.microsoft.com/fwlink/?LinkId=153339) (http://go.microsoft.com/fwlink/?LinkId=153339)。  
  
-   ["示例 TMA: HTTP 和 SOAP 适配器"](http://go.microsoft.com/fwlink/?LinkId=153340) (http://go.microsoft.com/fwlink/?LinkId=153340)。  
  
-   ["大型分布式体系结构"](http://go.microsoft.com/fwlink/?LinkId=153341) (http://go.microsoft.com/fwlink/?LinkId=153341)。  
  
## <a name="using-computers-running-biztalk-server-in-the-perimeter-network"></a>使用在外围网络中运行 BizTalk Server 的计算机  
 这不是首选的方法，用于发布[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务或 WCF 服务添加到 Internet，因为它需要运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]位于外围网络。 但是，不在外围网络中可用的反向代理时，你可以使用此方法。  
  
 此方法需要单向信任关系的 intranet 域中进行登记的外围网络域 （但 intranet 域不信任外围网络域）。 IIS 应用程序池必须在"BizTalk 隔离主机用户"域组中的 intranet 域帐户下运行的 Web 服务或外围网络域中的 WCF 服务承载。 这使应用程序池所需的权限，以发布到消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库。  
  
 您必须在防火墙，以适应这打开特定端口。 有关所需的端口的详细信息，请参阅["端口接收和发送服务器的"](http://go.microsoft.com/fwlink/?LinkId=153342) (http://go.microsoft.com/fwlink/?LinkId=153342) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。  
  
## <a name="exposing-biztalk-applications-on-the-cloud-using-appfabric-connect-for-services"></a>公开为服务使用 AppFabric 连接在云上的 BizTalk 应用程序  
 请参阅文章[上使用适用于服务的 AppFabric 连接云中公开 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=204700)(http://go.microsoft.com/fwlink/?LinkID=204700) 有关的详细信息公开 BizTalk 应用程序作为云上的 WCF 服务。  
  
## <a name="see-also"></a>另请参阅  
 [规划发布 Web Services1](../technical-guides/planning-for-publishing-web-services1.md)