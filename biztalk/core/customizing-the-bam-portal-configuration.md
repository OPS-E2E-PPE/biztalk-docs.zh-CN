---
title: 自定义 BAM 门户配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 507bd5f0-b2a0-4d52-85f8-9d984138ca79
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4749ada0c4e85252403a10dbe88d0f7ea2191a94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353168"
---
# <a name="customizing-the-bam-portal-configuration"></a><span data-ttu-id="953fa-102">自定义 BAM 门户配置</span><span class="sxs-lookup"><span data-stu-id="953fa-102">Customizing the BAM Portal Configuration</span></span>
<span data-ttu-id="953fa-103">有许多在 BAM 门户网站上的可配置选项。</span><span class="sxs-lookup"><span data-stu-id="953fa-103">There are a number of configurable options on the BAM portal.</span></span> <span data-ttu-id="953fa-104">以下过程介绍如何修改 BAM 门户，以获取最佳用户体验。</span><span class="sxs-lookup"><span data-stu-id="953fa-104">The following procedures show you how to modify the BAM portal to obtain the best user experience.</span></span>  

> [!NOTE]
>  <span data-ttu-id="953fa-105">当以非管理员身份配置门户模拟用户时，它可能有必要，以便先注销，然后再登录后才可以访问 BAM 门户功能而无需输入凭据。</span><span class="sxs-lookup"><span data-stu-id="953fa-105">When configuring the portal as a non-administrator impersonated user, it may be necessary for you to log off and then log back on before you have access to the BAM portal features without being asked to enter your credentials.</span></span> <span data-ttu-id="953fa-106">例如，考虑以下方案：</span><span class="sxs-lookup"><span data-stu-id="953fa-106">For example, consider the following scenario:</span></span>  
>   
>  <span data-ttu-id="953fa-107">使用非管理员模拟用户配置的 Web 服务或 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="953fa-107">You configure the Web service or BAM portal with a non-administrator impersonated user.</span></span> <span data-ttu-id="953fa-108">Everyone 组不具有对门户的访问，在门户上然后设置了权限。</span><span class="sxs-lookup"><span data-stu-id="953fa-108">You then set permissions on the portal such that the Everyone group does not have access to the portal.</span></span> <span data-ttu-id="953fa-109">然后创建名为 PortalUsersGroup 的本地组并将该组作为 Portal Users 组。</span><span class="sxs-lookup"><span data-stu-id="953fa-109">You then create a local group called PortalUsersGroup and assign that group as the Portal Users group.</span></span> <span data-ttu-id="953fa-110">这意味着只有该组中的用户有权访问门户。</span><span class="sxs-lookup"><span data-stu-id="953fa-110">This means that only users in that group have access to the portal.</span></span> <span data-ttu-id="953fa-111">配置 BAM 门户后，将当前用户添加到 Portal Users 组。</span><span class="sxs-lookup"><span data-stu-id="953fa-111">After you have configured the BAM portal, add the current user to the Portal Users group.</span></span> <span data-ttu-id="953fa-112">当您打开 BAM 门户时，你将要求输入凭据。</span><span class="sxs-lookup"><span data-stu-id="953fa-112">When you open the BAM portal, you will be asked for your credentials.</span></span> <span data-ttu-id="953fa-113">注销并重新登录，但是，你能够打开 BAM 门户，而不要求提供凭据。</span><span class="sxs-lookup"><span data-stu-id="953fa-113">If you log off and log back on, however, you are able to open the BAM portal without being asked for your credentials.</span></span>  
>   
>  <span data-ttu-id="953fa-114">BizTalk Server 支持只在单台计算机配置中的本地组和用户帐户。</span><span class="sxs-lookup"><span data-stu-id="953fa-114">BizTalk Server supports local group and user accounts only in single computer configurations.</span></span> <span data-ttu-id="953fa-115">BizTalk Server 支持单个和多计算机配置中的域组和用户帐户。</span><span class="sxs-lookup"><span data-stu-id="953fa-115">BizTalk Server supports domain group and user accounts in both single and multiple computer configurations.</span></span>  

