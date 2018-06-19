---
title: 故障排除 Windows SharePoint Services |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9acf9a0d-2c92-4227-80f8-b2d0cca0c232
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51243216f2adb73454477252c7b54358df229610
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286989"
---
# <a name="troubleshooting-windows-sharepoint-services"></a><span data-ttu-id="ae8e9-102">故障排除 Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="ae8e9-102">Troubleshooting Windows SharePoint Services</span></span>
<span data-ttu-id="ae8e9-103">Microsoft[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]由 Windows SharePoint Services 适配器使用。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-103">Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] is used by the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="ae8e9-104">本主题介绍使用 Windows SharePoint Services 时可能遇到的某些已知问题以及这些问题的可能解决方法。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-104">This topic describes some known issues that may be encountered with Windows SharePoint Services and possible resolutions to these issues.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="ae8e9-105">已知问题</span><span class="sxs-lookup"><span data-stu-id="ae8e9-105">Known Issues</span></span>  
  
#### <a name="login-failed-for-user-nt-authoritynetwork-service-error-occurs-when-attempting-to-create-content-database"></a><span data-ttu-id="ae8e9-106">用户“NT AUTHORITY\NETWORK SERVICE”尝试创建内容数据库时登录失败并出错</span><span class="sxs-lookup"><span data-stu-id="ae8e9-106">Login failed for user 'NT AUTHORITY\NETWORK SERVICE' error occurs when attempting to create content database</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="ae8e9-107">问题</span><span class="sxs-lookup"><span data-stu-id="ae8e9-107">Problem</span></span>  
 <span data-ttu-id="ae8e9-108">当您尝试使用 SharePoint 管理中心网站创建内容数据库时，将显示类似于以下内容的错误：</span><span class="sxs-lookup"><span data-stu-id="ae8e9-108">When you attempt to create a content database using the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="ae8e9-109">用户“NT AUTHORITY\NETWORK SERVICE”登录失败</span><span class="sxs-lookup"><span data-stu-id="ae8e9-109">Login failed for user 'NT AUTHORITY\NETWORK SERVICE'</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="ae8e9-110">原因</span><span class="sxs-lookup"><span data-stu-id="ae8e9-110">Cause</span></span>  
 <span data-ttu-id="ae8e9-111">当您连接到的数据库的数据库所有者与 Windows SharePoint Services 运行所用的应用程序池标识不同时，将出现这一问题。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-111">This issue occurs when the database owner of the database that you are connecting to is different from the application pool identity that Windows SharePoint Services is running under.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="ae8e9-112">解决方法</span><span class="sxs-lookup"><span data-stu-id="ae8e9-112">Resolution</span></span>  
 <span data-ttu-id="ae8e9-113">若要解决此问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ae8e9-113">To resolve this issue, do one of the following:</span></span>  
  
-   <span data-ttu-id="ae8e9-114">向“网络服务”帐户授予 SQL Server 中的“数据库创建”权限。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-114">Grant the NETWORK SERVICE account "Database Creation" rights in SQL Server.</span></span>  
  
-   <span data-ttu-id="ae8e9-115">将应用程序池标识帐户更改为在 SQL Server 中具有“数据库创建”权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-115">Change the application pool identity account to an account that has "Database Creation" rights in SQL Server.</span></span>  
  
