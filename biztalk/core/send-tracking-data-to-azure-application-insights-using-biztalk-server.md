---
title: 跟踪对 Application Insights 或事件中心的数据 |Microsoft Docs
description: 若要启用分析跟踪数据的 Azure Application Insights 或 Azure 事件中心在 BizTalk Server 中的功能包安装
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
ms.openlocfilehash: 981fc1222b2a9b63c8d87cf6ac35bb82b954c857
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254457"
---
# <a name="send-biztalk-tracking-data-to-azure-application-insights-or-event-hubs"></a><span data-ttu-id="a401b-103">发送到 Azure Application Insights 或事件中心跟踪数据的 BizTalk</span><span class="sxs-lookup"><span data-stu-id="a401b-103">Send BizTalk tracking data to Azure Application Insights or Event Hubs</span></span>

<span data-ttu-id="a401b-104">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，可以处理和跟踪数据发送到 Azure Application Insights。</span><span class="sxs-lookup"><span data-stu-id="a401b-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can process and send your tracking data to Azure Application Insights.</span></span> 
          
<span data-ttu-id="a401b-105">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**:</span><span class="sxs-lookup"><span data-stu-id="a401b-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**:</span></span>

* <span data-ttu-id="a401b-106">Application Insights 支持 SQL 默认实例和命名实例的 SQL</span><span class="sxs-lookup"><span data-stu-id="a401b-106">Application Insights supports SQL default instances, and SQL named instances</span></span>
* <span data-ttu-id="a401b-107">你可以处理和跟踪数据发送到 Azure 事件中心</span><span class="sxs-lookup"><span data-stu-id="a401b-107">You can process and send tracking data to Azure Event Hubs</span></span>