## <a name="running-the-bam-portal-in-a-64-bit-environment"></a><span data-ttu-id="953fa-116">在 64 位环境下运行 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="953fa-116">Running the BAM Portal in a 64-bit Environment</span></span>  
 <span data-ttu-id="953fa-117">如果在 64 位环境中使用 Internet 信息服务 (IIS)，则必须将 IIS 设置为 32 位模式运行 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="953fa-117">If you are using Internet Information Services (IIS) in a 64-bit environment, you must set IIS to 32-bit mode to run the BAM portal.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="953fa-118">您不必将 IIS7 设置为 32 位模式。</span><span class="sxs-lookup"><span data-stu-id="953fa-118">You do not have to set IIS7 to 32-bit mode.</span></span>  

#### <a name="to-set-a-64-bit-mode-iis-installation-to-32-bit-mode"></a><span data-ttu-id="953fa-119">若要设置为 32 位模式下的 64 位模式下的 IIS 安装</span><span class="sxs-lookup"><span data-stu-id="953fa-119">To set a 64-bit mode IIS installation to 32-bit mode</span></span>  

1.  <span data-ttu-id="953fa-120">打开命令提示符并运行**adsutil**命令。</span><span class="sxs-lookup"><span data-stu-id="953fa-120">Open a command prompt and run the **adsutil** command.</span></span> <span data-ttu-id="953fa-121">若要执行此操作，请单击**启动**，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="953fa-121">To do this, click **Start**, click **Run**, and then type **cmd**.</span></span>  

2.  <span data-ttu-id="953fa-122">在命令提示符下键入以下内容： `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`。</span><span class="sxs-lookup"><span data-stu-id="953fa-122">Type the following at the command prompt: `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`.</span></span>  

3.  <span data-ttu-id="953fa-123">关闭命令提示符。</span><span class="sxs-lookup"><span data-stu-id="953fa-123">Close the command prompt.</span></span>  

## <a name="configuring-the-bam-portal-banner"></a><span data-ttu-id="953fa-124">配置 BAM 门户横幅</span><span class="sxs-lookup"><span data-stu-id="953fa-124">Configuring the BAM Portal Banner</span></span>  
 <span data-ttu-id="953fa-125">可以修改 BAM 门户页以显示类似文本和有关您业务的图形：</span><span class="sxs-lookup"><span data-stu-id="953fa-125">You can modify the BAM portal page to display similar text and graphics about your business:</span></span>  

- <span data-ttu-id="953fa-126">Windows Server System 徽标，它位于 BAM 门户页的右上角。</span><span class="sxs-lookup"><span data-stu-id="953fa-126">The Windows Server System logo, which is located in the upper-right corner of the BAM portal page.</span></span>  

  <span data-ttu-id="953fa-127">在下面的过程中，您将编辑级联样式表文件 （.css 文件） 以自定义 BAM 门户的外观。</span><span class="sxs-lookup"><span data-stu-id="953fa-127">In the following procedure you edit a cascading style sheet file (.css file) to customize the look of the BAM portal.</span></span> <span data-ttu-id="953fa-128">对指定类的修改均受支持的唯一修改。</span><span class="sxs-lookup"><span data-stu-id="953fa-128">Modifications to the specified classes are the only modifications supported.</span></span> <span data-ttu-id="953fa-129">尽可能多地，对类进行修改的影响已被隔离，以便在修改过程中发生的错误则 BAM 门户仍处于工作状态。</span><span class="sxs-lookup"><span data-stu-id="953fa-129">As much as possible, the impact of modifications to classes has been isolated so that errors made during the modification process leave the BAM portal in a working state.</span></span>  

> [!CAUTION]
>  <span data-ttu-id="953fa-130">修改 styles.css 文件中的其他类将隐藏数据和门户功能，并且可能会使门户不可用。</span><span class="sxs-lookup"><span data-stu-id="953fa-130">Modifying other classes in the styles.css file will hide data and portal features, and may make the portal unusable.</span></span>  

#### <a name="to-configure-the-banner"></a><span data-ttu-id="953fa-131">若要配置横幅</span><span class="sxs-lookup"><span data-stu-id="953fa-131">To configure the banner</span></span>  

