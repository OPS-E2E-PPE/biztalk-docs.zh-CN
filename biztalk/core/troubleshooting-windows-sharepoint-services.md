---
title: Windows SharePoint Services 故障排除 |Microsoft Docs
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
ms.openlocfilehash: 95d0b833028afdc3c2b560ed60802ff60d6d4046
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253613"
---
# <a name="troubleshooting-windows-sharepoint-services"></a><span data-ttu-id="1afc7-102">Windows SharePoint Services 故障排除</span><span class="sxs-lookup"><span data-stu-id="1afc7-102">Troubleshooting Windows SharePoint Services</span></span>
<span data-ttu-id="1afc7-103">Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Windows SharePoint Services 适配器使用。</span><span class="sxs-lookup"><span data-stu-id="1afc7-103">Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] is used by the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="1afc7-104">本主题介绍与 Windows SharePoint Services 和这些问题的可能解决方法可能会遇到一些已知的问题。</span><span class="sxs-lookup"><span data-stu-id="1afc7-104">This topic describes some known issues that may be encountered with Windows SharePoint Services and possible resolutions to these issues.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="1afc7-105">已知问题</span><span class="sxs-lookup"><span data-stu-id="1afc7-105">Known Issues</span></span>  
  
#### <a name="login-failed-for-user-nt-authoritynetwork-service-error-occurs-when-attempting-to-create-content-database"></a><span data-ttu-id="1afc7-106">登录失败的用户 NT AUTHORITY\NETWORK SERVICE 错误发生时尝试创建内容数据库</span><span class="sxs-lookup"><span data-stu-id="1afc7-106">Login failed for user 'NT AUTHORITY\NETWORK SERVICE' error occurs when attempting to create content database</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="1afc7-107">问题</span><span class="sxs-lookup"><span data-stu-id="1afc7-107">Problem</span></span>  
 <span data-ttu-id="1afc7-108">当您尝试创建使用 SharePoint 管理中心网站的内容数据库时，将显示如下错误：</span><span class="sxs-lookup"><span data-stu-id="1afc7-108">When you attempt to create a content database using the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="1afc7-109">用户 NT AUTHORITY\NETWORK SERVICE 登录失败</span><span class="sxs-lookup"><span data-stu-id="1afc7-109">Login failed for user 'NT AUTHORITY\NETWORK SERVICE'</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="1afc7-110">原因</span><span class="sxs-lookup"><span data-stu-id="1afc7-110">Cause</span></span>  
 <span data-ttu-id="1afc7-111">要连接到数据库的数据库所有者不同于 Windows SharePoint Services 运行的应用程序池标识时，将出现此问题。</span><span class="sxs-lookup"><span data-stu-id="1afc7-111">This issue occurs when the database owner of the database that you are connecting to is different from the application pool identity that Windows SharePoint Services is running under.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="1afc7-112">解决方法</span><span class="sxs-lookup"><span data-stu-id="1afc7-112">Resolution</span></span>  
 <span data-ttu-id="1afc7-113">若要解决此问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1afc7-113">To resolve this issue, do one of the following:</span></span>  
  
-   <span data-ttu-id="1afc7-114">网络服务帐户授予 SQL Server 中的"数据库创建"权限。</span><span class="sxs-lookup"><span data-stu-id="1afc7-114">Grant the NETWORK SERVICE account "Database Creation" rights in SQL Server.</span></span>  
  
-   <span data-ttu-id="1afc7-115">将应用程序池标识帐户更改为 SQL Server 中具有"数据库创建"权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="1afc7-115">Change the application pool identity account to an account that has "Database Creation" rights in SQL Server.</span></span>  
  
