---
title: "配置操作数据源的 Power BI 与 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: "11"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 09b1b1fd7f350e168b2bb13d6bee2e45c12d49cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-operational-data-feed-for-power-bi-with-biztalk-server"></a><span data-ttu-id="00da3-102">配置操作数据源的 Power BI 与 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="00da3-102">Configure the operational data feed for Power BI with BizTalk Server</span></span>
<span data-ttu-id="00da3-103">读取通过 oData 数据源提供的操作数据[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00da3-103">Read operational data provided through an oData feed in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="00da3-104">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、 将跟踪发送到 Power BI 使用 Power BI 模板提供，或创建你自己。</span><span class="sxs-lookup"><span data-stu-id="00da3-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, send tracking to Power BI using the Power BI template provided, or create your own.</span></span> 

## <a name="what-is-operational-data"></a><span data-ttu-id="00da3-105">操作数据是什么</span><span class="sxs-lookup"><span data-stu-id="00da3-105">What is operational data</span></span>
<span data-ttu-id="00da3-106">操作数据是信息的实例和消息流经你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="00da3-106">Operational data is information on the instances and messages flowing through your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="00da3-107">操作数据源是你在获取看组中心数据库中的相同数据[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]控制台。</span><span class="sxs-lookup"><span data-stu-id="00da3-107">The operational data feed is the same data you get looking at Group Hub in the [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] console.</span></span> <span data-ttu-id="00da3-108">数据可访问和使用可视化工具，包括 Power BI 查询。</span><span class="sxs-lookup"><span data-stu-id="00da3-108">The data can be accessed and queried using visualization tools, including Power BI.</span></span> 

<span data-ttu-id="00da3-109">源包括以下表，数据：</span><span class="sxs-lookup"><span data-stu-id="00da3-109">The feed includes the following data tables:</span></span>
* <span data-ttu-id="00da3-110">应用程序数据</span><span class="sxs-lookup"><span data-stu-id="00da3-110">Application data</span></span>
* <span data-ttu-id="00da3-111">AS2 状态记录</span><span class="sxs-lookup"><span data-stu-id="00da3-111">AS2 Status Records</span></span>
* <span data-ttu-id="00da3-112">批处理的信息</span><span class="sxs-lookup"><span data-stu-id="00da3-112">Batching information</span></span>
* <span data-ttu-id="00da3-113">实例信息</span><span class="sxs-lookup"><span data-stu-id="00da3-113">Instance information</span></span>
* <span data-ttu-id="00da3-114">交换聚合记录</span><span class="sxs-lookup"><span data-stu-id="00da3-114">Interchange Aggregations Records</span></span>
* <span data-ttu-id="00da3-115">交换状态记录</span><span class="sxs-lookup"><span data-stu-id="00da3-115">Interchange Status Records</span></span>
* <span data-ttu-id="00da3-116">消息</span><span class="sxs-lookup"><span data-stu-id="00da3-116">Messages</span></span>
* <span data-ttu-id="00da3-117">订阅</span><span class="sxs-lookup"><span data-stu-id="00da3-117">Subscriptions</span></span>
* <span data-ttu-id="00da3-118">被跟踪的事件</span><span class="sxs-lookup"><span data-stu-id="00da3-118">Tracked Events</span></span>
* <span data-ttu-id="00da3-119">事务报表</span><span class="sxs-lookup"><span data-stu-id="00da3-119">Transaction reports</span></span>
* <span data-ttu-id="00da3-120">事务集</span><span class="sxs-lookup"><span data-stu-id="00da3-120">Transaction sets</span></span>

> [!TIP]
> <span data-ttu-id="00da3-121">[PowerBI.com](http://powerbi.microsoft.com)是一个很好的资源，若要了解，并了解有关 Power BI 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="00da3-121">[PowerBI.com](http://powerbi.microsoft.com) is a great resource to understand and learn more about Power BI.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="00da3-122">先决条件</span><span class="sxs-lookup"><span data-stu-id="00da3-122">Prerequisites</span></span>
* <span data-ttu-id="00da3-123">下载并安装[Power BI Desktop](https://powerbi.microsoft.com/desktop/)具有对网络访问的任何计算机上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00da3-123">Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) on any computer that has network access to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="00da3-124">安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00da3-124">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="00da3-125">在上安装 IIS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00da3-125">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="00da3-126">在大多数[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境中，IIS 已安装。</span><span class="sxs-lookup"><span data-stu-id="00da3-126">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="00da3-127">请参阅[的硬件和软件要求 BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="00da3-127">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span> 

## <a name="enable-operational-data-feed"></a><span data-ttu-id="00da3-128">启用操作数据馈送</span><span class="sxs-lookup"><span data-stu-id="00da3-128">Enable operational data feed</span></span>

1. <span data-ttu-id="00da3-129">以管理员身份运行 Windows PowerShell (**启动**菜单上，键入**PowerShell**，右键单击，然后选择**以管理员身份运行**)。</span><span class="sxs-lookup"><span data-stu-id="00da3-129">Run Windows PowerShell as Administrator (**Start** menu, type **PowerShell**, right click, and select **Run as administrator**).</span></span> 
2. <span data-ttu-id="00da3-130">浏览到的文件夹位置[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]安装**Program Files (x86)/Microsoft BizTalk Server 2016**</span><span class="sxs-lookup"><span data-stu-id="00da3-130">Browse to the folder where [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] is installed **Program Files (x86)/Microsoft BizTalk Server 2016**</span></span>
3. <span data-ttu-id="00da3-131">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="00da3-131">Run the following command.</span></span> <span data-ttu-id="00da3-132">请务必更新你`website`， `domain\user`， `password`，和`domain\group`用你的值：</span><span class="sxs-lookup"><span data-stu-id="00da3-132">Be sure to update your `website`, `domain\user`, `password`, and `domain\group` with your values:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1>, <domain>\<group2>'
    ```
4. <span data-ttu-id="00da3-133">运行该脚本后，浏览新 IIS 应用程序：</span><span class="sxs-lookup"><span data-stu-id="00da3-133">After you run the script, browse the new IIS Application:</span></span>  
    1. <span data-ttu-id="00da3-134">打开 web 浏览器</span><span class="sxs-lookup"><span data-stu-id="00da3-134">Open your web browser</span></span>
    2. <span data-ttu-id="00da3-135">转到**http://localhost/BizTalkOperationalDataService**</span><span class="sxs-lookup"><span data-stu-id="00da3-135">Go to **http://localhost/BizTalkOperationalDataService**</span></span>

## <a name="use-the-power-bi-template"></a><span data-ttu-id="00da3-136">使用 Power BI 模板</span><span class="sxs-lookup"><span data-stu-id="00da3-136">Use the Power BI template</span></span>
<span data-ttu-id="00da3-137">若要访问 Power BI 模板文件，并使用从 Microsoft 提供的可视化效果，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="00da3-137">To access the Power BI Template file, and use the provided visualization from Microsoft, use the following steps:</span></span>

1. <span data-ttu-id="00da3-138">下载并安装[Power BI Desktop](https://powerbi.microsoft.com/desktop/)。</span><span class="sxs-lookup"><span data-stu-id="00da3-138">Download and install the [Power BI Desktop](https://powerbi.microsoft.com/desktop/).</span></span>
2. <span data-ttu-id="00da3-139">浏览到 BizTalk Server 文件夹下**Program Files (x86) \Microsoft BizTalk Server 2016\OperationalDataService**。</span><span class="sxs-lookup"><span data-stu-id="00da3-139">Browse to your BizTalk Server folder under **Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService**.</span></span>
3. <span data-ttu-id="00da3-140">打开**BizTalkOperationalData.pbit**文件。</span><span class="sxs-lookup"><span data-stu-id="00da3-140">Open the **BizTalkOperationalData.pbit** file.</span></span>
4. <span data-ttu-id="00da3-141">出现提示时从 Power BI，将粘贴**http://localhost/\<yourWebSite\>** 为 OData 数据源创建的 URL。</span><span class="sxs-lookup"><span data-stu-id="00da3-141">When prompted from Power BI, paste the **http://localhost/\<yourWebSite\>** URL that you created for your OData feed.</span></span> <span data-ttu-id="00da3-142">例如，输入**http://localhost/OperationalDataService**。</span><span class="sxs-lookup"><span data-stu-id="00da3-142">For example, enter **http://localhost/OperationalDataService**.</span></span> 

    <span data-ttu-id="00da3-143">你的 URL 与以下类似：</span><span class="sxs-lookup"><span data-stu-id="00da3-143">Your URL looks similar to the following:</span></span> 
    
    ![粘贴到 Power BI 模板文件的 OData URL](../core/media/pasteurltopowerbitempaltefile.PNG)

5. <span data-ttu-id="00da3-145">选择**负载**来填充你的 Power BI 报表中的字段。</span><span class="sxs-lookup"><span data-stu-id="00da3-145">Select **Load** to populate the fields in your Power BI report.</span></span> 
6. <span data-ttu-id="00da3-146">模板文件自动生成的信息和可用表从 OData 数据源。</span><span class="sxs-lookup"><span data-stu-id="00da3-146">The Template file automatically generates the information and tables available from the OData feed.</span></span>

<span data-ttu-id="00da3-147">操作数据公开通过计算机，并可以访问和执行基于权限的其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="00da3-147">The operational data is exposed through the computer, and can be accessed and executed by other applications based on permissions.</span></span> 

<span data-ttu-id="00da3-148">若要了解有关 Power BI 中，以及如何将发布的报表联机转至[PowerBI.com](http://powerbi.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="00da3-148">To learn more about Power BI, and how to publish the report online go to [PowerBI.com](http://powerbi.microsoft.com)</span></span>

## <a name="see-also"></a><span data-ttu-id="00da3-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00da3-149">See also</span></span>

[<span data-ttu-id="00da3-150">了解有关 Power BI 的详细信息</span><span class="sxs-lookup"><span data-stu-id="00da3-150">Learn more about Power BI</span></span>](https://www.powerbi.com)  
[<span data-ttu-id="00da3-151">配置功能包</span><span class="sxs-lookup"><span data-stu-id="00da3-151">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)