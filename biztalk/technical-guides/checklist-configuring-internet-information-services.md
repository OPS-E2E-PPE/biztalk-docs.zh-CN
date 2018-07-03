---
title: 清单： 配置 Internet Information Services |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 186f82c0-bd50-4c79-a403-8b0d91cc68d6
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c9cddbec30bb1dd7953ec30cfd9915e6d87a791
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007518"
---
# <a name="checklist-configuring-internet-information-services"></a>清单： 配置 Internet Information Services
本主题列出了准备在生产中使用的 Internet 信息服务 (IIS) 时应遵循的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  


|                                                                                                                                                     步骤                                                                                                                                                      |                                                                                                                                                                                                                        参考                                                                                                                                                                                                                        |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                     IIS 设置为发布[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务和 WCF 服务                                                                                     |                                   -请参阅["启用 Web 服务"](http://go.microsoft.com/fwlink/?LinkId=153335) (<http://go.microsoft.com/fwlink/?LinkId=153335>) 中的 BizTalk Server 文档。<br />-请参阅["配置 IIS 的独立 WCF 接收适配器"](http://go.microsoft.com/fwlink/?LinkId=202825)(<http://go.microsoft.com/fwlink/?LinkId=202825>) 中的 BizTalk Server 文档。                                   |
|                                                                              验证[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务和 WCF 服务正常工作。                                                                               | -请参阅["测试已发布的 Web 服务"](http://go.microsoft.com/fwlink/?LinkId=153336) (<http://go.microsoft.com/fwlink/?LinkId=153336>) 中的 BizTalk Server 文档。<br />-请参阅["如何为创建.NET 应用程序到测试 WCF 服务发布使用 BizTalk WCF 服务发布向导"](http://go.microsoft.com/fwlink/?LinkId=202830) (<http://go.microsoft.com/fwlink/?LinkId=202830>) 中的 BizTalk Server 文档。 |
|                            锁定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务：<br /><br /> -关闭 web.config 或 machine.config 文件中的调试开关。<br />-配置，以便发布的内容唯一允许的谓词。                            |                        -请参阅 Microsoft 知识库文章 815145， ["如何： 将 ASP.NET Web 应用程序锁定或 Web 服务"](http://go.microsoft.com/fwlink/?LinkId=153337) (<http://go.microsoft.com/fwlink/?LinkId=153337>)。<br />-请参阅["ASP.NET 编辑规则对话框"](http://go.microsoft.com/fwlink/?LinkID=64566) (<http://go.microsoft.com/fwlink/?LinkID=64566>).NET Framework 2.0 文档中。                         |
|                                                                                      配置负载平衡使用 NLB （或其他负载均衡器） 以在 BizTalk Server Web 服务和 WCF 服务之间平衡负载。                                                                                       |             -   **适用于 Windows Server 2008**： 请参阅["网络负载平衡部署指南"](http://go.microsoft.com/fwlink/?LinkId=153139) (<http://go.microsoft.com/fwlink/?LinkId=153139>)。<br />-   **适用于 Windows Server 2003**： 请参阅["网络负载平衡： 配置 Windows 2000 和 Windows Server 2003 最佳做法"](http://go.microsoft.com/fwlink/?LinkID=69529) (<http://go.microsoft.com/fwlink/?LinkID=69529>)。              |
| 更改优化 Web 服务的 IIS 和 ASP.NET 的设置。 **注意：** ASP.NET 2.0 包括自动优化，因此修改这些设置应不必需的自动配置中的启用了 ASP.NET 2.0 网站的 web.config 文件\<processModel\>部分。 "autoConfig = true"是默认设置。 |                                                                         查看的"ASP.NET 设置，可能会影响 HTTP 或 SOAP 适配器的性能"部分中的主题["配置参数的影响适配器性能"](http://go.microsoft.com/fwlink/?LinkId=153338) (<http://go.microsoft.com/fwlink/?LinkId=153338>) 中的 BizTalk Server 文档。                                                                          |
|                                                                             实现一种方法来发布[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务和 WCF 服务。                                                                             |                                                           -请参阅[面向 Internet 的 Web 服务和 WCF 服务发布](../technical-guides/publishing-internet-facing-web-services-and-wcf-services.md)。<br />-请参阅["发布 WCF 服务"](http://go.microsoft.com/fwlink/?LinkId=202827) (<http://go.microsoft.com/fwlink/?LinkId=202827>) 中的 BizTalk Server 文档。                                                           |
|                                                                                                                             遵循有关优化 IIS 性能的最佳做法。                                                                                                                              |                                                                                                                                                    请参阅["Top 10 方法抽取 IIS 性能"](http://go.microsoft.com/fwlink/?LinkId=109107) (<http://go.microsoft.com/fwlink/?LinkId=109107>)。                                                                                                                                                    |
|                                                                                                                  请按照编写的 IIS web 应用程序的高性能的最佳做法。                                                                                                                  |                                                                                                                                              请参阅["编写高性能的十大技巧 Web 应用程序"](http://go.microsoft.com/fwlink/?LinkId=98290) (<http://go.microsoft.com/fwlink/?LinkId=98290>)。                                                                                                                                              |

## <a name="in-this-section"></a>本节内容  

-   [发布面向 Internet 的 Web 服务和 WCF 服务](../technical-guides/publishing-internet-facing-web-services-and-wcf-services.md)