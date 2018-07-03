---
title: 配置功能包 |Microsoft Docs
description: 安装和配置功能包 1，和功能包 2。 请参阅新的功能列表中，包括 API 管理、 team services 部署，新的 Azure 适配器、 备份和 BizTalk Server 2016 中的详细信息
ms.custom: ''
ms.date: 06/26/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1027bfa6-49b9-4f58-a2e2-3e0ae2fc3bf3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 210089dc225d85271a8c8fdc426d2ca68bf353e1
ms.sourcegitcommit: 080224caa88f9935b5b13fa035d372f8964d2e52
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957865"
---
# <a name="configure-the-feature-pack"></a>配置功能包

## <a name="overview"></a>概述

[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] 使用功能包提供的改进、 功能和使用 Azure 的更紧密集成。 这些功能包来扩展在关键领域，例如部署、 安全性、 分析、 运行时、 维护、 标准符合性和混合集成的功能。 

> [!NOTE]
> 功能包是适用于 Enterprise edition 和 Developer edition 的[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]时： 
> 
> - 使用具有软件保障 (SA) 或
> - 运行[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]在 Azure 中使用企业协议
> 
> 功能包不能用于任何其他[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本 （标准版和 Branch 版） 或任何其他[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本 (2013 R2，2013，2010 年，等等)。 

## <a name="download-and-install"></a>从

功能包是累积的。 因此在安装功能包 3 时，您还获得的功能和更新功能包 2 和 1。 您还可以获取最新的累积更新。

* 下载[!INCLUDE[bts2016_md](../includes/bts2016-md.md)][功能包 3](https://aka.ms/bts2016fp3)。

* 下载[!INCLUDE[bts2016_md](../includes/bts2016-md.md)][功能包 2](https://aka.ms/bts2016fp2)。

* 下载[!INCLUDE[bts2016_md](../includes/bts2016-md.md)][功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)。

#### <a name="install"></a>Install

1. 以管理员身份运行安装程序。
2. 在中**欢迎**，选择**下一步**。 
3. 接受许可协议，然后选择“下一步”。 
4. 继续安装。 在安装过程中多个命令窗口可能打开和关闭。 完成后，系统会提示您**完成**。

在中创建的安装日志`C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`。

>[!TIP]
> 有关安装的全面指南，请参阅[BizTalk Server 2016 功能包 3年： 分步安装](https://blog.sandro-pereira.com/2018/06/26/biztalk-server-2016-feature-pack-3/)博客文章。

## <a name="feature-pack-3-updates"></a>功能包 3 更新

**Office 365 适配器**


Microsoft Office 365 是一种基于云的订阅服务，汇集了最佳今天工作方式的工具。 通过将 Excel 和 Outlook 等的同类最佳的应用与 OneDrive 和 Microsoft Teams 等功能强大的云服务相结合，Office 365，任何可以创建和共享的任何设备上的任意位置。

适用于 Office 365 的 Microsoft BizTalk Server 适配器使 IT 专业人员和企业开发人员与基于 BizTalk Server 2016 的新解决方案集成 Outlook 邮件、 联系人和时间表。

#### <a name="office-365-mail-adapteroffice365-mail-adaptermd"></a>[Office 365 邮件适配器](office365-mail-adapter.md)
使用 BizTalk Adapter for Office 365 电子邮件，可以读取、 标记为已读或删除 Outlook 电子邮件消息通过单向 BizTalk Server 接收位置。 使用此适配器，您可以编写电子邮件，包括设置消息优先级，通过单向静态或动态 BizTalk Server 发送端口。

#### <a name="office-365-calendar-adapteroffice365-calendar-adaptermd"></a>[Office 365 日历适配器](office365-calendar-adapter.md)
使用 BizTalk Adapter for Office 365 日历，您可以获取未来的日历事件通过单向 BizTalk Server 接收位置。 使用此适配器，可以创建日历事件，并输入必选和可选与会者，通过单向静态或动态 BizTalk Server 发送端口。

#### <a name="office-365-contact-adapteroffice365-contact-adaptermd"></a>[Office 365 联系人适配器](office365-contact-adapter.md)
使用 BizTalk Adapter for Office 365 联系人，可以创建联系人，并输入所有设置，通过单向静态或动态 BizTalk Server 发送端口。

## <a name="feature-pack-2-updates"></a>功能包 2 更新

#### <a name="expose-soap-endpoints-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[公开 SOAP 终结点使用 API 管理](../core/connect-to-azure-api-management.md)

扩展使用 Feature Pack 1 进行的 API 管理集成，现在可以公开 Wcf-basichttp 接收位置作为 SOAP 终结点使用 BizTalk Server 管理控制台。 

#### <a name="use-the-event-hub-adapterevent-hubs-adaptermd"></a>[使用事件中心适配器](event-hubs-adapter.md)

将消息从 BizTalk 发送到 Azure 事件中心，并向 BizTalk Server 从 Azure 事件中心接收消息。 在配置的传输属性时，可以轻松地登录到 Azure 帐户，并自动选择你的 Azure 事件中心命名空间和事件中心。

#### <a name="backup-to-azure-blob-accountcorehow-to-configure-the-backup-biztalk-server-jobmd"></a>[备份到 Azure blob 帐户](../core/how-to-configure-the-backup-biztalk-server-job.md)
备份 BizTalk Server 作业备份 BizTalk 数据库和日志文件。 在配置此 SQL 代理作业时，可以输入作业属性中的 Azure blob 存储帐户。 这样，您可以备份你的数据，而不是使用本地的物理磁盘的另一个选项。 

#### <a name="multi-machine-deployment-using-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[使用 VSTS 的多计算机部署](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)
使用部署组，可以部署到多个 BizTalk Server 应用程序。 此外可以设置在应用程序项目中，应用程序名称，并通过输入你的管理服务器安装应用程序。

[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)上如何做到这一点在 VSTS 中提供更多详细信息。  

#### <a name="use-service-bus-premiumcoresb-messaging-adaptermd"></a>[使用服务总线高级版](../core/sb-messaging-adapter.md)

服务总线适配器支持服务总线高级版，包括将消息发送到分区的队列和主题。 [服务总线高级和标准消息传送层](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging)详细介绍了有关服务总线高级版的详细信息。 

#### <a name="use-named-instances-with-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[使用 Application Insights 中使用命名的实例](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)
在启用分析，并输入 Application Insights 密钥时，可能会收到错误： 

```
Group settings were not applied. (A database failure occurred due to database connectivity problems.)
```

使用 SQL 命名实例时，将发生这种情况。 这被固定的此功能包;你可以使用 SQL 默认实例和 SQL 命名实例。 

#### <a name="tls-12-support"></a>TLS 1.2 支持

在 BizTalk Server 中，包括所有适配器和加速器完全支持 TLS 1.2。 您可以禁用 SSL、 TLS 1.0 和 TLS 1.1 的 BizTalk 服务器上。 

重要信息： 

* 支持 TLS 1.2 所需的任何外部系统还与 BizTalk 进行通信
* 任何自定义代码，例如 functoid，可能需要更新为支持 TLS 1.2

[TLS/SSL 协议的说明](https://support.microsoft.com/kb/3155464)介绍了如何设置 TLS 1.2 环境。 

#### <a name="use-latest-newtonsoft-json"></a>使用最新 Newtonsoft JSON 
Newtonsoft 是用于.NET 的 JSON 框架。 在此功能包中，则包括为 10.0.3 版的支持。 [下载 v。10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3)直接从 NuGet。 


## <a name="feature-pack-1-updates"></a>功能包 1 更新

#### <a name="send-tracking-data-to-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[将跟踪数据发送到 Application Insights](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)

将跟踪数据发送到 Azure Application Insights 使用其功能，如分析、 机器学习、 诊断和的详细信息。 

#### <a name="configure-the-operational-data-feed-using-power-bicoreconfigure-the-operational-data-feed-for-power-bi-with-biztalk-servermd"></a>[配置操作数据源使用 Power BI](../core/configure-the-operational-data-feed-for-power-bi-with-biztalk-server.md)

将跟踪数据发送到 Power BI 中使用 oData。 例如，从端口和业务流程中获取跟踪数据的可视化表示的形式。 

#### <a name="connect-to-the-management-rest-apis-in-biztalkcoreinstall-and-configure-the-management-rest-apis-in-biztalk-servermd"></a>[连接到管理 REST Api 在 BizTalk 中](../core/install-and-configure-the-management-rest-apis-in-biztalk-server.md)

使用 REST Api 来远程管理你的 BizTalk 项目，包括协议、 挂起的实例、 已取消登记业务流程、 和的详细信息。

#### <a name="configure-advanced-schedulingcoreconfigure-the-time-zone-and-recurrence-scheduling-in-biztalk-servermd"></a>[配置高级计划](../core/configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server.md)

启用高级计划中将接收位置。 例如，将时区设置或特定月份的特定一天设置的重复服务时段。

#### <a name="configure-automatic-deployments-with-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[使用 VSTS 配置自动部署](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  

使用 Visual Studio Team Services (VSTS) 来自动部署解决方案，或更新现有应用程序。 与安装了代理通信，VSTS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。

#### <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-servercoreconnect-to-sql-server-always-encrypted-columns-with-biztalk-servermd"></a>[将连接到 BizTalk Server 与 SQL Server Always Encrypted 列](../core/connect-to-sql-server-always-encrypted-columns-with-biztalk-server.md)  

使用 WCF SQL 适配器来查询从 SQL Server 中的始终加密数据库加密的列。

#### <a name="integrate-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[与 API 管理集成](../core/connect-to-azure-api-management.md)

在 Azure API 管理服务中，可以创建和公开的 API 为 WSDL，并使用 BizTalk SOAP 终结点的 URI。  
