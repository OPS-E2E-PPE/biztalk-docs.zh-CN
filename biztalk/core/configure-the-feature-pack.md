---
title: "配置功能包 |Microsoft 文档"
description: "安装并配置功能包 1，和功能包 2。 请参阅新的功能列表中，包括 API 管理、 team services 部署，新的 Azure 适配器、 备份和 BizTalk Server 2016 中的详细信息"
ms.custom: 
ms.date: 11/22/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1027bfa6-49b9-4f58-a2e2-3e0ae2fc3bf3
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5b4164cf1f1355ab9a0d2f350aa5b3b5ce411e0
ms.sourcegitcommit: f4c0d7bc4b617688c643101a34062db90014851a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2017
---
# <a name="configure-the-feature-pack"></a>配置功能包

## <a name="overview"></a>概述

[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]使用功能包提供改进、 功能和使用 Azure 的集成更紧密。 这些功能包扩展密钥区域，如部署、 安全、 分析、 运行时，和备份中的功能。 

> [!NOTE]
> 功能包是否可使用的企业版和开发人员版本[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]时： 
> 
> - 用于软件保障 (SA)，或
> - 运行[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]使用企业协议在 Azure 中
> 
> 功能包不可用于任何其他[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]edition 或任何其他[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本。 

## <a name="download-and-install"></a>从

功能包是累积的。 因此时安装功能包 2，也可以获得的功能和更新功能包 1 中。

* 下载[!INCLUDE[bts2016_md](../includes/bts2016-md.md)][功能包 2](https://aka.ms/bts2016fp2)。

* 下载[!INCLUDE[bts2016_md](../includes/bts2016-md.md)][功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)。

#### <a name="install"></a>Install

1. 以管理员身份运行安装程序。
2. 在**欢迎**，选择**下一步**。 
3. 接受许可协议，然后选择“下一步”。 
4. 继续安装。 在安装过程几个命令窗口可打开和关闭。 完成后，则系统会提示**完成**。

安装程序日志中创建`C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`。

>[!TIP]
> 有关安装的全面指南，请参阅[功能包的分步安装](https://blog.sandro-pereira.com/2017/04/27/microsoft-biztalk-server-2016-feature-pack-1-step-by-step-installation/)博客文章。

## <a name="feature-pack-2-updates"></a>功能包 2 更新

#### <a name="expose-soap-endpoints-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[公开 SOAP 终结点使用 API 管理](../core/connect-to-azure-api-management.md)

扩展功能包 1 进行的 API 管理集成，你现在还能够公开 WCF BasicHTTP 接收 SOAP 终结点使用 BizTalk Server 管理控制台的位置。 

#### <a name="use-the-event-hub-adapterevent-hubs-adaptermd"></a>[使用事件中心适配器](event-hubs-adapter.md)

将消息从 BizTalk 发送到 Azure 事件中心，并给 BizTalk Server 从 Azure 事件中心接收消息。 当你配置的传输属性时，你可以轻松地登录到你的 Azure 帐户，并自动选择你的 Azure 事件中心命名空间和事件中心。

#### <a name="backup-to-azure-blob-accountcorehow-to-configure-the-backup-biztalk-server-jobmd"></a>[备份到 Azure blob 帐户](../core/how-to-configure-the-backup-biztalk-server-job.md)
备份 BizTalk Server 作业将备份的 BizTalk 数据库和日志文件。 在配置此 SQL 代理作业时，你可以输入在作业属性内的 Azure blob 存储帐户。 这将提供另一个选项用于备份你的数据，而不是使用本地物理磁盘。 

#### <a name="multi-machine-deployment-using-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[使用 VSTS 的多计算机部署](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)
使用部署组，可以部署到多个 BizTalk 服务器应用程序。 你还可以设置在应用程序项目中，应用程序名称，并通过输入你的管理服务器安装你的应用程序。

[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)如何做到这一点 VSTS 中提供了详细信息。  

#### <a name="use-service-bus-premiumcoresb-messaging-adaptermd"></a>[使用服务总线高级](../core/sb-messaging-adapter.md)

服务总线适配器支持服务总线高级，包括将消息发送到分区的队列和主题。 [服务总线高级和标准消息传送层](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging)详细说明了有关服务总线高级详细信息。 

#### <a name="use-named-instances-with-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[使用命名实例使用 Application Insights](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)
当你启用分析，并输入 Application Insights 密钥时，你可能会收到错误： 

```
Group settings were not applied. (A database failure occurred due to database connectivity problems.)
```

当你使用 SQL 命名实例时，将发生这种情况。 此功能包; 中解决此问题你可以使用 SQL 默认实例和 SQL 命名实例。 

#### <a name="tls-12-support"></a>TLS 1.2 支持

BizTalk Server 中，包括所有适配器和所有快捷键中完全支持 TLS 1.2。 你可以禁用 SSL、 TLS 1.0 和 BizTalk 服务器上的 TLS 1.1。 

密钥信息： 

* 此外与 BizTalk 通信任何外部系统需要支持 TLS 1.2
* 任何自定义代码，例如 functoid，可能需要更新为支持 TLS 1.2

[TLS/SSL 协议的说明](https://support.microsoft.com/kb/3155464)介绍如何设置 TLS 1.2 环境。 

#### <a name="use-latest-newtonsoft-json"></a>使用最新 Newtonsoft JSON 
Newtonsoft 是用于.NET 的 JSON 框架。 在此功能包中，支持的版本 10.0.3 是包含。 [下载 v。10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3)直接从 NuGet。 


## <a name="feature-pack-1-updates"></a>功能包 1 更新

#### <a name="send-tracking-data-to-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[将跟踪数据发送到 Application Insights](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)

将跟踪数据发送到 Azure Application Insights 使用其功能，如分析、 机器学习、 诊断和的详细信息。 

#### <a name="configure-the-operational-data-feed-using-power-bicoreconfigure-the-operational-data-feed-for-power-bi-with-biztalk-servermd"></a>[配置操作数据源使用 Power BI](../core/configure-the-operational-data-feed-for-power-bi-with-biztalk-server.md)

将跟踪数据发送到 Power BI 中使用 oData。 例如，获取从端口和业务流程的可视表示形式跟踪数据。 

#### <a name="connect-to-the-management-rest-apis-in-biztalkcoreinstall-and-configure-the-management-rest-apis-in-biztalk-servermd"></a>[连接到管理 REST Api 在 BizTalk](../core/install-and-configure-the-management-rest-apis-in-biztalk-server.md)

使用 REST Api 来远程管理你的 BizTalk 项目，包括协议、 挂起的实例、 已取消登记业务流程，和的详细信息。

#### <a name="configure-advanced-schedulingcoreconfigure-the-time-zone-and-recurrence-scheduling-in-biztalk-servermd"></a>[配置高级计划](../core/configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server.md)

启用高级计划在你接收位置。 例如，时区，或在特定月份上为特定的一天设置重复周期服务时段。

#### <a name="configure-automatic-deployments-with-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[使用 VSTS 配置自动部署](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  

使用 Visual Studio Team Services (VSTS) 来自动部署解决方案，或更新现有应用程序。 与上安装了代理通信 VSTS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。

#### <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-servercoreconnect-to-sql-server-always-encrypted-columns-with-biztalk-servermd"></a>[将连接到 SQL Server 始终加密的列与 BizTalk Server](../core/connect-to-sql-server-always-encrypted-columns-with-biztalk-server.md)  

使用 WCF SQL 适配器来查询加密的列从 SQL Server 中的始终加密数据库。

#### <a name="integrate-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[将与 API 管理集成](../core/connect-to-azure-api-management.md)

在 Azure API 管理服务中，你可以创建和公开 API 为 WSDL，并使用 BizTalk SOAP 终结点的 URI。  