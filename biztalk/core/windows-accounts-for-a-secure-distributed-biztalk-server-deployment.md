---
title: "Windows 帐户对于安全的分布式的 BizTalk 服务器部署 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, Windows groups
- user accounts, naming conventions
- user accounts
- access control, Windows groups
- security, access control
- architecture, security
- security, Windows accounts
- administrator accounts
- user accounts, administrators
- architecture, large distributions
ms.assetid: 2a0893ef-8bfb-481b-b024-7f7d6e2a6f09
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 678977b23f377425718e483d87725ba191bbda86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="windows-accounts-for-a-secure-distributed-biztalk-server-deployment"></a><span data-ttu-id="582f1-102">Windows 帐户，可以一种安全的分布式 BizTalk Server 部署</span><span class="sxs-lookup"><span data-stu-id="582f1-102">Windows Accounts for a Secure Distributed BizTalk Server Deployment</span></span>
<span data-ttu-id="582f1-103">有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="582f1-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="582f1-104">本部分提供有关在分布式 BizTalk Server 环境中创建 Windows 组和帐户的建议。</span><span class="sxs-lookup"><span data-stu-id="582f1-104">This section provides recommendations for creating Windows groups and accounts in a distributed BizTalk Server environment.</span></span> <span data-ttu-id="582f1-105">组名和帐户名暗示了组和帐户的功能。</span><span class="sxs-lookup"><span data-stu-id="582f1-105">The group and account names are suggestions based on the function of the groups and accounts.</span></span> <span data-ttu-id="582f1-106">您可以选择这些组和帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="582f1-106">You can choose the name of these groups and accounts.</span></span> <span data-ttu-id="582f1-107">有关分布式 BizTalk Server 体系结构的详细信息，请参阅[大型分布式体系结构](../core/large-distributed-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="582f1-107">For more information about distributed BizTalk Server architectures, see [Large Distributed Architecture](../core/large-distributed-architecture.md).</span></span>  
  
## <a name="windows-groups-for-a-secure-distributed-biztalk-server-deployment"></a><span data-ttu-id="582f1-108">安全分布式 BizTalk Server 部署的 Windows 组</span><span class="sxs-lookup"><span data-stu-id="582f1-108">Windows Groups for a Secure Distributed BizTalk Server Deployment</span></span>  
 <span data-ttu-id="582f1-109">下面列出了建议域管理员在域控制器的数据层创建的 Windows 组：</span><span class="sxs-lookup"><span data-stu-id="582f1-109">The following list describes the recommended Windows groups for the domain administrator to create in the domain controller in the data tier.</span></span>  
  
-   <span data-ttu-id="582f1-110">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="582f1-110">SSO Administrators</span></span>  
  
-   <span data-ttu-id="582f1-111">SSO Affiliate Administrators</span><span class="sxs-lookup"><span data-stu-id="582f1-111">SSO Affiliate Administrators</span></span>  
  
-   <span data-ttu-id="582f1-112">BizTalk Server Administrators</span><span class="sxs-lookup"><span data-stu-id="582f1-112">BizTalk Server Administrators</span></span>  
  
-   <span data-ttu-id="582f1-113">BizTalk Server Operators</span><span class="sxs-lookup"><span data-stu-id="582f1-113">BizTalk Server Operators</span></span>  
  
 <span data-ttu-id="582f1-114">有关 BizTalk Server 使用的 Windows 组的完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="582f1-114">For complete information about the Windows groups that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="582f1-115">除了上述域组之外，下表还列出了其他专用于确保部署安全的组，域管理员也可以在域控制器的数据层创建这些组：</span><span class="sxs-lookup"><span data-stu-id="582f1-115">In addition to the previous domain groups, the following table lists additional groups specific to secure deployment for the domain administrator to create in the domain controller in the data tier.</span></span>  
  