#### <a name="service-unavailable-error-occurs-when-accessing-the-sharepoint-central-administration-web-site"></a><span data-ttu-id="1afc7-116">访问 SharePoint 管理中心网站时出现"服务不可用"错误</span><span class="sxs-lookup"><span data-stu-id="1afc7-116">"Service Unavailable" error occurs when accessing the SharePoint Central Administration Web site</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="1afc7-117">问题</span><span class="sxs-lookup"><span data-stu-id="1afc7-117">Problem</span></span>  
 <span data-ttu-id="1afc7-118">当您尝试打开 SharePoint 管理中心网站时，将显示如下错误：</span><span class="sxs-lookup"><span data-stu-id="1afc7-118">When you attempt to open the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="1afc7-119">服务不可用</span><span class="sxs-lookup"><span data-stu-id="1afc7-119">Service Unavailable</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="1afc7-120">原因</span><span class="sxs-lookup"><span data-stu-id="1afc7-120">Cause</span></span>  
 <span data-ttu-id="1afc7-121">此错误的最常见原因是应用程序池 （IIS 6.0 或 IIS 7.0） 或宿主 COM + 应用程序 (IIS 5.x) 已停止 SharePoint 管理中心网站站点。</span><span class="sxs-lookup"><span data-stu-id="1afc7-121">The most common cause for this error is that the application pool (IIS 6.0 or IIS 7.0) or hosting COM+ application (IIS 5.x) for the SharePoint Central Administration Web site is stopped.</span></span> <span data-ttu-id="1afc7-122">这通常会发生的应用程序池或 COM + 应用程序使用标识配置，但如果指定的用户名和/或密码无效。</span><span class="sxs-lookup"><span data-stu-id="1afc7-122">This commonly occurs if the application pool or COM+ application is configured with an identity for which the specified user name and/or password is invalid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="1afc7-123">解决方法</span><span class="sxs-lookup"><span data-stu-id="1afc7-123">Resolution</span></span>  
 <span data-ttu-id="1afc7-124">按照本主题的"设置 IIS 应用程序主机进程标识"部分中的步骤[解决 IIS 权限疑难问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md)设置相应的主机进程标识。</span><span class="sxs-lookup"><span data-stu-id="1afc7-124">Follow the steps in the "Setting IIS Application Host Process Identity" section of the topic [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to set the appropriate host process identity.</span></span>  
  
#### <a name="cannot-connect-to-the-configuration-database-error-occurs-when-attempting-to-extend-and-create-a-content-database"></a><span data-ttu-id="1afc7-125">尝试扩展和创建内容数据库时出现"无法连接到配置数据库"错误</span><span class="sxs-lookup"><span data-stu-id="1afc7-125">"Cannot connect to the configuration database" error occurs when attempting to extend and create a content database</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="1afc7-126">问题</span><span class="sxs-lookup"><span data-stu-id="1afc7-126">Problem</span></span>  
 <span data-ttu-id="1afc7-127">当尝试扩展并创建使用 SharePoint 管理中心网站的内容数据库时，将显示如下错误：</span><span class="sxs-lookup"><span data-stu-id="1afc7-127">When you attempt to extend and create a content database using the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="1afc7-128">无法连接到配置数据库</span><span class="sxs-lookup"><span data-stu-id="1afc7-128">Cannot connect to the configuration database</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="1afc7-129">原因</span><span class="sxs-lookup"><span data-stu-id="1afc7-129">Cause</span></span>  
 <span data-ttu-id="1afc7-130">如果正在运行 SharePoint 管理中心网站的应用程序池使用的帐户不具有到 SQL Server 数据库所需的权限，将出现此问题。</span><span class="sxs-lookup"><span data-stu-id="1afc7-130">This issue occurs when the account that is used by the application pool that is running the SharePoint Central Administration Web site does not have the required permissions to the SQL Server database.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="1afc7-131">解决方法</span><span class="sxs-lookup"><span data-stu-id="1afc7-131">Resolution</span></span>  
 <span data-ttu-id="1afc7-132">若要解决此问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1afc7-132">To resolve this issue, do one of the following:</span></span>  
  
-   <span data-ttu-id="1afc7-133">授予应用程序池用于在 SQL Server 中的 SharePoint 管理中心 Web 站点"数据库创建"权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="1afc7-133">Grant the account that is used by the application pool for the SharePoint Central Administration Web site "Database Creation" rights in SQL Server.</span></span>  
  
-   <span data-ttu-id="1afc7-134">将应用程序池标识帐户更改为 SQL Server 中具有"数据库创建"权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="1afc7-134">Change the application pool identity account to an account that has "Database Creation" rights in SQL Server.</span></span>  
  
#### <a name="the-sharepoint-timer-service-service-failed-to-start-error-is-generated-in-the-application-log-after-rebooting-server"></a><span data-ttu-id="1afc7-135">重新启动服务器后应用程序日志中生成"SharePoint 定时服务无法启动"错误</span><span class="sxs-lookup"><span data-stu-id="1afc7-135">"The SharePoint Timer Service service failed to start" error is generated in the Application log after rebooting server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="1afc7-136">问题</span><span class="sxs-lookup"><span data-stu-id="1afc7-136">Problem</span></span>  
 <span data-ttu-id="1afc7-137">重新启动服务器之后, 您将看到事件日志中的以下错误：</span><span class="sxs-lookup"><span data-stu-id="1afc7-137">After restarting the server, you see the following error in the event logs:</span></span>  
  
 <span data-ttu-id="1afc7-138">SharePoint 定时服务无法启动</span><span class="sxs-lookup"><span data-stu-id="1afc7-138">The SharePoint Timer Service service failed to start</span></span>  
  
 <span data-ttu-id="1afc7-139">打开 SharePoint 管理中心站点时，还可能会看到以下错误：</span><span class="sxs-lookup"><span data-stu-id="1afc7-139">You may also see the following error when you open the SharePoint Central Administration site:</span></span>  
  
 <span data-ttu-id="1afc7-140">无法连接到 WSS 配置数据库 STS_Config</span><span class="sxs-lookup"><span data-stu-id="1afc7-140">Unable to connect to the WSS configuration database STS_Config</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="1afc7-141">原因</span><span class="sxs-lookup"><span data-stu-id="1afc7-141">Cause</span></span>  
 <span data-ttu-id="1afc7-142">SharePoint 定时服务无法联系时发生此错误[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]后重新启动数据库。</span><span class="sxs-lookup"><span data-stu-id="1afc7-142">This error occurs when the SharePoint Timer service fails to contact the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] database after rebooting.</span></span> <span data-ttu-id="1afc7-143">SharePoint 定时服务用于发送通知和执行计划的任务的[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1afc7-143">The SharePoint Timer service is used to send notifications and perform scheduled tasks for [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span> <span data-ttu-id="1afc7-144">SharePoint 定时服务无法启动的最常见原因是，通过为其用户名称和/或密码不再有效的标识配置用于运行服务的帐户。</span><span class="sxs-lookup"><span data-stu-id="1afc7-144">The most common reason that the SharePoint Timer service fails to start is that the account used to run the service is configured with an identity for which the user name and/or password are no longer valid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="1afc7-145">解决方法</span><span class="sxs-lookup"><span data-stu-id="1afc7-145">Resolution</span></span>  
 <span data-ttu-id="1afc7-146">请确保用户名和密码指定为 SharePoint 定时服务登录帐户正确并且已启动该服务。</span><span class="sxs-lookup"><span data-stu-id="1afc7-146">Ensure that the user name and password specified for the SharePoint Timer service logon account are correct and that the service has been started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1afc7-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="1afc7-147">See Also</span></span>  
 <span data-ttu-id="1afc7-148">[如何配置 Windows SharePoint Services 虚拟服务器](http://support.microsoft.com/kb/832769) </span><span class="sxs-lookup"><span data-stu-id="1afc7-148">[How to configure a Windows SharePoint Services virtual server](http://support.microsoft.com/kb/832769) </span></span>  
 <span data-ttu-id="1afc7-149">[如何备份和还原使用 Microsoft SQL Server 2000 桌面引擎 (Windows) 的 Windows SharePoint Services 的安装](http://support.microsoft.com/kb/833797) </span><span class="sxs-lookup"><span data-stu-id="1afc7-149">[How to back up and restore installations of Windows SharePoint Services that use Microsoft SQL Server 2000 Desktop Engine (Windows)](http://support.microsoft.com/kb/833797) </span></span>  
 <span data-ttu-id="1afc7-150">[连接到 Windows SharePoint Services Web 站点时收到"无法连接到配置数据库"错误消息](http://support.microsoft.com/kb/823287) </span><span class="sxs-lookup"><span data-stu-id="1afc7-150">[You receive a "Cannot connect to the configuration database" error message when you connect to your Windows SharePoint Services Web site](http://support.microsoft.com/kb/823287) </span></span>  
 <span data-ttu-id="1afc7-151">[当您浏览 Windows SharePoint Services 网站时收到"服务不可用"错误消息](http://support.microsoft.com/kb/823552) </span><span class="sxs-lookup"><span data-stu-id="1afc7-151">[You Receive a "Service Unavailable" Error Message When You Browse a Windows SharePoint Services Web Site](http://support.microsoft.com/kb/823552) </span></span>  
 [<span data-ttu-id="1afc7-152">管理您的 Windows SharePoint Services 内容数据库时收到"Database < 数据库名称 > 已存在"错误消息</span><span class="sxs-lookup"><span data-stu-id="1afc7-152">You receive a "Database <Database_Name> already exists" error message when you manage your Windows SharePoint Services content database</span></span>](http://support.microsoft.com/kb/828815)