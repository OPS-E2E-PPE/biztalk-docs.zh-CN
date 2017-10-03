---
title: "安装和配置 Microsoft BizTalk ESB 工具包 |Microsoft 文档"
description: "步骤的步骤说明上安装和配置 ESB 工具包 BizTalk Server"
caps.latest.revision: "8"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 698843f7-8361-4d02-9278-0e66f2a9f472
ms.author: mandia
ms.openlocfilehash: 33805fe58298e4f4729161a62742d3b204996b00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-and-configure-the-microsoft-biztalk-esb-toolkit"></a><span data-ttu-id="b71eb-103">安装和配置 Microsoft BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="b71eb-103">Install and configure the Microsoft BizTalk ESB Toolkit</span></span>
<span data-ttu-id="b71eb-104">使用 BizTalk Server 2013 和更高版本中，启动[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]与集成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="b71eb-104">Starting with BizTalk Server 2013 and newer versions, [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is integrated with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup.</span></span> <span data-ttu-id="b71eb-105">本主题说明如何安装和配置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，并且还包括社区编写的链接，以升级 ESB 工具包。</span><span class="sxs-lookup"><span data-stu-id="b71eb-105">This topic shows you how to install and configure [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and also includes a community-written link to upgrade the ESB Toolkit.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b71eb-106">你必须先安装 BizTalk Server，然后才能开始安装 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b71eb-106">You must have BizTalk Server installed before you start installing the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
## <a name="install"></a><span data-ttu-id="b71eb-107">Install</span><span class="sxs-lookup"><span data-stu-id="b71eb-107">Install</span></span> 
  
1.  <span data-ttu-id="b71eb-108">运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以管理员身份的 setup.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="b71eb-108">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup.exe file as Administrator.</span></span> <span data-ttu-id="b71eb-109">在设置中，选择**安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** 。</span><span class="sxs-lookup"><span data-stu-id="b71eb-109">In setup, select **Install [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**.</span></span>  
  
2.  <span data-ttu-id="b71eb-110">接受许可协议，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-110">Accept the license agreement, and then select **Next**.</span></span>  
  
3.  <span data-ttu-id="b71eb-111">在“组件安装”中，选择要安装的组件，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="b71eb-111">In **Component Installation**, select the components you want to install, and then select **Next**.</span></span>  
  
4.  <span data-ttu-id="b71eb-112">在**摘要**，查看您选择，，然后选择**安装**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-112">In the **Summary**, review what you chose, and then select **Install**.</span></span>  
  
5.  <span data-ttu-id="b71eb-113">选择“完成”关闭安装向导。</span><span class="sxs-lookup"><span data-stu-id="b71eb-113">Select **Finish** to close the installation wizard.</span></span>  

<span data-ttu-id="b71eb-114">安装日志文件将创建，类似于 C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm。</span><span class="sxs-lookup"><span data-stu-id="b71eb-114">An install log file is created, similar to \`C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm'.</span></span> 
  
## <a name="configure"></a><span data-ttu-id="b71eb-115">配置</span><span class="sxs-lookup"><span data-stu-id="b71eb-115">Configure</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="b71eb-116">你必须先配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后才能配置 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b71eb-116">You must configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] before configuring [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
1.  <span data-ttu-id="b71eb-117">从**启动**菜单上，选择**Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** ，然后选择**ESB 配置工具**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-117">From the **Start** menu, select **Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**, and then select **ESB Configuration Tool**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b71eb-118">以管理员身份运行 ESB 配置工具。</span><span class="sxs-lookup"><span data-stu-id="b71eb-118">Run the ESB Configuration Tool as an administrator.</span></span>  
  
2.  <span data-ttu-id="b71eb-119">在配置中，选择**数据库服务器**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-119">In the configuration, select **Database Server**.</span></span> <span data-ttu-id="b71eb-120">输入数据库服务器名称承载[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="b71eb-120">Enter the database server name that hosts the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] databases.</span></span>   
  
3.  <span data-ttu-id="b71eb-121">在**IIS Web 服务**，输入用户帐户和运行创建的 IIS 应用程序的密码[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b71eb-121">In **IIS Web Services**, enter the user account and password that runs the IIS applications created by the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span> <span data-ttu-id="b71eb-122">接下来，输入承载应用程序的 IIS 网站。</span><span class="sxs-lookup"><span data-stu-id="b71eb-122">Next, enter the IIS website that hosts the applications.</span></span>  
  
4.  <span data-ttu-id="b71eb-123">**BizTalk 用户组**列出通常用于 ESB 配置的默认用户组。</span><span class="sxs-lookup"><span data-stu-id="b71eb-123">The **BizTalk User Groups** lists the default user groups typically used for ESB configuration.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b71eb-124">在此阶段，你可以选择**应用配置**配置[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]使用这些默认设置。</span><span class="sxs-lookup"><span data-stu-id="b71eb-124">At this stage, you can select **Apply Configuration** to configure the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] with these default settings.</span></span> <span data-ttu-id="b71eb-125">但是，如果你想要自定义配置，则完成剩余步骤。</span><span class="sxs-lookup"><span data-stu-id="b71eb-125">However, if you want to do a custom configuration, complete the remaining steps.</span></span> <span data-ttu-id="b71eb-126">在后续步骤中输入的 Rhe 值优先于默认值。</span><span class="sxs-lookup"><span data-stu-id="b71eb-126">Rhe values you enter in the next steps take precedence over the default values.</span></span>  
  
5.  <span data-ttu-id="b71eb-127">在左窗格中，展开**ESB 配置**，展开 * * 异常管理 * *，然后：</span><span class="sxs-lookup"><span data-stu-id="b71eb-127">In the left pane, expand **ESB Configuration**, expand ** Exception Management**, and then:</span></span>  
  
    -   <span data-ttu-id="b71eb-128">如果你不想要配置异常管理数据库，然后选择**数据库**，并取消选中**启用异常管理数据库**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-128">If you don't want to configure an exception management database, then select **Database**, and uncheck the **Enable Exception Management Database**.</span></span>
  
    -   <span data-ttu-id="b71eb-129">如果你想要使用现有数据库，而不是创建一个新数据库，然后选择**数据库**，然后选择**使用现有数据库**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-129">If you want to use an existing database instead of creating a new database, then select **Database**, and select the **Use Existing Database**.</span></span> <span data-ttu-id="b71eb-130">输入数据库服务器名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="b71eb-130">Enter the database server name and the database name.</span></span>  
  
    -   <span data-ttu-id="b71eb-131">如果你不想要配置异常 web 服务，然后选择**异常 Web 服务**，并取消选中**启用异常服务**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-131">If you don't want to configure exception web service, then select **Exception Web Services**, and uncheck **Enable Exception Services**.</span></span>  <span data-ttu-id="b71eb-132">如果你想要运行这些服务在不同的网站下，你可以在此处输入的。</span><span class="sxs-lookup"><span data-stu-id="b71eb-132">If you want to run these services under a different website, you can enter that here.</span></span>  
  
6.  <span data-ttu-id="b71eb-133">在左窗格中，展开**ESB 核心组件**，，然后：</span><span class="sxs-lookup"><span data-stu-id="b71eb-133">In the left pane, expand **ESB Core Components**, and then:</span></span>  
  
    -   <span data-ttu-id="b71eb-134">如果你不想要配置路线数据库，然后选择**路线数据库**，并取消选中**路线数据库**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-134">If you don't want to configure an itinerary database, then select **Itinerary Database**, and uncheck **Itinerary Database** .</span></span>  
  
    -   <span data-ttu-id="b71eb-135">如果你想要使用现有路线数据库，然后选择**路线数据库**，然后选择**使用现有数据库**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-135">If you want to use an existing itinerary database, then select **Itinerary Database**, and select **Use Existing Database**.</span></span> <span data-ttu-id="b71eb-136">输入数据库服务器名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="b71eb-136">Enter the database server name and the database name.</span></span>  
  
    -   <span data-ttu-id="b71eb-137">如果你不想要配置这些 web 服务，然后选择**核心 Web 服务**，并取消选中**启用核心服务**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-137">If you don't want to configure these web service, then select **Core Web Services**, and uncheck **Enable Core Services**.</span></span> <span data-ttu-id="b71eb-138">如果你想要运行这些服务在不同的网站下，你可以在此处输入的。</span><span class="sxs-lookup"><span data-stu-id="b71eb-138">If you want to run these services under a different website, you can enter that here.</span></span>
  
7.  <span data-ttu-id="b71eb-139">在左窗格中，选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-139">In the left pane, select **Configuration**.</span></span>  
    <span data-ttu-id="b71eb-140">如果你安装和配置[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]在单个服务器环境中，选择**文件配置源**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-140">If you are installing and configuring the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] in a single server environment, select **File Configuration Source**.</span></span> <span data-ttu-id="b71eb-141">如果您设置了多计算机部署，选择**SSO 配置源**，然后输入以下：</span><span class="sxs-lookup"><span data-stu-id="b71eb-141">If you are setting up a multiple-machine deployment, select the **SSO Configuration Source**, and then enter the following:</span></span>  
  
    -   <span data-ttu-id="b71eb-142">**SSO 服务器**： 输入 SSO 服务器的名称</span><span class="sxs-lookup"><span data-stu-id="b71eb-142">**SSO Server**: Enter the name of the SSO server</span></span>
  
    -   <span data-ttu-id="b71eb-143">**配置文件**： 选择省略号**（...）**，然后浏览到 esb.config 文件 (\Program Files (x86) \Microsoft BizTalk ESB 工具包)</span><span class="sxs-lookup"><span data-stu-id="b71eb-143">**Configuration file**: Select the ellipsis **(…)**, and then browse to the esb.config file (\Program Files (x86)\Microsoft BizTalk ESB Toolkit)</span></span>
  
    -   <span data-ttu-id="b71eb-144">**应用程序名称**： 输入 SSO 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="b71eb-144">**Application Name**: Enter a name for the SSO application.</span></span> <span data-ttu-id="b71eb-145">例如，输入`ESB Toolkit`。</span><span class="sxs-lookup"><span data-stu-id="b71eb-145">For example,  enter `ESB Toolkit`.</span></span>  
  
    -   <span data-ttu-id="b71eb-146">**联系信息**： 采用以下格式输入有效的电子邮件地址的合适的联系信息： `someone@example.com`。</span><span class="sxs-lookup"><span data-stu-id="b71eb-146">**Contact Information**: Enter a valid email address the appropriate contact information in the following format: `someone@example.com`.</span></span>  
  
    -   <span data-ttu-id="b71eb-147">**管理员组名称**： 选择省略号**（...）**，然后浏览到相应的管理员组</span><span class="sxs-lookup"><span data-stu-id="b71eb-147">**Administrator Group Name**: Select the ellipsis **(…)**, and then browse to the appropriate admin group</span></span>  
  
    -   <span data-ttu-id="b71eb-148">**用户组名称**： 选择省略号**（...）**，然后浏览到相应的组</span><span class="sxs-lookup"><span data-stu-id="b71eb-148">**User Group Name**: Select the ellipsis **(…)**, and then browse to the appropriate group</span></span>  

8.  <span data-ttu-id="b71eb-149">选择**应用配置**。</span><span class="sxs-lookup"><span data-stu-id="b71eb-149">Select **Apply Configuration**.</span></span> <span data-ttu-id="b71eb-150">打开 IIS，并请注意，现在已在配置 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]时指定的网站下创建了 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b71eb-150">Open IIS and notice that the applications required for [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] are now created under the website you specified while configuring [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
9. <span data-ttu-id="b71eb-151">在**ESB 配置工具**，选择**ESB BizTalk 应用程序**，，然后：</span><span class="sxs-lookup"><span data-stu-id="b71eb-151">In the **ESB Configuration Tool**, select **ESB BizTalk Applications**, and then:</span></span>  
  
    -   <span data-ttu-id="b71eb-152">选择**BizTalk Server 中启用 ESB 的核心组件**创建中的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b71eb-152">Select **Enable ESB Core Components in BizTalk Server** to create the application in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="b71eb-153">选择**使用默认绑定**要绑定到默认主机此应用程序。</span><span class="sxs-lookup"><span data-stu-id="b71eb-153">Select **Use Default Binding** to bind this application to the default host.</span></span> <span data-ttu-id="b71eb-154">选择**不使用默认绑定**如果你不想要绑定到默认主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="b71eb-154">Select **Do not use Default Binding** if you do not want to bind the application to the default host.</span></span> <span data-ttu-id="b71eb-155">在此方案中，你必须显式将绑定到主机应用程序后创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="b71eb-155">In this scenario, you must explicitly bind the application to a host once the application is created.</span></span>  
  
    -   <span data-ttu-id="b71eb-156">选择**BizTalk Server 中启用 ESB JMS/WMQ 组件**创建中的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b71eb-156">Select **Enable ESB JMS/WMQ Components in BizTalk Server** to create the application in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="b71eb-157">选择**使用默认绑定**要绑定到默认主机此应用程序。</span><span class="sxs-lookup"><span data-stu-id="b71eb-157">Select **Use Default Binding** to bind this application to the default host.</span></span> <span data-ttu-id="b71eb-158">选择**不使用默认绑定**如果你不想要绑定到默认主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="b71eb-158">Select **Do not use Default Binding** if you do not want to bind the application to the default host.</span></span> <span data-ttu-id="b71eb-159">在此方案中，你必须显式将绑定到主机应用程序后创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="b71eb-159">In this scenario, you must explicitly bind the application to a host once the application is created.</span></span>  
  
    -   <span data-ttu-id="b71eb-160">选择**应用配置**创建你选定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b71eb-160">Select **Apply Configuration** to create the applications you selected.</span></span> <span data-ttu-id="b71eb-161">验证是否在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建了该应用程序。</span><span class="sxs-lookup"><span data-stu-id="b71eb-161">Verify that the applications are created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="upgrade-esb-toolkit--community-addition"></a><span data-ttu-id="b71eb-162">升级 ESB 工具包 – 社区加码</span><span class="sxs-lookup"><span data-stu-id="b71eb-162">Upgrade ESB Toolkit – Community Addition</span></span>  
 <span data-ttu-id="b71eb-163">[将 ESB 工具包 2.1 就地升级到 2.2](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html) (http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)</span><span class="sxs-lookup"><span data-stu-id="b71eb-163">[In-place upgrade of ESB Toolkit 2.1 to 2.2](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html) (http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)</span></span>

## <a name="see-also"></a><span data-ttu-id="b71eb-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b71eb-164">See also</span></span>
[<span data-ttu-id="b71eb-165">解决安装问题，以及常见的错误和解决方法</span><span class="sxs-lookup"><span data-stu-id="b71eb-165">Troubleshoot installation issues, and common errors & resolutions</span></span>](troubleshooting-the-biztalk-esb-toolkit.md)