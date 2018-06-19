---
title: 跟踪对 Application Insights 或事件中心的数据 |Microsoft 文档
description: 安装功能包启用的跟踪数据与 Azure Application Insights 或 BizTalk Server 中的 Azure 事件中心的分析
ms.custom: fp1, fp2
ms.date: 11/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: 10
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5ddd60f72955c7196edfc8bf2310b73226d2abe
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710776"
---
# <a name="send-biztalk-tracking-data-to-azure-application-insights-or-event-hubs"></a><span data-ttu-id="86fb6-103">发送到 Azure Application Insights 或事件中心跟踪数据的 BizTalk</span><span class="sxs-lookup"><span data-stu-id="86fb6-103">Send BizTalk tracking data to Azure Application Insights or Event Hubs</span></span>

<span data-ttu-id="86fb6-104">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，您可以过程，并将跟踪数据发送到 Azure Application Insights。</span><span class="sxs-lookup"><span data-stu-id="86fb6-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can process and send your tracking data to Azure Application Insights.</span></span> 
          
<span data-ttu-id="86fb6-105">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**:</span><span class="sxs-lookup"><span data-stu-id="86fb6-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**:</span></span>

* <span data-ttu-id="86fb6-106">Application Insights 支持 SQL 默认实例和命名实例的 SQL</span><span class="sxs-lookup"><span data-stu-id="86fb6-106">Application Insights supports SQL default instances, and SQL named instances</span></span>
* <span data-ttu-id="86fb6-107">您可以过程，并将跟踪数据发送到 Azure 事件中心</span><span class="sxs-lookup"><span data-stu-id="86fb6-107">You can process and send tracking data to Azure Event Hubs</span></span>