|<span data-ttu-id="582f1-116">组名（建议）</span><span class="sxs-lookup"><span data-stu-id="582f1-116">Group name (suggested)</span></span>|<span data-ttu-id="582f1-117">用途</span><span class="sxs-lookup"><span data-stu-id="582f1-117">Purpose</span></span>|  
|------------------------------|-------------|  
|<span data-ttu-id="582f1-118">BizTalk Processing Host Users 1</span><span class="sxs-lookup"><span data-stu-id="582f1-118">BizTalk Processing Host Users 1</span></span>|<span data-ttu-id="582f1-119">用于特定进程内主机（用来处理消息）的实例的组。</span><span class="sxs-lookup"><span data-stu-id="582f1-119">Group for the host instances of a specific in-process host that you use for processing messages.</span></span> <span data-ttu-id="582f1-120">在 BizTalk Server 环境中将为用于处理消息的每个进程内主机创建一个组。</span><span class="sxs-lookup"><span data-stu-id="582f1-120">Create a group for each in-process host that you use for processing messages in your BizTalk Server environment.</span></span>|  
|<span data-ttu-id="582f1-121">BizTalk Send Host Users 1</span><span class="sxs-lookup"><span data-stu-id="582f1-121">BizTalk Send Host Users 1</span></span>|<span data-ttu-id="582f1-122">用于特定进程内主机（用来发送消息）的实例的组。</span><span class="sxs-lookup"><span data-stu-id="582f1-122">Group for the host instance of a specific in-process host that you use for sending messages.</span></span> <span data-ttu-id="582f1-123">在 BizTalk Server 环境中将为用于发送消息的每个进程内主机创建一个组。</span><span class="sxs-lookup"><span data-stu-id="582f1-123">Create a group for each in-process host that you use for sending messages in your BizTalk Server environment.</span></span>|  
|<span data-ttu-id="582f1-124">BizTalk Receive Host Users 1</span><span class="sxs-lookup"><span data-stu-id="582f1-124">BizTalk Receive Host Users 1</span></span>|<span data-ttu-id="582f1-125">用于特定进程内主机（用来接收消息）的实例的组。</span><span class="sxs-lookup"><span data-stu-id="582f1-125">Group for the host instance of a specific in-process host that you use for receiving messages.</span></span> <span data-ttu-id="582f1-126">在 BizTalk Server 环境中将为用于接收消息的每个进程内主机创建一个组。</span><span class="sxs-lookup"><span data-stu-id="582f1-126">Create a group for each in-process host that you use for receiving messages in your BizTalk Server environment.</span></span>|  
|<span data-ttu-id="582f1-127">BizTalk Tracking Host Users</span><span class="sxs-lookup"><span data-stu-id="582f1-127">BizTalk Tracking Host Users</span></span>|<span data-ttu-id="582f1-128">用于专门进行跟踪的 BizTalk 主机的组。</span><span class="sxs-lookup"><span data-stu-id="582f1-128">Group for the BizTalk host that you dedicate for tracking.</span></span>|  
|<span data-ttu-id="582f1-129">BizTalk SOAP Users </span><span class="sxs-lookup"><span data-stu-id="582f1-129">BizTalk SOAP Users</span></span>|<span data-ttu-id="582f1-130">用于为 SOAP 适配器使用的独立主机的实例的组。</span><span class="sxs-lookup"><span data-stu-id="582f1-130">Group for the host instances of the isolated host you use for the SOAP adapter.</span></span>|  
|<span data-ttu-id="582f1-131">BizTalk HTTP Users</span><span class="sxs-lookup"><span data-stu-id="582f1-131">BizTalk HTTP Users</span></span>|<span data-ttu-id="582f1-132">用于为 HTTP 适配器使用的独立主机的实例的组。</span><span class="sxs-lookup"><span data-stu-id="582f1-132">Group for the host instances of the isolated hosts you use for the HTTP adapter.</span></span>|  
  
 <span data-ttu-id="582f1-133">域管理员必须在服务接口域的域控制器中创建以下组：</span><span class="sxs-lookup"><span data-stu-id="582f1-133">The domain administrator must create the following groups in the domain controller of the service interfaces domain:</span></span>  
  
-   <span data-ttu-id="582f1-134">BizTalk BAM Portal Users</span><span class="sxs-lookup"><span data-stu-id="582f1-134">BizTalk BAM Portal Users</span></span>  
  
## <a name="windows-user-or-service-accounts-for-a-secure-distributed-biztalk-server-deployment"></a><span data-ttu-id="582f1-135">安全分布式 BizTalk Server 部署的 Windows 用户或服务帐户</span><span class="sxs-lookup"><span data-stu-id="582f1-135">Windows User or Service Accounts for a Secure Distributed BizTalk Server Deployment</span></span>  
 <span data-ttu-id="582f1-136">下表列出了建议域管理员在数据域的域控制器中创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="582f1-136">The following table lists the recommended accounts for the domain administrator to create in the domain controller of the data domain.</span></span> <span data-ttu-id="582f1-137">域管理员必须确保这些帐户是所指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="582f1-137">The domain administrator must ensure the accounts are members of the groups indicated.</span></span>  
  
 <span data-ttu-id="582f1-138">有关 BizTalk Server 使用的用户帐户的完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="582f1-138">For complete information about the user accounts that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
