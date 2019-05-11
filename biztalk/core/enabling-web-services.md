---
title: 启用 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- hosts, isolated
- Web services, planning
- Web services, enabling
ms.assetid: 2a4681f6-9ded-423d-baa5-5831e6a85c61
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59a811fe61a6a5b17e8c5cbf803b35d630836d05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349694"
---
# <a name="enabling-web-services"></a><span data-ttu-id="25841-102">启用 Web Services</span><span class="sxs-lookup"><span data-stu-id="25841-102">Enabling Web Services</span></span>
<span data-ttu-id="25841-103">若要发布 Web 服务，必须配置 Internet 信息服务 (IIS)、 BizTalk Isolated Hosts 和 Windows 用户和组帐户。</span><span class="sxs-lookup"><span data-stu-id="25841-103">To publish Web services, you must configure Internet Information Services (IIS), BizTalk Isolated Hosts, and Windows user and group accounts.</span></span> <span data-ttu-id="25841-104">本部分讨论如何能够在 IIS 中的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="25841-104">This section discusses how to enable Web services in IIS.</span></span> <span data-ttu-id="25841-105">有关启用 Web services 的详细信息，请参阅 IIS 文档。</span><span class="sxs-lookup"><span data-stu-id="25841-105">For more information about enabling Web services, see the IIS documentation.</span></span>  
  
 <span data-ttu-id="25841-106">**Internet Information Services**</span><span class="sxs-lookup"><span data-stu-id="25841-106">**Internet Information Services**</span></span>  
  
 <span data-ttu-id="25841-107">可以将 Web 服务发布到了配置有 ASP.NET 的 IIS 的 Windows 系统。</span><span class="sxs-lookup"><span data-stu-id="25841-107">You can publish Web services to Windows systems that have IIS configured with ASP.NET.</span></span> <span data-ttu-id="25841-108">对于每个服务器，所有 Web 服务在 ASP.NET 工作进程都运行。</span><span class="sxs-lookup"><span data-stu-id="25841-108">For each server, all Web services run within the ASP.NET worker process.</span></span>  
  
 <span data-ttu-id="25841-109">默认情况下，ASP.NET 工作进程使用本地 ASPNET 帐户。</span><span class="sxs-lookup"><span data-stu-id="25841-109">The ASP.NET worker process uses the local ASPNET account by default.</span></span> <span data-ttu-id="25841-110">IIS 使用应用程序池处理 Web 服务请求。</span><span class="sxs-lookup"><span data-stu-id="25841-110">IIS uses application pools for processing Web service requests.</span></span>  
  
 <span data-ttu-id="25841-111">**BizTalk 独立主机主机**</span><span class="sxs-lookup"><span data-stu-id="25841-111">**BizTalk Isolated Hosts**</span></span>  
  
 <span data-ttu-id="25841-112">若要启用 Web 服务，必须在 BizTalk Server 中创建至少一个独立的主机。</span><span class="sxs-lookup"><span data-stu-id="25841-112">To enable Web services, you must create at least one Isolated Host in BizTalk Server.</span></span> <span data-ttu-id="25841-113">独立主机是外部进程，如 ISAPI 扩展和 ASP.NET 进程的 BizTalk Server 不创建或控制。</span><span class="sxs-lookup"><span data-stu-id="25841-113">Isolated Hosts represent external processes, such as ISAPI extensions and ASP.NET processes that BizTalk Server does not create or control.</span></span> <span data-ttu-id="25841-114">这些类型的外部进程必须承载某些适配器，如 HTTP/S 和 SOAP。</span><span class="sxs-lookup"><span data-stu-id="25841-114">These types of external processes must host certain adapters, such as HTTP/S and SOAP.</span></span>  
  
 <span data-ttu-id="25841-115">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Manager 创建 BizTalk 用作默认的 BizTalkServerIsolatedHost 独立的主机。</span><span class="sxs-lookup"><span data-stu-id="25841-115">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Manager creates the BizTalkServerIsolatedHost that BizTalk uses as the default Isolated Host.</span></span> <span data-ttu-id="25841-116">BizTalk Isolated Host Users 组是默认情况下与此主机关联的 Windows 组的名称。</span><span class="sxs-lookup"><span data-stu-id="25841-116">The BizTalk Isolated Host Users group is the name of the Windows group associated with this host by default.</span></span> <span data-ttu-id="25841-117">有关主机和主机实例的详细信息，请参阅[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="25841-117">For more information about Hosts and Host Instances, see [Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md).</span></span>  
  
 <span data-ttu-id="25841-118">一个独立的主机实例运行只有一个适配器。</span><span class="sxs-lookup"><span data-stu-id="25841-118">An isolated host instance can run only one adapter.</span></span> <span data-ttu-id="25841-119">如果用一个独立主机配置 HTTP 和 SOAP 适配器的接收处理程序，必须创建两个应用程序池，每个适配器的一个应用程序池。</span><span class="sxs-lookup"><span data-stu-id="25841-119">If you configure the receive handlers of HTTP and SOAP adapters with the one isolated host, you must create two application pools, one application pool for each adapter.</span></span>  
  
 <span data-ttu-id="25841-120">例如，如果你打算配置两个独立主机，如下所示：</span><span class="sxs-lookup"><span data-stu-id="25841-120">For example, if you plan to configure two isolated hosts as following:</span></span>  
  
|<span data-ttu-id="25841-121">独立的主机名称</span><span class="sxs-lookup"><span data-stu-id="25841-121">Isolated host name</span></span>|<span data-ttu-id="25841-122">接收位置</span><span class="sxs-lookup"><span data-stu-id="25841-122">Receive locations</span></span>|  
|------------------------|-----------------------|  
|<span data-ttu-id="25841-123">独立主机 1</span><span class="sxs-lookup"><span data-stu-id="25841-123">Isolated Host 1</span></span>|<span data-ttu-id="25841-124">HTTP_ReceiveLocation1A</span><span class="sxs-lookup"><span data-stu-id="25841-124">HTTP_ReceiveLocation1A</span></span><br /><br /> <span data-ttu-id="25841-125">HTTP_ReceiveLocation1B</span><span class="sxs-lookup"><span data-stu-id="25841-125">HTTP_ReceiveLocation1B</span></span><br /><br /> <span data-ttu-id="25841-126">SOAP_ReceiveLocation1**注意：\*\*\*\*独立主机 1**用于 SOAP 和 HTTP 适配器的接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="25841-126">SOAP_ReceiveLocation1 **Note:**  The **Isolated Host 1** is used for receive handlers of both SOAP and HTTP adapters.</span></span>|  
|<span data-ttu-id="25841-127">独立的主机 2</span><span class="sxs-lookup"><span data-stu-id="25841-127">Isolated Host 2</span></span>|<span data-ttu-id="25841-128">HTTP_ReceiveLocation2</span><span class="sxs-lookup"><span data-stu-id="25841-128">HTTP_ReceiveLocation2</span></span>|  
  
 <span data-ttu-id="25841-129">你可以创建四个虚拟目录，每个接收位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="25841-129">You may create four virtual directories, one for each receive location as follows:</span></span>  
  
|<span data-ttu-id="25841-130">接收位置</span><span class="sxs-lookup"><span data-stu-id="25841-130">Receive location</span></span>|<span data-ttu-id="25841-131">虚拟目录</span><span class="sxs-lookup"><span data-stu-id="25841-131">Virtual directory</span></span>|  
|----------------------|-----------------------|  
|<span data-ttu-id="25841-132">HTTP_ReceiveLocation1A</span><span class="sxs-lookup"><span data-stu-id="25841-132">HTTP_ReceiveLocation1A</span></span>|<span data-ttu-id="25841-133">IIS_Virtual_Directory1A</span><span class="sxs-lookup"><span data-stu-id="25841-133">IIS_Virtual_Directory1A</span></span>|  
|<span data-ttu-id="25841-134">HTTP_ReceiveLocation1B</span><span class="sxs-lookup"><span data-stu-id="25841-134">HTTP_ReceiveLocation1B</span></span>|<span data-ttu-id="25841-135">IIS_Virtual_Directory1B</span><span class="sxs-lookup"><span data-stu-id="25841-135">IIS_Virtual_Directory1B</span></span>|  
|<span data-ttu-id="25841-136">SOAP_ReceiveLocation1</span><span class="sxs-lookup"><span data-stu-id="25841-136">SOAP_ReceiveLocation1</span></span>|<span data-ttu-id="25841-137">IIS_Virtual_Directory1C</span><span class="sxs-lookup"><span data-stu-id="25841-137">IIS_Virtual_Directory1C</span></span>|  
|<span data-ttu-id="25841-138">HTTP_ReceiveLocation2</span><span class="sxs-lookup"><span data-stu-id="25841-138">HTTP_ReceiveLocation2</span></span>|<span data-ttu-id="25841-139">IIS_Virtual_Directory2</span><span class="sxs-lookup"><span data-stu-id="25841-139">IIS_Virtual_Directory2</span></span>|  
  
 <span data-ttu-id="25841-140">然后，必须创建至少三个应用程序池的虚拟目录，如下所示：</span><span class="sxs-lookup"><span data-stu-id="25841-140">Then, you must create at least three application pools for the virtual directories as follows:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25841-141">必须为每个独立主机创建至少一个应用程序池。</span><span class="sxs-lookup"><span data-stu-id="25841-141">You must create at least one application pool for each isolated host.</span></span>  
  
|<span data-ttu-id="25841-142">虚拟目录</span><span class="sxs-lookup"><span data-stu-id="25841-142">Virtual directories</span></span>|<span data-ttu-id="25841-143">应用程序池</span><span class="sxs-lookup"><span data-stu-id="25841-143">Application pool</span></span>|<span data-ttu-id="25841-144">Description</span><span class="sxs-lookup"><span data-stu-id="25841-144">Description</span></span>|  
|-------------------------|----------------------|-----------------|  
|<span data-ttu-id="25841-145">IIS_Virtual_Directory1A</span><span class="sxs-lookup"><span data-stu-id="25841-145">IIS_Virtual_Directory1A</span></span><br /><br /> <span data-ttu-id="25841-146">IIS_Virtual_Directory1B</span><span class="sxs-lookup"><span data-stu-id="25841-146">IIS_Virtual_Directory1B</span></span>|<span data-ttu-id="25841-147">AppPool_Host1_HTTP</span><span class="sxs-lookup"><span data-stu-id="25841-147">AppPool_Host1_HTTP</span></span>|<span data-ttu-id="25841-148">因为所有接收位置都具有相同的独立主机 (独立主机 1) 和相同的协议，则不需要单独的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="25841-148">A separate application pool is not required because all of the receive locations have the same isolated host (Isolated Host 1), and the same protocol.</span></span>|  
|<span data-ttu-id="25841-149">IIS_Virtual_Directory1C</span><span class="sxs-lookup"><span data-stu-id="25841-149">IIS_Virtual_Directory1C</span></span>|<span data-ttu-id="25841-150">AppPool_Host1_SOAP</span><span class="sxs-lookup"><span data-stu-id="25841-150">AppPool_Host1_SOAP</span></span>|<span data-ttu-id="25841-151">需要单独的应用程序池，因为接收位置从同一主机 (独立主机 1) 中的其他接收位置使用不同协议 (SOAP)。</span><span class="sxs-lookup"><span data-stu-id="25841-151">A separate application pool is required because the receive location uses the different protocol (SOAP) from the other receive locations in the same host (Isolated Host 1).</span></span>|  
|<span data-ttu-id="25841-152">IIS_Virtual_Directory2</span><span class="sxs-lookup"><span data-stu-id="25841-152">IIS_Virtual_Directory2</span></span>|<span data-ttu-id="25841-153">AppPool_Host2_HTTP</span><span class="sxs-lookup"><span data-stu-id="25841-153">AppPool_Host2_HTTP</span></span>|<span data-ttu-id="25841-154">需要单独的应用程序池，因为接收位置在独立主机 1 以外的主机下运行。</span><span class="sxs-lookup"><span data-stu-id="25841-154">A separate application pool is required because the receive location runs under the different host from Isolated Host 1.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="25841-155">必须将应用程序池的用户帐户添加到独立的主机的相应本地或域组。</span><span class="sxs-lookup"><span data-stu-id="25841-155">You must add the user account for the application pools to the appropriate local or domain groups of the isolated hosts.</span></span> <span data-ttu-id="25841-156">有关详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="25841-156">For more information, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25841-157">你需要匹配独立主机实例和相应的应用程序池根据上述表格之间的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="25841-157">You need to match the user account between an isolated host instance and the corresponding application pool according to the previous tables.</span></span> <span data-ttu-id="25841-158">有关独立主机实例和应用程序池的用户帐户之间的关系的详细信息，请参阅[如何更改服务帐户和密码](../core/how-to-change-service-accounts-and-passwords.md)。</span><span class="sxs-lookup"><span data-stu-id="25841-158">For more information about the relationship between user accounts of isolated host instance and application pools, see [How to Change Service Accounts and Passwords](../core/how-to-change-service-accounts-and-passwords.md).</span></span>  
  
 <span data-ttu-id="25841-159">**单服务器安装的数据库访问**</span><span class="sxs-lookup"><span data-stu-id="25841-159">**Database access for single server installations**</span></span>  
  
 <span data-ttu-id="25841-160">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 BizTalk 管理数据库驻留在同一服务器上，应将 ASP.NET 工作进程或 IIS 应用程序池的用户上下文设置为本地 ASPNET 用户帐户或具有最低权限的本地或域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="25841-160">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the BizTalk Management database reside on the same server, you should set the user context of the ASP.NET worker process or the IIS Application Pool to the local ASPNET user account, or a local or domain user account that has minimal privileges.</span></span>  
  
 <span data-ttu-id="25841-161">**多个服务器安装的数据库访问**</span><span class="sxs-lookup"><span data-stu-id="25841-161">**Database access for multiple server installations**</span></span>  
  
 <span data-ttu-id="25841-162">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 BizTalk 管理数据库驻留在不同服务器上，应将 ASP.NET 工作进程或 IIS 应用程序池的用户上下文更改为域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="25841-162">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the BizTalk Management database reside on different servers, you should change the user context of the ASP.NET worker process or the IIS Application Pool to a domain user account.</span></span>  
  
 <span data-ttu-id="25841-163">当实现多服务器部署时，独立的主机 Windows 组必须存在属于 BizTalk 数据库服务器的域。</span><span class="sxs-lookup"><span data-stu-id="25841-163">When implementing a multi-server deployment, the Isolated Host Windows groups must exist on the domain which the BizTalk database servers belong to.</span></span>  
  
 <span data-ttu-id="25841-164">**帐户权限和用户权限降至最低**</span><span class="sxs-lookup"><span data-stu-id="25841-164">**Minimizing account privileges and user rights**</span></span>  
  
 <span data-ttu-id="25841-165">使用独立的主机以便运行在外部进程访问到所需的资源与 BizTalk Server 进行交互的最小数量的适配器。</span><span class="sxs-lookup"><span data-stu-id="25841-165">You use Isolated Hosts to give adapters that run in external processes access to the minimal amount of required resources to interact with BizTalk Server.</span></span> <span data-ttu-id="25841-166">为确保部署的您应该为提供的用户上下文的外部进程最小特权。</span><span class="sxs-lookup"><span data-stu-id="25841-166">For a secure deployment, you should give the user context for the external processes minimal privileges.</span></span>  
  
 <span data-ttu-id="25841-167">**BizTalk Web Services 发布向导的安全建议**</span><span class="sxs-lookup"><span data-stu-id="25841-167">**Security recommendations for BizTalk Web Services Publishing Wizard**</span></span>  
  
 <span data-ttu-id="25841-168">BizTalk Web Services 发布向导创建的虚拟目录将从父虚拟目录或网站继承访问控制列表 (ACL) 和身份验证要求。</span><span class="sxs-lookup"><span data-stu-id="25841-168">The virtual directory created by the BizTalk Web Services Publishing Wizard will inherit the access control lists (ACL) and authentication requirements from the parent virtual directory or Web site.</span></span> <span data-ttu-id="25841-169">如果父虚拟目录或网站允许匿名访问，BizTalk Web Services 发布向导将创建虚拟目录时删除该功能。</span><span class="sxs-lookup"><span data-stu-id="25841-169">If the parent virtual directory or Web site allows anonymous access, the BizTalk Web Services Publishing Wizard will remove that capability when creating the virtual directory.</span></span>  
  
 <span data-ttu-id="25841-170">以下包含安全说明和建议[!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="25841-170">The following contains security notes and recommendations for [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)].</span></span>  
  
## <a name="next"></a><span data-ttu-id="25841-171">Next</span><span class="sxs-lookup"><span data-stu-id="25841-171">Next</span></span>
  
[<span data-ttu-id="25841-172">如何为已发布的 Web Services 启用 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="25841-172">How to Enable ASP.NET for Published Web Services</span></span>](../core/how-to-enable-asp-net-4-0-for-published-web-services.md)