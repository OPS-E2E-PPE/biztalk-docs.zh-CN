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
ms.openlocfilehash: 5f1cf1bf2cb2400d4209686e6b1d3d3b11a4461c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987334"
---
# <a name="customizing-the-bam-portal-configuration"></a><span data-ttu-id="b523a-102">自定义 BAM 门户配置</span><span class="sxs-lookup"><span data-stu-id="b523a-102">Customizing the BAM Portal Configuration</span></span>
<span data-ttu-id="b523a-103">BAM 门户有多个可配置选项。</span><span class="sxs-lookup"><span data-stu-id="b523a-103">There are a number of configurable options on the BAM portal.</span></span> <span data-ttu-id="b523a-104">以下过程介绍如何修改 BAM 门户，以获取最佳用户体验。</span><span class="sxs-lookup"><span data-stu-id="b523a-104">The following procedures show you how to modify the BAM portal to obtain the best user experience.</span></span>  

> [!NOTE]
>  <span data-ttu-id="b523a-105">以非管理员模拟用户身份配置门户时，你很有必要注销然后再登录，以便能够访问 BAM 门户功能而无需输入凭据。</span><span class="sxs-lookup"><span data-stu-id="b523a-105">When configuring the portal as a non-administrator impersonated user, it may be necessary for you to log off and then log back on before you have access to the BAM portal features without being asked to enter your credentials.</span></span> <span data-ttu-id="b523a-106">例如，请考虑以下情况：</span><span class="sxs-lookup"><span data-stu-id="b523a-106">For example, consider the following scenario:</span></span>  
>   
>  <span data-ttu-id="b523a-107">使用非管理员模拟用户配置的 Web 服务或 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="b523a-107">You configure the Web service or BAM portal with a non-administrator impersonated user.</span></span> <span data-ttu-id="b523a-108">然后设置对门户的权限，例如 Everyone 组没有门户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b523a-108">You then set permissions on the portal such that the Everyone group does not have access to the portal.</span></span> <span data-ttu-id="b523a-109">然后创建名为 PortalUsersGroup 的本地组，并将该组指定为 Portal Users 组。</span><span class="sxs-lookup"><span data-stu-id="b523a-109">You then create a local group called PortalUsersGroup and assign that group as the Portal Users group.</span></span> <span data-ttu-id="b523a-110">这意味着只有该组中的用户可以访问门户。</span><span class="sxs-lookup"><span data-stu-id="b523a-110">This means that only users in that group have access to the portal.</span></span> <span data-ttu-id="b523a-111">对 BAM 门户进行配置后，将当前用户添加到 Portal Users 组。</span><span class="sxs-lookup"><span data-stu-id="b523a-111">After you have configured the BAM portal, add the current user to the Portal Users group.</span></span> <span data-ttu-id="b523a-112">打开 BAM 门户时，将要求您提供凭据。</span><span class="sxs-lookup"><span data-stu-id="b523a-112">When you open the BAM portal, you will be asked for your credentials.</span></span> <span data-ttu-id="b523a-113">如果您注销然后再登录，则可以在不要求提供凭据的情况下打开 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="b523a-113">If you log off and log back on, however, you are able to open the BAM portal without being asked for your credentials.</span></span>  
>   
>  <span data-ttu-id="b523a-114">BizTalk Server 只有在单计算机配置中才支持本地组和本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b523a-114">BizTalk Server supports local group and user accounts only in single computer configurations.</span></span> <span data-ttu-id="b523a-115">BizTalk Server 在单计算机配置和多计算机配置中都支持域组和域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b523a-115">BizTalk Server supports domain group and user accounts in both single and multiple computer configurations.</span></span>  

## <a name="running-the-bam-portal-in-a-64-bit-environment"></a><span data-ttu-id="b523a-116">在 64 位环境下运行 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="b523a-116">Running the BAM Portal in a 64-bit Environment</span></span>  
 <span data-ttu-id="b523a-117">如果在 64 位环境中使用 Internet 信息服务 (IIS)，则必须将 IIS 设置为 32 位模式运行 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="b523a-117">If you are using Internet Information Services (IIS) in a 64-bit environment, you must set IIS to 32-bit mode to run the BAM portal.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="b523a-118">不必将 IIS7 设置为 32 位模式。</span><span class="sxs-lookup"><span data-stu-id="b523a-118">You do not have to set IIS7 to 32-bit mode.</span></span>  