1. <span data-ttu-id="953fa-132">编辑 BAM 门户 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-132">Edit the BAM portal web.config file.</span></span> <span data-ttu-id="953fa-133">若要执行此操作，请单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，然后再单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="953fa-133">To do this, click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="953fa-134">主页快速入门内容是可替换通过修改以下行：\<添加键 ="MainPageContentUrl"value="~/MainPageContent.htm"/\>。</span><span class="sxs-lookup"><span data-stu-id="953fa-134">The main page quick-start contents are replaceable by modifying the following line: \<add key="MainPageContentUrl" value="~/MainPageContent.htm"/\>.</span></span> <span data-ttu-id="953fa-135">更改**MainPageContent.htm**值字段，使其指向您自己的 HTML 文件中。</span><span class="sxs-lookup"><span data-stu-id="953fa-135">Change **MainPageContent.htm** in the value field to point to your own HTML file.</span></span> <span data-ttu-id="953fa-136">HTML 文件必须在 web.config 文件所在的同一目录中。</span><span class="sxs-lookup"><span data-stu-id="953fa-136">The HTML file must be in the same directory as the web.config file.</span></span>  

3. <span data-ttu-id="953fa-137">可以更改页标识文本通过将以下行添加到 web.config 文件：\<添加键 ="PortalTitle"value ="新标识 text"/\>。</span><span class="sxs-lookup"><span data-stu-id="953fa-137">Change the page identifying text by adding the following line to the web.config file: \<add key=”PortalTitle” value=”New Identifying text”/\>.</span></span> <span data-ttu-id="953fa-138">更改值字段，以包含标识门户的文本。</span><span class="sxs-lookup"><span data-stu-id="953fa-138">Change the value field to contain the text to identify the portal.</span></span>  

4. <span data-ttu-id="953fa-139">编辑 BAM 门户 styles.css 文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-139">Edit the BAM portal styles.css file.</span></span> <span data-ttu-id="953fa-140">单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="953fa-140">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css, and then click **OK**.</span></span>  

5. <span data-ttu-id="953fa-141">通过找到.headerLogo div 类并将以下行更改中右上角的徽标： 背景图像： url("../ images/WSS_Logo.gif");使其指向已创建的图像文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-141">Change the logo in the upper-right corner by locating the .headerLogo div class and changing the following line:   background-image: url("../images/WSS_Logo.gif"); to point to the image file you have created.</span></span> <span data-ttu-id="953fa-142">我们建议您使用.gif 格式的图像。</span><span class="sxs-lookup"><span data-stu-id="953fa-142">We recommend that you use a .gif format image.</span></span>  

6. <span data-ttu-id="953fa-143">更改 SharePoint 图标，请找到.headerPageIcon div 类并将以下行： 背景图像： url("../ images/btsSuiteProduction.gif");使其指向已创建的图像文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-143">Change the SharePoint icon by locating the .headerPageIcon div class and changing the following line: background-image: url("../images/btsSuiteProduction.gif"); to point to the image file you have created.</span></span>  

7. <span data-ttu-id="953fa-144">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-144">Save the file.</span></span>  

8. <span data-ttu-id="953fa-145">打开 BAM 门户以查看所做的更改。</span><span class="sxs-lookup"><span data-stu-id="953fa-145">Open the BAM portal to view your changes.</span></span>  

## <a name="modifying-the-bam-portal-webconfig-file"></a><span data-ttu-id="953fa-146">修改 BAM 门户 web.config 文件</span><span class="sxs-lookup"><span data-stu-id="953fa-146">Modifying the BAM Portal web.config File</span></span>  
 <span data-ttu-id="953fa-147">如果 BAM 门户驻留在使用安全套接字层 (SSL) 的企业单一登录 (SSO) 证书的服务器上，你必须配置门户以接受该证书的正确 URL。</span><span class="sxs-lookup"><span data-stu-id="953fa-147">If your BAM portal resides on a server that uses Enterprise Single Sign-On (SSO) certificates for Secure Sockets Layer (SSL), you must configure the portal to accept the proper URL for the certificate.</span></span>  

#### <a name="to-modify-the-bam-portal-to-support-ssl-sites"></a><span data-ttu-id="953fa-148">若要修改 BAM 门户为支持 SSL 站点</span><span class="sxs-lookup"><span data-stu-id="953fa-148">To modify the BAM portal to support SSL sites</span></span>  

1. <span data-ttu-id="953fa-149">打开使用记事本的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-149">Open the web.config file using Notepad.</span></span> <span data-ttu-id="953fa-150">单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，然后再单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="953fa-150">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="953fa-151">修改文件以指向已启用 SSL 的门户的位置中的以下两行：</span><span class="sxs-lookup"><span data-stu-id="953fa-151">Modify the following two lines in the file to point to the location of your SSL-enabled portal:</span></span>  

   ```  
   <add key="BamQueryWSUrl" value="http://localhost/BAM/BamQueryService/BamQueryService.asmx"/>  
   <add key="BamManagementWSUrl" value="http://localhost/BAM/BamManagementService/BamManagementService.asmx"/>  
   ```  

