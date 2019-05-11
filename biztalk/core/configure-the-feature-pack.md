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
ms.openlocfilehash: 5e9dad92a11357c121e01a958996d0b335ba741b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356448"
---
# <a name="configure-the-feature-pack"></a><span data-ttu-id="017e1-104">配置功能包</span><span class="sxs-lookup"><span data-stu-id="017e1-104">Configure the feature pack</span></span>

## <a name="overview"></a><span data-ttu-id="017e1-105">概述</span><span class="sxs-lookup"><span data-stu-id="017e1-105">Overview</span></span>

[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="017e1-106">使用功能包提供的改进、 功能和使用 Azure 的更紧密集成。</span><span class="sxs-lookup"><span data-stu-id="017e1-106">uses feature packs to provide improvements, features, and closer integration with Azure.</span></span> <span data-ttu-id="017e1-107">这些功能包来扩展在关键领域，例如部署、 安全性、 分析、 运行时、 维护、 标准符合性和混合集成的功能。</span><span class="sxs-lookup"><span data-stu-id="017e1-107">These feature packs extend functionality in key areas, such as deployment, security, analytics, runtime, maintainance, standard compliance, and hybrid integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="017e1-108">功能包是适用于 Enterprise edition 和 Developer edition 的[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]时：</span><span class="sxs-lookup"><span data-stu-id="017e1-108">The feature packs are available with the Enterprise and Developer editions of [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] when:</span></span> 
> 
> - <span data-ttu-id="017e1-109">使用具有软件保障 (SA) 或</span><span class="sxs-lookup"><span data-stu-id="017e1-109">Used with Software Assurance (SA), OR</span></span>
> - <span data-ttu-id="017e1-110">运行[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]在 Azure 中使用企业协议</span><span class="sxs-lookup"><span data-stu-id="017e1-110">Running [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in Azure using an Enterprise Agreement</span></span>
> 
> <span data-ttu-id="017e1-111">功能包不能用于任何其他[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本 （标准版和 Branch 版） 或任何其他[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本 (2013 R2，2013，2010 年，等等)。</span><span class="sxs-lookup"><span data-stu-id="017e1-111">The feature packs are not available for any other [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] edition (Standard and Branch editions), or any other [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] version (2013 R2, 2013, 2010, and so on).</span></span> 

## <a name="download-and-install"></a><span data-ttu-id="017e1-112">从</span><span class="sxs-lookup"><span data-stu-id="017e1-112">Download and install</span></span>

<span data-ttu-id="017e1-113">功能包是累积的。</span><span class="sxs-lookup"><span data-stu-id="017e1-113">The feature packs are cumulative.</span></span> <span data-ttu-id="017e1-114">因此在安装功能包 3 时，您还获得的功能和更新功能包 2 和 1。</span><span class="sxs-lookup"><span data-stu-id="017e1-114">So when you install feature pack 3, you also get the features and updates in feature packs 2 and 1.</span></span> <span data-ttu-id="017e1-115">您还可以获取最新的累积更新。</span><span class="sxs-lookup"><span data-stu-id="017e1-115">You also get the latest cumulative updates.</span></span>

* <span data-ttu-id="017e1-116">下载[!INCLUDE[bts2016_md](../includes/bts2016-md.md)][功能包 3](https://aka.ms/bts2016fp3)。</span><span class="sxs-lookup"><span data-stu-id="017e1-116">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>

* <span data-ttu-id="017e1-117">下载[!INCLUDE[bts2016_md](../includes/bts2016-md.md)][功能包 2](https://aka.ms/bts2016fp2)。</span><span class="sxs-lookup"><span data-stu-id="017e1-117">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2](https://aka.ms/bts2016fp2).</span></span>

* <span data-ttu-id="017e1-118">下载[!INCLUDE[bts2016_md](../includes/bts2016-md.md)][功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)。</span><span class="sxs-lookup"><span data-stu-id="017e1-118">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100).</span></span>

#### <a name="install"></a><span data-ttu-id="017e1-119">安装</span><span class="sxs-lookup"><span data-stu-id="017e1-119">Install</span></span>

1. <span data-ttu-id="017e1-120">以管理员身份运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="017e1-120">Run setup as administrator.</span></span>
2. <span data-ttu-id="017e1-121">在中**欢迎**，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="017e1-121">In **Welcome**, select **Next**.</span></span> 
3. <span data-ttu-id="017e1-122">接受许可协议，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="017e1-122">Accept the license agreement, and select **Next**.</span></span> 
4. <span data-ttu-id="017e1-123">继续进行安装。</span><span class="sxs-lookup"><span data-stu-id="017e1-123">Continue with the installation.</span></span> <span data-ttu-id="017e1-124">在安装过程中多个命令窗口可能打开和关闭。</span><span class="sxs-lookup"><span data-stu-id="017e1-124">During the install, several command windows may open and close.</span></span> <span data-ttu-id="017e1-125">完成后，系统会提示您**完成**。</span><span class="sxs-lookup"><span data-stu-id="017e1-125">When complete, you are prompted to **Finish**.</span></span>

<span data-ttu-id="017e1-126">在中创建的安装日志`C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`。</span><span class="sxs-lookup"><span data-stu-id="017e1-126">A setup log is created in `C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`.</span></span>

>[!TIP]
> <span data-ttu-id="017e1-127">有关安装的全面指南，请参阅[BizTalk Server 2016 功能包 3年： 分步安装](https://blog.sandro-pereira.com/2018/06/26/biztalk-server-2016-feature-pack-3/)博客文章。</span><span class="sxs-lookup"><span data-stu-id="017e1-127">For comprehensive guidance on the installation, see the [BizTalk Server 2016 Feature Pack 3: step-by-step installation](https://blog.sandro-pereira.com/2018/06/26/biztalk-server-2016-feature-pack-3/) blog post.</span></span>

## <a name="feature-pack-3-updates"></a><span data-ttu-id="017e1-128">功能包 3 更新</span><span class="sxs-lookup"><span data-stu-id="017e1-128">Feature Pack 3 updates</span></span>

<span data-ttu-id="017e1-129">**Office 365 适配器**</span><span class="sxs-lookup"><span data-stu-id="017e1-129">**Office 365 Adapters**</span></span>


<span data-ttu-id="017e1-130">Microsoft Office 365 是一种基于云的订阅服务，汇集了最佳今天工作方式的工具。</span><span class="sxs-lookup"><span data-stu-id="017e1-130">Microsoft Office 365 is a cloud-based subscription service that brings together the best tools for the way people work today.</span></span> <span data-ttu-id="017e1-131">通过将 Excel 和 Outlook 等的同类最佳的应用与 OneDrive 和 Microsoft Teams 等功能强大的云服务相结合，Office 365，任何可以创建和共享的任何设备上的任意位置。</span><span class="sxs-lookup"><span data-stu-id="017e1-131">By combining best-in-class apps like Excel and Outlook with powerful cloud services like OneDrive and Microsoft Teams, Office 365 lets anyone create and share anywhere on any device.</span></span>

<span data-ttu-id="017e1-132">适用于 Office 365 的 Microsoft BizTalk Server 适配器使 IT 专业人员和企业开发人员与基于 BizTalk Server 2016 的新解决方案集成 Outlook 邮件、 联系人和时间表。</span><span class="sxs-lookup"><span data-stu-id="017e1-132">Microsoft BizTalk Server adapters for Office 365 enable IT professionals and enterprise developers to integrate Outlook mail, contacts, and schedules with new solutions based on BizTalk Server 2016.</span></span>

#### <a name="office-365-mail-adapteroffice365-mail-adaptermd"></a>[<span data-ttu-id="017e1-133">Office 365 邮件适配器</span><span class="sxs-lookup"><span data-stu-id="017e1-133">Office 365 Mail adapter</span></span>](office365-mail-adapter.md)
<span data-ttu-id="017e1-134">使用 BizTalk Adapter for Office 365 电子邮件，可以读取、 标记为已读或删除 Outlook 电子邮件消息通过单向 BizTalk Server 接收位置。</span><span class="sxs-lookup"><span data-stu-id="017e1-134">Using the BizTalk Adapter for Office 365 Mail, you can read, mark as read or delete Outlook e-mail messages through one-way BizTalk Server receive locations.</span></span> <span data-ttu-id="017e1-135">使用此适配器，您可以编写电子邮件，包括设置消息优先级，通过单向静态或动态 BizTalk Server 发送端口。</span><span class="sxs-lookup"><span data-stu-id="017e1-135">Using this adapter, you can write e-mail message, including setting message priority, through one-way static or dynamic BizTalk Server send ports.</span></span>

#### <a name="office-365-calendar-adapteroffice365-calendar-adaptermd"></a>[<span data-ttu-id="017e1-136">Office 365 日历适配器</span><span class="sxs-lookup"><span data-stu-id="017e1-136">Office 365 Calendar adapter</span></span>](office365-calendar-adapter.md)
<span data-ttu-id="017e1-137">使用 BizTalk Adapter for Office 365 日历，您可以获取未来的日历事件通过单向 BizTalk Server 接收位置。</span><span class="sxs-lookup"><span data-stu-id="017e1-137">Using the BizTalk Adapter for Office 365 Calendar, you can get future calendar events through one-way BizTalk Server receive locations.</span></span> <span data-ttu-id="017e1-138">使用此适配器，可以创建日历事件，并输入必选和可选与会者，通过单向静态或动态 BizTalk Server 发送端口。</span><span class="sxs-lookup"><span data-stu-id="017e1-138">Using this adapter, you can create calendar events, and enter required and optional attendees, through one-way static or dynamic BizTalk Server send ports.</span></span>

#### <a name="office-365-contact-adapteroffice365-contact-adaptermd"></a>[<span data-ttu-id="017e1-139">Office 365 联系人适配器</span><span class="sxs-lookup"><span data-stu-id="017e1-139">Office 365 Contact adapter</span></span>](office365-contact-adapter.md)
<span data-ttu-id="017e1-140">使用 BizTalk Adapter for Office 365 联系人，可以创建联系人，并输入所有设置，通过单向静态或动态 BizTalk Server 发送端口。</span><span class="sxs-lookup"><span data-stu-id="017e1-140">Using the BizTalk Adapter for Office 365 Contact, you can create contacts, and enter all settings, through one-way static or dynamic BizTalk Server send ports.</span></span>

## <a name="feature-pack-2-updates"></a><span data-ttu-id="017e1-141">功能包 2 更新</span><span class="sxs-lookup"><span data-stu-id="017e1-141">Feature Pack 2 updates</span></span>

#### <a name="expose-soap-endpoints-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[<span data-ttu-id="017e1-142">公开 SOAP 终结点使用 API 管理</span><span class="sxs-lookup"><span data-stu-id="017e1-142">Expose SOAP endpoints with API Management</span></span>](../core/connect-to-azure-api-management.md)

<span data-ttu-id="017e1-143">扩展使用 Feature Pack 1 进行的 API 管理集成，现在可以公开 Wcf-basichttp 接收位置作为 SOAP 终结点使用 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="017e1-143">Expanding on the API management integration made with Feature Pack 1, you can now expose a WCF-BasicHTTP receive location as a SOAP endpoint using the BizTalk Server Administration console.</span></span> 

#### <a name="use-the-event-hub-adapterevent-hubs-adaptermd"></a>[<span data-ttu-id="017e1-144">使用事件中心适配器</span><span class="sxs-lookup"><span data-stu-id="017e1-144">Use the Event Hub adapter</span></span>](event-hubs-adapter.md)

<span data-ttu-id="017e1-145">将消息从 BizTalk 发送到 Azure 事件中心，并向 BizTalk Server 从 Azure 事件中心接收消息。</span><span class="sxs-lookup"><span data-stu-id="017e1-145">Send messages from BizTalk to Azure Event Hubs, and receive messages from Azure Event Hubs to BizTalk Server.</span></span> <span data-ttu-id="017e1-146">在配置的传输属性时，可以轻松地登录到 Azure 帐户，并自动选择你的 Azure 事件中心命名空间和事件中心。</span><span class="sxs-lookup"><span data-stu-id="017e1-146">When you configure the transport properties, you can easily sign in to your Azure account, and automatically select your Azure Event Hubs namespace, and Event Hub.</span></span>

#### <a name="backup-to-azure-blob-accountcorehow-to-configure-the-backup-biztalk-server-jobmd"></a>[<span data-ttu-id="017e1-147">备份到 Azure blob 帐户</span><span class="sxs-lookup"><span data-stu-id="017e1-147">Backup to Azure blob account</span></span>](../core/how-to-configure-the-backup-biztalk-server-job.md)
<span data-ttu-id="017e1-148">备份 BizTalk Server 作业备份 BizTalk 数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="017e1-148">The Backup BizTalk Server job backs up the BizTalk databases and log files.</span></span> <span data-ttu-id="017e1-149">在配置此 SQL 代理作业时，可以输入作业属性中的 Azure blob 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="017e1-149">When you configure this SQL Agent job, you can enter an Azure blob storage account within the job properties.</span></span> <span data-ttu-id="017e1-150">这样，您可以备份你的数据，而不是使用本地的物理磁盘的另一个选项。</span><span class="sxs-lookup"><span data-stu-id="017e1-150">This gives you another option to backup your data, instead of using a local physical disk.</span></span> 

#### <a name="multi-machine-deployment-using-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[<span data-ttu-id="017e1-151">使用 VSTS 的多计算机部署</span><span class="sxs-lookup"><span data-stu-id="017e1-151">Multi-machine deployment using VSTS</span></span>](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)
<span data-ttu-id="017e1-152">使用部署组，可以部署到多个 BizTalk Server 应用程序。</span><span class="sxs-lookup"><span data-stu-id="017e1-152">Using deployment groups, you can deploy your applications to multiple BizTalk Servers.</span></span> <span data-ttu-id="017e1-153">此外可以设置在应用程序项目中，应用程序名称，并通过输入你的管理服务器安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="017e1-153">You can also set the application name within the application project, and install your application by entering your management server.</span></span>

<span data-ttu-id="017e1-154">[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)上如何做到这一点在 VSTS 中提供更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="017e1-154">[Deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) provides more details on how this is done in VSTS.</span></span>  

#### <a name="use-service-bus-premiumcoresb-messaging-adaptermd"></a>[<span data-ttu-id="017e1-155">使用服务总线高级版</span><span class="sxs-lookup"><span data-stu-id="017e1-155">Use Service Bus Premium</span></span>](../core/sb-messaging-adapter.md)

<span data-ttu-id="017e1-156">服务总线适配器支持服务总线高级版，包括将消息发送到分区的队列和主题。</span><span class="sxs-lookup"><span data-stu-id="017e1-156">The Service Bus adapter supports Service Bus Premium, including sending messages to partitioned queues and topics.</span></span> <span data-ttu-id="017e1-157">[服务总线高级和标准消息传送层](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging)详细介绍了有关服务总线高级版的详细信息。</span><span class="sxs-lookup"><span data-stu-id="017e1-157">[Service Bus Premium and Standard messaging tiers](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging) details more about Service Bus Premium.</span></span> 

#### <a name="use-named-instances-with-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[<span data-ttu-id="017e1-158">使用 Application Insights 中使用命名的实例</span><span class="sxs-lookup"><span data-stu-id="017e1-158">Use named instances with Application Insights</span></span>](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)
<span data-ttu-id="017e1-159">在启用分析，并输入 Application Insights 密钥时，可能会收到错误：</span><span class="sxs-lookup"><span data-stu-id="017e1-159">When you enable Analytics, and enter the Application Insights key, you may get error:</span></span> 

```
Group settings were not applied. (A database failure occurred due to database connectivity problems.)
```

<span data-ttu-id="017e1-160">使用 SQL 命名实例时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="017e1-160">This happens when you use SQL named instances.</span></span> <span data-ttu-id="017e1-161">这被固定的此功能包;你可以使用 SQL 默认实例和 SQL 命名实例。</span><span class="sxs-lookup"><span data-stu-id="017e1-161">This is fixed in this feature pack; you can use SQL default instances, and SQL named instances.</span></span> 

#### <a name="tls-12-support"></a><span data-ttu-id="017e1-162">TLS 1.2 支持</span><span class="sxs-lookup"><span data-stu-id="017e1-162">TLS 1.2 support</span></span>

<span data-ttu-id="017e1-163">在 BizTalk Server 中，包括所有适配器和加速器完全支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="017e1-163">TLS 1.2 is fully supported in BizTalk Server, including all the adapters and all the accelerators.</span></span> <span data-ttu-id="017e1-164">您可以禁用 SSL、 TLS 1.0 和 TLS 1.1 的 BizTalk 服务器上。</span><span class="sxs-lookup"><span data-stu-id="017e1-164">You can disable SSL, TLS 1.0, and TLS 1.1 on the BizTalk Server.</span></span> 

<span data-ttu-id="017e1-165">重要信息：</span><span class="sxs-lookup"><span data-stu-id="017e1-165">Key information:</span></span> 

* <span data-ttu-id="017e1-166">支持 TLS 1.2 所需的任何外部系统还与 BizTalk 进行通信</span><span class="sxs-lookup"><span data-stu-id="017e1-166">Any external systems communicating with BizTalk also need to support TLS 1.2</span></span>
* <span data-ttu-id="017e1-167">任何自定义代码，例如 functoid，可能需要更新为支持 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="017e1-167">Any custom code, such as functoids, may need to be updated to support TLS 1.2</span></span>

<span data-ttu-id="017e1-168">[TLS/SSL 协议的说明](https://support.microsoft.com/kb/3155464)介绍了如何设置 TLS 1.2 环境。</span><span class="sxs-lookup"><span data-stu-id="017e1-168">[Description of the TLS/SSL protocol](https://support.microsoft.com/kb/3155464) describes how to setup a TLS 1.2 environment.</span></span> 

#### <a name="use-latest-newtonsoft-json"></a><span data-ttu-id="017e1-169">使用最新 Newtonsoft JSON</span><span class="sxs-lookup"><span data-stu-id="017e1-169">Use latest Newtonsoft JSON</span></span> 
<span data-ttu-id="017e1-170">Newtonsoft 是用于.NET 的 JSON 框架。</span><span class="sxs-lookup"><span data-stu-id="017e1-170">Newtonsoft is a JSON framework for .NET.</span></span> <span data-ttu-id="017e1-171">在此功能包中，则包括为 10.0.3 版的支持。</span><span class="sxs-lookup"><span data-stu-id="017e1-171">In this feature pack, support for version 10.0.3 is included.</span></span> <span data-ttu-id="017e1-172">[下载 v。10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3)直接从 NuGet。</span><span class="sxs-lookup"><span data-stu-id="017e1-172">[Download v. 10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) directly from NuGet.</span></span> 


## <a name="feature-pack-1-updates"></a><span data-ttu-id="017e1-173">功能包 1 更新</span><span class="sxs-lookup"><span data-stu-id="017e1-173">Feature Pack 1 updates</span></span>

#### <a name="send-tracking-data-to-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[<span data-ttu-id="017e1-174">将跟踪数据发送到 Application Insights</span><span class="sxs-lookup"><span data-stu-id="017e1-174">Send tracking data to Application Insights</span></span>](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)

<span data-ttu-id="017e1-175">将跟踪数据发送到 Azure Application Insights 使用其功能，如分析、 机器学习、 诊断和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="017e1-175">Send tracking data to Azure Application Insights to use its features, such as analytics, machine learning, diagnostics, and more.</span></span> 

#### <a name="configure-the-operational-data-feed-using-power-bicoreconfigure-the-operational-data-feed-for-power-bi-with-biztalk-servermd"></a>[<span data-ttu-id="017e1-176">配置操作数据源使用 Power BI</span><span class="sxs-lookup"><span data-stu-id="017e1-176">Configure the operational data feed using Power BI</span></span>](../core/configure-the-operational-data-feed-for-power-bi-with-biztalk-server.md)

<span data-ttu-id="017e1-177">将跟踪数据发送到 Power BI 中使用 oData。</span><span class="sxs-lookup"><span data-stu-id="017e1-177">Send tracking data to Power BI using oData.</span></span> <span data-ttu-id="017e1-178">例如，从端口和业务流程中获取跟踪数据的可视化表示的形式。</span><span class="sxs-lookup"><span data-stu-id="017e1-178">For example, get a visual representation of your tracking data from your ports and orchestrations.</span></span> 

#### <a name="connect-to-the-management-rest-apis-in-biztalkcoreinstall-and-configure-the-management-rest-apis-in-biztalk-servermd"></a>[<span data-ttu-id="017e1-179">连接到管理 REST Api 在 BizTalk 中</span><span class="sxs-lookup"><span data-stu-id="017e1-179">Connect to the management REST APIs in BizTalk</span></span>](../core/install-and-configure-the-management-rest-apis-in-biztalk-server.md)

<span data-ttu-id="017e1-180">使用 REST Api 来远程管理你的 BizTalk 项目，包括协议、 挂起的实例、 已取消登记业务流程、 和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="017e1-180">Use REST APIs to remotely manage your BizTalk artifacts, including agreements, suspended instances, unenlisted orchestrations, and more.</span></span>

#### <a name="configure-advanced-schedulingcoreconfigure-the-time-zone-and-recurrence-scheduling-in-biztalk-servermd"></a>[<span data-ttu-id="017e1-181">配置高级计划</span><span class="sxs-lookup"><span data-stu-id="017e1-181">Configure advanced scheduling</span></span>](../core/configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server.md)

<span data-ttu-id="017e1-182">启用高级计划中将接收位置。</span><span class="sxs-lookup"><span data-stu-id="017e1-182">Enable advanced scheduling in your receive locations.</span></span> <span data-ttu-id="017e1-183">例如，将时区设置或特定月份的特定一天设置的重复服务时段。</span><span class="sxs-lookup"><span data-stu-id="017e1-183">For example, set the timezone, or set a recurrence service window for a specific day on a specific month.</span></span>

#### <a name="configure-automatic-deployments-with-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[<span data-ttu-id="017e1-184">使用 VSTS 配置自动部署</span><span class="sxs-lookup"><span data-stu-id="017e1-184">Configure automatic deployments with VSTS</span></span>](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  

<span data-ttu-id="017e1-185">使用 Visual Studio Team Services (VSTS) 来自动部署解决方案，或更新现有应用程序。</span><span class="sxs-lookup"><span data-stu-id="017e1-185">Use Visual Studio Team Services (VSTS) to automatically deploy your solutions, or update existing applications.</span></span> <span data-ttu-id="017e1-186">与安装了代理通信，VSTS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="017e1-186">VSTS communicates with an agent installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

#### <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-servercoreconnect-to-sql-server-always-encrypted-columns-with-biztalk-servermd"></a>[<span data-ttu-id="017e1-187">将连接到 BizTalk Server 与 SQL Server Always Encrypted 列</span><span class="sxs-lookup"><span data-stu-id="017e1-187">Connect to SQL Server Always Encrypted columns with BizTalk Server</span></span>](../core/connect-to-sql-server-always-encrypted-columns-with-biztalk-server.md)  

<span data-ttu-id="017e1-188">使用 WCF SQL 适配器来查询从 SQL Server 中的始终加密数据库加密的列。</span><span class="sxs-lookup"><span data-stu-id="017e1-188">Use the WCF-SQL adapter to query encrypted columns from an Always Encrypted database in SQL Server.</span></span>

#### <a name="integrate-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[<span data-ttu-id="017e1-189">与 API 管理集成</span><span class="sxs-lookup"><span data-stu-id="017e1-189">Integrate with API Management</span></span>](../core/connect-to-azure-api-management.md)

<span data-ttu-id="017e1-190">在 Azure API 管理服务中，可以创建和公开的 API 为 WSDL，并使用 BizTalk SOAP 终结点的 URI。</span><span class="sxs-lookup"><span data-stu-id="017e1-190">Within your Azure API management service, you can create and expose an API as WSDL, and use the URI to a BizTalk SOAP endpoint.</span></span>  