|<span data-ttu-id="582f1-139">帐户名（示例）</span><span class="sxs-lookup"><span data-stu-id="582f1-139">Account name (example)</span></span>|<span data-ttu-id="582f1-140">类型</span><span class="sxs-lookup"><span data-stu-id="582f1-140">Type</span></span>|<span data-ttu-id="582f1-141">所属的组</span><span class="sxs-lookup"><span data-stu-id="582f1-141">Member of group</span></span>|  
|------------------------------|----------|---------------------|  
|<span data-ttu-id="582f1-142">SSO administrator</span><span class="sxs-lookup"><span data-stu-id="582f1-142">SSO administrator</span></span>|<span data-ttu-id="582f1-143">用户</span><span class="sxs-lookup"><span data-stu-id="582f1-143">User</span></span>|<span data-ttu-id="582f1-144">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="582f1-144">SSO Administrators</span></span>|  
|<span data-ttu-id="582f1-145">SSO service</span><span class="sxs-lookup"><span data-stu-id="582f1-145">SSO service</span></span>|<span data-ttu-id="582f1-146">服务</span><span class="sxs-lookup"><span data-stu-id="582f1-146">Service</span></span>|<span data-ttu-id="582f1-147">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="582f1-147">SSO Administrators</span></span>|  
|<span data-ttu-id="582f1-148">SSO master secret</span><span class="sxs-lookup"><span data-stu-id="582f1-148">SSO master secret</span></span>|<span data-ttu-id="582f1-149">服务</span><span class="sxs-lookup"><span data-stu-id="582f1-149">Service</span></span>|<span data-ttu-id="582f1-150">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="582f1-150">SSO Administrators</span></span>|  
|<span data-ttu-id="582f1-151">BizTalk administrator</span><span class="sxs-lookup"><span data-stu-id="582f1-151">BizTalk administrator</span></span>|<span data-ttu-id="582f1-152">用户</span><span class="sxs-lookup"><span data-stu-id="582f1-152">User</span></span>|<span data-ttu-id="582f1-153">BizTalk Administrators</span><span class="sxs-lookup"><span data-stu-id="582f1-153">BizTalk Administrators</span></span><br /><br /> <span data-ttu-id="582f1-154">SSO Affiliate Administrators</span><span class="sxs-lookup"><span data-stu-id="582f1-154">SSO Affiliate Administrators</span></span>|  
|<span data-ttu-id="582f1-155">BizTalk operator</span><span class="sxs-lookup"><span data-stu-id="582f1-155">BizTalk operator</span></span>|<span data-ttu-id="582f1-156">用户</span><span class="sxs-lookup"><span data-stu-id="582f1-156">User</span></span>|<span data-ttu-id="582f1-157">BizTalk Operators</span><span class="sxs-lookup"><span data-stu-id="582f1-157">BizTalk Operators</span></span>|  
|<span data-ttu-id="582f1-158">BizTalk Processing 1</span><span class="sxs-lookup"><span data-stu-id="582f1-158">BizTalk Processing 1</span></span>|<span data-ttu-id="582f1-159">服务</span><span class="sxs-lookup"><span data-stu-id="582f1-159">Service</span></span>|<span data-ttu-id="582f1-160">BizTalk Processing Host Users 1</span><span class="sxs-lookup"><span data-stu-id="582f1-160">BizTalk Processing Host Users 1</span></span>|  
|<span data-ttu-id="582f1-161">BizTalk 处理 2**注意：**可以在你的环境中对于每个处理主机创建多个帐户。</span><span class="sxs-lookup"><span data-stu-id="582f1-161">BizTalk Processing 2 **Note:**  You can create multiple accounts for each processing host in your environment.</span></span>|<span data-ttu-id="582f1-162">服务</span><span class="sxs-lookup"><span data-stu-id="582f1-162">Service</span></span>|<span data-ttu-id="582f1-163">BizTalk Processing Host Users 1</span><span class="sxs-lookup"><span data-stu-id="582f1-163">BizTalk Processing Host Users 1</span></span>|  
|<span data-ttu-id="582f1-164">BizTalk Tracking</span><span class="sxs-lookup"><span data-stu-id="582f1-164">BizTalk Tracking</span></span>|<span data-ttu-id="582f1-165">服务</span><span class="sxs-lookup"><span data-stu-id="582f1-165">Service</span></span>|<span data-ttu-id="582f1-166">BizTalk Tracking Host Users</span><span class="sxs-lookup"><span data-stu-id="582f1-166">BizTalk Tracking Host Users</span></span>|  
|<span data-ttu-id="582f1-167">SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="582f1-167">SOAP adapter</span></span>|<span data-ttu-id="582f1-168">服务</span><span class="sxs-lookup"><span data-stu-id="582f1-168">Service</span></span>|<span data-ttu-id="582f1-169">BizTalk SOAP Users </span><span class="sxs-lookup"><span data-stu-id="582f1-169">BizTalk SOAP Users</span></span>|  
|<span data-ttu-id="582f1-170">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="582f1-170">HTTP adapter</span></span>|<span data-ttu-id="582f1-171">服务</span><span class="sxs-lookup"><span data-stu-id="582f1-171">Service</span></span>|<span data-ttu-id="582f1-172">BizTalk HTTP Users</span><span class="sxs-lookup"><span data-stu-id="582f1-172">BizTalk HTTP Users</span></span>|  
|<span data-ttu-id="582f1-173">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="582f1-173">Rule Engine Update Service</span></span>|<span data-ttu-id="582f1-174">服务</span><span class="sxs-lookup"><span data-stu-id="582f1-174">Service</span></span>||  
|<span data-ttu-id="582f1-175">安装</span><span class="sxs-lookup"><span data-stu-id="582f1-175">Installation</span></span>|<span data-ttu-id="582f1-176">用户</span><span class="sxs-lookup"><span data-stu-id="582f1-176">User</span></span>|<span data-ttu-id="582f1-177">SSO Administrators（只用于配置主密钥服务器）</span><span class="sxs-lookup"><span data-stu-id="582f1-177">SSO Administrators (only for configuring the master secret server)</span></span><br /><br /> <span data-ttu-id="582f1-178">本地管理员</span><span class="sxs-lookup"><span data-stu-id="582f1-178">local Administrators</span></span><br /><br /> <span data-ttu-id="582f1-179">sysadmin SQL Server 角色</span><span class="sxs-lookup"><span data-stu-id="582f1-179">sysadmin SQL Server Role</span></span><br /><br /> <span data-ttu-id="582f1-180">OLAP Administrator</span><span class="sxs-lookup"><span data-stu-id="582f1-180">OLAP Administrator</span></span>|  
|<span data-ttu-id="582f1-181">BAM Application pool</span><span class="sxs-lookup"><span data-stu-id="582f1-181">BAM Application pool</span></span>|<span data-ttu-id="582f1-182">服务</span><span class="sxs-lookup"><span data-stu-id="582f1-182">Service</span></span>|<span data-ttu-id="582f1-183">IIS_WPG</span><span class="sxs-lookup"><span data-stu-id="582f1-183">IIS_WPG</span></span>|  
|<span data-ttu-id="582f1-184">BAM Management</span><span class="sxs-lookup"><span data-stu-id="582f1-184">BAM Management</span></span>|<span data-ttu-id="582f1-185">服务</span><span class="sxs-lookup"><span data-stu-id="582f1-185">Service</span></span>|<span data-ttu-id="582f1-186">IIS_WPG</span><span class="sxs-lookup"><span data-stu-id="582f1-186">IIS_WPG</span></span>|  
|<span data-ttu-id="582f1-187">BAM Notification</span><span class="sxs-lookup"><span data-stu-id="582f1-187">BAM Notification</span></span>|<span data-ttu-id="582f1-188">服务</span><span class="sxs-lookup"><span data-stu-id="582f1-188">Service</span></span>|<span data-ttu-id="582f1-189">SQLServer2005NotificationServicesUser$\<**ComputerName**></span><span class="sxs-lookup"><span data-stu-id="582f1-189">SQLServer2005NotificationServicesUser$\<**ComputerName**></span></span>|  
  
 <span data-ttu-id="582f1-190">下表列出了建议域管理员在公司域的域控制器中创建的帐户：</span><span class="sxs-lookup"><span data-stu-id="582f1-190">The following table lists the recommended accounts for the domain administrator to create in the domain controller of the corporate domain.</span></span>  
  