#### <a name="service-unavailable-error-occurs-when-accessing-the-sharepoint-central-administration-web-site"></a><span data-ttu-id="ae8e9-116">访问 SharePoint 管理中心网站时出现“服务不可用”错误</span><span class="sxs-lookup"><span data-stu-id="ae8e9-116">"Service Unavailable" error occurs when accessing the SharePoint Central Administration Web site</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="ae8e9-117">问题</span><span class="sxs-lookup"><span data-stu-id="ae8e9-117">Problem</span></span>  
 <span data-ttu-id="ae8e9-118">当您尝试打开 SharePoint 管理中心网站时，将显示类似于以下内容的错误：</span><span class="sxs-lookup"><span data-stu-id="ae8e9-118">When you attempt to open the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="ae8e9-119">服务不可用</span><span class="sxs-lookup"><span data-stu-id="ae8e9-119">Service Unavailable</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="ae8e9-120">原因</span><span class="sxs-lookup"><span data-stu-id="ae8e9-120">Cause</span></span>  
 <span data-ttu-id="ae8e9-121">此错误的最常见原因是 SharePoint 管理中心网站的应用程序池（IIS 6.0 或 IIS 7.0）或宿主 COM+ 应用程序 (IIS 5.x) 已停止。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-121">The most common cause for this error is that the application pool (IIS 6.0 or IIS 7.0) or hosting COM+ application (IIS 5.x) for the SharePoint Central Administration Web site is stopped.</span></span> <span data-ttu-id="ae8e9-122">如果该应用程序池或 COM+ 应用程序配置了标识，但指定的用户名和/或密码无效，则通常会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-122">This commonly occurs if the application pool or COM+ application is configured with an identity for which the specified user name and/or password is invalid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="ae8e9-123">解决方法</span><span class="sxs-lookup"><span data-stu-id="ae8e9-123">Resolution</span></span>  
 <span data-ttu-id="ae8e9-124">按照主题的"设置 IIS 应用程序主机进程标识"部分中的步骤[解决 IIS 权限问题的指导原则](../core/guidelines-for-resolving-iis-permissions-problems.md)设置适当的主机进程标识。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-124">Follow the steps in the "Setting IIS Application Host Process Identity" section of the topic [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to set the appropriate host process identity.</span></span>  
  
#### <a name="cannot-connect-to-the-configuration-database-error-occurs-when-attempting-to-extend-and-create-a-content-database"></a><span data-ttu-id="ae8e9-125">当尝试扩展和创建内容数据库时，出现“无法连接到配置数据库”错误</span><span class="sxs-lookup"><span data-stu-id="ae8e9-125">"Cannot connect to the configuration database" error occurs when attempting to extend and create a content database</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="ae8e9-126">问题</span><span class="sxs-lookup"><span data-stu-id="ae8e9-126">Problem</span></span>  
 <span data-ttu-id="ae8e9-127">当您尝试使用 SharePoint 管理中心网站扩展和创建内容数据库时，将显示类似于以下内容的错误：</span><span class="sxs-lookup"><span data-stu-id="ae8e9-127">When you attempt to extend and create a content database using the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="ae8e9-128">无法连接到配置数据库</span><span class="sxs-lookup"><span data-stu-id="ae8e9-128">Cannot connect to the configuration database</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="ae8e9-129">原因</span><span class="sxs-lookup"><span data-stu-id="ae8e9-129">Cause</span></span>  
 <span data-ttu-id="ae8e9-130">当由正在运行 SharePoint 管理中心网站的应用程序池使用的帐户对 SQL Server 数据库不具备所需的权限时，将出现此错误。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-130">This issue occurs when the account that is used by the application pool that is running the SharePoint Central Administration Web site does not have the required permissions to the SQL Server database.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="ae8e9-131">解决方法</span><span class="sxs-lookup"><span data-stu-id="ae8e9-131">Resolution</span></span>  
 <span data-ttu-id="ae8e9-132">若要解决此问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ae8e9-132">To resolve this issue, do one of the following:</span></span>  
  
-   <span data-ttu-id="ae8e9-133">向由应用程序池用于运行 SharePoint 管理中心网站的帐户授予 SQL Server 中的“数据库创建”权限。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-133">Grant the account that is used by the application pool for the SharePoint Central Administration Web site "Database Creation" rights in SQL Server.</span></span>  
  
-   <span data-ttu-id="ae8e9-134">将应用程序池标识帐户更改为在 SQL Server 中具有“数据库创建”权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-134">Change the application pool identity account to an account that has "Database Creation" rights in SQL Server.</span></span>  
  