<span data-ttu-id="86fb6-108">使用这些 Azure 服务从接收端口、 发送端口和业务流程跟踪您的实例。</span><span class="sxs-lookup"><span data-stu-id="86fb6-108">Use these Azure services to track your instances from receive ports, send ports, and orchestrations.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86fb6-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="86fb6-109">Prerequisites</span></span>
* <span data-ttu-id="86fb6-110">创建的新实例[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource)。</span><span class="sxs-lookup"><span data-stu-id="86fb6-110">Create a new instance of [Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource).</span></span> <span data-ttu-id="86fb6-111">BizTalk Server 使用**检测密钥**进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="86fb6-111">BizTalk Server uses the **Instrumentation Key** to authenticate.</span></span>
* <span data-ttu-id="86fb6-112">创建[Azure 事件中心命名空间和事件中心](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)。</span><span class="sxs-lookup"><span data-stu-id="86fb6-112">Create an [Azure Event Hubs namespace and event hub](https://docs.microsoft.com/azure/event-hubs/event-hubs-create).</span></span> <span data-ttu-id="86fb6-113">BizTalk Server 使用的 SAS （命名空间级别） 或事件中心级别策略进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="86fb6-113">BizTalk Server uses the SAS (namespace-level) or event hub-level policy to authenticate.</span></span>
* <span data-ttu-id="86fb6-114">安装[功能包 2](https://aka.ms/bts2016fp2)上你</span><span class="sxs-lookup"><span data-stu-id="86fb6-114">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your</span></span> [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

## <a name="enable-analytics-for-your-environment"></a><span data-ttu-id="86fb6-115">启用针对你的环境分析</span><span class="sxs-lookup"><span data-stu-id="86fb6-115">Enable analytics for your environment</span></span>

1. <span data-ttu-id="86fb6-116">打开**BizTalk Server 管理**控制台中，右键单击**BizTalk 组**，然后选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="86fb6-116">Open the **BizTalk Server Administration** console, right-click the **BizTalk Group**, and select **Settings**.</span></span> 
2. <span data-ttu-id="86fb6-117">检查**启用组级别分析**。</span><span class="sxs-lookup"><span data-stu-id="86fb6-117">Check **Enable group-level analytics**.</span></span>
3. <span data-ttu-id="86fb6-118">有关**目标类型**，选择**Application Insight**或**事件中心**从列表中。</span><span class="sxs-lookup"><span data-stu-id="86fb6-118">For the **Target type**, select **Application Insight** or **Event Hub** from the list.</span></span>
    <span data-ttu-id="86fb6-119">![启用针对你的环境分析](../core/media/environmentsettingapplicationinishgt.PNG)</span><span class="sxs-lookup"><span data-stu-id="86fb6-119">![Enable analytics for your environment](../core/media/environmentsettingapplicationinishgt.PNG)</span></span>

4. <span data-ttu-id="86fb6-120">有关**连接参数**，选择 **...** 按钮，和**登录**到你的 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="86fb6-120">For the **Connection parameters**, select the **...** button, and **Sign-in** to your Azure account.</span></span>  

    <span data-ttu-id="86fb6-121">**有关 Application Insights**</span><span class="sxs-lookup"><span data-stu-id="86fb6-121">**For Application Insights**</span></span>  
    <span data-ttu-id="86fb6-122">选择你**订阅**，**资源组**，和 Application Insights 实例。</span><span class="sxs-lookup"><span data-stu-id="86fb6-122">Select your **Subscription**, **Resource Group**, and your Application Insights instance.</span></span>

    ![启用针对你的环境分析](../core/media/analytics-group-application-insights.png)

    <span data-ttu-id="86fb6-124">**事件中心**</span><span class="sxs-lookup"><span data-stu-id="86fb6-124">**For Event Hub**</span></span>  
    <span data-ttu-id="86fb6-125">选择你**订阅**，**资源组**，事件中心命名空间和事件中心。</span><span class="sxs-lookup"><span data-stu-id="86fb6-125">Select your **Subscription**, **Resource Group**, Event Hub namespace, and event hub.</span></span> <span data-ttu-id="86fb6-126">对于身份验证，可以在命名空间级别或事件中心级别处的实体签名中使用的访问签名 (SAS)。</span><span class="sxs-lookup"><span data-stu-id="86fb6-126">For authentication, you can use an access signature (SAS) at the namespace-level, or entity signature at the event hub-level.</span></span> <span data-ttu-id="86fb6-127">可用键内以前配置的值是自动填充[Azure](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="86fb6-127">Your available keys are auto-populated with the values previously configured within [Azure](https://portal.azure.com).</span></span>

    ![启用针对你的环境分析](../core/media/send-tracking-data-to-azure.png)

5. <span data-ttu-id="86fb6-129">选择 **确定** 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="86fb6-129">Select **OK** to save your changes.</span></span> 

<span data-ttu-id="86fb6-130">在启用之后，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]已准备好将数据传输到 Azure 资源。</span><span class="sxs-lookup"><span data-stu-id="86fb6-130">Once enabled, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] is ready to transmit data to your Azure resource.</span></span> <span data-ttu-id="86fb6-131">接下来，启用在端口和业务流程的分析。</span><span class="sxs-lookup"><span data-stu-id="86fb6-131">Next, enable analytics on your ports and orchestrations.</span></span> 

## <a name="enable-analytics-on-your-artifacts"></a><span data-ttu-id="86fb6-132">启用你的项目上的分析</span><span class="sxs-lookup"><span data-stu-id="86fb6-132">Enable analytics on your artifacts</span></span>

1. <span data-ttu-id="86fb6-133">在 BizTalk Server 管理中，右键单击**接收端口**，**发送端口**或**orchestration**，然后选择**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="86fb6-133">In BizTalk Server Administration, right-click a **receive port**, **send port** or **orchestration**, and select **Tracking**.</span></span>
2. <span data-ttu-id="86fb6-134">下**分析**，检查**启用分析**，类似于以下。</span><span class="sxs-lookup"><span data-stu-id="86fb6-134">Under **Analytics**, check **Enable Analytics**, similar to the following.</span></span> <span data-ttu-id="86fb6-135">此设置将开始跟踪和传输数据从该项目复制到 Azure 资源。</span><span class="sxs-lookup"><span data-stu-id="86fb6-135">This setting starts tracking and transmitting data from the artifact to your Azure resource.</span></span>
    
    ![业务流程的跟踪数据](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. <span data-ttu-id="86fb6-137">选择 **确定** 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="86fb6-137">Select **OK** to save your changes.</span></span>
4. <span data-ttu-id="86fb6-138">重新启动跟踪主机实例，并确认启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="86fb6-138">Restart the tracking host Instance, and confirm the BizTalk Application is started.</span></span>

> [!TIP]
> <span data-ttu-id="86fb6-139">连接你的 BizTalk Server 分析与其他系统，若要了解更多的组织数据。</span><span class="sxs-lookup"><span data-stu-id="86fb6-139">Connect your BizTalk Server Analytics with other systems to gain even more insight into your organizations data.</span></span>

## <a name="view-your-data"></a><span data-ttu-id="86fb6-140">查看你的数据</span><span class="sxs-lookup"><span data-stu-id="86fb6-140">View your data</span></span>

#### <a name="use-application-insights"></a><span data-ttu-id="86fb6-141">使用 Application Insights</span><span class="sxs-lookup"><span data-stu-id="86fb6-141">Use Application Insights</span></span>
<span data-ttu-id="86fb6-142">后的数据发送到 Application Insights，可以使用在 Azure 中的分析工具来创建高级的查询，并分析你的数据。</span><span class="sxs-lookup"><span data-stu-id="86fb6-142">Once the data is sent to Application Insights, you can use the analytics tools within Azure to create advanced queries, and analyze your data.</span></span>

1. <span data-ttu-id="86fb6-143">登录到[Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="86fb6-143">Sign in to the [Azure Portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="86fb6-144">打开 Application Insights 资源，并选择**指标资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="86fb6-144">Open your Application Insights resource, and select **Metrics Explorer**.</span></span>
3. <span data-ttu-id="86fb6-145">空的图表可能会显示。</span><span class="sxs-lookup"><span data-stu-id="86fb6-145">Empty charts may display.</span></span> <span data-ttu-id="86fb6-146">在图表中，选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="86fb6-146">In a chart, select **Edit**.</span></span> <span data-ttu-id="86fb6-147">下**指标**，选择**自定义**若要查看可用的跟踪的属性。</span><span class="sxs-lookup"><span data-stu-id="86fb6-147">Under **Metrics**, select **Custom** to see the available tracked properties.</span></span> <span data-ttu-id="86fb6-148">选择的某些不同的选项来查看图表上的更改：</span><span class="sxs-lookup"><span data-stu-id="86fb6-148">Select some of the different options to see the changes on your chart:</span></span> 

    ![Azure 分析](../core/media/azure-stream-metrics-custom.png)

4. <span data-ttu-id="86fb6-150">返回到你的 Application Insights 资源，并选择**分析**。</span><span class="sxs-lookup"><span data-stu-id="86fb6-150">Go back to your Application Insights resource, and select **Analytics**.</span></span> <span data-ttu-id="86fb6-151">在**用法**，选择**运行**。</span><span class="sxs-lookup"><span data-stu-id="86fb6-151">In **Usage**, select **Run**.</span></span> <span data-ttu-id="86fb6-152">示例查询将执行，并且结果将显示在图表中。</span><span class="sxs-lookup"><span data-stu-id="86fb6-152">A sample query is executed, and the results are displayed in a chart.</span></span>  

> [!TIP]
> <span data-ttu-id="86fb6-153">Azure 的 Application Insights 是一个功能强大的工具。</span><span class="sxs-lookup"><span data-stu-id="86fb6-153">Azure Application Insights is a powerful tool.</span></span> <span data-ttu-id="86fb6-154">资源可帮助你在 Application Insights 在编写查询[Application Insights 中的分析](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)，甚至可以开始[什么是 Application Insights？](https://docs.microsoft.com/azure/application-insights/app-insights-overview)。</span><span class="sxs-lookup"><span data-stu-id="86fb6-154">There are resources to help you write queries in Application Insights at [Analytics in Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics), and even to get started at [What is Application Insights?](https://docs.microsoft.com/azure/application-insights/app-insights-overview).</span></span>

#### <a name="use-event-hubs"></a><span data-ttu-id="86fb6-155">使用事件中心</span><span class="sxs-lookup"><span data-stu-id="86fb6-155">Use Event Hubs</span></span>
<span data-ttu-id="86fb6-156">后将数据发送到事件中心，有几种方法要查看的数据。</span><span class="sxs-lookup"><span data-stu-id="86fb6-156">Once the data is sent to Event Hubs, there are a couple of ways to see the data.</span></span> <span data-ttu-id="86fb6-157">许多事件中心用户正在使用事件中心捕获来流式处理数据加载到 Azure。</span><span class="sxs-lookup"><span data-stu-id="86fb6-157">Many Event Hubs users are using Event Hubs Capture to load streaming data into Azure.</span></span> <span data-ttu-id="86fb6-158">其目的是为你焦点上的数据处理，而不是在数据捕获。</span><span class="sxs-lookup"><span data-stu-id="86fb6-158">The intent is for you to focus on data processing, rather than on data capture.</span></span> <span data-ttu-id="86fb6-159">[事件中心捕获](https://docs.microsoft.com/azure/event-hubs/event-hubs-capture-overview)介绍它的工作原理，以及如何将其设置。</span><span class="sxs-lookup"><span data-stu-id="86fb6-159">[Event Hubs Capture](https://docs.microsoft.com/azure/event-hubs/event-hubs-capture-overview) explains how it works, and how to set it up.</span></span>

<span data-ttu-id="86fb6-160">另一个选项是创建接收端口和接收位置使用事件中心适配器。</span><span class="sxs-lookup"><span data-stu-id="86fb6-160">Another option is to create a receive port and receive location using the Event Hub Adapter.</span></span> <span data-ttu-id="86fb6-161">然后，你可以将数据输出到一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="86fb6-161">Then, you can output the data to a folder.</span></span> <span data-ttu-id="86fb6-162">如果你想要测试的方案，则可能适合采用这一点。</span><span class="sxs-lookup"><span data-stu-id="86fb6-162">This idea may be best if you want to test the scenario.</span></span> <span data-ttu-id="86fb6-163">[事件中心适配器](event-hubs-adapter.md)列出的步骤，以接收从事件中心的 BizTalk Server 到消息。</span><span class="sxs-lookup"><span data-stu-id="86fb6-163">[Event Hubs adapter](event-hubs-adapter.md) lists the steps to receive messages into BizTalk Server from Event Hubs.</span></span>

## <a name="where-the-data-is-stored"></a><span data-ttu-id="86fb6-164">数据存储位置</span><span class="sxs-lookup"><span data-stu-id="86fb6-164">Where the data is stored</span></span>

<span data-ttu-id="86fb6-165">跟踪数据应会显示相当迅速地 （在几分钟内） 在 Azure 资源。</span><span class="sxs-lookup"><span data-stu-id="86fb6-165">Your tracking data should display fairly quickly (within a few minutes) within your Azure resources.</span></span> <span data-ttu-id="86fb6-166">如果它不存在，然后可能有跟踪主机的问题。</span><span class="sxs-lookup"><span data-stu-id="86fb6-166">If it doesn't, then there may be an issue with the tracking host.</span></span> <span data-ttu-id="86fb6-167">在 SQL Server，分析数据存储在 BizTalkMsgBoxDb 数据库，请在 TrackingData_2_*x*表。</span><span class="sxs-lookup"><span data-stu-id="86fb6-167">In SQL Server, the Analytics data is stored in the BizTalkMsgBoxDb database, in the TrackingData_2_*x* tables.</span></span> <span data-ttu-id="86fb6-168">在 SQL Server Management Studio，在以下四个表上中返回前 1000年行。</span><span class="sxs-lookup"><span data-stu-id="86fb6-168">In SQL Server Management Studio, return the top 1000 rows on these four tables.</span></span> <span data-ttu-id="86fb6-169">如果数据不存在，然后跟踪主机是不将数据移到 BizTalkDTADb 数据库。</span><span class="sxs-lookup"><span data-stu-id="86fb6-169">If the data is there, then the tracking host is not moving the data to the BizTalkDTADb database.</span></span> 

<span data-ttu-id="86fb6-170">一些可能的解决方法：</span><span class="sxs-lookup"><span data-stu-id="86fb6-170">Some possible resolutions:</span></span>

1. <span data-ttu-id="86fb6-171">重新启动跟踪主机。</span><span class="sxs-lookup"><span data-stu-id="86fb6-171">Restart the tracking host.</span></span>
2. <span data-ttu-id="86fb6-172">创建专用的跟踪主机。</span><span class="sxs-lookup"><span data-stu-id="86fb6-172">Create a dedicated tracking host.</span></span> <span data-ttu-id="86fb6-173">安装 BizTalk Server 时，可能在启用跟踪**BizTalk Server 应用程序 1**主机。</span><span class="sxs-lookup"><span data-stu-id="86fb6-173">When BizTalk Server is installed, tracking may be enabled on the **BizTalk Server Application 1** host.</span></span> <span data-ttu-id="86fb6-174">通常情况下，此应用程序还用于处理消息。</span><span class="sxs-lookup"><span data-stu-id="86fb6-174">Typically, this application is also used to process messages.</span></span> <span data-ttu-id="86fb6-175">创建于专用的跟踪主机可以使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="86fb6-175">Create a dedicated tracking host using the following steps:</span></span> 

    1. <span data-ttu-id="86fb6-176">在 BizTalk Server 管理中，打开 BizTalk Server 应用程序 1 主机的属性，并取消选中**允许主机跟踪**。</span><span class="sxs-lookup"><span data-stu-id="86fb6-176">In BizTalk Server Administration, open the properties of the BizTalk Server Application 1 host, and uncheck **Allow Host Tracking**.</span></span> <span data-ttu-id="86fb6-177">重新启动此主机实例。</span><span class="sxs-lookup"><span data-stu-id="86fb6-177">Restart this host instance.</span></span>

    2. <span data-ttu-id="86fb6-178">创建新的主机名为**跟踪**，并检查**允许主机跟踪**。</span><span class="sxs-lookup"><span data-stu-id="86fb6-178">Create a new host named **Tracking**, and check **Allow Host Tracking**.</span></span> <span data-ttu-id="86fb6-179">创建一个主机实例，并启动它。</span><span class="sxs-lookup"><span data-stu-id="86fb6-179">Create a host instance, and start it.</span></span>

<span data-ttu-id="86fb6-180">现在，再次查询 BizTalkMsgBoxDb TrackingData_2_x 表。</span><span class="sxs-lookup"><span data-stu-id="86fb6-180">Now, query the BizTalkMsgBoxDb TrackingData_2_x tables again.</span></span> <span data-ttu-id="86fb6-181">如果表为空，数据移动，，并且应开始在 Application Insights 中显示。</span><span class="sxs-lookup"><span data-stu-id="86fb6-181">If the tables are empty, then the data was moved, and should start displaying in Application Insights.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="86fb6-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86fb6-182">See also</span></span>
 [<span data-ttu-id="86fb6-183">安装并配置功能包</span><span class="sxs-lookup"><span data-stu-id="86fb6-183">Install & configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)