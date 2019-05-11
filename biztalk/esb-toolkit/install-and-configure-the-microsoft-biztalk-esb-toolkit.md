---
title: 安装和配置 Microsoft BizTalk ESB 工具包 |Microsoft Docs
description: 若要安装和配置 BizTalk Server 上的 ESB 工具包的步骤的步骤说明
caps.latest.revision: 8
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 698843f7-8361-4d02-9278-0e66f2a9f472
ms.author: mandia
ms.openlocfilehash: 1672b3c2afd7dbca1f1843dedea81111a0a5a6a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400307"
---
# <a name="install-and-configure-the-microsoft-biztalk-esb-toolkit"></a><span data-ttu-id="4ace7-103">安装和配置 Microsoft BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="4ace7-103">Install and configure the Microsoft BizTalk ESB Toolkit</span></span>
<span data-ttu-id="4ace7-104">使用 BizTalk Server 2013 和较新版本中，启动[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]与集成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="4ace7-104">Starting with BizTalk Server 2013 and newer versions, [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is integrated with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup.</span></span> <span data-ttu-id="4ace7-105">本主题说明如何安装和配置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，并且还包括用于升级 ESB 工具包的社区编写的链接。</span><span class="sxs-lookup"><span data-stu-id="4ace7-105">This topic shows you how to install and configure [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and also includes a community-written link to upgrade the ESB Toolkit.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4ace7-106">必须具有已开始安装之前安装 BizTalk Server [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ace7-106">You must have BizTalk Server installed before you start installing the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
## <a name="install"></a><span data-ttu-id="4ace7-107">安装</span><span class="sxs-lookup"><span data-stu-id="4ace7-107">Install</span></span> 
  
1. <span data-ttu-id="4ace7-108">运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]setup.exe 文件，以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="4ace7-108">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup.exe file as Administrator.</span></span> <span data-ttu-id="4ace7-109">在安装过程中，选择**安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** 。</span><span class="sxs-lookup"><span data-stu-id="4ace7-109">In setup, select **Install [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**.</span></span>  
  
2. <span data-ttu-id="4ace7-110">接受许可协议，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-110">Accept the license agreement, and then select **Next**.</span></span>  
  
3. <span data-ttu-id="4ace7-111">在中**组件安装**，选择你想要安装，然后选择的组件**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-111">In **Component Installation**, select the components you want to install, and then select **Next**.</span></span>  
  
4. <span data-ttu-id="4ace7-112">在中**摘要**，查看您选择，然后选择**安装**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-112">In the **Summary**, review what you chose, and then select **Install**.</span></span>  
  
5. <span data-ttu-id="4ace7-113">选择**完成**若要关闭安装向导。</span><span class="sxs-lookup"><span data-stu-id="4ace7-113">Select **Finish** to close the installation wizard.</span></span>  

<span data-ttu-id="4ace7-114">安装日志会创建一个文件，类似于 C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm。</span><span class="sxs-lookup"><span data-stu-id="4ace7-114">An install log file is created, similar to \`C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm'.</span></span> 
  
## <a name="configure"></a><span data-ttu-id="4ace7-115">配置</span><span class="sxs-lookup"><span data-stu-id="4ace7-115">Configure</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="4ace7-116">必须配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置之前[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ace7-116">You must configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] before configuring [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
1. <span data-ttu-id="4ace7-117">从**启动**菜单中，选择**Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** ，然后选择**ESB 配置工具**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-117">From the **Start** menu, select **Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**, and then select **ESB Configuration Tool**.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="4ace7-118">以管理员身份运行 ESB 配置工具。</span><span class="sxs-lookup"><span data-stu-id="4ace7-118">Run the ESB Configuration Tool as an administrator.</span></span>  
  
2. <span data-ttu-id="4ace7-119">在配置中，选择**数据库服务器**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-119">In the configuration, select **Database Server**.</span></span> <span data-ttu-id="4ace7-120">输入承载的数据库服务器名称[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="4ace7-120">Enter the database server name that hosts the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] databases.</span></span>   
  
3. <span data-ttu-id="4ace7-121">在中**IIS Web 服务**，输入用户帐户和运行创建的 IIS 应用程序的密码[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ace7-121">In **IIS Web Services**, enter the user account and password that runs the IIS applications created by the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span> <span data-ttu-id="4ace7-122">接下来，输入承载应用程序的 IIS 网站。</span><span class="sxs-lookup"><span data-stu-id="4ace7-122">Next, enter the IIS website that hosts the applications.</span></span>  
  
4. <span data-ttu-id="4ace7-123">**BizTalk 用户组**列出了通常用于 ESB 配置的默认用户组。</span><span class="sxs-lookup"><span data-stu-id="4ace7-123">The **BizTalk User Groups** lists the default user groups typically used for ESB configuration.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="4ace7-124">在此阶段，你可以选择**应用配置**若要配置[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]使用这些默认设置。</span><span class="sxs-lookup"><span data-stu-id="4ace7-124">At this stage, you can select **Apply Configuration** to configure the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] with these default settings.</span></span> <span data-ttu-id="4ace7-125">但是，如果你想要进行自定义配置，完成剩余步骤。</span><span class="sxs-lookup"><span data-stu-id="4ace7-125">However, if you want to do a custom configuration, complete the remaining steps.</span></span> <span data-ttu-id="4ace7-126">按照下一步骤中输入的值优先于默认值。</span><span class="sxs-lookup"><span data-stu-id="4ace7-126">Rhe values you enter in the next steps take precedence over the default values.</span></span>  
  
5. <span data-ttu-id="4ace7-127">在左窗格中，展开**ESB 配置**，展开 \* \* 异常管理 \* \*，然后：</span><span class="sxs-lookup"><span data-stu-id="4ace7-127">In the left pane, expand **ESB Configuration**, expand \*\* Exception Management\*\*, and then:</span></span>  
  
   -   <span data-ttu-id="4ace7-128">如果不想配置例外管理数据库，然后选择**数据库**，并取消选中**启用例外管理数据库**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-128">If you don't want to configure an exception management database, then select **Database**, and uncheck the **Enable Exception Management Database**.</span></span>
  
   -   <span data-ttu-id="4ace7-129">如果你想要使用现有数据库，而不是创建一个新数据库，然后选择**数据库**，然后选择**使用现有数据库**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-129">If you want to use an existing database instead of creating a new database, then select **Database**, and select the **Use Existing Database**.</span></span> <span data-ttu-id="4ace7-130">输入数据库服务器名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="4ace7-130">Enter the database server name and the database name.</span></span>  
  
   -   <span data-ttu-id="4ace7-131">如果不想配置异常 web 服务，然后选择**异常 Web 服务**，并取消选中**启用异常服务**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-131">If you don't want to configure exception web service, then select **Exception Web Services**, and uncheck **Enable Exception Services**.</span></span>  <span data-ttu-id="4ace7-132">如果你想要不同的网站下运行这些服务，你可以在此处输入的。</span><span class="sxs-lookup"><span data-stu-id="4ace7-132">If you want to run these services under a different website, you can enter that here.</span></span>  
  
6. <span data-ttu-id="4ace7-133">在左窗格中，展开**ESB 核心组件**，，然后：</span><span class="sxs-lookup"><span data-stu-id="4ace7-133">In the left pane, expand **ESB Core Components**, and then:</span></span>  
  
   -   <span data-ttu-id="4ace7-134">如果不想配置行程数据库，然后选择**行程数据库**，并取消选中**行程数据库**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-134">If you don't want to configure an itinerary database, then select **Itinerary Database**, and uncheck **Itinerary Database** .</span></span>  
  
   -   <span data-ttu-id="4ace7-135">如果你想要使用现有的行程数据库，然后选择**行程数据库**，然后选择**使用现有数据库**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-135">If you want to use an existing itinerary database, then select **Itinerary Database**, and select **Use Existing Database**.</span></span> <span data-ttu-id="4ace7-136">输入数据库服务器名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="4ace7-136">Enter the database server name and the database name.</span></span>  
  
   -   <span data-ttu-id="4ace7-137">如果不想配置这些 web 服务，然后选择**核心 Web 服务**，并取消选中**启用核心服务**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-137">If you don't want to configure these web service, then select **Core Web Services**, and uncheck **Enable Core Services**.</span></span> <span data-ttu-id="4ace7-138">如果你想要不同的网站下运行这些服务，你可以在此处输入的。</span><span class="sxs-lookup"><span data-stu-id="4ace7-138">If you want to run these services under a different website, you can enter that here.</span></span>
  
7. <span data-ttu-id="4ace7-139">在左窗格中，选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-139">In the left pane, select **Configuration**.</span></span>  
   <span data-ttu-id="4ace7-140">如果在安装和配置[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]在单服务器环境中，选择**文件配置源**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-140">If you are installing and configuring the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] in a single server environment, select **File Configuration Source**.</span></span> <span data-ttu-id="4ace7-141">如果您设置了多计算机部署，请选择**SSO 配置源**，然后输入以下：</span><span class="sxs-lookup"><span data-stu-id="4ace7-141">If you are setting up a multiple-machine deployment, select the **SSO Configuration Source**, and then enter the following:</span></span>  
  
   -   <span data-ttu-id="4ace7-142">**SSO 服务器**:输入 SSO 服务器的名称</span><span class="sxs-lookup"><span data-stu-id="4ace7-142">**SSO Server**: Enter the name of the SSO server</span></span>
  
   -   <span data-ttu-id="4ace7-143">**配置文件**:选择省略号 **（...）**，然后浏览到 esb.config 文件 (\Program 文件 (x86) \Microsoft BizTalk ESB 工具包)</span><span class="sxs-lookup"><span data-stu-id="4ace7-143">**Configuration file**: Select the ellipsis **(…)**, and then browse to the esb.config file (\Program Files (x86)\Microsoft BizTalk ESB Toolkit)</span></span>
  
   -   <span data-ttu-id="4ace7-144">**应用程序名称**:输入 SSO 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="4ace7-144">**Application Name**: Enter a name for the SSO application.</span></span> <span data-ttu-id="4ace7-145">例如，输入`ESB Toolkit`。</span><span class="sxs-lookup"><span data-stu-id="4ace7-145">For example,  enter `ESB Toolkit`.</span></span>  
  
   -   <span data-ttu-id="4ace7-146">**联系信息**:按以下格式输入有效的电子邮件地址的相应的联系信息： `someone@example.com`。</span><span class="sxs-lookup"><span data-stu-id="4ace7-146">**Contact Information**: Enter a valid email address the appropriate contact information in the following format: `someone@example.com`.</span></span>  
  
   -   <span data-ttu-id="4ace7-147">**管理员组名称**:选择省略号 **（...）**，然后浏览到适当的管理组</span><span class="sxs-lookup"><span data-stu-id="4ace7-147">**Administrator Group Name**: Select the ellipsis **(…)**, and then browse to the appropriate admin group</span></span>  
  
   -   <span data-ttu-id="4ace7-148">**用户组名称**:选择省略号 **（...）**，然后浏览到相应的组</span><span class="sxs-lookup"><span data-stu-id="4ace7-148">**User Group Name**: Select the ellipsis **(…)**, and then browse to the appropriate group</span></span>  

8. <span data-ttu-id="4ace7-149">选择**应用配置**。</span><span class="sxs-lookup"><span data-stu-id="4ace7-149">Select **Apply Configuration**.</span></span> <span data-ttu-id="4ace7-150">打开 IIS，并请注意，应用程序所需的[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]现在配置时指定在网站下创建[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ace7-150">Open IIS and notice that the applications required for [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] are now created under the website you specified while configuring [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
9. <span data-ttu-id="4ace7-151">在中**ESB 配置工具**，选择**ESB BizTalk 应用程序**，，然后：</span><span class="sxs-lookup"><span data-stu-id="4ace7-151">In the **ESB Configuration Tool**, select **ESB BizTalk Applications**, and then:</span></span>  
  
   - <span data-ttu-id="4ace7-152">选择**BizTalk Server 中启用 ESB 核心组件**若要创建中的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4ace7-152">Select **Enable ESB Core Components in BizTalk Server** to create the application in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="4ace7-153">选择**使用默认绑定**要绑定到默认主机的此应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ace7-153">Select **Use Default Binding** to bind this application to the default host.</span></span> <span data-ttu-id="4ace7-154">选择**不使用默认绑定**如果确实想要绑定到默认主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ace7-154">Select **Do not use Default Binding** if you do not want to bind the application to the default host.</span></span> <span data-ttu-id="4ace7-155">在此方案中，您必须显式将绑定到主机应用程序后创建的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ace7-155">In this scenario, you must explicitly bind the application to a host once the application is created.</span></span>  
  
   - <span data-ttu-id="4ace7-156">选择**在 BizTalk Server 中启用 ESB JMS/WMQ 组件**若要创建中的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4ace7-156">Select **Enable ESB JMS/WMQ Components in BizTalk Server** to create the application in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="4ace7-157">选择**使用默认绑定**要绑定到默认主机的此应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ace7-157">Select **Use Default Binding** to bind this application to the default host.</span></span> <span data-ttu-id="4ace7-158">选择**不使用默认绑定**如果确实想要绑定到默认主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ace7-158">Select **Do not use Default Binding** if you do not want to bind the application to the default host.</span></span> <span data-ttu-id="4ace7-159">在此方案中，您必须显式将绑定到主机应用程序后创建的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ace7-159">In this scenario, you must explicitly bind the application to a host once the application is created.</span></span>  
  
   - <span data-ttu-id="4ace7-160">选择**应用配置**创建所选的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ace7-160">Select **Apply Configuration** to create the applications you selected.</span></span> <span data-ttu-id="4ace7-161">验证是否在创建了应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4ace7-161">Verify that the applications are created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="upgrade-esb-toolkit--community-addition"></a><span data-ttu-id="4ace7-162">升级 ESB 工具包 – 社区添加内容</span><span class="sxs-lookup"><span data-stu-id="4ace7-162">Upgrade ESB Toolkit – Community Addition</span></span>  
 <span data-ttu-id="4ace7-163">[就地将 ESB 工具包 2.1 升级到 2.2](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html) (http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)</span><span class="sxs-lookup"><span data-stu-id="4ace7-163">[In-place upgrade of ESB Toolkit 2.1 to 2.2](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html) (http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)</span></span>

## <a name="see-also"></a><span data-ttu-id="4ace7-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ace7-164">See also</span></span>
[<span data-ttu-id="4ace7-165">排查安装问题和常见错误和解决方法</span><span class="sxs-lookup"><span data-stu-id="4ace7-165">Troubleshoot installation issues, and common errors & resolutions</span></span>](troubleshooting-the-biztalk-esb-toolkit.md)