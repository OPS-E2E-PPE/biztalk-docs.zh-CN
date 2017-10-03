---
title: "自定义 BAM 门户配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, alerts
- BAM portal, timeout setting
- queries [BAM], timeout setting
- BAM portal, retry interval
- alerts, configuration options
- BAM portal, configuring
- BAM portal, portal banner
- clustering, NLB [BAM portal]
- BAM portal, Web.config file
- Kerberos protocol, BAM portal
- BAM portal, culture setting
- BAM portal, IIS
- IIS, BAM portal
- BAM portal, NLB cluster
- Web.config file
- BAM portal, 64-bit environments
- BAM portal, Kerberos protocol
- BAM portal, clustering
- 64-bit environments, BAM portal
- IIS, 64-bit support
- NLB system, BAM portal
- BAM portal, customizing
- configuring, BAM portal banner
- 64-bit support, IIS
- BAM portal, distributed environment
ms.assetid: 507bd5f0-b2a0-4d52-85f8-9d984138ca79
caps.latest.revision: "47"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bad22e9bf2ecddcc50983078b21672f2c755c8a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="customizing-the-bam-portal-configuration"></a><span data-ttu-id="a5266-102">自定义 BAM 门户配置</span><span class="sxs-lookup"><span data-stu-id="a5266-102">Customizing the BAM Portal Configuration</span></span>
<span data-ttu-id="a5266-103">BAM 门户有多个可配置选项。</span><span class="sxs-lookup"><span data-stu-id="a5266-103">There are a number of configurable options on the BAM portal.</span></span> <span data-ttu-id="a5266-104">下面的过程演示如何修改 BAM 门户，以获取最佳用户体验。</span><span class="sxs-lookup"><span data-stu-id="a5266-104">The following procedures show you how to modify the BAM portal to obtain the best user experience.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5266-105">以非管理员模拟用户身份配置门户时，你很有必要注销然后再登录，以便能够访问 BAM 门户功能而无需输入凭据。</span><span class="sxs-lookup"><span data-stu-id="a5266-105">When configuring the portal as a non-administrator impersonated user, it may be necessary for you to log off and then log back on before you have access to the BAM portal features without being asked to enter your credentials.</span></span> <span data-ttu-id="a5266-106">例如，请考虑以下情况：</span><span class="sxs-lookup"><span data-stu-id="a5266-106">For example, consider the following scenario:</span></span>  
>   
>  <span data-ttu-id="a5266-107">你可以配置 Web 服务或 BAM 门户与非管理员模拟用户。</span><span class="sxs-lookup"><span data-stu-id="a5266-107">You configure the Web service or BAM portal with a non-administrator impersonated user.</span></span> <span data-ttu-id="a5266-108">然后设置对门户的权限，例如 Everyone 组没有门户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a5266-108">You then set permissions on the portal such that the Everyone group does not have access to the portal.</span></span> <span data-ttu-id="a5266-109">然后创建名为 PortalUsersGroup 的本地组，并将该组指定为 Portal Users 组。</span><span class="sxs-lookup"><span data-stu-id="a5266-109">You then create a local group called PortalUsersGroup and assign that group as the Portal Users group.</span></span> <span data-ttu-id="a5266-110">这意味着只有该组中的用户可以访问门户。</span><span class="sxs-lookup"><span data-stu-id="a5266-110">This means that only users in that group have access to the portal.</span></span> <span data-ttu-id="a5266-111">对 BAM 门户进行配置后，将当前用户添加到 Portal Users 组。</span><span class="sxs-lookup"><span data-stu-id="a5266-111">After you have configured the BAM portal, add the current user to the Portal Users group.</span></span> <span data-ttu-id="a5266-112">打开 BAM 门户时，将要求您提供凭据。</span><span class="sxs-lookup"><span data-stu-id="a5266-112">When you open the BAM portal, you will be asked for your credentials.</span></span> <span data-ttu-id="a5266-113">如果您注销然后再登录，则可以在不要求提供凭据的情况下打开 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="a5266-113">If you log off and log back on, however, you are able to open the BAM portal without being asked for your credentials.</span></span>  
>   
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a5266-114">单个计算机配置中仅支持本地组和用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a5266-114"> supports local group and user accounts only in single computer configurations.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a5266-115">支持在单个和多个计算机配置中的域组和用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a5266-115"> supports domain group and user accounts in both single and multiple computer configurations.</span></span>  
  