#### <a name="to-set-a-64-bit-mode-iis-installation-to-32-bit-mode"></a><span data-ttu-id="b523a-119">将安装的 64 位模式 IIS 设置为 32 位模式</span><span class="sxs-lookup"><span data-stu-id="b523a-119">To set a 64-bit mode IIS installation to 32-bit mode</span></span>  

1.  <span data-ttu-id="b523a-120">打开命令提示符并运行**adsutil**命令。</span><span class="sxs-lookup"><span data-stu-id="b523a-120">Open a command prompt and run the **adsutil** command.</span></span> <span data-ttu-id="b523a-121">若要执行此操作，请单击**启动**，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="b523a-121">To do this, click **Start**, click **Run**, and then type **cmd**.</span></span>  

2.  <span data-ttu-id="b523a-122">在命令提示符下键入以下内容： `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`。</span><span class="sxs-lookup"><span data-stu-id="b523a-122">Type the following at the command prompt: `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`.</span></span>  

3.  <span data-ttu-id="b523a-123">关闭命令提示符。</span><span class="sxs-lookup"><span data-stu-id="b523a-123">Close the command prompt.</span></span>  

## <a name="configuring-the-bam-portal-banner"></a><span data-ttu-id="b523a-124">配置 BAM 门户横幅</span><span class="sxs-lookup"><span data-stu-id="b523a-124">Configuring the BAM Portal Banner</span></span>  
 <span data-ttu-id="b523a-125">可以修改 BAM 门户页以显示类似如下的、有关您业务的文本和图形：</span><span class="sxs-lookup"><span data-stu-id="b523a-125">You can modify the BAM portal page to display similar text and graphics about your business:</span></span>  

- <span data-ttu-id="b523a-126">Windows Server System 徽标，它位于 BAM 门户页的右上角。</span><span class="sxs-lookup"><span data-stu-id="b523a-126">The Windows Server System logo, which is located in the upper-right corner of the BAM portal page.</span></span>  

  <span data-ttu-id="b523a-127">在以下过程中，您将编辑级联样式表文件（.css 文件）来自定义 BAM 门户的外观。</span><span class="sxs-lookup"><span data-stu-id="b523a-127">In the following procedure you edit a cascading style sheet file (.css file) to customize the look of the BAM portal.</span></span> <span data-ttu-id="b523a-128">只支持对指定类的修改。</span><span class="sxs-lookup"><span data-stu-id="b523a-128">Modifications to the specified classes are the only modifications supported.</span></span> <span data-ttu-id="b523a-129">系统已尽可能孤立对类所做修改的影响，这样如果修改过程中出现错误，则 BAM 门户仍处于工作状态。</span><span class="sxs-lookup"><span data-stu-id="b523a-129">As much as possible, the impact of modifications to classes has been isolated so that errors made during the modification process leave the BAM portal in a working state.</span></span>  

> [!CAUTION]
>  <span data-ttu-id="b523a-130">在 styles.css 文件中修改其他类将隐藏数据和门户功能，并可能使门户无法使用。</span><span class="sxs-lookup"><span data-stu-id="b523a-130">Modifying other classes in the styles.css file will hide data and portal features, and may make the portal unusable.</span></span>  

#### <a name="to-configure-the-banner"></a><span data-ttu-id="b523a-131">配置横幅</span><span class="sxs-lookup"><span data-stu-id="b523a-131">To configure the banner</span></span>  

1. <span data-ttu-id="b523a-132">编辑 BAM 门户 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-132">Edit the BAM portal web.config file.</span></span> <span data-ttu-id="b523a-133">若要执行此操作，请单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，然后再单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b523a-133">To do this, click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="b523a-134">主页快速入门内容是可替换通过修改以下行：\<添加键 ="MainPageContentUrl"value="~/MainPageContent.htm"/\>。</span><span class="sxs-lookup"><span data-stu-id="b523a-134">The main page quick-start contents are replaceable by modifying the following line: \<add key="MainPageContentUrl" value="~/MainPageContent.htm"/\>.</span></span> <span data-ttu-id="b523a-135">更改**MainPageContent.htm**值字段，使其指向您自己的 HTML 文件中。</span><span class="sxs-lookup"><span data-stu-id="b523a-135">Change **MainPageContent.htm** in the value field to point to your own HTML file.</span></span> <span data-ttu-id="b523a-136">该 HTML 文件必须位于 web.config 文件所在的目录中。</span><span class="sxs-lookup"><span data-stu-id="b523a-136">The HTML file must be in the same directory as the web.config file.</span></span>  

