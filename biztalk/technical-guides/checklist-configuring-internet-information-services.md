---
title: "清单： 配置 Internet Information Services |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 186f82c0-bd50-4c79-a403-8b0d91cc68d6
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24c2c0c97cb70dca268273d9ed5855f72372a2ca
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="checklist-configuring-internet-information-services"></a>清单： 配置 Internet Information Services
本主题列出了用于在生产中准备 Internet 信息服务 (IIS) 时应遵循的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
|步骤|参考|  
|-----------|---------------|  
|将 IIS 设置为发布[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务和 WCF 服务|-请参阅["启用 Web 服务"](http://go.microsoft.com/fwlink/?LinkId=153335) (http://go.microsoft.com/fwlink/?LinkId=153335) BizTalk Server 文档中。<br />-请参阅["配置 IIS 的独立 WCF 接收适配器"](http://go.microsoft.com/fwlink/?LinkId=202825)(http://go.microsoft.com/fwlink/?LinkId=202825) BizTalk Server 文档中。|  
|验证[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务和 WCF 服务正常工作。|-请参阅["测试已发布的 Web 服务"](http://go.microsoft.com/fwlink/?LinkId=153336) (http://go.microsoft.com/fwlink/?LinkId=153336) BizTalk Server 文档中。<br />-请参阅["如何创建.NET 应用程序到测试 WCF 服务发布与 BizTalk WCF 服务发布向导"](http://go.microsoft.com/fwlink/?LinkId=202830) (http://go.microsoft.com/fwlink/?LinkId=202830) BizTalk Server 文档中。|  
|锁定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务：<br /><br /> -关闭 web.config 或 machine.config 文件中的调试开关。<br />-配置以便仅允许的谓词的文章。|-请参阅 Microsoft 知识库文章 815145， ["HOW TO： 锁定 ASP.NET Web 应用程序或 Web 服务"](http://go.microsoft.com/fwlink/?LinkId=153337) (http://go.microsoft.com/fwlink/?LinkId=153337)。<br />-请参阅["ASP.NET 编辑规则对话框中"](http://go.microsoft.com/fwlink/?LinkID=64566) (http://go.microsoft.com/fwlink/?LinkID=64566) 中的.NET Framework 2.0 文档。|  
|配置负载平衡使用 NLB （或其他负载平衡器） 可负载分摊 BizTalk 服务器 Web 服务和 WCF 服务。|-   **对于 Windows Server 2008**： 请参阅["网络负载平衡部署指南"](http://go.microsoft.com/fwlink/?LinkId=153139) (http://go.microsoft.com/fwlink/?LinkId=153139)。<br />-   **对于 Windows Server 2003**： 请参阅["网络负载平衡： 配置 Windows 2000 和 Windows Server 2003 最佳做法"](http://go.microsoft.com/fwlink/?LinkID=69529) (http://go.microsoft.com/fwlink/?LinkID=69529)。|  
|更改 IIS 和 ASP.NET 设置，以优化 Web 服务。 **注意：** ASP.NET 2.0 包括自动优化，因此修改这些设置应不需要为 ASP.NET 2.0 Web 站点自动配置在何处启用网站的 web.config 文件\<processModel\>部分。 "autoConfig = true"是默认设置。|查看"ASP.NET 设置可能会影响 HTTP 或 SOAP 适配器性能"主题的部分["配置参数，影响适配器性能"](http://go.microsoft.com/fwlink/?LinkId=153338) (http://go.microsoft.com/fwlink/?LinkId=153338) BizTalk Server 文档中。|  
|实现一种方法来发布[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务和 WCF 服务。|-请参阅[发布的面向 Internet 的 Web 服务和 WCF 服务](../technical-guides/publishing-internet-facing-web-services-and-wcf-services.md)。<br />-请参阅["发布 WCF 服务"](http://go.microsoft.com/fwlink/?LinkId=202827) (http://go.microsoft.com/fwlink/?LinkId=202827) BizTalk Server 文档中。|  
|遵循有关优化 IIS 性能的最佳做法。|请参阅["排名靠前的 10 个方面与 IIS 性能泵"](http://go.microsoft.com/fwlink/?LinkId=109107) (http://go.microsoft.com/fwlink/?LinkId=109107)。|  
|按照编写为 IIS 的 web 应用程序的高性能的最佳做法。|请参阅["编写高性能的 10 个提示 Web 应用程序"](http://go.microsoft.com/fwlink/?LinkId=98290) (http://go.microsoft.com/fwlink/?LinkId=98290)。|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [发布面向 Internet 的 Web 服务和 WCF 服务](../technical-guides/publishing-internet-facing-web-services-and-wcf-services.md)