<span data-ttu-id="a401b-108">使用这些 Azure 服务从接收端口、 发送端口和业务流程跟踪你的实例。</span><span class="sxs-lookup"><span data-stu-id="a401b-108">Use these Azure services to track your instances from receive ports, send ports, and orchestrations.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a401b-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="a401b-109">Prerequisites</span></span>
* <span data-ttu-id="a401b-110">创建的新实例[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource)。</span><span class="sxs-lookup"><span data-stu-id="a401b-110">Create a new instance of [Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource).</span></span> <span data-ttu-id="a401b-111">BizTalk Server 使用**检测密钥**进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a401b-111">BizTalk Server uses the **Instrumentation Key** to authenticate.</span></span>
* <span data-ttu-id="a401b-112">创建[Azure 事件中心命名空间和事件中心](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)。</span><span class="sxs-lookup"><span data-stu-id="a401b-112">Create an [Azure Event Hubs namespace and event hub](https://docs.microsoft.com/azure/event-hubs/event-hubs-create).</span></span> <span data-ttu-id="a401b-113">BizTalk Server 使用的 SAS （命名空间级别） 或事件中心级别策略进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a401b-113">BizTalk Server uses the SAS (namespace-level) or event hub-level policy to authenticate.</span></span>
* <span data-ttu-id="a401b-114">安装[功能包 2](https://aka.ms/bts2016fp2)上你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a401b-114">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

## <a name="enable-analytics-for-your-environment"></a><span data-ttu-id="a401b-115">启用针对你的环境分析</span><span class="sxs-lookup"><span data-stu-id="a401b-115">Enable analytics for your environment</span></span>

1. <span data-ttu-id="a401b-116">打开**BizTalk Server 管理**控制台中，右键单击**BizTalk 组**，然后选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="a401b-116">Open the **BizTalk Server Administration** console, right-click the **BizTalk Group**, and select **Settings**.</span></span> 
2. <span data-ttu-id="a401b-117">检查**启用组级别分析**。</span><span class="sxs-lookup"><span data-stu-id="a401b-117">Check **Enable group-level analytics**.</span></span>
3. <span data-ttu-id="a401b-118">有关**目标类型**，选择**Application Insight**或**事件中心**从列表中。</span><span class="sxs-lookup"><span data-stu-id="a401b-118">For the **Target type**, select **Application Insight** or **Event Hub** from the list.</span></span>
    <span data-ttu-id="a401b-119">![启用针对你的环境分析](../core/media/environmentsettingapplicationinishgt.PNG)</span><span class="sxs-lookup"><span data-stu-id="a401b-119">![Enable analytics for your environment](../core/media/environmentsettingapplicationinishgt.PNG)</span></span>

4. <span data-ttu-id="a401b-120">有关**连接参数**，选择 **...** 按钮，并**登录**到 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="a401b-120">For the **Connection parameters**, select the **...** button, and **Sign-in** to your Azure account.</span></span>  

    <span data-ttu-id="a401b-121">**Application insights**</span><span class="sxs-lookup"><span data-stu-id="a401b-121">**For Application Insights**</span></span>  
    <span data-ttu-id="a401b-122">选择你**订阅**，**资源组**，和 Application Insights 实例。</span><span class="sxs-lookup"><span data-stu-id="a401b-122">Select your **Subscription**, **Resource Group**, and your Application Insights instance.</span></span>

    ![启用针对你的环境分析](../core/media/analytics-group-application-insights.png)

    <span data-ttu-id="a401b-124">**事件中心**</span><span class="sxs-lookup"><span data-stu-id="a401b-124">**For Event Hub**</span></span>  
    <span data-ttu-id="a401b-125">选择你**订阅**，**资源组**，事件中心命名空间和事件中心。</span><span class="sxs-lookup"><span data-stu-id="a401b-125">Select your **Subscription**, **Resource Group**, Event Hub namespace, and event hub.</span></span> <span data-ttu-id="a401b-126">对于身份验证，可以在命名空间级别或事件中心级别处的实体签名中使用的访问签名 (SAS)。</span><span class="sxs-lookup"><span data-stu-id="a401b-126">For authentication, you can use an access signature (SAS) at the namespace-level, or entity signature at the event hub-level.</span></span> <span data-ttu-id="a401b-127">可用键内以前配置的值会自动填充[Azure](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="a401b-127">Your available keys are auto-populated with the values previously configured within [Azure](https://portal.azure.com).</span></span>

    ![启用针对你的环境分析](../core/media/send-tracking-data-to-azure.png)

5. <span data-ttu-id="a401b-129">选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a401b-129">Select **OK** to save your changes.</span></span> 

<span data-ttu-id="a401b-130">启用后，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]已准备好将数据传输到 Azure 资源。</span><span class="sxs-lookup"><span data-stu-id="a401b-130">Once enabled, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] is ready to transmit data to your Azure resource.</span></span> <span data-ttu-id="a401b-131">接下来，启用端口和业务流程上的分析。</span><span class="sxs-lookup"><span data-stu-id="a401b-131">Next, enable analytics on your ports and orchestrations.</span></span> 

## <a name="enable-analytics-on-your-artifacts"></a><span data-ttu-id="a401b-132">分析你的项目</span><span class="sxs-lookup"><span data-stu-id="a401b-132">Enable analytics on your artifacts</span></span>

1. <span data-ttu-id="a401b-133">在 BizTalk Server 管理，右键单击**接收端口**，**发送端口**或**业务流程**，然后选择**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="a401b-133">In BizTalk Server Administration, right-click a **receive port**, **send port** or **orchestration**, and select **Tracking**.</span></span>
2. <span data-ttu-id="a401b-134">下**Analytics**，检查**启用分析**，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a401b-134">Under **Analytics**, check **Enable Analytics**, similar to the following.</span></span> <span data-ttu-id="a401b-135">此设置启动跟踪和传输从项目到 Azure 资源的数据。</span><span class="sxs-lookup"><span data-stu-id="a401b-135">This setting starts tracking and transmitting data from the artifact to your Azure resource.</span></span>
    
    ![业务流程的跟踪数据](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. <span data-ttu-id="a401b-137">选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a401b-137">Select **OK** to save your changes.</span></span>
4. <span data-ttu-id="a401b-138">重新启动跟踪主机实例，并确认 BizTalk 应用程序已启动。</span><span class="sxs-lookup"><span data-stu-id="a401b-138">Restart the tracking host Instance, and confirm the BizTalk Application is started.</span></span>

> [!TIP]
> <span data-ttu-id="a401b-139">与其他系统，若要了解更多的组织数据连接在 BizTalk Server 的分析。</span><span class="sxs-lookup"><span data-stu-id="a401b-139">Connect your BizTalk Server Analytics with other systems to gain even more insight into your organizations data.</span></span>

## <a name="view-your-data"></a><span data-ttu-id="a401b-140">查看你的数据</span><span class="sxs-lookup"><span data-stu-id="a401b-140">View your data</span></span>

#### <a name="use-application-insights"></a><span data-ttu-id="a401b-141">使用 Application Insights</span><span class="sxs-lookup"><span data-stu-id="a401b-141">Use Application Insights</span></span>
<span data-ttu-id="a401b-142">一旦将数据发送到 Application Insights，可以使用在 Azure 中的分析工具来创建高级的查询和分析你的数据。</span><span class="sxs-lookup"><span data-stu-id="a401b-142">Once the data is sent to Application Insights, you can use the analytics tools within Azure to create advanced queries, and analyze your data.</span></span>

1. <span data-ttu-id="a401b-143">登录到[Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="a401b-143">Sign in to the [Azure Portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="a401b-144">打开 Application Insights 资源，并选择**指标资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="a401b-144">Open your Application Insights resource, and select **Metrics Explorer**.</span></span>
3. <span data-ttu-id="a401b-145">空图表可能会显示。</span><span class="sxs-lookup"><span data-stu-id="a401b-145">Empty charts may display.</span></span> <span data-ttu-id="a401b-146">在图表中，选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="a401b-146">In a chart, select **Edit**.</span></span> <span data-ttu-id="a401b-147">下**指标**，选择**自定义**若要查看可用的跟踪的属性。</span><span class="sxs-lookup"><span data-stu-id="a401b-147">Under **Metrics**, select **Custom** to see the available tracked properties.</span></span> <span data-ttu-id="a401b-148">选择一些不同的选项，在图表上看到所做的更改：</span><span class="sxs-lookup"><span data-stu-id="a401b-148">Select some of the different options to see the changes on your chart:</span></span> 

    ![Azure Analytics](../core/media/azure-stream-metrics-custom.png)

4. <span data-ttu-id="a401b-150">返回到 Application Insights 资源，并选择**Analytics**。</span><span class="sxs-lookup"><span data-stu-id="a401b-150">Go back to your Application Insights resource, and select **Analytics**.</span></span> <span data-ttu-id="a401b-151">在中**使用情况**，选择**运行**。</span><span class="sxs-lookup"><span data-stu-id="a401b-151">In **Usage**, select **Run**.</span></span> <span data-ttu-id="a401b-152">执行示例查询，并在图表中显示结果。</span><span class="sxs-lookup"><span data-stu-id="a401b-152">A sample query is executed, and the results are displayed in a chart.</span></span>  

> [!TIP]
> <span data-ttu-id="a401b-153">Azure Application Insights 是一个强大的工具。</span><span class="sxs-lookup"><span data-stu-id="a401b-153">Azure Application Insights is a powerful tool.</span></span> <span data-ttu-id="a401b-154">资源可帮助你在 Application Insights 在编写查询[Application Insights 中的 Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)，甚至可以开始在[什么是 Application Insights？](https://docs.microsoft.com/azure/application-insights/app-insights-overview)。</span><span class="sxs-lookup"><span data-stu-id="a401b-154">There are resources to help you write queries in Application Insights at [Analytics in Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics), and even to get started at [What is Application Insights?](https://docs.microsoft.com/azure/application-insights/app-insights-overview).</span></span>

#### <a name="use-event-hubs"></a><span data-ttu-id="a401b-155">使用事件中心</span><span class="sxs-lookup"><span data-stu-id="a401b-155">Use Event Hubs</span></span>
<span data-ttu-id="a401b-156">后的数据发送到事件中心，有两种方法查看的数据。</span><span class="sxs-lookup"><span data-stu-id="a401b-156">Once the data is sent to Event Hubs, there are a couple of ways to see the data.</span></span> <span data-ttu-id="a401b-157">事件中心使用的用户数量事件中心捕获将流式处理数据加载到 Azure。</span><span class="sxs-lookup"><span data-stu-id="a401b-157">Many Event Hubs users are using Event Hubs Capture to load streaming data into Azure.</span></span> <span data-ttu-id="a401b-158">其目的是为您专注于数据处理，而不是数据捕获。</span><span class="sxs-lookup"><span data-stu-id="a401b-158">The intent is for you to focus on data processing, rather than on data capture.</span></span> <span data-ttu-id="a401b-159">[事件中心捕获](https://docs.microsoft.com/azure/event-hubs/event-hubs-capture-overview)介绍它的工作原理，以及如何将其设置。</span><span class="sxs-lookup"><span data-stu-id="a401b-159">[Event Hubs Capture](https://docs.microsoft.com/azure/event-hubs/event-hubs-capture-overview) explains how it works, and how to set it up.</span></span>

<span data-ttu-id="a401b-160">另一种方法是创建一个接收端口和接收位置使用事件中心适配器。</span><span class="sxs-lookup"><span data-stu-id="a401b-160">Another option is to create a receive port and receive location using the Event Hub Adapter.</span></span> <span data-ttu-id="a401b-161">然后，您可以将数据输出到一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="a401b-161">Then, you can output the data to a folder.</span></span> <span data-ttu-id="a401b-162">这一想法可能是最佳方案，如果你想要测试的方案。</span><span class="sxs-lookup"><span data-stu-id="a401b-162">This idea may be best if you want to test the scenario.</span></span> <span data-ttu-id="a401b-163">[事件中心适配器](event-hubs-adapter.md)列出了消息接收到来自事件中心的 BizTalk Server 的步骤。</span><span class="sxs-lookup"><span data-stu-id="a401b-163">[Event Hubs adapter](event-hubs-adapter.md) lists the steps to receive messages into BizTalk Server from Event Hubs.</span></span>

## <a name="where-the-data-is-stored"></a><span data-ttu-id="a401b-164">存储数据</span><span class="sxs-lookup"><span data-stu-id="a401b-164">Where the data is stored</span></span>

<span data-ttu-id="a401b-165">跟踪数据的显示应很快 （几分钟内） 对 Azure 资源内。</span><span class="sxs-lookup"><span data-stu-id="a401b-165">Your tracking data should display fairly quickly (within a few minutes) within your Azure resources.</span></span> <span data-ttu-id="a401b-166">如果没有，则可能有跟踪主机的问题。</span><span class="sxs-lookup"><span data-stu-id="a401b-166">If it doesn't, then there may be an issue with the tracking host.</span></span> <span data-ttu-id="a401b-167">SQL Server 中的分析数据存储在 BizTalkMsgBoxDb 数据库中，在 TrackingData_2_*x*表。</span><span class="sxs-lookup"><span data-stu-id="a401b-167">In SQL Server, the Analytics data is stored in the BizTalkMsgBoxDb database, in the TrackingData_2_*x* tables.</span></span> <span data-ttu-id="a401b-168">在 SQL Server Management Studio，在以下四个表返回前 1000年行。</span><span class="sxs-lookup"><span data-stu-id="a401b-168">In SQL Server Management Studio, return the top 1000 rows on these four tables.</span></span> <span data-ttu-id="a401b-169">如果数据存在时，跟踪主机不到 BizTalkDTADb 数据库移动数据。</span><span class="sxs-lookup"><span data-stu-id="a401b-169">If the data is there, then the tracking host is not moving the data to the BizTalkDTADb database.</span></span> 

<span data-ttu-id="a401b-170">一些可能的解决方法：</span><span class="sxs-lookup"><span data-stu-id="a401b-170">Some possible resolutions:</span></span>

1. <span data-ttu-id="a401b-171">重新启动跟踪主机。</span><span class="sxs-lookup"><span data-stu-id="a401b-171">Restart the tracking host.</span></span>
2. <span data-ttu-id="a401b-172">创建专用的跟踪主机。</span><span class="sxs-lookup"><span data-stu-id="a401b-172">Create a dedicated tracking host.</span></span> <span data-ttu-id="a401b-173">安装 BizTalk Server 时，可能会在启用跟踪**BizTalk Server 应用程序 1**主机。</span><span class="sxs-lookup"><span data-stu-id="a401b-173">When BizTalk Server is installed, tracking may be enabled on the **BizTalk Server Application 1** host.</span></span> <span data-ttu-id="a401b-174">通常情况下，此应用程序还用于处理消息。</span><span class="sxs-lookup"><span data-stu-id="a401b-174">Typically, this application is also used to process messages.</span></span> <span data-ttu-id="a401b-175">创建专用的跟踪主机使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a401b-175">Create a dedicated tracking host using the following steps:</span></span> 

    1. <span data-ttu-id="a401b-176">BizTalk Server 管理中打开 BizTalk Server 应用程序 1 主机的属性，并取消选中**允许主机跟踪**。</span><span class="sxs-lookup"><span data-stu-id="a401b-176">In BizTalk Server Administration, open the properties of the BizTalk Server Application 1 host, and uncheck **Allow Host Tracking**.</span></span> <span data-ttu-id="a401b-177">重新启动此主机实例。</span><span class="sxs-lookup"><span data-stu-id="a401b-177">Restart this host instance.</span></span>

    2. <span data-ttu-id="a401b-178">创建一个名为的新主机**跟踪**，并检查**允许主机跟踪**。</span><span class="sxs-lookup"><span data-stu-id="a401b-178">Create a new host named **Tracking**, and check **Allow Host Tracking**.</span></span> <span data-ttu-id="a401b-179">创建主机实例，并启动它。</span><span class="sxs-lookup"><span data-stu-id="a401b-179">Create a host instance, and start it.</span></span>

<span data-ttu-id="a401b-180">现在，再次查询 BizTalkMsgBoxDb TrackingData_2_x 表。</span><span class="sxs-lookup"><span data-stu-id="a401b-180">Now, query the BizTalkMsgBoxDb TrackingData_2_x tables again.</span></span> <span data-ttu-id="a401b-181">如果表为空，将数据移动，并且应开始显示在 Application Insights 中。</span><span class="sxs-lookup"><span data-stu-id="a401b-181">If the tables are empty, then the data was moved, and should start displaying in Application Insights.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a401b-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a401b-182">See also</span></span>
 [<span data-ttu-id="a401b-183">安装并配置功能包</span><span class="sxs-lookup"><span data-stu-id="a401b-183">Install & configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)