3. <span data-ttu-id="953fa-152">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-152">Save the file.</span></span>  

   <span data-ttu-id="953fa-153">BAM 门户显示并接受数据根据其配置为其的区域性设置格式。</span><span class="sxs-lookup"><span data-stu-id="953fa-153">The BAM portal displays and accepts data formatted according to the culture for which it has been configured.</span></span> <span data-ttu-id="953fa-154">在 web.config 文件中指定配置。</span><span class="sxs-lookup"><span data-stu-id="953fa-154">The configuration is specified in the web.config file.</span></span> <span data-ttu-id="953fa-155">Web 门户将忽略发送的 Internet Explorer 的"接受语言"信息。</span><span class="sxs-lookup"><span data-stu-id="953fa-155">The Web portal ignores the “Accept Language” information sent by Internet Explorer.</span></span> <span data-ttu-id="953fa-156">例如，假设您正在运行 Internet Explorer 设置为日语区域性设置和 BAM 门户配置为使用美国英语区域性设置。</span><span class="sxs-lookup"><span data-stu-id="953fa-156">For example, suppose that you are running Internet Explorer which is set for a Japanese culture setting and have configured the BAM portal to use the U.S. English culture setting.</span></span> <span data-ttu-id="953fa-157">在这种情况下数据的项，如日期和整数，则会显示，接受，并使用适用于美国规则排序英语区域性设置而不是适用于日语区域性设置的规则。</span><span class="sxs-lookup"><span data-stu-id="953fa-157">In this case data items, such as dates and integers, will be displayed, accepted, and sorted using rules appropriate to the U.S. English culture setting rather than rules appropriate to the Japanese culture setting.</span></span> <span data-ttu-id="953fa-158">任何使用日语格式输入的特定于区域性的信息将被视为无效的 BAM 门户因为它只接受采用格式美国的数据（美国）。</span><span class="sxs-lookup"><span data-stu-id="953fa-158">Any culture-specific information entered using Japanese formatting will be considered invalid by the BAM portal because it will expect data formatted for U.S. English.</span></span>  

   <span data-ttu-id="953fa-159">若要获取一致的处理方式的显示和格式设置是根据区域性设置的变量的数据，请选择一种语言，适用于所有 BAM 门户客户端。</span><span class="sxs-lookup"><span data-stu-id="953fa-159">To obtain consistent handling of display and formatting of data that is variable based on the culture settings, choose a language that is appropriate for all BAM portal clients.</span></span> <span data-ttu-id="953fa-160">配置 BAM 门户为此区域性。</span><span class="sxs-lookup"><span data-stu-id="953fa-160">Configure the BAM portal for this culture.</span></span> <span data-ttu-id="953fa-161">您必须确保每个客户端安装多语言用户界面包设置为所选区域性。</span><span class="sxs-lookup"><span data-stu-id="953fa-161">You must ensure that every client is set to the chosen culture by installing the Multilingual User Interface Pack.</span></span>  

   <span data-ttu-id="953fa-162">非美国的英语安装 BAM 它可能需要在 web.config 文件中设置的区域性参数。</span><span class="sxs-lookup"><span data-stu-id="953fa-162">For non-U.S. English installations of BAM it may be necessary to set the culture parameter in the web.config file.</span></span> <span data-ttu-id="953fa-163">您可能需要执行此操作的情况是：</span><span class="sxs-lookup"><span data-stu-id="953fa-163">Cases where you may need to do this are:</span></span>  

-   <span data-ttu-id="953fa-164">要本地化的日期和时间显示格式。</span><span class="sxs-lookup"><span data-stu-id="953fa-164">To localize the format of date and time displays.</span></span>  

-   <span data-ttu-id="953fa-165">要本地化货币的显示格式。</span><span class="sxs-lookup"><span data-stu-id="953fa-165">To localize the format of currency displays.</span></span>  

#### <a name="to-modify-the-culture-setting-of-the-portal"></a><span data-ttu-id="953fa-166">若要修改在门户的区域性设置</span><span class="sxs-lookup"><span data-stu-id="953fa-166">To modify the culture setting of the portal</span></span>  

