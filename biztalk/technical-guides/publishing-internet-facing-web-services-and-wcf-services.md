---
title: 面向 Internet 的 Web 服务和 WCF 服务发布 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7553608-f57a-470e-91d4-75504b3fd52b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c16812fc99c6fa38ad55c7e69afb8b6bb256136c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399553"
---
# <a name="publishing-internet-facing-web-services-and-wcf-services"></a>发布面向 Internet 的 Web 服务和 WCF 服务
可以使用多种方法进行发布[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务和 WCF 服务添加到 Internet:  
  
- 外围网络 （也称为 DMZ、 外围安全区域和外围子网） 中使用反向代理规则。  
  
- 将运行计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，将 Web 服务或 WCF 服务发布到外围网络域。  
  
- 使用 BizTalk Server 云推动器功能将 Web 服务或 WCF 服务发布为 Azure AppFabric 服务总线中继终结点。  
  
## <a name="using-a-reverse-proxy"></a>使用反向代理  
 这一直是进行发布的传统方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务和 WCF 服务。 在外围网络中使用反向代理规则便无需使用 BizTalk server 将位于外围网络中。 反向代理规则只需将转发 HTTP 和 SOAP 请求从外围网络到运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]intranet 域中。  
  
 有关使用反向代理的详细信息，请参阅 BizTalk Server 帮助中的以下主题：  
  
-   ["示例体系结构：HTTP 和 SOAP 适配器"](http://go.microsoft.com/fwlink/?LinkId=153339) (http://go.microsoft.com/fwlink/?LinkId=153339)。  
  
-   ["示例 TMA:HTTP 和 SOAP 适配器"](http://go.microsoft.com/fwlink/?LinkId=153340) (http://go.microsoft.com/fwlink/?LinkId=153340)。  
  
-   ["大型分布式体系结构"](http://go.microsoft.com/fwlink/?LinkId=153341) (http://go.microsoft.com/fwlink/?LinkId=153341)。  
  
## <a name="using-computers-running-biztalk-server-in-the-perimeter-network"></a>使用外围网络中运行 BizTalk Server 的计算机  
 这不是首选的方法进行发布[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务或 WCF 服务添加到 Internet，因为它需要运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]位于外围网络中。 但是，不在外围网络中可用的反向代理时，您可以使用此方法。  
  
 此方法要求要在与 intranet 域之间的单向信任中登记的外围网络域 （但 intranet 域不信任的外围网络域）。 IIS 应用程序池的 Web 服务或外围网络域中的 WCF 服务必须在"BizTalk Isolated Host Users"域组中的 intranet 域帐户下运行该主机。 这使应用程序池所需的权限，才能发布消息到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库。  
  
 必须为解决此问题在防火墙中打开特定端口。 有关所需的端口的详细信息，请参阅["端口用于接收和发送服务器"](http://go.microsoft.com/fwlink/?LinkId=153342) (<http://go.microsoft.com/fwlink/?LinkId=153342>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。  
  
## <a name="exposing-biztalk-applications-on-the-cloud-using-appfabric-connect-for-services"></a>公开为服务使用 AppFabric 连接在云上的 BizTalk 应用程序  
 请参阅文章[BizTalk 应用程序公开为服务使用 AppFabric 连接在云中](http://go.microsoft.com/fwlink/?LinkID=204700)(http://go.microsoft.com/fwlink/?LinkID=204700)有关详细信息将 BizTalk 应用程序公开为 WCF 服务在云上。  
  
## <a name="see-also"></a>请参阅  
 [规划发布 Web Services1](../technical-guides/planning-for-publishing-web-services1.md)