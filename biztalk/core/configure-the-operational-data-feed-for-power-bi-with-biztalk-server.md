---
title: 启用 Power BI |Microsoft Docs
description: 为 BizTalk Server 功能包中安装 Power BI 模板
ms.custom: fp1
ms.date: 6/26/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bfe842e3b131e6b0fcde75485c1d472320644c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994174"
---
# <a name="configure-the-power-bi-operational-data-feed-in-biztalk-server"></a><span data-ttu-id="54d95-103">配置 BizTalk Server 中的源的 Power BI 操作数据</span><span class="sxs-lookup"><span data-stu-id="54d95-103">Configure the Power BI operational data feed in BizTalk Server</span></span>

<span data-ttu-id="54d95-104">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、 将跟踪发送到 Power BI 中使用 Power BI 模板提供，或创建您自己。</span><span class="sxs-lookup"><span data-stu-id="54d95-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, send tracking to Power BI using the Power BI template provided, or create your own.</span></span> 

## <a name="what-is-operational-data"></a><span data-ttu-id="54d95-105">什么是操作数据</span><span class="sxs-lookup"><span data-stu-id="54d95-105">What is operational data</span></span>
<span data-ttu-id="54d95-106">操作数据是信息的实例和消息流经您[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="54d95-106">Operational data is information on the instances and messages flowing through your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="54d95-107">操作数据源是相同的数据获取查看组中心[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="54d95-107">The operational data feed is the same data you get looking at Group Hub in [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span> <span data-ttu-id="54d95-108">访问和查询使用可视化工具，包括 Power BI 的数据。</span><span class="sxs-lookup"><span data-stu-id="54d95-108">The data is accessed and queried using visualization tools, including Power BI.</span></span> 

<span data-ttu-id="54d95-109">源包含以下数据表：</span><span class="sxs-lookup"><span data-stu-id="54d95-109">The feed includes the following data tables:</span></span>
* <span data-ttu-id="54d95-110">应用程序数据</span><span class="sxs-lookup"><span data-stu-id="54d95-110">Application data</span></span>
* <span data-ttu-id="54d95-111">AS2 状态记录</span><span class="sxs-lookup"><span data-stu-id="54d95-111">AS2 Status Records</span></span>
* <span data-ttu-id="54d95-112">批处理的信息</span><span class="sxs-lookup"><span data-stu-id="54d95-112">Batching information</span></span>
* <span data-ttu-id="54d95-113">实例信息</span><span class="sxs-lookup"><span data-stu-id="54d95-113">Instance information</span></span>
* <span data-ttu-id="54d95-114">交换聚合记录</span><span class="sxs-lookup"><span data-stu-id="54d95-114">Interchange Aggregations Records</span></span>
* <span data-ttu-id="54d95-115">交换状态记录</span><span class="sxs-lookup"><span data-stu-id="54d95-115">Interchange Status Records</span></span>
* <span data-ttu-id="54d95-116">消息</span><span class="sxs-lookup"><span data-stu-id="54d95-116">Messages</span></span>
* <span data-ttu-id="54d95-117">订阅</span><span class="sxs-lookup"><span data-stu-id="54d95-117">Subscriptions</span></span>
* <span data-ttu-id="54d95-118">跟踪的事件</span><span class="sxs-lookup"><span data-stu-id="54d95-118">Tracked Events</span></span>
* <span data-ttu-id="54d95-119">事务报告</span><span class="sxs-lookup"><span data-stu-id="54d95-119">Transaction reports</span></span>
* <span data-ttu-id="54d95-120">事务集</span><span class="sxs-lookup"><span data-stu-id="54d95-120">Transaction sets</span></span>

> [!TIP]
> <span data-ttu-id="54d95-121">[PowerBI.com](http://powerbi.microsoft.com)是一个不错的资源以了解并了解有关 Power BI 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="54d95-121">[PowerBI.com](http://powerbi.microsoft.com) is a great resource to understand and learn more about Power BI.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="54d95-122">必要條件</span><span class="sxs-lookup"><span data-stu-id="54d95-122">Prerequisites</span></span>
* <span data-ttu-id="54d95-123">下载并安装[Power BI Desktop](https://powerbi.microsoft.com/desktop/)具有网络访问权限的任何计算机上你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54d95-123">Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) on any computer that has network access to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="54d95-124">安装[功能包 2](https://aka.ms/bts2016fp2)，或更高版本上功能包，你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54d95-124">Install [Feature Pack 2](https://aka.ms/bts2016fp2), or newer feature pack, on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="54d95-125">上安装 IIS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="54d95-125">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="54d95-126">在大多数[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境中，IIS 已安装。</span><span class="sxs-lookup"><span data-stu-id="54d95-126">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="54d95-127">请参阅[硬件和软件要求 BizTalk Server 2016 的](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="54d95-127">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span> <span data-ttu-id="54d95-128">确认 IIS 安装通过打开**Internet Information Services Manager**。</span><span class="sxs-lookup"><span data-stu-id="54d95-128">Confirm IIS is installed by opening **Internet Information Services Manager**.</span></span> 
* <span data-ttu-id="54d95-129">可选。</span><span class="sxs-lookup"><span data-stu-id="54d95-129">Optional.</span></span> <span data-ttu-id="54d95-130">安装和配置[Power BI Gateway](https://powerbi.microsoft.com/gateway/)连接[PowerBI.com](http://powerbi.microsoft.com)与你的本地 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="54d95-130">Install and configure a [Power BI Gateway](https://powerbi.microsoft.com/gateway/) to connect [PowerBI.com](http://powerbi.microsoft.com) with your on-premises BizTalk Server.</span></span> <span data-ttu-id="54d95-131">如果您不使用的本地 BizTalk Server，则不需要网关。</span><span class="sxs-lookup"><span data-stu-id="54d95-131">If you're not using an on-premises BizTalk Server, then you don't need the gateway.</span></span>

## <a name="step-1-enable-operational-data"></a><span data-ttu-id="54d95-132">步骤 1： 启用操作数据</span><span class="sxs-lookup"><span data-stu-id="54d95-132">Step 1: Enable operational data</span></span>

1. <span data-ttu-id="54d95-133">以管理员身份运行 Windows PowerShell (**启动**菜单中，键入**PowerShell**，右键单击，然后选择**以管理员身份运行**)。</span><span class="sxs-lookup"><span data-stu-id="54d95-133">Run Windows PowerShell as Administrator (**Start** menu, type **PowerShell**, right click, and select **Run as administrator**).</span></span> 
2. <span data-ttu-id="54d95-134">转到 BizTalk 安装文件夹 (例如，键入： `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。</span><span class="sxs-lookup"><span data-stu-id="54d95-134">Go to the BizTalk installation folder (for example, type: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).</span></span>
3. <span data-ttu-id="54d95-135">在以下文本替换`Default Web Site`， `operationalDataServiceAppPool`， `domain\user`， `password`，和`domain\group`与你的值：</span><span class="sxs-lookup"><span data-stu-id="54d95-135">In the following text, replace `Default Web Site`, `operationalDataServiceAppPool`, `domain\user`, `password`, and `domain\group` with your values:</span></span>

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user\> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1\>, <domain>\<group2\>, <domain>\<user\>, <domain>\<user2\>'
    ```

   * <span data-ttu-id="54d95-136">**服务**： 若要配置的服务 (**OperationalData**适用于 Power BI)</span><span class="sxs-lookup"><span data-stu-id="54d95-136">**Service**: The service to be configured (**OperationalData** for Power BI)</span></span>
   * <span data-ttu-id="54d95-137">**WebSiteName**： 现有托管服务的 IIS web 站点。</span><span class="sxs-lookup"><span data-stu-id="54d95-137">**WebSiteName**: The existing IIS web site that hosts the service.</span></span> <span data-ttu-id="54d95-138">默认值是**默认网站**。</span><span class="sxs-lookup"><span data-stu-id="54d95-138">The default value is **Default Web Site**.</span></span>
   * <span data-ttu-id="54d95-139">**ApplicationPool**： 服务使用的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="54d95-139">**ApplicationPool**: The Application Pool used by the service.</span></span> <span data-ttu-id="54d95-140">如果存在，则不会创建一个新。</span><span class="sxs-lookup"><span data-stu-id="54d95-140">If it exists, a new one is not created.</span></span> <span data-ttu-id="54d95-141">默认值是**DefaultAppPool**。</span><span class="sxs-lookup"><span data-stu-id="54d95-141">The default value is **DefaultAppPool**.</span></span>
   * <span data-ttu-id="54d95-142">**ApplicationPoolUser**： 配置要作为此用户身份运行的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="54d95-142">**ApplicationPoolUser**: Configures the application pool to run as this user identity.</span></span> <span data-ttu-id="54d95-143">必须具有 BizTalk Server 操作员或更高的权限。</span><span class="sxs-lookup"><span data-stu-id="54d95-143">Must have BizTalk Server Operator, or higher privileges.</span></span>
   * <span data-ttu-id="54d95-144">**ApplicationPoolUserPassword**: ApplicationPoolUser 密码</span><span class="sxs-lookup"><span data-stu-id="54d95-144">**ApplicationPoolUserPassword**: Password for the ApplicationPoolUser</span></span>
   * <span data-ttu-id="54d95-145">**AuthorizationAccount**： 授权组或用户可以使用此服务的列表</span><span class="sxs-lookup"><span data-stu-id="54d95-145">**AuthorizationAccount**: List of authorized Groups or Users that can use this service</span></span>

     <span data-ttu-id="54d95-146">在以下示例中，我们将使用`Default Web Site`，创建名为应用程序池`PowerBIAppPool`，运行作为应用程序池`bootcampbts2016\btsservice`帐户，请使用`BIZTALK-serviceacct`作为用户帐户密码，并授予`BizTalk Server Administrators`组权限。</span><span class="sxs-lookup"><span data-stu-id="54d95-146">In the following example, we use the `Default Web Site`, create an application pool named `PowerBIAppPool`, run the appPool as the `bootcampbts2016\btsservice` account, use `BIZTALK-serviceacct` as the user account password, and give the `BizTalk Server Administrators` group permissions.</span></span> <span data-ttu-id="54d95-147">确保输入以下信息，包括单个空格周围值加引号：</span><span class="sxs-lookup"><span data-stu-id="54d95-147">Be sure to enter the following, including the single quotes surrounding values with spaces:</span></span> 

     ```Powershell
     FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName 'Default Web Site' -ApplicationPool PowerBIAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
     ```

     <span data-ttu-id="54d95-148">完成后，BizTalkOperationalDataService 应用程序是在 IIS 中创建：</span><span class="sxs-lookup"><span data-stu-id="54d95-148">When complete, the BizTalkOperationalDataService application is created within IIS:</span></span>  
     ![BizTalkMOperationalDataServer 应用程序](../core/media/biztalkmanagementservice-apppool.png)


4. <span data-ttu-id="54d95-150">若要确认其是否工作，请浏览到`http://localhost/BizTalkOperationalDataService`。</span><span class="sxs-lookup"><span data-stu-id="54d95-150">To confirm it’s working, browse to `http://localhost/BizTalkOperationalDataService`.</span></span> 

    <span data-ttu-id="54d95-151">如果系统会提示登录，是你在上一步中输入域 \ 组的成员的帐户登录 (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。</span><span class="sxs-lookup"><span data-stu-id="54d95-151">If you are prompted to sign-in, sign in with an account that is member of the domain\group you entered in the previous step (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`).</span></span> 

    <span data-ttu-id="54d95-152">如果系统提示打开或保存 BizTalkOperationalDataService.json，你的安装已完成。</span><span class="sxs-lookup"><span data-stu-id="54d95-152">If you are prompted to open or save BizTalkOperationalDataService.json, then your install completed.</span></span> <span data-ttu-id="54d95-153">您可以将它保存在本地，并打开记事本或 Visual Studio 以查看内容。</span><span class="sxs-lookup"><span data-stu-id="54d95-153">You can save it locally, and then open it in notepad or Visual Studio to see the contents.</span></span> 

> [!WARNING]
> <span data-ttu-id="54d95-154">BizTalkOperationalDataService 应用程序在 IIS 中的使用的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="54d95-154">The BizTalkOperationalDataService application in IIS uses a web.config file.</span></span> <span data-ttu-id="54d95-155">Web.config 中的元素**区分大小写**。</span><span class="sxs-lookup"><span data-stu-id="54d95-155">Elements within web.config **are case sensitive**.</span></span> <span data-ttu-id="54d95-156">因此在执行 Windows PowerShell 脚本，请确保输入正确的大小写的`-AuthorizationRoles`值。</span><span class="sxs-lookup"><span data-stu-id="54d95-156">So when you execute the Windows PowerShell script, be sure to enter the correct case for `-AuthorizationRoles` value.</span></span> <span data-ttu-id="54d95-157">如果您不确定的这种情况，下面是找出的简单办法：</span><span class="sxs-lookup"><span data-stu-id="54d95-157">If you’re not sure of the case, here’s an easy way to find out:</span></span> 
> 
> 1. <span data-ttu-id="54d95-158">打开**计算机管理**，然后展开**本地用户和组**。</span><span class="sxs-lookup"><span data-stu-id="54d95-158">Open **Computer Management**, and expand **Local Users and Groups**.</span></span>
> 2. <span data-ttu-id="54d95-159">选择**组**，向下滚动到**SQLServer...**</span><span class="sxs-lookup"><span data-stu-id="54d95-159">Select **Groups**, and scroll down to the **SQLServer…**</span></span> <span data-ttu-id="54d95-160">组。</span><span class="sxs-lookup"><span data-stu-id="54d95-160">groups.</span></span> 
> 3. <span data-ttu-id="54d95-161">在下面的示例，请注意**BOOTCAMPBTS2016**是在全大写形式。</span><span class="sxs-lookup"><span data-stu-id="54d95-161">In the following example, notice **BOOTCAMPBTS2016** is in all caps.</span></span> <span data-ttu-id="54d95-162">如果您看到全部大写的则所有 caps 中输入计算机名称。</span><span class="sxs-lookup"><span data-stu-id="54d95-162">If you see all caps, then enter the computer name in all caps.</span></span> 
> 
> ![计算机名称是在全大写形式](../core/media/groups-case.png)

## <a name="step-2-use-the-template-in-power-bi"></a><span data-ttu-id="54d95-164">步骤 2： 在 Power BI 中使用模板</span><span class="sxs-lookup"><span data-stu-id="54d95-164">Step 2: Use the template in Power BI</span></span>

1. <span data-ttu-id="54d95-165">下载并安装[Power BI Desktop](https://powerbi.microsoft.com/desktop/) BizTalk 服务器上。</span><span class="sxs-lookup"><span data-stu-id="54d95-165">Download and install the [Power BI Desktop](https://powerbi.microsoft.com/desktop/) on your BizTalk Server.</span></span> <span data-ttu-id="54d95-166">您可以选择将其打开，它是可选的。</span><span class="sxs-lookup"><span data-stu-id="54d95-166">You can select to open it, which is optional.</span></span> <span data-ttu-id="54d95-167">如果您有工作或学校帐户，可能有权访问 Power BI。</span><span class="sxs-lookup"><span data-stu-id="54d95-167">If you have a work or school account, you may have access to Power BI.</span></span> <span data-ttu-id="54d95-168">请尝试使用该帐户登录。</span><span class="sxs-lookup"><span data-stu-id="54d95-168">Try signing in with that account.</span></span> <span data-ttu-id="54d95-169">或者，您可以在注册后免费试用它。</span><span class="sxs-lookup"><span data-stu-id="54d95-169">Or, you can try it for free after signing up.</span></span> 
2. <span data-ttu-id="54d95-170">打开`\Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService`文件夹，并打开`BizTalkOperationalData.pbit`文件：</span><span class="sxs-lookup"><span data-stu-id="54d95-170">Open the `\Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService` folder, and open the `BizTalkOperationalData.pbit` file:</span></span>  
<span data-ttu-id="54d95-171">![打开 pbit 文件](../core/media/operational-data-pbit.png)</span><span class="sxs-lookup"><span data-stu-id="54d95-171">![Open pbit file](../core/media/operational-data-pbit.png)</span></span>

3. <span data-ttu-id="54d95-172">Power BI desktop 将打开，并且会提示输入一个 URL。</span><span class="sxs-lookup"><span data-stu-id="54d95-172">Power BI desktop opens, and you are prompted for a URL.</span></span> <span data-ttu-id="54d95-173">输入`http://localhost/<yourWebSite>`为 OData 数据源创建的 URL。</span><span class="sxs-lookup"><span data-stu-id="54d95-173">Enter the `http://localhost/<yourWebSite>` URL that you created for your OData feed.</span></span> <span data-ttu-id="54d95-174">例如，输入`http://localhost/BizTalkOperationalDataService`。</span><span class="sxs-lookup"><span data-stu-id="54d95-174">For example, enter `http://localhost/BizTalkOperationalDataService`.</span></span> <span data-ttu-id="54d95-175">你的 URL 类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="54d95-175">Your URL looks similar to the following:</span></span>  
<span data-ttu-id="54d95-176">![输入的 URL](../core/media/operational-data-url.png)</span><span class="sxs-lookup"><span data-stu-id="54d95-176">![Enter the URL](../core/media/operational-data-url.png)</span></span>

4. <span data-ttu-id="54d95-177">选择**负载**。</span><span class="sxs-lookup"><span data-stu-id="54d95-177">Select **Load**.</span></span> <span data-ttu-id="54d95-178">在窗口加载并连接到不同的 oData 源 BizTalkOperationalDataService.json 文件中。</span><span class="sxs-lookup"><span data-stu-id="54d95-178">The window loads and connects to the different oData sources in the BizTalkOperationalDataService.json file.</span></span> <span data-ttu-id="54d95-179">操作完成时，仪表板显示有关你的环境的详细信息。</span><span class="sxs-lookup"><span data-stu-id="54d95-179">When it completes, the dashboard shows details about your environment.</span></span>

## <a name="couldnt-authenticate"></a><span data-ttu-id="54d95-180">无法进行身份验证</span><span class="sxs-lookup"><span data-stu-id="54d95-180">Couldn't authenticate</span></span>
<span data-ttu-id="54d95-181">如果收到`couldn't authenticate with the credentials provided`消息类似于以下内容，则可能你的应用程序池标识不具有足够到 BizTalk Server 数据库的访问权限。</span><span class="sxs-lookup"><span data-stu-id="54d95-181">If you get `couldn't authenticate with the credentials provided` message similar to the following, then it’s possible your application pool identity doesn’t have enough access to the BizTalk Server databases.</span></span> <span data-ttu-id="54d95-182">您可以更改 IIS 中的应用程序池标识到具有更多权限的帐户可能已登录用户帐户 （它具有本地管理员权限）。</span><span class="sxs-lookup"><span data-stu-id="54d95-182">You can change the appPool identity within IIS to an account with more privileges, maybe your signed-in user account (which has local admin privileges).</span></span> 

![无法使用提供的凭据进行身份验证](../core/media/operational-data-authentication-error.png)

## <a name="do-more"></a><span data-ttu-id="54d95-184">执行更多操作</span><span class="sxs-lookup"><span data-stu-id="54d95-184">Do more</span></span>
<span data-ttu-id="54d95-185">这仅仅是个开始。</span><span class="sxs-lookup"><span data-stu-id="54d95-185">This is just the beginning.</span></span> <span data-ttu-id="54d95-186">Power BI 还提供可以在本地 BizTalk Server 安装的网关。</span><span class="sxs-lookup"><span data-stu-id="54d95-186">Power BI also has a gateway that can be installed on an on-premises BizTalk Server.</span></span> <span data-ttu-id="54d95-187">使用网关，可以发布你的仪表板，获取实时数据，并创建计划以刷新仪表板。</span><span class="sxs-lookup"><span data-stu-id="54d95-187">Using the gateway, you can publish your dashboard, get real-time data, and create a schedule to refresh the dashboard.</span></span> <span data-ttu-id="54d95-188">以下博客能够很好地详细描述这些步骤：</span><span class="sxs-lookup"><span data-stu-id="54d95-188">The following blog does a great job detailing these steps:</span></span> 

* [<span data-ttu-id="54d95-189">如何将发布 Power BI – 分步配置上的 BizTalk 操作数据</span><span class="sxs-lookup"><span data-stu-id="54d95-189">How to publish BizTalk operational data on Power BI – Step-by-step configuration</span></span>](https://blog.sandro-pereira.com/2017/05/07/biztalk-server-2016-feature-pack-1-how-to-publish-biztalk-operational-data-power-bi-step-by-step-configuration-part-3/)

<span data-ttu-id="54d95-190">[引导式学习](https://powerbi.microsoft.com/guided-learning/)也是一个很好的了解有关 Power BI 的详细信息以及您可以执行的所有操作。</span><span class="sxs-lookup"><span data-stu-id="54d95-190">The [Guided Learning](https://powerbi.microsoft.com/guided-learning/) is also a great place to learn more about Power BI, and all the things you can do.</span></span> 

## <a name="see-also"></a><span data-ttu-id="54d95-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54d95-191">See also</span></span>

[<span data-ttu-id="54d95-192">了解有关 Power BI 的详细信息</span><span class="sxs-lookup"><span data-stu-id="54d95-192">Learn more about Power BI</span></span>](https://www.powerbi.com)  
[<span data-ttu-id="54d95-193">配置功能包</span><span class="sxs-lookup"><span data-stu-id="54d95-193">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)