1. <span data-ttu-id="953fa-167">打开使用记事本的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-167">Open the web.config file using Notepad.</span></span> <span data-ttu-id="953fa-168">单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，然后再单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="953fa-168">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="953fa-169">修改以下行中的文件以反映相应的全球化设置区域性属性：</span><span class="sxs-lookup"><span data-stu-id="953fa-169">Modify the culture attributes in the following line in the file to reflect the appropriate globalization settings:</span></span>  

   ```  
   <globalization requestEncoding="utf-8" responseEncoding="utf-8" culture="de-DE" uiCulture="en" />  
   ```  

3. <span data-ttu-id="953fa-170">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-170">Save the file.</span></span>  

   <span data-ttu-id="953fa-171">在您等待大量 SQL 查询时遇到超时的情况下，可能需要增大查询服务超时值。</span><span class="sxs-lookup"><span data-stu-id="953fa-171">In cases where you are experiencing time-outs while waiting for large SQL queries, it may be necessary to increase the query service time-out value.</span></span>  

#### <a name="to-increase-the-query-service-time-out-value"></a><span data-ttu-id="953fa-172">若要增大查询服务超时值</span><span class="sxs-lookup"><span data-stu-id="953fa-172">To increase the query service time-out value</span></span>  

1. <span data-ttu-id="953fa-173">打开使用记事本的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-173">Open the web.config file using Notepad.</span></span> <span data-ttu-id="953fa-174">单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="953fa-174">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="953fa-175">Queryservicetimeout 的默认值为 45 秒。</span><span class="sxs-lookup"><span data-stu-id="953fa-175">The default value for the QueryServiceTimeout is 45 seconds.</span></span> <span data-ttu-id="953fa-176">修改以下行，以增加或减小超时时间间隔中的值：</span><span class="sxs-lookup"><span data-stu-id="953fa-176">Modify the value in the following line to increase or decrease the time-out interval:</span></span>  

   ```  
   <add key="QueryServiceTimeout" value="45" />  
   ```  

3. <span data-ttu-id="953fa-177">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-177">Save the file.</span></span>  

   <span data-ttu-id="953fa-178">多服务器环境中可能有一台服务器处于脱机状态时的时间。</span><span class="sxs-lookup"><span data-stu-id="953fa-178">In a multiserver environment there may be times when a server is offline.</span></span> <span data-ttu-id="953fa-179">在此情况下，在门户的用户可能会在 BAM 门户停止响应的时间延迟。</span><span class="sxs-lookup"><span data-stu-id="953fa-179">When this happens, users of the portal may experience time delays where the BAM portal stops responding.</span></span> <span data-ttu-id="953fa-180">若要改善用户体验可以修改服务器重试时间间隔。</span><span class="sxs-lookup"><span data-stu-id="953fa-180">To improve the user experience you can modify the server retry interval.</span></span> <span data-ttu-id="953fa-181">这将创建在此期间，将假定服务器处于脱机状态之后连接失败一次, BAM 查询 Web 服务的最小时间。</span><span class="sxs-lookup"><span data-stu-id="953fa-181">This creates a minimum time during which the BAM query Web service assumes that the server is offline after a connection has failed once.</span></span>  

   <span data-ttu-id="953fa-182">值指示是否本地数据库超时尝试联系远程数据库时，将数据标记为不完整和本地计算机不会尝试连接到远程数据库，直到指定的时间已过。</span><span class="sxs-lookup"><span data-stu-id="953fa-182">The value indicates that if a local database times out while trying to contact a remote database, the data is marked as incomplete and the local computer will not attempt to connect to the remote database until the specified time has elapsed.</span></span>  

#### <a name="to-increase-the-retry-interval-for-distributed-activities-in-a-multiserver-environment"></a><span data-ttu-id="953fa-183">若要增加多服务器环境中的分布式活动的重试间隔</span><span class="sxs-lookup"><span data-stu-id="953fa-183">To increase the retry interval for distributed activities in a multiserver environment</span></span>  

1. <span data-ttu-id="953fa-184">打开使用记事本的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-184">Open the web.config file using Notepad.</span></span> <span data-ttu-id="953fa-185">单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="953fa-185">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="953fa-186">Serverretryinterval 的默认值为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="953fa-186">The default value for the ServerRetryInterval is five minutes.</span></span> <span data-ttu-id="953fa-187">修改以下行以增大或减小服务器重试时间间隔中的值：</span><span class="sxs-lookup"><span data-stu-id="953fa-187">Modify the value in the following line to increase or decrease the server retry interval:</span></span>  

   ```  
   <add key="ServerRetryInterval" value="5"/>  
   ```  