3. <span data-ttu-id="b523a-137">可以更改页标识文本通过将以下行添加到 web.config 文件：\<添加键 ="PortalTitle"value ="新标识 text"/\>。</span><span class="sxs-lookup"><span data-stu-id="b523a-137">Change the page identifying text by adding the following line to the web.config file: \<add key=”PortalTitle” value=”New Identifying text”/\>.</span></span> <span data-ttu-id="b523a-138">将值字段更改为包含标识门户的文本。</span><span class="sxs-lookup"><span data-stu-id="b523a-138">Change the value field to contain the text to identify the portal.</span></span>  

4. <span data-ttu-id="b523a-139">编辑 BAM 门户 styles.css 文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-139">Edit the BAM portal styles.css file.</span></span> <span data-ttu-id="b523a-140">单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b523a-140">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css, and then click **OK**.</span></span>  

5. <span data-ttu-id="b523a-141">通过找到.headerLogo div 类并将以下行更改中右上角的徽标： 背景图像： url("../ images/WSS_Logo.gif");使其指向已创建的图像文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-141">Change the logo in the upper-right corner by locating the .headerLogo div class and changing the following line:   background-image: url("../images/WSS_Logo.gif"); to point to the image file you have created.</span></span> <span data-ttu-id="b523a-142">建议您使用 .gif 格式的图像。</span><span class="sxs-lookup"><span data-stu-id="b523a-142">We recommend that you use a .gif format image.</span></span>  

6. <span data-ttu-id="b523a-143">更改 SharePoint 图标，请找到.headerPageIcon div 类并将以下行： 背景图像： url("../ images/btsSuiteProduction.gif");使其指向已创建的图像文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-143">Change the SharePoint icon by locating the .headerPageIcon div class and changing the following line: background-image: url("../images/btsSuiteProduction.gif"); to point to the image file you have created.</span></span>  

7. <span data-ttu-id="b523a-144">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-144">Save the file.</span></span>  

8. <span data-ttu-id="b523a-145">打开 BAM 门户查看您所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b523a-145">Open the BAM portal to view your changes.</span></span>  

## <a name="modifying-the-bam-portal-webconfig-file"></a><span data-ttu-id="b523a-146">修改 BAM 门户 web.config 文件</span><span class="sxs-lookup"><span data-stu-id="b523a-146">Modifying the BAM Portal web.config File</span></span>  
 <span data-ttu-id="b523a-147">如果 BAM 门户驻留在将企业单一登录 (SSO) 证书用于安全套接字层 (SSL) 的服务器上，则必须将该门户配置为接受证书的正确 URL。</span><span class="sxs-lookup"><span data-stu-id="b523a-147">If your BAM portal resides on a server that uses Enterprise Single Sign-On (SSO) certificates for Secure Sockets Layer (SSL), you must configure the portal to accept the proper URL for the certificate.</span></span>  

#### <a name="to-modify-the-bam-portal-to-support-ssl-sites"></a><span data-ttu-id="b523a-148">将 BAM 门户修改为支持 SSL 站点</span><span class="sxs-lookup"><span data-stu-id="b523a-148">To modify the BAM portal to support SSL sites</span></span>  

1. <span data-ttu-id="b523a-149">使用记事本打开 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-149">Open the web.config file using Notepad.</span></span> <span data-ttu-id="b523a-150">单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，然后再单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b523a-150">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="b523a-151">将文件中的以下两行修改为指向启用了 SSL 的门户的位置：</span><span class="sxs-lookup"><span data-stu-id="b523a-151">Modify the following two lines in the file to point to the location of your SSL-enabled portal:</span></span>  

   ```  
   <add key="BamQueryWSUrl" value="http://localhost/BAM/BamQueryService/BamQueryService.asmx"/>  
   <add key="BamManagementWSUrl" value="http://localhost/BAM/BamManagementService/BamManagementService.asmx"/>  
   ```  

