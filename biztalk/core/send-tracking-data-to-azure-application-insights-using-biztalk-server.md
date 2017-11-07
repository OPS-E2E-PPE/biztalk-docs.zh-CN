---
title: "将跟踪数据发送到 Azure Application Insights |Microsoft 文档"
description: "安装功能包启用的跟踪数据与 BizTalk Server 中的 Azure Application Insights 的分析"
ms.custom: fp1
ms.date: 11/06/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: "10"
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a65ffd2c5ee76d857effde6ab82dddf17b3de4b
ms.sourcegitcommit: 30189176c44873e3de42cc5f2b8951da51ffd251
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="send-tracking-data-to-azure-application-insights-using-biztalk-server"></a><span data-ttu-id="e9763-103">将跟踪数据发送到 Azure Application Insights 使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e9763-103">Send tracking data to Azure Application Insights using BizTalk Server</span></span>

<span data-ttu-id="e9763-104">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，您可以过程，并将跟踪数据发送到 Azure Application Insights。</span><span class="sxs-lookup"><span data-stu-id="e9763-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can process and send your tracking data to Azure Application Insights.</span></span> <span data-ttu-id="e9763-105">使用 Application Insights 功能来接收端口、 发送端口和业务流程从跟踪您的实例。</span><span class="sxs-lookup"><span data-stu-id="e9763-105">Use the Application Insights features to track your instances from receive ports, send ports, and orchestrations.</span></span>
          
> [!IMPORTANT]
> <span data-ttu-id="e9763-106">此功能当前并不适用于 SQL 命名实例。</span><span class="sxs-lookup"><span data-stu-id="e9763-106">This feature currently does not work with SQL Named Instances.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e9763-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="e9763-107">Prerequisites</span></span>
* <span data-ttu-id="e9763-108">创建的新实例[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource)。</span><span class="sxs-lookup"><span data-stu-id="e9763-108">Create a new instance of [Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource).</span></span> <span data-ttu-id="e9763-109">在其属性，复制**检测密钥**。</span><span class="sxs-lookup"><span data-stu-id="e9763-109">In its properties, copy the **Instrumentation Key**.</span></span> <span data-ttu-id="e9763-110">将其粘贴在另一个文件因此你必须准备就绪。</span><span class="sxs-lookup"><span data-stu-id="e9763-110">Paste it in another file so you have it ready.</span></span> <span data-ttu-id="e9763-111">我们使用内 BizTalk Server 此密钥。</span><span class="sxs-lookup"><span data-stu-id="e9763-111">We use this key within BizTalk Server.</span></span> 
* <span data-ttu-id="e9763-112">安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9763-112">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

## <a name="enable-analytics-for-your-environment"></a><span data-ttu-id="e9763-113">启用针对你的环境分析</span><span class="sxs-lookup"><span data-stu-id="e9763-113">Enable analytics for your environment</span></span>

1. <span data-ttu-id="e9763-114">打开**BizTalk Server 管理**控制台中，右键单击**BizTalk 组**，然后选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="e9763-114">Open the **BizTalk Server Administration** console, right-click the **BizTalk Group**, and select **Settings**.</span></span> 
2. <span data-ttu-id="e9763-115">检查**启用组级别分析**。</span><span class="sxs-lookup"><span data-stu-id="e9763-115">Check **Enable group-level analytics**.</span></span>
3. <span data-ttu-id="e9763-116">有关**目标类型**，选择**Application Insight**从列表中。</span><span class="sxs-lookup"><span data-stu-id="e9763-116">For the **Target type**, select **Application Insight** from the list.</span></span>
4. <span data-ttu-id="e9763-117">有关**连接参数**，输入你的 Application Insights **[检测密钥](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)** （在 Azure 门户中可用）。</span><span class="sxs-lookup"><span data-stu-id="e9763-117">For the **Connection parameters**, enter your Application Insights **[instrumentation key](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)** (available in the Azure portal).</span></span> <span data-ttu-id="e9763-118">你的组设置类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="e9763-118">Your Group settings look similar to the following:</span></span> 

    ![启用针对你的环境分析](../core/media/environmentsettingapplicationinishgt.PNG)

5. <span data-ttu-id="e9763-120">单击“确定”保存更改。</span><span class="sxs-lookup"><span data-stu-id="e9763-120">Select **OK** to save your changes.</span></span> 

<span data-ttu-id="e9763-121">在启用之后，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]已准备好将数据传输到 Application Insights。</span><span class="sxs-lookup"><span data-stu-id="e9763-121">Once enabled, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] is ready to transmit data to Application Insights.</span></span> <span data-ttu-id="e9763-122">接下来，启用在端口和业务流程的分析。</span><span class="sxs-lookup"><span data-stu-id="e9763-122">Next, enable analytics on your ports and orchestrations.</span></span> 