|<span data-ttu-id="582f1-191">帐户名</span><span class="sxs-lookup"><span data-stu-id="582f1-191">Account name</span></span>|<span data-ttu-id="582f1-192">类型</span><span class="sxs-lookup"><span data-stu-id="582f1-192">Type</span></span>|  
|------------------|----------|  
|<span data-ttu-id="582f1-193">SharePoint administrator</span><span class="sxs-lookup"><span data-stu-id="582f1-193">SharePoint administrator</span></span>|<span data-ttu-id="582f1-194">用户</span><span class="sxs-lookup"><span data-stu-id="582f1-194">User</span></span>|  
|<span data-ttu-id="582f1-195">SharePoint Site credential</span><span class="sxs-lookup"><span data-stu-id="582f1-195">SharePoint Site credential</span></span>|<span data-ttu-id="582f1-196">用户</span><span class="sxs-lookup"><span data-stu-id="582f1-196">User</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="582f1-197">另请参阅</span><span class="sxs-lookup"><span data-stu-id="582f1-197">See Also</span></span>  
 <span data-ttu-id="582f1-198">[大型分布式体系结构](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="582f1-198">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="582f1-199">[最低安全用户权限](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="582f1-199">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 <span data-ttu-id="582f1-200">[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="582f1-200">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="582f1-201">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="582f1-201">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)