3. <span data-ttu-id="b523a-152">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-152">Save the file.</span></span>  

   <span data-ttu-id="b523a-153">BAM 门户显示并接受符合已为数据配置的区域性的数据格式。</span><span class="sxs-lookup"><span data-stu-id="b523a-153">The BAM portal displays and accepts data formatted according to the culture for which it has been configured.</span></span> <span data-ttu-id="b523a-154">该配置在 web.config 文件中指定。</span><span class="sxs-lookup"><span data-stu-id="b523a-154">The configuration is specified in the web.config file.</span></span> <span data-ttu-id="b523a-155">Web 门户将忽略 Internet Explorer 发送的“接受语言”信息。</span><span class="sxs-lookup"><span data-stu-id="b523a-155">The Web portal ignores the “Accept Language” information sent by Internet Explorer.</span></span> <span data-ttu-id="b523a-156">例如，假设您正在运行 Internet Explorer 设置为日语区域性设置和 BAM 门户配置为使用美国英语区域性设置。</span><span class="sxs-lookup"><span data-stu-id="b523a-156">For example, suppose that you are running Internet Explorer which is set for a Japanese culture setting and have configured the BAM portal to use the U.S. English culture setting.</span></span> <span data-ttu-id="b523a-157">在这种情况下数据的项，如日期和整数，则会显示，接受，并使用适用于美国规则排序英语区域性设置而不是适用于日语区域性设置的规则。</span><span class="sxs-lookup"><span data-stu-id="b523a-157">In this case data items, such as dates and integers, will be displayed, accepted, and sorted using rules appropriate to the U.S. English culture setting rather than rules appropriate to the Japanese culture setting.</span></span> <span data-ttu-id="b523a-158">任何使用日语格式输入的特定于区域性的信息将被视为无效的 BAM 门户因为它只接受采用格式美国的数据美国英语的默认值。</span><span class="sxs-lookup"><span data-stu-id="b523a-158">Any culture-specific information entered using Japanese formatting will be considered invalid by the BAM portal because it will expect data formatted for U.S. English.</span></span>  

   <span data-ttu-id="b523a-159">若要基于区域性设置对数据的可变显示和格式设置进行一致性处理，请选择适用于所有 BAM 门户客户端的语言。</span><span class="sxs-lookup"><span data-stu-id="b523a-159">To obtain consistent handling of display and formatting of data that is variable based on the culture settings, choose a language that is appropriate for all BAM portal clients.</span></span> <span data-ttu-id="b523a-160">配置 BAM 门户为此区域性。</span><span class="sxs-lookup"><span data-stu-id="b523a-160">Configure the BAM portal for this culture.</span></span> <span data-ttu-id="b523a-161">必须安装多语言用户界面包以确保将每个客户端设置为所选区域性。</span><span class="sxs-lookup"><span data-stu-id="b523a-161">You must ensure that every client is set to the chosen culture by installing the Multilingual User Interface Pack.</span></span>  

   <span data-ttu-id="b523a-162">非美国的英语安装 BAM 它可能需要在 web.config 文件中设置的区域性参数。</span><span class="sxs-lookup"><span data-stu-id="b523a-162">For non-U.S. English installations of BAM it may be necessary to set the culture parameter in the web.config file.</span></span> <span data-ttu-id="b523a-163">需要设置区域性参数的情况包括：</span><span class="sxs-lookup"><span data-stu-id="b523a-163">Cases where you may need to do this are:</span></span>  

-   <span data-ttu-id="b523a-164">要本地化日期和时间的显示格式。</span><span class="sxs-lookup"><span data-stu-id="b523a-164">To localize the format of date and time displays.</span></span>  

-   <span data-ttu-id="b523a-165">要本地化货币的显示格式。</span><span class="sxs-lookup"><span data-stu-id="b523a-165">To localize the format of currency displays.</span></span>  

#### <a name="to-modify-the-culture-setting-of-the-portal"></a><span data-ttu-id="b523a-166">修改门户的区域性设置</span><span class="sxs-lookup"><span data-stu-id="b523a-166">To modify the culture setting of the portal</span></span>  

