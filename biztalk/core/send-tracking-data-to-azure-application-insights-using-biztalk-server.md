---
title: "将跟踪数据发送到 Azure Application Insights 使用 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: "10"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: f587c3049e191505c87ba456b5ddfd41011862c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="send-tracking-data-to-azure-application-insights-using-biztalk-server"></a><span data-ttu-id="dc9bb-102">将跟踪数据发送到 Azure Application Insights 使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="dc9bb-102">Send tracking data to Azure Application Insights using BizTalk Server</span></span>
<span data-ttu-id="dc9bb-103">发送[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]到 Azure 应用程序 Inisights 跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-103">Send [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] tracking data to Azure Application Inisights.</span></span> 

<span data-ttu-id="dc9bb-104">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，您可以过程，并将跟踪数据发送到 Azure Application Insights。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can process and send your tracking data to Azure Application Insights.</span></span> <span data-ttu-id="dc9bb-105">使用 Application Insights 功能来接收端口、 发送端口和业务流程从跟踪您的实例。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-105">Use the Application Insights features to track your instances from receive ports, send ports, and orchestrations.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dc9bb-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="dc9bb-106">Prerequisites</span></span>
* <span data-ttu-id="dc9bb-107">创建的新实例[Application Insights](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)</span><span class="sxs-lookup"><span data-stu-id="dc9bb-107">Create a new instance of [Application Insights](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)</span></span>
* <span data-ttu-id="dc9bb-108">安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc9bb-108">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

## <a name="enable-analytics-for-your-environment"></a><span data-ttu-id="dc9bb-109">启用针对你的环境分析</span><span class="sxs-lookup"><span data-stu-id="dc9bb-109">Enable analytics for your environment</span></span>

1. <span data-ttu-id="dc9bb-110">打开**BizTalk Server 管理**控制台中，展开**BizTalk 管理**，右键单击**BizTalk 组**，然后选择**设置**.</span><span class="sxs-lookup"><span data-stu-id="dc9bb-110">Open the **BizTalk Server Administration** console, expand **BizTalk Administration**, right-click the **BizTalk Group**, and select **Settings**.</span></span> 
2. <span data-ttu-id="dc9bb-111">检查**启用组级别分析**。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-111">Check **Enable group-level analytics**.</span></span>
3. <span data-ttu-id="dc9bb-112">有关**目标类型**，选择**Application Insight**从列表中。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-112">For the **Target type**, select **Application Insight** from the list.</span></span>
4. <span data-ttu-id="dc9bb-113">有关**连接参数**，输入你的 Application Insights **[检测密钥](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)** （在 Azure 门户中可用）。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-113">For the **Connection parameters**, enter your Application Insights **[instrumentation key](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)** (available in the Azure portal).</span></span>

    <span data-ttu-id="dc9bb-114">你的组设置类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="dc9bb-114">Your Group settings look similar to the following:</span></span> 

    ![启用针对你的环境分析](../core/media/environmentsettingapplicationinishgt.PNG)

5. <span data-ttu-id="dc9bb-116">单击“确定”保存更改。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-116">Select **OK** to save your changes.</span></span> 

<span data-ttu-id="dc9bb-117">在启用之后，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]已准备好将数据传输到 Application Insights。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-117">Once enabled, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] is ready to transmit data to Application Insights.</span></span> <span data-ttu-id="dc9bb-118">接下来，启用在端口和业务流程的分析。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-118">Next, enable analytics on your ports and orchestrations.</span></span> 

## <a name="enable-analytics-on-your-artifacts"></a><span data-ttu-id="dc9bb-119">启用你的项目上的分析</span><span class="sxs-lookup"><span data-stu-id="dc9bb-119">Enable analytics on your artifacts</span></span>

1. <span data-ttu-id="dc9bb-120">在 BizTalk Server 管理中，右键单击**接收端口**，**发送端口**或**orchestration**，然后选择**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-120">In BizTalk Server Administration, right-click a **receive port**, **send port** or **orchestration**, and select **Tracking**.</span></span>
2. <span data-ttu-id="dc9bb-121">下**分析**，检查**启用分析**。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-121">Under **Analytics**, check **Enable Analytics**.</span></span> <span data-ttu-id="dc9bb-122">此设置将开始跟踪和传输到 Application Insights 从项目的数据。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-122">This setting starts tracking and transmitting data from the artifact to Application Insights.</span></span>

    <span data-ttu-id="dc9bb-123">你的项目设置类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="dc9bb-123">Your artifact settings look similar to the following:</span></span> 
    
    ![业务流程的跟踪数据](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. <span data-ttu-id="dc9bb-125">单击“确定”保存更改。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-125">Select **OK** to save your changes.</span></span>

<span data-ttu-id="dc9bb-126">接下来，运行以查看你的数据的 Application Insights 中的查询。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-126">Next, run queries within Application Insights to see your data.</span></span>  

> [!TIP]
> <span data-ttu-id="dc9bb-127">连接你的 BizTalk Server 分析与其他系统，若要了解更多的组织数据。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-127">Connect your BizTalk Server Analytics with other systems to gain even more insight into your organizations data.</span></span>

## <a name="run-queries-on-your-data"></a><span data-ttu-id="dc9bb-128">对数据运行查询</span><span class="sxs-lookup"><span data-stu-id="dc9bb-128">Run queries on your data</span></span>
<span data-ttu-id="dc9bb-129">后的数据发送到 Application Insights，可以使用在 Azure 中的分析工具来创建高级的查询，并分析你的数据。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-129">Once the data is sent to Application Insights, you can use the analytics tools within Azure to create advanced queries, and analyze your data.</span></span>

1. <span data-ttu-id="dc9bb-130">登录到[Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-130">Sign in to the [Azure Portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="dc9bb-131">打开 Application Insights 资源，并选择**分析**。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-131">Open your Application Insights resource, and select **Analytics**.</span></span>
3. <span data-ttu-id="dc9bb-132">选择**用法**，并运行查询提供。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-132">Select **usage**, and run the query provided.</span></span>

    > [!TIP]
    > <span data-ttu-id="dc9bb-133">了解有关如何在 Application Insights 在编写查询[Application Insights 中的分析](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)。</span><span class="sxs-lookup"><span data-stu-id="dc9bb-133">Learn more about how to write queries in Application Insights at [Analytics in Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dc9bb-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc9bb-134">See also</span></span>
 [<span data-ttu-id="dc9bb-135">配置功能包</span><span class="sxs-lookup"><span data-stu-id="dc9bb-135">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)