#### <a name="the-sharepoint-timer-service-service-failed-to-start-error-is-generated-in-the-application-log-after-rebooting-server"></a><span data-ttu-id="ae8e9-135">重新启动服务器后，在应用程序日志中生成“SharePoint 定时服务无法启动”错误</span><span class="sxs-lookup"><span data-stu-id="ae8e9-135">"The SharePoint Timer Service service failed to start" error is generated in the Application log after rebooting server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="ae8e9-136">问题</span><span class="sxs-lookup"><span data-stu-id="ae8e9-136">Problem</span></span>  
 <span data-ttu-id="ae8e9-137">后重新启动服务器，你将看到事件日志中的以下错误：</span><span class="sxs-lookup"><span data-stu-id="ae8e9-137">After restarting the server, you see the following error in the event logs:</span></span>  
  
 <span data-ttu-id="ae8e9-138">SharePoint 定时服务无法启动</span><span class="sxs-lookup"><span data-stu-id="ae8e9-138">The SharePoint Timer Service service failed to start</span></span>  
  
 <span data-ttu-id="ae8e9-139">当您打开 SharePoint 管理中心站点时，您还可以看到以下错误：</span><span class="sxs-lookup"><span data-stu-id="ae8e9-139">You may also see the following error when you open the SharePoint Central Administration site:</span></span>  
  
 <span data-ttu-id="ae8e9-140">无法连接到 WSS 配置数据库 STS_Config</span><span class="sxs-lookup"><span data-stu-id="ae8e9-140">Unable to connect to the WSS configuration database STS_Config</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="ae8e9-141">原因</span><span class="sxs-lookup"><span data-stu-id="ae8e9-141">Cause</span></span>  
 <span data-ttu-id="ae8e9-142">重新启动后，当 SharePoint 定时服务无法与 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 数据库取得联系时，将出现此错误。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-142">This error occurs when the SharePoint Timer service fails to contact the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] database after rebooting.</span></span> <span data-ttu-id="ae8e9-143">SharePoint 定时服务用于为 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 发送通知和执行已计划的任务。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-143">The SharePoint Timer service is used to send notifications and perform scheduled tasks for [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span> <span data-ttu-id="ae8e9-144">SharePoint 定时服务无法启动的最常见原因是：用于运行此服务的帐户配置了一个标识，而此标识的用户名和/或密码不再有效。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-144">The most common reason that the SharePoint Timer service fails to start is that the account used to run the service is configured with an identity for which the user name and/or password are no longer valid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="ae8e9-145">解决方法</span><span class="sxs-lookup"><span data-stu-id="ae8e9-145">Resolution</span></span>  
 <span data-ttu-id="ae8e9-146">确保为 SharePoint 定时服务登录帐户指定的用户名和密码正确无误，并且已启动此服务。</span><span class="sxs-lookup"><span data-stu-id="ae8e9-146">Ensure that the user name and password specified for the SharePoint Timer service logon account are correct and that the service has been started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8e9-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae8e9-147">See Also</span></span>  
 <span data-ttu-id="ae8e9-148">[如何配置 Windows SharePoint Services 虚拟服务器](http://support.microsoft.com/kb/832769) </span><span class="sxs-lookup"><span data-stu-id="ae8e9-148">[How to configure a Windows SharePoint Services virtual server](http://support.microsoft.com/kb/832769) </span></span>  
 <span data-ttu-id="ae8e9-149">[如何备份和还原使用 Microsoft SQL Server 2000 桌面引擎 (Windows) 的 Windows SharePoint Services 的安装](http://support.microsoft.com/kb/833797) </span><span class="sxs-lookup"><span data-stu-id="ae8e9-149">[How to back up and restore installations of Windows SharePoint Services that use Microsoft SQL Server 2000 Desktop Engine (Windows)](http://support.microsoft.com/kb/833797) </span></span>  
 <span data-ttu-id="ae8e9-150">[当你连接到你的 Windows SharePoint Services Web 站点收到"无法连接到配置数据库"错误消息](http://support.microsoft.com/kb/823287) </span><span class="sxs-lookup"><span data-stu-id="ae8e9-150">[You receive a "Cannot connect to the configuration database" error message when you connect to your Windows SharePoint Services Web site](http://support.microsoft.com/kb/823287) </span></span>  
 <span data-ttu-id="ae8e9-151">[当您浏览 Windows SharePoint Services 网站时，你会收到"服务不可用"错误消息](http://support.microsoft.com/kb/823552) </span><span class="sxs-lookup"><span data-stu-id="ae8e9-151">[You Receive a "Service Unavailable" Error Message When You Browse a Windows SharePoint Services Web Site](http://support.microsoft.com/kb/823552) </span></span>  
 [<span data-ttu-id="ae8e9-152">管理您的 Windows SharePoint Services 内容数据库时收到"已存在数据库 < a s e _ >"错误消息</span><span class="sxs-lookup"><span data-stu-id="ae8e9-152">You receive a "Database <Database_Name> already exists" error message when you manage your Windows SharePoint Services content database</span></span>](http://support.microsoft.com/kb/828815)