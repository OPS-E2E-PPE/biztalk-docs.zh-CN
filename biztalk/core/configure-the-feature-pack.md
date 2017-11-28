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
# <a name="configure-the-feature-pack"></a><span data-ttu-id="6259a-104">配置功能包</span><span class="sxs-lookup"><span data-stu-id="6259a-104">Configure the feature pack</span></span>

## <a name="overview"></a><span data-ttu-id="6259a-105">概述</span><span class="sxs-lookup"><span data-stu-id="6259a-105">Overview</span></span>

[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6259a-106">使用功能包提供改进、 功能和使用 Azure 的集成更紧密。</span><span class="sxs-lookup"><span data-stu-id="6259a-106"> uses feature packs to provide improvements, features, and closer integration with Azure.</span></span> <span data-ttu-id="6259a-107">这些功能包扩展密钥区域，如部署、 安全、 分析、 运行时，和备份中的功能。</span><span class="sxs-lookup"><span data-stu-id="6259a-107">These feature packs extend functionality in key areas, such as deployment, security, analytics, runtime, and backup.</span></span> 

> [!NOTE]
> <span data-ttu-id="6259a-108">功能包是否可使用的企业版和开发人员版本[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]时：</span><span class="sxs-lookup"><span data-stu-id="6259a-108">The feature packs are available with the Enterprise and Developer editions of [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] when:</span></span> 
> 
> - <span data-ttu-id="6259a-109">用于软件保障 (SA)，或</span><span class="sxs-lookup"><span data-stu-id="6259a-109">Used with Software Assurance (SA), OR</span></span>
> - <span data-ttu-id="6259a-110">运行[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]使用企业协议在 Azure 中</span><span class="sxs-lookup"><span data-stu-id="6259a-110">Running [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in Azure using an Enterprise Agreement</span></span>
> 
> <span data-ttu-id="6259a-111">功能包不可用于任何其他[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]edition 或任何其他[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本。</span><span class="sxs-lookup"><span data-stu-id="6259a-111">The feature packs are not available for any other [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] edition, or any other [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] version.</span></span> 

## <a name="download-and-install"></a><span data-ttu-id="6259a-112">从</span><span class="sxs-lookup"><span data-stu-id="6259a-112">Download and install</span></span>

<span data-ttu-id="6259a-113">功能包是累积的。</span><span class="sxs-lookup"><span data-stu-id="6259a-113">The feature packs are cumulative.</span></span> <span data-ttu-id="6259a-114">因此时安装功能包 2，也可以获得的功能和更新功能包 1 中。</span><span class="sxs-lookup"><span data-stu-id="6259a-114">So when you install feature pack 2, you also get the features and updates in feature pack 1.</span></span>

* <span data-ttu-id="6259a-115">下载[!INCLUDE[bts2016_md](../includes/bts2016-md.md)][功能包 2](https://aka.ms/bts2016fp2)。</span><span class="sxs-lookup"><span data-stu-id="6259a-115">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2](https://aka.ms/bts2016fp2).</span></span>

* <span data-ttu-id="6259a-116">下载[!INCLUDE[bts2016_md](../includes/bts2016-md.md)][功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)。</span><span class="sxs-lookup"><span data-stu-id="6259a-116">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100).</span></span>

#### <a name="install"></a><span data-ttu-id="6259a-117">Install</span><span class="sxs-lookup"><span data-stu-id="6259a-117">Install</span></span>

1. <span data-ttu-id="6259a-118">以管理员身份运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="6259a-118">Run setup as administrator.</span></span>
2. <span data-ttu-id="6259a-119">在**欢迎**，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6259a-119">In **Welcome**, select **Next**.</span></span> 
3. <span data-ttu-id="6259a-120">接受许可协议，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="6259a-120">Accept the license agreement, and select **Next**.</span></span> 
4. <span data-ttu-id="6259a-121">继续安装。</span><span class="sxs-lookup"><span data-stu-id="6259a-121">Continue with the installation.</span></span> <span data-ttu-id="6259a-122">在安装过程几个命令窗口可打开和关闭。</span><span class="sxs-lookup"><span data-stu-id="6259a-122">During the install, several command windows may open and close.</span></span> <span data-ttu-id="6259a-123">完成后，则系统会提示**完成**。</span><span class="sxs-lookup"><span data-stu-id="6259a-123">When complete, you are prompted to **Finish**.</span></span>

<span data-ttu-id="6259a-124">安装程序日志中创建`C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`。</span><span class="sxs-lookup"><span data-stu-id="6259a-124">A setup log is created in `C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`.</span></span>

>[!TIP]
> <span data-ttu-id="6259a-125">有关安装的全面指南，请参阅[功能包的分步安装](https://blog.sandro-pereira.com/2017/04/27/microsoft-biztalk-server-2016-feature-pack-1-step-by-step-installation/)博客文章。</span><span class="sxs-lookup"><span data-stu-id="6259a-125">For comprehensive guidance on the installation, see the [Feature Pack step-by-step installation](https://blog.sandro-pereira.com/2017/04/27/microsoft-biztalk-server-2016-feature-pack-1-step-by-step-installation/) blog post.</span></span>

## <a name="feature-pack-2-updates"></a><span data-ttu-id="6259a-126">功能包 2 更新</span><span class="sxs-lookup"><span data-stu-id="6259a-126">Feature Pack 2 updates</span></span>

#### <a name="expose-soap-endpoints-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[<span data-ttu-id="6259a-127">公开 SOAP 终结点使用 API 管理</span><span class="sxs-lookup"><span data-stu-id="6259a-127">Expose SOAP endpoints with API Management</span></span>](../core/connect-to-azure-api-management.md)

<span data-ttu-id="6259a-128">扩展功能包 1 进行的 API 管理集成，你现在还能够公开 WCF BasicHTTP 接收 SOAP 终结点使用 BizTalk Server 管理控制台的位置。</span><span class="sxs-lookup"><span data-stu-id="6259a-128">Expanding on the API management integration made with Feature Pack 1, you can now expose a WCF-BasicHTTP receive location as a SOAP endpoint using the BizTalk Server Administration console.</span></span> 

#### <a name="use-the-event-hub-adapterevent-hubs-adaptermd"></a>[<span data-ttu-id="6259a-129">使用事件中心适配器</span><span class="sxs-lookup"><span data-stu-id="6259a-129">Use the Event Hub adapter</span></span>](event-hubs-adapter.md)

<span data-ttu-id="6259a-130">将消息从 BizTalk 发送到 Azure 事件中心，并给 BizTalk Server 从 Azure 事件中心接收消息。</span><span class="sxs-lookup"><span data-stu-id="6259a-130">Send messages from BizTalk to Azure Event Hubs, and receive messages from Azure Event Hubs to BizTalk Server.</span></span> <span data-ttu-id="6259a-131">当你配置的传输属性时，你可以轻松地登录到你的 Azure 帐户，并自动选择你的 Azure 事件中心命名空间和事件中心。</span><span class="sxs-lookup"><span data-stu-id="6259a-131">When you configure the transport properties, you can easily sign in to your Azure account, and automatically select your Azure Event Hubs namespace, and Event Hub.</span></span>

#### <a name="backup-to-azure-blob-accountcorehow-to-configure-the-backup-biztalk-server-jobmd"></a>[<span data-ttu-id="6259a-132">备份到 Azure blob 帐户</span><span class="sxs-lookup"><span data-stu-id="6259a-132">Backup to Azure blob account</span></span>](../core/how-to-configure-the-backup-biztalk-server-job.md)
<span data-ttu-id="6259a-133">备份 BizTalk Server 作业将备份的 BizTalk 数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="6259a-133">The Backup BizTalk Server job backs up the BizTalk databases and log files.</span></span> <span data-ttu-id="6259a-134">在配置此 SQL 代理作业时，你可以输入在作业属性内的 Azure blob 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="6259a-134">When you configure this SQL Agent job, you can enter an Azure blob storage account within the job properties.</span></span> <span data-ttu-id="6259a-135">这将提供另一个选项用于备份你的数据，而不是使用本地物理磁盘。</span><span class="sxs-lookup"><span data-stu-id="6259a-135">This gives you another option to backup your data, instead of using a local physical disk.</span></span> 

#### <a name="multi-machine-deployment-using-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[<span data-ttu-id="6259a-136">使用 VSTS 的多计算机部署</span><span class="sxs-lookup"><span data-stu-id="6259a-136">Multi-machine deployment using VSTS</span></span>](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)
<span data-ttu-id="6259a-137">使用部署组，可以部署到多个 BizTalk 服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="6259a-137">Using deployment groups, you can deploy your applications to multiple BizTalk Servers.</span></span> <span data-ttu-id="6259a-138">你还可以设置在应用程序项目中，应用程序名称，并通过输入你的管理服务器安装你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6259a-138">You can also set the application name within the application project, and install your application by entering your management server.</span></span>

<span data-ttu-id="6259a-139">[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)如何做到这一点 VSTS 中提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="6259a-139">[Deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) provides more details on how this is done in VSTS.</span></span>  

#### <a name="use-service-bus-premiumcoresb-messaging-adaptermd"></a>[<span data-ttu-id="6259a-140">使用服务总线高级</span><span class="sxs-lookup"><span data-stu-id="6259a-140">Use Service Bus Premium</span></span>](../core/sb-messaging-adapter.md)

<span data-ttu-id="6259a-141">服务总线适配器支持服务总线高级，包括将消息发送到分区的队列和主题。</span><span class="sxs-lookup"><span data-stu-id="6259a-141">The Service Bus adapter supports Service Bus Premium, including sending messages to partitioned queues and topics.</span></span> <span data-ttu-id="6259a-142">[服务总线高级和标准消息传送层](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging)详细说明了有关服务总线高级详细信息。</span><span class="sxs-lookup"><span data-stu-id="6259a-142">[Service Bus Premium and Standard messaging tiers](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging) details more about Service Bus Premium.</span></span> 

#### <a name="use-named-instances-with-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[<span data-ttu-id="6259a-143">使用命名实例使用 Application Insights</span><span class="sxs-lookup"><span data-stu-id="6259a-143">Use named instances with Application Insights</span></span>](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)
<span data-ttu-id="6259a-144">当你启用分析，并输入 Application Insights 密钥时，你可能会收到错误：</span><span class="sxs-lookup"><span data-stu-id="6259a-144">When you enable Analytics, and enter the Application Insights key, you may get error:</span></span> 

```
Group settings were not applied. (A database failure occurred due to database connectivity problems.)
```

<span data-ttu-id="6259a-145">当你使用 SQL 命名实例时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="6259a-145">This happens when you use SQL named instances.</span></span> <span data-ttu-id="6259a-146">此功能包; 中解决此问题你可以使用 SQL 默认实例和 SQL 命名实例。</span><span class="sxs-lookup"><span data-stu-id="6259a-146">This is fixed in this feature pack; you can use SQL default instances, and SQL named instances.</span></span> 

#### <a name="tls-12-support"></a><span data-ttu-id="6259a-147">TLS 1.2 支持</span><span class="sxs-lookup"><span data-stu-id="6259a-147">TLS 1.2 support</span></span>

<span data-ttu-id="6259a-148">BizTalk Server 中，包括所有适配器和所有快捷键中完全支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="6259a-148">TLS 1.2 is fully supported in BizTalk Server, including all the adapters and all the accelerators.</span></span> <span data-ttu-id="6259a-149">你可以禁用 SSL、 TLS 1.0 和 BizTalk 服务器上的 TLS 1.1。</span><span class="sxs-lookup"><span data-stu-id="6259a-149">You can disable SSL, TLS 1.0, and TLS 1.1 on the BizTalk Server.</span></span> 

<span data-ttu-id="6259a-150">密钥信息：</span><span class="sxs-lookup"><span data-stu-id="6259a-150">Key information:</span></span> 

* <span data-ttu-id="6259a-151">此外与 BizTalk 通信任何外部系统需要支持 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="6259a-151">Any external systems communicating with BizTalk also need to support TLS 1.2</span></span>
* <span data-ttu-id="6259a-152">任何自定义代码，例如 functoid，可能需要更新为支持 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="6259a-152">Any custom code, such as functoids, may need to be updated to support TLS 1.2</span></span>

<span data-ttu-id="6259a-153">[TLS/SSL 协议的说明](https://support.microsoft.com/kb/3155464)介绍如何设置 TLS 1.2 环境。</span><span class="sxs-lookup"><span data-stu-id="6259a-153">[Description of the TLS/SSL protocol](https://support.microsoft.com/kb/3155464) describes how to setup a TLS 1.2 environment.</span></span> 

#### <a name="use-latest-newtonsoft-json"></a><span data-ttu-id="6259a-154">使用最新 Newtonsoft JSON</span><span class="sxs-lookup"><span data-stu-id="6259a-154">Use latest Newtonsoft JSON</span></span> 
<span data-ttu-id="6259a-155">Newtonsoft 是用于.NET 的 JSON 框架。</span><span class="sxs-lookup"><span data-stu-id="6259a-155">Newtonsoft is a JSON framework for .NET.</span></span> <span data-ttu-id="6259a-156">在此功能包中，支持的版本 10.0.3 是包含。</span><span class="sxs-lookup"><span data-stu-id="6259a-156">In this feature pack, support for version 10.0.3 is included.</span></span> <span data-ttu-id="6259a-157">[下载 v。10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3)直接从 NuGet。</span><span class="sxs-lookup"><span data-stu-id="6259a-157">[Download v. 10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) directly from NuGet.</span></span> 


## <a name="feature-pack-1-updates"></a><span data-ttu-id="6259a-158">功能包 1 更新</span><span class="sxs-lookup"><span data-stu-id="6259a-158">Feature Pack 1 updates</span></span>

#### <a name="send-tracking-data-to-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[<span data-ttu-id="6259a-159">将跟踪数据发送到 Application Insights</span><span class="sxs-lookup"><span data-stu-id="6259a-159">Send tracking data to Application Insights</span></span>](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)

<span data-ttu-id="6259a-160">将跟踪数据发送到 Azure Application Insights 使用其功能，如分析、 机器学习、 诊断和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6259a-160">Send tracking data to Azure Application Insights to use its features, such as analytics, machine learning, diagnostics, and more.</span></span> 

#### <a name="configure-the-operational-data-feed-using-power-bicoreconfigure-the-operational-data-feed-for-power-bi-with-biztalk-servermd"></a>[<span data-ttu-id="6259a-161">配置操作数据源使用 Power BI</span><span class="sxs-lookup"><span data-stu-id="6259a-161">Configure the operational data feed using Power BI</span></span>](../core/configure-the-operational-data-feed-for-power-bi-with-biztalk-server.md)

<span data-ttu-id="6259a-162">将跟踪数据发送到 Power BI 中使用 oData。</span><span class="sxs-lookup"><span data-stu-id="6259a-162">Send tracking data to Power BI using oData.</span></span> <span data-ttu-id="6259a-163">例如，获取从端口和业务流程的可视表示形式跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="6259a-163">For example, get a visual representation of your tracking data from your ports and orchestrations.</span></span> 

#### <a name="connect-to-the-management-rest-apis-in-biztalkcoreinstall-and-configure-the-management-rest-apis-in-biztalk-servermd"></a>[<span data-ttu-id="6259a-164">连接到管理 REST Api 在 BizTalk</span><span class="sxs-lookup"><span data-stu-id="6259a-164">Connect to the management REST APIs in BizTalk</span></span>](../core/install-and-configure-the-management-rest-apis-in-biztalk-server.md)

<span data-ttu-id="6259a-165">使用 REST Api 来远程管理你的 BizTalk 项目，包括协议、 挂起的实例、 已取消登记业务流程，和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6259a-165">Use REST APIs to remotely manage your BizTalk artifacts, including agreements, suspended instances, unenlisted orchestrations, and more.</span></span>

#### <a name="configure-advanced-schedulingcoreconfigure-the-time-zone-and-recurrence-scheduling-in-biztalk-servermd"></a>[<span data-ttu-id="6259a-166">配置高级计划</span><span class="sxs-lookup"><span data-stu-id="6259a-166">Configure advanced scheduling</span></span>](../core/configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server.md)

<span data-ttu-id="6259a-167">启用高级计划在你接收位置。</span><span class="sxs-lookup"><span data-stu-id="6259a-167">Enable advanced scheduling in your receive locations.</span></span> <span data-ttu-id="6259a-168">例如，时区，或在特定月份上为特定的一天设置重复周期服务时段。</span><span class="sxs-lookup"><span data-stu-id="6259a-168">For example, set the timezone, or set a recurrence service window for a specific day on a specific month.</span></span>

#### <a name="configure-automatic-deployments-with-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[<span data-ttu-id="6259a-169">使用 VSTS 配置自动部署</span><span class="sxs-lookup"><span data-stu-id="6259a-169">Configure automatic deployments with VSTS</span></span>](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  

<span data-ttu-id="6259a-170">使用 Visual Studio Team Services (VSTS) 来自动部署解决方案，或更新现有应用程序。</span><span class="sxs-lookup"><span data-stu-id="6259a-170">Use Visual Studio Team Services (VSTS) to automatically deploy your solutions, or update existing applications.</span></span> <span data-ttu-id="6259a-171">与上安装了代理通信 VSTS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6259a-171">VSTS communicates with an agent installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

#### <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-servercoreconnect-to-sql-server-always-encrypted-columns-with-biztalk-servermd"></a>[<span data-ttu-id="6259a-172">将连接到 SQL Server 始终加密的列与 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6259a-172">Connect to SQL Server Always Encrypted columns with BizTalk Server</span></span>](../core/connect-to-sql-server-always-encrypted-columns-with-biztalk-server.md)  

<span data-ttu-id="6259a-173">使用 WCF SQL 适配器来查询加密的列从 SQL Server 中的始终加密数据库。</span><span class="sxs-lookup"><span data-stu-id="6259a-173">Use the WCF-SQL adapter to query encrypted columns from an Always Encrypted database in SQL Server.</span></span>

#### <a name="integrate-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[<span data-ttu-id="6259a-174">将与 API 管理集成</span><span class="sxs-lookup"><span data-stu-id="6259a-174">Integrate with API Management</span></span>](../core/connect-to-azure-api-management.md)

<span data-ttu-id="6259a-175">在 Azure API 管理服务中，你可以创建和公开 API 为 WSDL，并使用 BizTalk SOAP 终结点的 URI。</span><span class="sxs-lookup"><span data-stu-id="6259a-175">Within your Azure API management service, you can create and expose an API as WSDL, and use the URI to a BizTalk SOAP endpoint.</span></span>  