1. <span data-ttu-id="b523a-167">使用记事本打开 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-167">Open the web.config file using Notepad.</span></span> <span data-ttu-id="b523a-168">单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，然后再单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b523a-168">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="b523a-169">修改以下行中的文件以反映相应的全球化设置区域性属性：</span><span class="sxs-lookup"><span data-stu-id="b523a-169">Modify the culture attributes in the following line in the file to reflect the appropriate globalization settings:</span></span>  

   ```  
   <globalization requestEncoding="utf-8" responseEncoding="utf-8" culture="de-DE" uiCulture="en" />  
   ```  

3. <span data-ttu-id="b523a-170">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-170">Save the file.</span></span>  

   <span data-ttu-id="b523a-171">在因等待大量 SQL 查询而超时的情况下，需要增大查询服务超时值。</span><span class="sxs-lookup"><span data-stu-id="b523a-171">In cases where you are experiencing time-outs while waiting for large SQL queries, it may be necessary to increase the query service time-out value.</span></span>  

#### <a name="to-increase-the-query-service-time-out-value"></a><span data-ttu-id="b523a-172">若要增大查询服务超时值</span><span class="sxs-lookup"><span data-stu-id="b523a-172">To increase the query service time-out value</span></span>  

1. <span data-ttu-id="b523a-173">使用记事本打开 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-173">Open the web.config file using Notepad.</span></span> <span data-ttu-id="b523a-174">单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b523a-174">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="b523a-175">QueryServiceTimeout 的默认值为 45 秒。</span><span class="sxs-lookup"><span data-stu-id="b523a-175">The default value for the QueryServiceTimeout is 45 seconds.</span></span> <span data-ttu-id="b523a-176">修改以下行中的值以增大或减小超时时间间隔：</span><span class="sxs-lookup"><span data-stu-id="b523a-176">Modify the value in the following line to increase or decrease the time-out interval:</span></span>  

   ```  
   <add key="QueryServiceTimeout" value="45" />  
   ```  

3. <span data-ttu-id="b523a-177">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-177">Save the file.</span></span>  

   <span data-ttu-id="b523a-178">在多服务器环境下，有时候某一服务器会脱机。</span><span class="sxs-lookup"><span data-stu-id="b523a-178">In a multiserver environment there may be times when a server is offline.</span></span> <span data-ttu-id="b523a-179">发生这种情况时，门户用户可能会因 BAM 门户停止响应而受到延迟。</span><span class="sxs-lookup"><span data-stu-id="b523a-179">When this happens, users of the portal may experience time delays where the BAM portal stops responding.</span></span> <span data-ttu-id="b523a-180">若要改善用户的延迟体验，可以修改服务器重试时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b523a-180">To improve the user experience you can modify the server retry interval.</span></span> <span data-ttu-id="b523a-181">这将设置一段最短时间，在这段时间内如果连接失败，则 BAM 查询 Web Services 假定服务器为脱机。</span><span class="sxs-lookup"><span data-stu-id="b523a-181">This creates a minimum time during which the BAM query Web service assumes that the server is offline after a connection has failed once.</span></span>  

   <span data-ttu-id="b523a-182">值指示是否本地数据库超时尝试联系远程数据库时，将数据标记为不完整和本地计算机不会尝试连接到远程数据库，直到指定的时间已过。</span><span class="sxs-lookup"><span data-stu-id="b523a-182">The value indicates that if a local database times out while trying to contact a remote database, the data is marked as incomplete and the local computer will not attempt to connect to the remote database until the specified time has elapsed.</span></span>  

#### <a name="to-increase-the-retry-interval-for-distributed-activities-in-a-multiserver-environment"></a><span data-ttu-id="b523a-183">增大多服务器环境下发布式活动的重试时间间隔</span><span class="sxs-lookup"><span data-stu-id="b523a-183">To increase the retry interval for distributed activities in a multiserver environment</span></span>  

1. <span data-ttu-id="b523a-184">使用记事本打开 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-184">Open the web.config file using Notepad.</span></span> <span data-ttu-id="b523a-185">单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b523a-185">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="b523a-186">ServerRetryInterval 的默认值为五分钟。</span><span class="sxs-lookup"><span data-stu-id="b523a-186">The default value for the ServerRetryInterval is five minutes.</span></span> <span data-ttu-id="b523a-187">修改以下行中的值以增大或减小服务器重试时间间隔：</span><span class="sxs-lookup"><span data-stu-id="b523a-187">Modify the value in the following line to increase or decrease the server retry interval:</span></span>  

   ```  
   <add key="ServerRetryInterval" value="5"/>  
   ```  