## <a name="enable-analytics-on-your-artifacts"></a><span data-ttu-id="e9763-123">启用你的项目上的分析</span><span class="sxs-lookup"><span data-stu-id="e9763-123">Enable analytics on your artifacts</span></span>

1. <span data-ttu-id="e9763-124">在 BizTalk Server 管理中，右键单击**接收端口**，**发送端口**或**orchestration**，然后选择**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="e9763-124">In BizTalk Server Administration, right-click a **receive port**, **send port** or **orchestration**, and select **Tracking**.</span></span>
2. <span data-ttu-id="e9763-125">下**分析**，检查**启用分析**，类似于以下。</span><span class="sxs-lookup"><span data-stu-id="e9763-125">Under **Analytics**, check **Enable Analytics**, similar to the following.</span></span> <span data-ttu-id="e9763-126">此设置将开始跟踪和传输到 Application Insights 从项目的数据。</span><span class="sxs-lookup"><span data-stu-id="e9763-126">This setting starts tracking and transmitting data from the artifact to Application Insights.</span></span>
    
    ![业务流程的跟踪数据](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. <span data-ttu-id="e9763-128">单击“确定”保存更改。</span><span class="sxs-lookup"><span data-stu-id="e9763-128">Select **OK** to save your changes.</span></span>
4. <span data-ttu-id="e9763-129">重新启动跟踪主机实例，并确认启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e9763-129">Restart the tracking host Instance, and confirm the BizTalk Application is started.</span></span>

<span data-ttu-id="e9763-130">接下来，运行以查看你的数据的 Application Insights 中的查询。</span><span class="sxs-lookup"><span data-stu-id="e9763-130">Next, run queries within Application Insights to see your data.</span></span>  

> [!TIP]
> <span data-ttu-id="e9763-131">连接你的 BizTalk Server 分析与其他系统，若要了解更多的组织数据。</span><span class="sxs-lookup"><span data-stu-id="e9763-131">Connect your BizTalk Server Analytics with other systems to gain even more insight into your organizations data.</span></span>

## <a name="view-your-data"></a><span data-ttu-id="e9763-132">查看你的数据</span><span class="sxs-lookup"><span data-stu-id="e9763-132">View your data</span></span>
<span data-ttu-id="e9763-133">后的数据发送到 Application Insights，可以使用在 Azure 中的分析工具来创建高级的查询，并分析你的数据。</span><span class="sxs-lookup"><span data-stu-id="e9763-133">Once the data is sent to Application Insights, you can use the analytics tools within Azure to create advanced queries, and analyze your data.</span></span>

1. <span data-ttu-id="e9763-134">登录到[Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="e9763-134">Sign in to the [Azure Portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="e9763-135">打开 Application Insights 资源，并选择**指标资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="e9763-135">Open your Application Insights resource, and select **Metrics Explorer**.</span></span>
3. <span data-ttu-id="e9763-136">空的图表可能会显示。</span><span class="sxs-lookup"><span data-stu-id="e9763-136">Empty charts may display.</span></span> <span data-ttu-id="e9763-137">在图表中，选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="e9763-137">In a chart, select **Edit**.</span></span> <span data-ttu-id="e9763-138">下**指标**，选择**自定义**若要查看可用的跟踪的属性。</span><span class="sxs-lookup"><span data-stu-id="e9763-138">Under **Metrics**, select **Custom** to see the available tracked properties.</span></span> <span data-ttu-id="e9763-139">选择的某些不同的选项来查看图表上的更改：</span><span class="sxs-lookup"><span data-stu-id="e9763-139">Select some of the different options to see the changes on your chart:</span></span> 

    ![Azure 分析](../core/media/azure-stream-metrics-custom.png)

4. <span data-ttu-id="e9763-141">返回到你的 Application Insights 资源，并选择**分析**。</span><span class="sxs-lookup"><span data-stu-id="e9763-141">Go back to your Application Insights resource, and select **Analytics**.</span></span> <span data-ttu-id="e9763-142">在**用法**，选择**运行**。</span><span class="sxs-lookup"><span data-stu-id="e9763-142">In **Usage**, select **Run**.</span></span> <span data-ttu-id="e9763-143">示例查询将执行，并且结果将显示在图表中。</span><span class="sxs-lookup"><span data-stu-id="e9763-143">A sample query is executed, and the results are displayed in a chart.</span></span>  

> [!TIP]
> <span data-ttu-id="e9763-144">Azure 的 Application Insights 是一个功能强大的工具。</span><span class="sxs-lookup"><span data-stu-id="e9763-144">Azure Application Insights is a powerful tool.</span></span> <span data-ttu-id="e9763-145">资源可帮助你在 Application Insights 在编写查询[Application Insights 中的分析](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)，甚至可以开始[什么是 Application Insights？](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-overview)。</span><span class="sxs-lookup"><span data-stu-id="e9763-145">There are resources to help you write queries in Application Insights at [Analytics in Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics), and even to get started at [What is Application Insights?](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-overview).</span></span>

## <a name="where-the-data-is-stored"></a><span data-ttu-id="e9763-146">数据存储位置</span><span class="sxs-lookup"><span data-stu-id="e9763-146">Where the data is stored</span></span>

<span data-ttu-id="e9763-147">跟踪数据应会显示相当迅速地 （在几分钟内） 在 Application Insights。</span><span class="sxs-lookup"><span data-stu-id="e9763-147">Your tracking data should display fairly quickly (within a few minutes) within Application Insights.</span></span> <span data-ttu-id="e9763-148">如果它不存在，然后可能有跟踪主机的问题。</span><span class="sxs-lookup"><span data-stu-id="e9763-148">If it doesn't, then there may be an issue with the tracking host.</span></span> <span data-ttu-id="e9763-149">在 SQL Server，分析数据存储在 BizTalkMsgBoxDb 数据库，请在 TrackingData_2_*x*表。</span><span class="sxs-lookup"><span data-stu-id="e9763-149">In SQL Server, the Analytics data is stored in the BizTalkMsgBoxDb database, in the TrackingData_2_*x* tables.</span></span> <span data-ttu-id="e9763-150">在 SQL Server Management Studio，在以下四个表上中返回前 1000年行。</span><span class="sxs-lookup"><span data-stu-id="e9763-150">In SQL Server Management Studio, return the top 1000 rows on these four tables.</span></span> <span data-ttu-id="e9763-151">如果数据不存在，然后跟踪主机是不将数据移到 BizTalkDTADb 数据库。</span><span class="sxs-lookup"><span data-stu-id="e9763-151">If the data is there, then the tracking host is not moving the data to the BizTalkDTADb database.</span></span> 

<span data-ttu-id="e9763-152">一些可能的解决方法：</span><span class="sxs-lookup"><span data-stu-id="e9763-152">Some possible resolutions:</span></span>

1. <span data-ttu-id="e9763-153">重新启动跟踪主机。</span><span class="sxs-lookup"><span data-stu-id="e9763-153">Restart the tracking host.</span></span>
2. <span data-ttu-id="e9763-154">创建专用的跟踪主机。</span><span class="sxs-lookup"><span data-stu-id="e9763-154">Create a dedicated tracking host.</span></span> <span data-ttu-id="e9763-155">安装 BizTalk Server 时，可能在启用跟踪**BizTalk Server 应用程序 1**主机。</span><span class="sxs-lookup"><span data-stu-id="e9763-155">When BizTalk Server is installed, tracking may be enabled on the **BizTalk Server Application 1** host.</span></span> <span data-ttu-id="e9763-156">通常情况下，此应用程序还用于处理消息。</span><span class="sxs-lookup"><span data-stu-id="e9763-156">Typically, this application is also used to process messages.</span></span> <span data-ttu-id="e9763-157">创建于专用的跟踪主机可以使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e9763-157">Create a dedicated tracking host using the following steps:</span></span> 

    1. <span data-ttu-id="e9763-158">在 BizTalk Server 管理中，打开 BizTalk Server 应用程序 1 主机的属性，并取消选中**允许主机跟踪**。</span><span class="sxs-lookup"><span data-stu-id="e9763-158">In BizTalk Server Administration, open the properties of the BizTalk Server Application 1 host, and uncheck **Allow Host Tracking**.</span></span> <span data-ttu-id="e9763-159">重新启动此主机实例。</span><span class="sxs-lookup"><span data-stu-id="e9763-159">Restart this host instance.</span></span>

    2. <span data-ttu-id="e9763-160">创建新的主机名为**跟踪**，并检查**允许主机跟踪**。</span><span class="sxs-lookup"><span data-stu-id="e9763-160">Create a new host named **Tracking**, and check **Allow Host Tracking**.</span></span> <span data-ttu-id="e9763-161">创建一个主机实例，并启动它。</span><span class="sxs-lookup"><span data-stu-id="e9763-161">Create a host instance, and start it.</span></span>

<span data-ttu-id="e9763-162">现在，再次查询 BizTalkMsgBoxDb TrackingData_2_x 表。</span><span class="sxs-lookup"><span data-stu-id="e9763-162">Now, query the BizTalkMsgBoxDb TrackingData_2_x tables again.</span></span> <span data-ttu-id="e9763-163">如果表为空，数据移动，，并且应开始在 Application Insights 中显示。</span><span class="sxs-lookup"><span data-stu-id="e9763-163">If the tables are empty, then the data was moved, and should start displaying in Application Insights.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e9763-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9763-164">See also</span></span>
 [<span data-ttu-id="e9763-165">配置功能包</span><span class="sxs-lookup"><span data-stu-id="e9763-165">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)