## <a name="running-the-bam-portal-in-a-64-bit-environment"></a><span data-ttu-id="a5266-116">在 64 位环境下运行 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="a5266-116">Running the BAM Portal in a 64-bit Environment</span></span>  
 <span data-ttu-id="a5266-117">如果在 64 位环境中使用 Internet 信息服务 (IIS) 6，则必须将 IIS 设置为 32 位模式才能运行 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="a5266-117">If you are using Internet Information Services (IIS) 6 in a 64-bit environment, you must set IIS to 32-bit mode to run the BAM portal.</span></span> <span data-ttu-id="a5266-118">有关设置模式的其他信息，请参阅"如何切换 ASP.NET 1.1 的 32 位版本和 64 位版本的 ASP.NET 2.0 上的 64 位版本的 Windows"在[http://go.microsoft.com/fwlink/?LinkId=61991](http://go.microsoft.com/fwlink/?LinkId=61991)。</span><span class="sxs-lookup"><span data-stu-id="a5266-118">For additional information about setting the mode, see "How to switch between the 32-bit versions of ASP.NET 1.1 and the 64-bit version of ASP.NET 2.0 on a 64-bit version of Windows" at [http://go.microsoft.com/fwlink/?LinkId=61991](http://go.microsoft.com/fwlink/?LinkId=61991).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a5266-119">不必将 IIS7 设置为 32 位模式。</span><span class="sxs-lookup"><span data-stu-id="a5266-119">You do not have to set IIS7 to 32-bit mode.</span></span>  
  
#### <a name="to-set-a-64-bit-mode-iis-installation-to-32-bit-mode"></a><span data-ttu-id="a5266-120">将安装的 64 位模式 IIS 设置为 32 位模式</span><span class="sxs-lookup"><span data-stu-id="a5266-120">To set a 64-bit mode IIS installation to 32-bit mode</span></span>  
  
1.  <span data-ttu-id="a5266-121">打开命令提示符并运行**adsutil**命令。</span><span class="sxs-lookup"><span data-stu-id="a5266-121">Open a command prompt and run the **adsutil** command.</span></span> <span data-ttu-id="a5266-122">若要执行此操作，请单击**启动**，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="a5266-122">To do this, click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="a5266-123">在命令提示符下键入以下内容： `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`。</span><span class="sxs-lookup"><span data-stu-id="a5266-123">Type the following at the command prompt: `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`.</span></span>  
  
3.  <span data-ttu-id="a5266-124">关闭命令提示符。</span><span class="sxs-lookup"><span data-stu-id="a5266-124">Close the command prompt.</span></span>  
  
## <a name="configuring-the-bam-portal-banner"></a><span data-ttu-id="a5266-125">配置 BAM 门户横幅</span><span class="sxs-lookup"><span data-stu-id="a5266-125">Configuring the BAM Portal Banner</span></span>  
 <span data-ttu-id="a5266-126">可以修改 BAM 门户页以显示类似如下的、有关您业务的文本和图形：</span><span class="sxs-lookup"><span data-stu-id="a5266-126">You can modify the BAM portal page to display similar text and graphics about your business:</span></span>  
  
-   <span data-ttu-id="a5266-127">Windows Server System 徽标，它位于 BAM 门户页的右上角。</span><span class="sxs-lookup"><span data-stu-id="a5266-127">The Windows Server System logo, which is located in the upper-right corner of the BAM portal page.</span></span>  
  
 <span data-ttu-id="a5266-128">在以下过程中，您将编辑级联样式表文件（.css 文件）来自定义 BAM 门户的外观。</span><span class="sxs-lookup"><span data-stu-id="a5266-128">In the following procedure you edit a cascading style sheet file (.css file) to customize the look of the BAM portal.</span></span> <span data-ttu-id="a5266-129">只支持对指定类的修改。</span><span class="sxs-lookup"><span data-stu-id="a5266-129">Modifications to the specified classes are the only modifications supported.</span></span> <span data-ttu-id="a5266-130">系统已尽可能孤立对类所做修改的影响，这样如果修改过程中出现错误，则 BAM 门户仍处于工作状态。</span><span class="sxs-lookup"><span data-stu-id="a5266-130">As much as possible, the impact of modifications to classes has been isolated so that errors made during the modification process leave the BAM portal in a working state.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a5266-131">在 styles.css 文件中修改其他类将隐藏数据和门户功能，并可能使门户无法使用。</span><span class="sxs-lookup"><span data-stu-id="a5266-131">Modifying other classes in the styles.css file will hide data and portal features, and may make the portal unusable.</span></span>  
  
#### <a name="to-configure-the-banner"></a><span data-ttu-id="a5266-132">配置横幅</span><span class="sxs-lookup"><span data-stu-id="a5266-132">To configure the banner</span></span>  
  
1.  <span data-ttu-id="a5266-133">编辑 BAM 门户 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-133">Edit the BAM portal web.config file.</span></span> <span data-ttu-id="a5266-134">若要执行此操作，请单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5266-134">To do this, click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="a5266-135">主页快速入门内容是可替换的通过修改以下行：\<添加键 ="MainPageContentUrl"value="~/MainPageContent.htm"/ >。</span><span class="sxs-lookup"><span data-stu-id="a5266-135">The main page quick-start contents are replaceable by modifying the following line: \<add key="MainPageContentUrl" value="~/MainPageContent.htm"/>.</span></span> <span data-ttu-id="a5266-136">更改**MainPageContent.htm**值字段，使其指向你自己的 HTML 文件中。</span><span class="sxs-lookup"><span data-stu-id="a5266-136">Change **MainPageContent.htm** in the value field to point to your own HTML file.</span></span> <span data-ttu-id="a5266-137">该 HTML 文件必须位于 web.config 文件所在的目录中。</span><span class="sxs-lookup"><span data-stu-id="a5266-137">The HTML file must be in the same directory as the web.config file.</span></span>  
  
3.  <span data-ttu-id="a5266-138">更改标识通过将以下行添加到 web.config 文件的文本页：\<添加键 ="PortalTitle"value ="新标识 text"/ >。</span><span class="sxs-lookup"><span data-stu-id="a5266-138">Change the page identifying text by adding the following line to the web.config file: \<add key=”PortalTitle” value=”New Identifying text”/>.</span></span> <span data-ttu-id="a5266-139">将值字段更改为包含标识门户的文本。</span><span class="sxs-lookup"><span data-stu-id="a5266-139">Change the value field to contain the text to identify the portal.</span></span>  
  
4.  <span data-ttu-id="a5266-140">编辑 BAM 门户 styles.css 文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-140">Edit the BAM portal styles.css file.</span></span> <span data-ttu-id="a5266-141">单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5266-141">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="a5266-142">通过查找.headerLogo div 类并更改以下行来更改右上角的徽标： 背景图像： url("../ images/WSS_Logo.gif");使其指向已创建的映像文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-142">Change the logo in the upper-right corner by locating the .headerLogo div class and changing the following line:   background-image: url("../images/WSS_Logo.gif"); to point to the image file you have created.</span></span> <span data-ttu-id="a5266-143">建议您使用 .gif 格式的图像。</span><span class="sxs-lookup"><span data-stu-id="a5266-143">We recommend that you use a .gif format image.</span></span>  
  
6.  <span data-ttu-id="a5266-144">通过查找.headerPageIcon div 类并更改以下行来更改显示 SharePoint 图标： 背景图像： url("../ images/btsSuiteProduction.gif");使其指向已创建的映像文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-144">Change the SharePoint icon by locating the .headerPageIcon div class and changing the following line: background-image: url("../images/btsSuiteProduction.gif"); to point to the image file you have created.</span></span>  
  
7.  <span data-ttu-id="a5266-145">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-145">Save the file.</span></span>  
  
8.  <span data-ttu-id="a5266-146">打开 BAM 门户查看您所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a5266-146">Open the BAM portal to view your changes.</span></span>  
  
## <a name="modifying-the-bam-portal-webconfig-file"></a><span data-ttu-id="a5266-147">修改 BAM 门户 web.config 文件</span><span class="sxs-lookup"><span data-stu-id="a5266-147">Modifying the BAM Portal web.config File</span></span>  
 <span data-ttu-id="a5266-148">如果 BAM 门户驻留在将企业单一登录 (SSO) 证书用于安全套接字层 (SSL) 的服务器上，则必须将该门户配置为接受证书的正确 URL。</span><span class="sxs-lookup"><span data-stu-id="a5266-148">If your BAM portal resides on a server that uses Enterprise Single Sign-On (SSO) certificates for Secure Sockets Layer (SSL), you must configure the portal to accept the proper URL for the certificate.</span></span>  
  
#### <a name="to-modify-the-bam-portal-to-support-ssl-sites"></a><span data-ttu-id="a5266-149">将 BAM 门户修改为支持 SSL 站点</span><span class="sxs-lookup"><span data-stu-id="a5266-149">To modify the BAM portal to support SSL sites</span></span>  
  
1.  <span data-ttu-id="a5266-150">使用记事本打开 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-150">Open the web.config file using Notepad.</span></span> <span data-ttu-id="a5266-151">单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5266-151">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="a5266-152">将文件中的以下两行修改为指向启用了 SSL 的门户的位置：</span><span class="sxs-lookup"><span data-stu-id="a5266-152">Modify the following two lines in the file to point to the location of your SSL-enabled portal:</span></span>  
  
    ```  
    <add key="BamQueryWSUrl" value="http://localhost/BAM/BamQueryService/BamQueryService.asmx"/>  
    <add key="BamManagementWSUrl" value="http://localhost/BAM/BamManagementService/BamManagementService.asmx"/>  
    ```  
  
3.  <span data-ttu-id="a5266-153">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-153">Save the file.</span></span>  
  
 <span data-ttu-id="a5266-154">BAM 门户显示并接受符合已为数据配置的区域性的数据格式。</span><span class="sxs-lookup"><span data-stu-id="a5266-154">The BAM portal displays and accepts data formatted according to the culture for which it has been configured.</span></span> <span data-ttu-id="a5266-155">该配置在 web.config 文件中指定。</span><span class="sxs-lookup"><span data-stu-id="a5266-155">The configuration is specified in the web.config file.</span></span> <span data-ttu-id="a5266-156">Web 门户将忽略 Internet Explorer 发送的“接受语言”信息。</span><span class="sxs-lookup"><span data-stu-id="a5266-156">The Web portal ignores the “Accept Language” information sent by Internet Explorer.</span></span> <span data-ttu-id="a5266-157">例如，假设您正在运行 Internet Explorer 这设置为日语区域性设置并已配置 BAM 门户以使用美国英语区域性设置。</span><span class="sxs-lookup"><span data-stu-id="a5266-157">For example, suppose that you are running Internet Explorer which is set for a Japanese culture setting and have configured the BAM portal to use the U.S. English culture setting.</span></span> <span data-ttu-id="a5266-158">在这种情况下数据项，如将显示日期和整数，，接受，并使用适用于美国规则排序英语区域性设置而不是适用于日语区域性设置的规则。</span><span class="sxs-lookup"><span data-stu-id="a5266-158">In this case data items, such as dates and integers, will be displayed, accepted, and sorted using rules appropriate to the U.S. English culture setting rather than rules appropriate to the Japanese culture setting.</span></span> <span data-ttu-id="a5266-159">输入使用日语格式设置的任何特定于区域性的信息将被视为无效 BAM 门户因为应适用于美国格式数据美国英语的默认值。</span><span class="sxs-lookup"><span data-stu-id="a5266-159">Any culture-specific information entered using Japanese formatting will be considered invalid by the BAM portal because it will expect data formatted for U.S. English.</span></span>  
  
 <span data-ttu-id="a5266-160">若要基于区域性设置对数据的可变显示和格式设置进行一致性处理，请选择适用于所有 BAM 门户客户端的语言。</span><span class="sxs-lookup"><span data-stu-id="a5266-160">To obtain consistent handling of display and formatting of data that is variable based on the culture settings, choose a language that is appropriate for all BAM portal clients.</span></span> <span data-ttu-id="a5266-161">为此区域性 BAM 门户进行配置。</span><span class="sxs-lookup"><span data-stu-id="a5266-161">Configure the BAM portal for this culture.</span></span> <span data-ttu-id="a5266-162">必须安装多语言用户界面包以确保将每个客户端设置为所选区域性。</span><span class="sxs-lookup"><span data-stu-id="a5266-162">You must ensure that every client is set to the chosen culture by installing the Multilingual User Interface Pack.</span></span>  
  
 <span data-ttu-id="a5266-163">适用于非美国BAM 的英语安装它可能有必要在 web.config 文件中设置的区域性参数。</span><span class="sxs-lookup"><span data-stu-id="a5266-163">For non-U.S. English installations of BAM it may be necessary to set the culture parameter in the web.config file.</span></span> <span data-ttu-id="a5266-164">需要设置区域性参数的情况包括：</span><span class="sxs-lookup"><span data-stu-id="a5266-164">Cases where you may need to do this are:</span></span>  
  
-   <span data-ttu-id="a5266-165">要本地化日期和时间的显示格式。</span><span class="sxs-lookup"><span data-stu-id="a5266-165">To localize the format of date and time displays.</span></span>  
  
-   <span data-ttu-id="a5266-166">要本地化货币的显示格式。</span><span class="sxs-lookup"><span data-stu-id="a5266-166">To localize the format of currency displays.</span></span>  
  
#### <a name="to-modify-the-culture-setting-of-the-portal"></a><span data-ttu-id="a5266-167">修改门户的区域性设置</span><span class="sxs-lookup"><span data-stu-id="a5266-167">To modify the culture setting of the portal</span></span>  
  
1.  <span data-ttu-id="a5266-168">使用记事本打开 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-168">Open the web.config file using Notepad.</span></span> <span data-ttu-id="a5266-169">单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5266-169">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="a5266-170">修改文件以反映相应的全球化设置中的以下行中的区域性属性：</span><span class="sxs-lookup"><span data-stu-id="a5266-170">Modify the culture attributes in the following line in the file to reflect the appropriate globalization settings:</span></span>  
  
    ```  
    <globalization requestEncoding="utf-8" responseEncoding="utf-8" culture="de-DE" uiCulture="en" />  
    ```  
  
3.  <span data-ttu-id="a5266-171">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-171">Save the file.</span></span>  
  
 <span data-ttu-id="a5266-172">在因等待大量 SQL 查询而超时的情况下，需要增大查询服务超时值。</span><span class="sxs-lookup"><span data-stu-id="a5266-172">In cases where you are experiencing time-outs while waiting for large SQL queries, it may be necessary to increase the query service time-out value.</span></span>  
  
#### <a name="to-increase-the-query-service-time-out-value"></a><span data-ttu-id="a5266-173">若要增加查询服务超时值</span><span class="sxs-lookup"><span data-stu-id="a5266-173">To increase the query service time-out value</span></span>  
  
1.  <span data-ttu-id="a5266-174">使用记事本打开 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-174">Open the web.config file using Notepad.</span></span> <span data-ttu-id="a5266-175">单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5266-175">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="a5266-176">QueryServiceTimeout 的默认值为 45 秒。</span><span class="sxs-lookup"><span data-stu-id="a5266-176">The default value for the QueryServiceTimeout is 45 seconds.</span></span> <span data-ttu-id="a5266-177">修改以下行中的值以增大或减小超时时间间隔：</span><span class="sxs-lookup"><span data-stu-id="a5266-177">Modify the value in the following line to increase or decrease the time-out interval:</span></span>  
  
    ```  
    <add key="QueryServiceTimeout" value="45" />  
    ```  
  
3.  <span data-ttu-id="a5266-178">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-178">Save the file.</span></span>  
  
 <span data-ttu-id="a5266-179">在多服务器环境下，有时候某一服务器会脱机。</span><span class="sxs-lookup"><span data-stu-id="a5266-179">In a multiserver environment there may be times when a server is offline.</span></span> <span data-ttu-id="a5266-180">发生这种情况时，门户用户可能会因 BAM 门户停止响应而受到延迟。</span><span class="sxs-lookup"><span data-stu-id="a5266-180">When this happens, users of the portal may experience time delays where the BAM portal stops responding.</span></span> <span data-ttu-id="a5266-181">若要改善用户的延迟体验，可以修改服务器重试时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a5266-181">To improve the user experience you can modify the server retry interval.</span></span> <span data-ttu-id="a5266-182">这将设置一段最短时间，在这段时间内如果连接失败，则 BAM 查询 Web Services 假定服务器为脱机。</span><span class="sxs-lookup"><span data-stu-id="a5266-182">This creates a minimum time during which the BAM query Web service assumes that the server is offline after a connection has failed once.</span></span>  
  
 <span data-ttu-id="a5266-183">如果本地数据库超时尝试联系远程数据库时，数据将被标记为不完整和本地计算机将不会尝试连接到远程数据库，直到经过了指定的时间之后，将指示的值。</span><span class="sxs-lookup"><span data-stu-id="a5266-183">The value indicates that if a local database times out while trying to contact a remote database, the data is marked as incomplete and the local computer will not attempt to connect to the remote database until the specified time has elapsed.</span></span>  
  
#### <a name="to-increase-the-retry-interval-for-distributed-activities-in-a-multiserver-environment"></a><span data-ttu-id="a5266-184">增大多服务器环境下发布式活动的重试时间间隔</span><span class="sxs-lookup"><span data-stu-id="a5266-184">To increase the retry interval for distributed activities in a multiserver environment</span></span>  
  
1.  <span data-ttu-id="a5266-185">使用记事本打开 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-185">Open the web.config file using Notepad.</span></span> <span data-ttu-id="a5266-186">单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5266-186">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="a5266-187">ServerRetryInterval 的默认值为五分钟。</span><span class="sxs-lookup"><span data-stu-id="a5266-187">The default value for the ServerRetryInterval is five minutes.</span></span> <span data-ttu-id="a5266-188">修改以下行中的值以增大或减小服务器重试时间间隔：</span><span class="sxs-lookup"><span data-stu-id="a5266-188">Modify the value in the following line to increase or decrease the server retry interval:</span></span>  
  
    ```  
    <add key="ServerRetryInterval" value="5"/>  
    ```  
  
3.  <span data-ttu-id="a5266-189">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-189">Save the file.</span></span>  
  
#### <a name="to-configure-how-alert-notification-options-are-presented-in-the-bam-portal"></a><span data-ttu-id="a5266-190">配置如何在 BAM 门户中显示警报通知选项</span><span class="sxs-lookup"><span data-stu-id="a5266-190">To configure how alert notification options are presented in the BAM portal</span></span>  
  
1.  <span data-ttu-id="a5266-191">使用记事本打开 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-191">Open the web.config file using Notepad.</span></span> <span data-ttu-id="a5266-192">单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5266-192">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="a5266-193">修改中的值字段\<添加键 ="AlertNotificationOptions"value =""/ > 行包含指定有效的通知选项具有下列值之一以逗号分隔列表的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-193">Modify the value field in the \<add key="AlertNotificationOptions" value="" /> line of the web.config file with a comma-delimited list specifying valid notification options with one of the following values.</span></span> <span data-ttu-id="a5266-194">空值将以服务器返回的顺序显示服务器上可用的所有通知选项。</span><span class="sxs-lookup"><span data-stu-id="a5266-194">An empty value displays all notification options available on the server in the order returned by the server.</span></span> <span data-ttu-id="a5266-195">任何不可识别的值等效于空值。</span><span class="sxs-lookup"><span data-stu-id="a5266-195">Any unrecognized value is equivalent to an empty value.</span></span>  
  
    |<span data-ttu-id="a5266-196">值</span><span class="sxs-lookup"><span data-stu-id="a5266-196">Value</span></span>|<span data-ttu-id="a5266-197">Description</span><span class="sxs-lookup"><span data-stu-id="a5266-197">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="a5266-198">File, Email</span><span class="sxs-lookup"><span data-stu-id="a5266-198">File, Email</span></span>|<span data-ttu-id="a5266-199">显示文件选项和电子邮件选项。</span><span class="sxs-lookup"><span data-stu-id="a5266-199">File and E-mail options are displayed.</span></span> <span data-ttu-id="a5266-200">在下拉列表中，先显示文件再显示电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a5266-200">In the drop-down list, File is displayed first and then E-mail.</span></span>|  
    |<span data-ttu-id="a5266-201">Email, File</span><span class="sxs-lookup"><span data-stu-id="a5266-201">Email, File</span></span>|<span data-ttu-id="a5266-202">显示文件选项和电子邮件选项。</span><span class="sxs-lookup"><span data-stu-id="a5266-202">File and E-mail options are displayed.</span></span> <span data-ttu-id="a5266-203">在下拉列表中，先显示电子邮件再显示文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-203">In the drop-down list, E-mail is displayed first and then File.</span></span>|  
    |<span data-ttu-id="a5266-204">文件</span><span class="sxs-lookup"><span data-stu-id="a5266-204">File</span></span>|<span data-ttu-id="a5266-205">在门户中仅显示文件通知。</span><span class="sxs-lookup"><span data-stu-id="a5266-205">Only File notification is displayed in portal.</span></span>|  
    |<span data-ttu-id="a5266-206">电子邮件</span><span class="sxs-lookup"><span data-stu-id="a5266-206">Email</span></span>|<span data-ttu-id="a5266-207">在门户中仅显示电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="a5266-207">Only E-mail notification is displayed in portal.</span></span>|  
  
3.  <span data-ttu-id="a5266-208">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="a5266-208">Save the file.</span></span>  
  
## <a name="distributed-server-environments"></a><span data-ttu-id="a5266-209">分布式服务器环境</span><span class="sxs-lookup"><span data-stu-id="a5266-209">Distributed Server Environments</span></span>  
 <span data-ttu-id="a5266-210">如果你安装 BAM 门户放在不同服务器上警报和 BAM 门户，你将看到事件日志中的以下错误:"System.Reflection.TargetInvocationException： 目标的调用引发异常。</span><span class="sxs-lookup"><span data-stu-id="a5266-210">If your installation of the BAM portal places the alerts and the BAM portal on different servers, you will see the following error in the event log: "System.Reflection.TargetInvocationException: Exception has been thrown by the target of an invocation.</span></span> <span data-ttu-id="a5266-211">---> 找不到项通知服务的指定实例的注册表。"</span><span class="sxs-lookup"><span data-stu-id="a5266-211">---> The registry entries for the specified instance of Notification Services could not be found."</span></span>  
  
#### <a name="to-configure-the-portal-and-alerts-on-different-servers"></a><span data-ttu-id="a5266-212">配置位于不同服务器上的门户和警报</span><span class="sxs-lookup"><span data-stu-id="a5266-212">To configure the portal and alerts on different servers</span></span>  
  
1.  <span data-ttu-id="a5266-213">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="a5266-213">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="a5266-214">运行**C:\Program Files\Microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register-name bamalerts-服务器***\<服务器名称 >*替换 *\<服务器名称 >*与服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="a5266-214">Run **C:\Program Files\Microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register -name bamalerts -server***\<server name>* Replace *\<server name>* with the name of the server.</span></span>  
  
3.  <span data-ttu-id="a5266-215">按下 F5 键来刷新浏览器。</span><span class="sxs-lookup"><span data-stu-id="a5266-215">Press F5 to refresh your browser.</span></span>  
  
## <a name="configuring-iis-to-allow-the-bam-portal-to-use-the-kerberos-network-protocol"></a><span data-ttu-id="a5266-216">将 IIS 配置为允许 BAM 门户使用 Kerberos 网络协议</span><span class="sxs-lookup"><span data-stu-id="a5266-216">Configuring IIS to Allow the BAM Portal to Use the Kerberos Network Protocol</span></span>  
 <span data-ttu-id="a5266-217">如果要在 BAM 门户中使用 Kerberos 网络协议，必须修改 Web 门户站点的 ACL 安全性。</span><span class="sxs-lookup"><span data-stu-id="a5266-217">If you want to use the Kerberos network protocol with the BAM portal you must modify the ACL security for the Web portal.</span></span> <span data-ttu-id="a5266-218">如果 IIS 配置不正确，用户将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="a5266-218">If IIS is not configured properly, users will receive the following error:</span></span>  
  
 <span data-ttu-id="a5266-219">HTTP 错误 401.1-未授权： 由于凭据无效而被拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="a5266-219">HTTP Error 401.1 - Unauthorized: Access is denied due to invalid credentials.</span></span>  
  
 <span data-ttu-id="a5266-220">有关 IIS 安全设置修改的其他信息，请参阅知识库文章， [http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922)。</span><span class="sxs-lookup"><span data-stu-id="a5266-220">For additional information about modifying the IIS security settings, see the Knowledge Base article at [http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922).</span></span>  
  
## <a name="viewing-aggregate-bam-data-in-the-bam-portal-in-sql-server-2008--deployments"></a><span data-ttu-id="a5266-221">在 SQL Server 2008 部署 BAM 门户查看聚合 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="a5266-221">Viewing Aggregate BAM Data in the BAM Portal in SQL Server 2008  Deployments</span></span>  
 <span data-ttu-id="a5266-222">若要在部署环境中使用 [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] 时从连接到 BAM 门户的客户端计算机查看 BAM 门户中的聚合数据，您必须在客户端计算机上安装 Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB 提供程序。</span><span class="sxs-lookup"><span data-stu-id="a5266-222">To view aggregate data in the BAM portal from a client computer connecting to the BAM portal when the deployment environment uses [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], you must install Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB Provider on the client computer.</span></span> <span data-ttu-id="a5266-223">如果未安装分析服务，用户将会收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="a5266-223">If the analysis services are not installed users will receive the following error message:</span></span>  
  
 <span data-ttu-id="a5266-224">服务器 *\<servername >*无法连接或太忙。</span><span class="sxs-lookup"><span data-stu-id="a5266-224">The server *\<servername>* cannot be contacted or is too busy.</span></span>  
  
 <span data-ttu-id="a5266-225">若要安装 for Microsoft SQL Server 2008 功能包，请参阅[http://go.microsoft.com/fwlink/?LinkId=70728](http://go.microsoft.com/fwlink/?LinkId=70728)。</span><span class="sxs-lookup"><span data-stu-id="a5266-225">To install the Feature Pack for Microsoft SQL Server 2008, see [http://go.microsoft.com/fwlink/?LinkId=70728](http://go.microsoft.com/fwlink/?LinkId=70728).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5266-226">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5266-226">See Also</span></span>  
 [<span data-ttu-id="a5266-227">规划 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="a5266-227">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)