3. <span data-ttu-id="b523a-188">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-188">Save the file.</span></span>  

#### <a name="to-configure-how-alert-notification-options-are-presented-in-the-bam-portal"></a><span data-ttu-id="b523a-189">配置如何在 BAM 门户中显示警报通知选项</span><span class="sxs-lookup"><span data-stu-id="b523a-189">To configure how alert notification options are presented in the BAM portal</span></span>  

1. <span data-ttu-id="b523a-190">使用记事本打开 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-190">Open the web.config file using Notepad.</span></span> <span data-ttu-id="b523a-191">单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，然后再单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b523a-191">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="b523a-192">修改中的值字段\<添加键 ="AlertNotificationOptions"value =""/\>的 web.config 文件中使用以逗号分隔的列表指定有效的通知选项具有下列值之一的行。</span><span class="sxs-lookup"><span data-stu-id="b523a-192">Modify the value field in the \<add key="AlertNotificationOptions" value="" /\> line of the web.config file with a comma-delimited list specifying valid notification options with one of the following values.</span></span> <span data-ttu-id="b523a-193">空值将以服务器返回的顺序显示服务器上可用的所有通知选项。</span><span class="sxs-lookup"><span data-stu-id="b523a-193">An empty value displays all notification options available on the server in the order returned by the server.</span></span> <span data-ttu-id="b523a-194">任何不可识别的值等效于空值。</span><span class="sxs-lookup"><span data-stu-id="b523a-194">Any unrecognized value is equivalent to an empty value.</span></span>  


   |    <span data-ttu-id="b523a-195">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="b523a-195">Value</span></span>    |                                              <span data-ttu-id="b523a-196">Description</span><span class="sxs-lookup"><span data-stu-id="b523a-196">Description</span></span>                                               |
   |-------------|--------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="b523a-197">File, Email</span><span class="sxs-lookup"><span data-stu-id="b523a-197">File, Email</span></span> | <span data-ttu-id="b523a-198">显示文件选项和电子邮件选项。</span><span class="sxs-lookup"><span data-stu-id="b523a-198">File and E-mail options are displayed.</span></span> <span data-ttu-id="b523a-199">在下拉列表中，先显示文件再显示电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b523a-199">In the drop-down list, File is displayed first and then E-mail.</span></span> |
   | <span data-ttu-id="b523a-200">Email, File</span><span class="sxs-lookup"><span data-stu-id="b523a-200">Email, File</span></span> | <span data-ttu-id="b523a-201">显示文件选项和电子邮件选项。</span><span class="sxs-lookup"><span data-stu-id="b523a-201">File and E-mail options are displayed.</span></span> <span data-ttu-id="b523a-202">在下拉列表中，先显示电子邮件再显示文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-202">In the drop-down list, E-mail is displayed first and then File.</span></span> |
   |    <span data-ttu-id="b523a-203">文件</span><span class="sxs-lookup"><span data-stu-id="b523a-203">File</span></span>     |                             <span data-ttu-id="b523a-204">在门户中仅显示文件通知。</span><span class="sxs-lookup"><span data-stu-id="b523a-204">Only File notification is displayed in portal.</span></span>                             |
   |    <span data-ttu-id="b523a-205">电子邮件</span><span class="sxs-lookup"><span data-stu-id="b523a-205">Email</span></span>    |                            <span data-ttu-id="b523a-206">在门户中仅显示电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="b523a-206">Only E-mail notification is displayed in portal.</span></span>                            |


3. <span data-ttu-id="b523a-207">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="b523a-207">Save the file.</span></span>  

## <a name="distributed-server-environments"></a><span data-ttu-id="b523a-208">分布式服务器环境</span><span class="sxs-lookup"><span data-stu-id="b523a-208">Distributed Server Environments</span></span>  
 <span data-ttu-id="b523a-209">如果您安装的 BAM 门户将警报和 BAM 门户置于不同的服务器上，你将看到事件日志中的以下错误:"System.Reflection.TargetInvocationException： 调用目标引发异常。</span><span class="sxs-lookup"><span data-stu-id="b523a-209">If your installation of the BAM portal places the alerts and the BAM portal on different servers, you will see the following error in the event log: "System.Reflection.TargetInvocationException: Exception has been thrown by the target of an invocation.</span></span> <span data-ttu-id="b523a-210">---> 找不到指定的 Notification Services 实例的项的注册表。"</span><span class="sxs-lookup"><span data-stu-id="b523a-210">---> The registry entries for the specified instance of Notification Services could not be found."</span></span>  