3. <span data-ttu-id="953fa-188">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-188">Save the file.</span></span>  

#### <a name="to-configure-how-alert-notification-options-are-presented-in-the-bam-portal"></a><span data-ttu-id="953fa-189">若要配置如何警报通知选项将显示在 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="953fa-189">To configure how alert notification options are presented in the BAM portal</span></span>  

1. <span data-ttu-id="953fa-190">打开使用记事本的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-190">Open the web.config file using Notepad.</span></span> <span data-ttu-id="953fa-191">单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，然后再单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="953fa-191">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="953fa-192">修改中的值字段\<添加键 ="AlertNotificationOptions"value =""/\>的 web.config 文件中使用以逗号分隔的列表指定有效的通知选项具有下列值之一的行。</span><span class="sxs-lookup"><span data-stu-id="953fa-192">Modify the value field in the \<add key="AlertNotificationOptions" value="" /\> line of the web.config file with a comma-delimited list specifying valid notification options with one of the following values.</span></span> <span data-ttu-id="953fa-193">空值由服务器返回的顺序在服务器上显示所有可用的通知选项。</span><span class="sxs-lookup"><span data-stu-id="953fa-193">An empty value displays all notification options available on the server in the order returned by the server.</span></span> <span data-ttu-id="953fa-194">无法识别的任何值等同于空值。</span><span class="sxs-lookup"><span data-stu-id="953fa-194">Any unrecognized value is equivalent to an empty value.</span></span>  


   |    <span data-ttu-id="953fa-195">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="953fa-195">Value</span></span>    |                                              <span data-ttu-id="953fa-196">Description</span><span class="sxs-lookup"><span data-stu-id="953fa-196">Description</span></span>                                               |
   |-------------|--------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="953fa-197">文件中，电子邮件</span><span class="sxs-lookup"><span data-stu-id="953fa-197">File, Email</span></span> | <span data-ttu-id="953fa-198">将显示文件和电子邮件选项。</span><span class="sxs-lookup"><span data-stu-id="953fa-198">File and E-mail options are displayed.</span></span> <span data-ttu-id="953fa-199">在下拉列表中，文件首先显示，然后发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="953fa-199">In the drop-down list, File is displayed first and then E-mail.</span></span> |
   | <span data-ttu-id="953fa-200">电子邮件、 文件</span><span class="sxs-lookup"><span data-stu-id="953fa-200">Email, File</span></span> | <span data-ttu-id="953fa-201">将显示文件和电子邮件选项。</span><span class="sxs-lookup"><span data-stu-id="953fa-201">File and E-mail options are displayed.</span></span> <span data-ttu-id="953fa-202">在下拉列表中，电子邮件首先显示，然后将文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-202">In the drop-down list, E-mail is displayed first and then File.</span></span> |
   |    <span data-ttu-id="953fa-203">文件</span><span class="sxs-lookup"><span data-stu-id="953fa-203">File</span></span>     |                             <span data-ttu-id="953fa-204">仅文件通知显示在门户中。</span><span class="sxs-lookup"><span data-stu-id="953fa-204">Only File notification is displayed in portal.</span></span>                             |
   |    <span data-ttu-id="953fa-205">电子邮件</span><span class="sxs-lookup"><span data-stu-id="953fa-205">Email</span></span>    |                            <span data-ttu-id="953fa-206">在门户中显示仅电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="953fa-206">Only E-mail notification is displayed in portal.</span></span>                            |


3. <span data-ttu-id="953fa-207">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="953fa-207">Save the file.</span></span>  

## <a name="distributed-server-environments"></a><span data-ttu-id="953fa-208">分布式的服务器环境</span><span class="sxs-lookup"><span data-stu-id="953fa-208">Distributed Server Environments</span></span>  
 <span data-ttu-id="953fa-209">如果您安装的 BAM 门户将警报和 BAM 门户置于不同的服务器上，您将看到事件日志中的以下错误："System.Reflection.TargetInvocationException:调用的目标已引发异常。</span><span class="sxs-lookup"><span data-stu-id="953fa-209">If your installation of the BAM portal places the alerts and the BAM portal on different servers, you will see the following error in the event log: "System.Reflection.TargetInvocationException: Exception has been thrown by the target of an invocation.</span></span> <span data-ttu-id="953fa-210">---> 找不到指定的 Notification Services 实例的项的注册表。"</span><span class="sxs-lookup"><span data-stu-id="953fa-210">---> The registry entries for the specified instance of Notification Services could not be found."</span></span>  

#### <a name="to-configure-the-portal-and-alerts-on-different-servers"></a><span data-ttu-id="953fa-211">若要配置不同的服务器上的门户和警报</span><span class="sxs-lookup"><span data-stu-id="953fa-211">To configure the portal and alerts on different servers</span></span>  

1. <span data-ttu-id="953fa-212">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="953fa-212">Open a command prompt.</span></span>  

2. <span data-ttu-id="953fa-213">运行**C:\Program Files\Microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register-name bamalerts-server**<em>\<服务器名称\></em>替换*\<服务器名称\>* 与服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="953fa-213">Run **C:\Program Files\Microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register -name bamalerts -server**<em>\<server name\></em> Replace *\<server name\>* with the name of the server.</span></span>  

3. <span data-ttu-id="953fa-214">按 F5 刷新浏览器。</span><span class="sxs-lookup"><span data-stu-id="953fa-214">Press F5 to refresh your browser.</span></span>  

## <a name="configuring-iis-to-allow-the-bam-portal-to-use-the-kerberos-network-protocol"></a><span data-ttu-id="953fa-215">将 IIS 配置为允许 BAM 门户使用 Kerberos 网络协议</span><span class="sxs-lookup"><span data-stu-id="953fa-215">Configuring IIS to Allow the BAM Portal to Use the Kerberos Network Protocol</span></span>  
 <span data-ttu-id="953fa-216">如果你想要使用 BAM 门户使用 Kerberos 网络协议必须修改 Web 门户的 ACL 安全性。</span><span class="sxs-lookup"><span data-stu-id="953fa-216">If you want to use the Kerberos network protocol with the BAM portal you must modify the ACL security for the Web portal.</span></span> <span data-ttu-id="953fa-217">如果 IIS 配置不正确，用户将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="953fa-217">If IIS is not configured properly, users will receive the following error:</span></span>  

 <span data-ttu-id="953fa-218">HTTP 错误 401.1-未经授权：由于凭据无效，访问被拒绝。</span><span class="sxs-lookup"><span data-stu-id="953fa-218">HTTP Error 401.1 - Unauthorized: Access is denied due to invalid credentials.</span></span>  

 <span data-ttu-id="953fa-219">有关修改 IIS 安全设置的其他信息，请参阅知识库文章，网址[ http://go.microsoft.com/fwlink/?LinkId=57922 ](http://go.microsoft.com/fwlink/?LinkId=57922)。</span><span class="sxs-lookup"><span data-stu-id="953fa-219">For additional information about modifying the IIS security settings, see the Knowledge Base article at [http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922).</span></span>  

## <a name="viewing-aggregate-bam-data-in-the-bam-portal-in-sql-server-2008--deployments"></a><span data-ttu-id="953fa-220">在 SQL Server 2008 部署 BAM 门户中查看聚合 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="953fa-220">Viewing Aggregate BAM Data in the BAM Portal in SQL Server 2008  Deployments</span></span>  
 <span data-ttu-id="953fa-221">若要从部署环境中使用 SQL Server 2008 时连接到 BAM 门户的客户端计算机在 BAM 门户中查看聚合数据，必须在客户端计算机上安装 Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB 访问接口。</span><span class="sxs-lookup"><span data-stu-id="953fa-221">To view aggregate data in the BAM portal from a client computer connecting to the BAM portal when the deployment environment uses SQL Server 2008, you must install Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB Provider on the client computer.</span></span> <span data-ttu-id="953fa-222">如果未安装的 analysis services 的用户将收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="953fa-222">If the analysis services are not installed users will receive the following error message:</span></span>  

 <span data-ttu-id="953fa-223">在服务器*\<servername\>* 太忙或无法联系。</span><span class="sxs-lookup"><span data-stu-id="953fa-223">The server *\<servername\>* cannot be contacted or is too busy.</span></span>  



## <a name="see-also"></a><span data-ttu-id="953fa-224">请参阅</span><span class="sxs-lookup"><span data-stu-id="953fa-224">See Also</span></span>  
 [<span data-ttu-id="953fa-225">规划 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="953fa-225">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)