#### <a name="to-configure-the-portal-and-alerts-on-different-servers"></a><span data-ttu-id="b523a-211">配置位于不同服务器上的门户和警报</span><span class="sxs-lookup"><span data-stu-id="b523a-211">To configure the portal and alerts on different servers</span></span>  

1. <span data-ttu-id="b523a-212">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="b523a-212">Open a command prompt.</span></span>  

2. <span data-ttu-id="b523a-213">运行**C:\Program Files\Microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register-name bamalerts-server**<em>\<服务器名称\></em>替换*\<服务器名称\>* 与服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="b523a-213">Run **C:\Program Files\Microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register -name bamalerts -server**<em>\<server name\></em> Replace *\<server name\>* with the name of the server.</span></span>  

3. <span data-ttu-id="b523a-214">按下 F5 键来刷新浏览器。</span><span class="sxs-lookup"><span data-stu-id="b523a-214">Press F5 to refresh your browser.</span></span>  

## <a name="configuring-iis-to-allow-the-bam-portal-to-use-the-kerberos-network-protocol"></a><span data-ttu-id="b523a-215">将 IIS 配置为允许 BAM 门户使用 Kerberos 网络协议</span><span class="sxs-lookup"><span data-stu-id="b523a-215">Configuring IIS to Allow the BAM Portal to Use the Kerberos Network Protocol</span></span>  
 <span data-ttu-id="b523a-216">如果要在 BAM 门户中使用 Kerberos 网络协议，必须修改 Web 门户站点的 ACL 安全性。</span><span class="sxs-lookup"><span data-stu-id="b523a-216">If you want to use the Kerberos network protocol with the BAM portal you must modify the ACL security for the Web portal.</span></span> <span data-ttu-id="b523a-217">如果 IIS 配置不正确，用户将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="b523a-217">If IIS is not configured properly, users will receive the following error:</span></span>  

 <span data-ttu-id="b523a-218">HTTP 错误 401.1-未经授权： 由于凭据无效而被拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="b523a-218">HTTP Error 401.1 - Unauthorized: Access is denied due to invalid credentials.</span></span>  

 <span data-ttu-id="b523a-219">有关修改 IIS 安全设置的其他信息，请参阅知识库文章，网址[ http://go.microsoft.com/fwlink/?LinkId=57922 ](http://go.microsoft.com/fwlink/?LinkId=57922)。</span><span class="sxs-lookup"><span data-stu-id="b523a-219">For additional information about modifying the IIS security settings, see the Knowledge Base article at [http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922).</span></span>  

## <a name="viewing-aggregate-bam-data-in-the-bam-portal-in-sql-server-2008--deployments"></a><span data-ttu-id="b523a-220">在 SQL Server 2008 部署 BAM 门户中查看聚合 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="b523a-220">Viewing Aggregate BAM Data in the BAM Portal in SQL Server 2008  Deployments</span></span>  
 <span data-ttu-id="b523a-221">若要从部署环境中使用 SQL Server 2008 时连接到 BAM 门户的客户端计算机在 BAM 门户中查看聚合数据，必须在客户端计算机上安装 Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB 访问接口。</span><span class="sxs-lookup"><span data-stu-id="b523a-221">To view aggregate data in the BAM portal from a client computer connecting to the BAM portal when the deployment environment uses SQL Server 2008, you must install Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB Provider on the client computer.</span></span> <span data-ttu-id="b523a-222">如果未安装分析服务，用户将会收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="b523a-222">If the analysis services are not installed users will receive the following error message:</span></span>  

 <span data-ttu-id="b523a-223">在服务器*\<servername\>* 太忙或无法联系。</span><span class="sxs-lookup"><span data-stu-id="b523a-223">The server *\<servername\>* cannot be contacted or is too busy.</span></span>  



## <a name="see-also"></a><span data-ttu-id="b523a-224">请参阅</span><span class="sxs-lookup"><span data-stu-id="b523a-224">See Also</span></span>  
 [<span data-ttu-id="b523a-225">规划 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="b523a-225">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)