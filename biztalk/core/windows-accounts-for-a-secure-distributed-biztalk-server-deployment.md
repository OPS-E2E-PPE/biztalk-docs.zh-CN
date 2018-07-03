---
title: Windows 帐户安全分布式的 BizTalk Server 部署 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e05753c1693de75bbe6fa8422162a8c6e284bcff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985694"
---
# <a name="windows-accounts-for-a-secure-distributed-biztalk-server-deployment"></a><span data-ttu-id="8352b-102">Windows 帐户安全分布式 BizTalk Server 部署</span><span class="sxs-lookup"><span data-stu-id="8352b-102">Windows Accounts for a Secure Distributed BizTalk Server Deployment</span></span>
<span data-ttu-id="8352b-103">有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="8352b-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="8352b-104">本部分提供有关在分布式 BizTalk Server 环境中创建 Windows 组和帐户的建议。</span><span class="sxs-lookup"><span data-stu-id="8352b-104">This section provides recommendations for creating Windows groups and accounts in a distributed BizTalk Server environment.</span></span> <span data-ttu-id="8352b-105">组名和帐户名暗示了组和帐户的功能。</span><span class="sxs-lookup"><span data-stu-id="8352b-105">The group and account names are suggestions based on the function of the groups and accounts.</span></span> <span data-ttu-id="8352b-106">您可以选择这些组和帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="8352b-106">You can choose the name of these groups and accounts.</span></span> <span data-ttu-id="8352b-107">有关分布式 BizTalk Server 体系结构的详细信息，请参阅[大型分布式体系结构](../core/large-distributed-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="8352b-107">For more information about distributed BizTalk Server architectures, see [Large Distributed Architecture](../core/large-distributed-architecture.md).</span></span>  
  
## <a name="windows-groups-for-a-secure-distributed-biztalk-server-deployment"></a><span data-ttu-id="8352b-108">安全分布式 BizTalk Server 部署的 Windows 组</span><span class="sxs-lookup"><span data-stu-id="8352b-108">Windows Groups for a Secure Distributed BizTalk Server Deployment</span></span>  
 <span data-ttu-id="8352b-109">下面列出了建议域管理员在域控制器的数据层创建的 Windows 组：</span><span class="sxs-lookup"><span data-stu-id="8352b-109">The following list describes the recommended Windows groups for the domain administrator to create in the domain controller in the data tier.</span></span>  
  
- <span data-ttu-id="8352b-110">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="8352b-110">SSO Administrators</span></span>  
  
- <span data-ttu-id="8352b-111">SSO Affiliate Administrators</span><span class="sxs-lookup"><span data-stu-id="8352b-111">SSO Affiliate Administrators</span></span>  
  
- <span data-ttu-id="8352b-112">BizTalk Server Administrators</span><span class="sxs-lookup"><span data-stu-id="8352b-112">BizTalk Server Administrators</span></span>  
  
- <span data-ttu-id="8352b-113">BizTalk Server Operators</span><span class="sxs-lookup"><span data-stu-id="8352b-113">BizTalk Server Operators</span></span>  
  
  <span data-ttu-id="8352b-114">有关 BizTalk Server 使用的 Windows 组的完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8352b-114">For complete information about the Windows groups that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
  <span data-ttu-id="8352b-115">除了上述域组之外，下表还列出了其他专用于确保部署安全的组，域管理员也可以在域控制器的数据层创建这些组：</span><span class="sxs-lookup"><span data-stu-id="8352b-115">In addition to the previous domain groups, the following table lists additional groups specific to secure deployment for the domain administrator to create in the domain controller in the data tier.</span></span>  
  
|<span data-ttu-id="8352b-116">组名（建议）</span><span class="sxs-lookup"><span data-stu-id="8352b-116">Group name (suggested)</span></span>|<span data-ttu-id="8352b-117">用途</span><span class="sxs-lookup"><span data-stu-id="8352b-117">Purpose</span></span>|  
|------------------------------|-------------|  
|<span data-ttu-id="8352b-118">BizTalk Processing Host Users 1</span><span class="sxs-lookup"><span data-stu-id="8352b-118">BizTalk Processing Host Users 1</span></span>|<span data-ttu-id="8352b-119">用于特定进程内主机（用来处理消息）的实例的组。</span><span class="sxs-lookup"><span data-stu-id="8352b-119">Group for the host instances of a specific in-process host that you use for processing messages.</span></span> <span data-ttu-id="8352b-120">在 BizTalk Server 环境中将为用于处理消息的每个进程内主机创建一个组。</span><span class="sxs-lookup"><span data-stu-id="8352b-120">Create a group for each in-process host that you use for processing messages in your BizTalk Server environment.</span></span>|  
|<span data-ttu-id="8352b-121">BizTalk Send Host Users 1</span><span class="sxs-lookup"><span data-stu-id="8352b-121">BizTalk Send Host Users 1</span></span>|<span data-ttu-id="8352b-122">用于特定进程内主机（用来发送消息）的实例的组。</span><span class="sxs-lookup"><span data-stu-id="8352b-122">Group for the host instance of a specific in-process host that you use for sending messages.</span></span> <span data-ttu-id="8352b-123">在 BizTalk Server 环境中将为用于发送消息的每个进程内主机创建一个组。</span><span class="sxs-lookup"><span data-stu-id="8352b-123">Create a group for each in-process host that you use for sending messages in your BizTalk Server environment.</span></span>|  
|<span data-ttu-id="8352b-124">BizTalk Receive Host Users 1</span><span class="sxs-lookup"><span data-stu-id="8352b-124">BizTalk Receive Host Users 1</span></span>|<span data-ttu-id="8352b-125">用于特定进程内主机（用来接收消息）的实例的组。</span><span class="sxs-lookup"><span data-stu-id="8352b-125">Group for the host instance of a specific in-process host that you use for receiving messages.</span></span> <span data-ttu-id="8352b-126">在 BizTalk Server 环境中将为用于接收消息的每个进程内主机创建一个组。</span><span class="sxs-lookup"><span data-stu-id="8352b-126">Create a group for each in-process host that you use for receiving messages in your BizTalk Server environment.</span></span>|  
|<span data-ttu-id="8352b-127">BizTalk Tracking Host Users</span><span class="sxs-lookup"><span data-stu-id="8352b-127">BizTalk Tracking Host Users</span></span>|<span data-ttu-id="8352b-128">用于专门进行跟踪的 BizTalk 主机的组。</span><span class="sxs-lookup"><span data-stu-id="8352b-128">Group for the BizTalk host that you dedicate for tracking.</span></span>|  
|<span data-ttu-id="8352b-129">BizTalk SOAP Users </span><span class="sxs-lookup"><span data-stu-id="8352b-129">BizTalk SOAP Users</span></span>|<span data-ttu-id="8352b-130">用于为 SOAP 适配器使用的独立主机的实例的组。</span><span class="sxs-lookup"><span data-stu-id="8352b-130">Group for the host instances of the isolated host you use for the SOAP adapter.</span></span>|  
|<span data-ttu-id="8352b-131">BizTalk HTTP Users</span><span class="sxs-lookup"><span data-stu-id="8352b-131">BizTalk HTTP Users</span></span>|<span data-ttu-id="8352b-132">用于为 HTTP 适配器使用的独立主机的实例的组。</span><span class="sxs-lookup"><span data-stu-id="8352b-132">Group for the host instances of the isolated hosts you use for the HTTP adapter.</span></span>|  
  
 <span data-ttu-id="8352b-133">域管理员必须在服务接口域的域控制器中创建以下组：</span><span class="sxs-lookup"><span data-stu-id="8352b-133">The domain administrator must create the following groups in the domain controller of the service interfaces domain:</span></span>  
  
-   <span data-ttu-id="8352b-134">BizTalk BAM Portal Users</span><span class="sxs-lookup"><span data-stu-id="8352b-134">BizTalk BAM Portal Users</span></span>  
  
## <a name="windows-user-or-service-accounts-for-a-secure-distributed-biztalk-server-deployment"></a><span data-ttu-id="8352b-135">安全分布式 BizTalk Server 部署的 Windows 用户或服务帐户</span><span class="sxs-lookup"><span data-stu-id="8352b-135">Windows User or Service Accounts for a Secure Distributed BizTalk Server Deployment</span></span>  
 <span data-ttu-id="8352b-136">下表列出了建议域管理员在数据域的域控制器中创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="8352b-136">The following table lists the recommended accounts for the domain administrator to create in the domain controller of the data domain.</span></span> <span data-ttu-id="8352b-137">域管理员必须确保这些帐户是所指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="8352b-137">The domain administrator must ensure the accounts are members of the groups indicated.</span></span>  
  
 <span data-ttu-id="8352b-138">有关 BizTalk Server 使用的用户帐户的完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8352b-138">For complete information about the user accounts that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
|<span data-ttu-id="8352b-139">帐户名（示例）</span><span class="sxs-lookup"><span data-stu-id="8352b-139">Account name (example)</span></span>|<span data-ttu-id="8352b-140">类型</span><span class="sxs-lookup"><span data-stu-id="8352b-140">Type</span></span>|<span data-ttu-id="8352b-141">所属的组</span><span class="sxs-lookup"><span data-stu-id="8352b-141">Member of group</span></span>|  
|------------------------------|----------|---------------------|  
|<span data-ttu-id="8352b-142">SSO administrator</span><span class="sxs-lookup"><span data-stu-id="8352b-142">SSO administrator</span></span>|<span data-ttu-id="8352b-143">用户</span><span class="sxs-lookup"><span data-stu-id="8352b-143">User</span></span>|<span data-ttu-id="8352b-144">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="8352b-144">SSO Administrators</span></span>|  
|<span data-ttu-id="8352b-145">SSO service</span><span class="sxs-lookup"><span data-stu-id="8352b-145">SSO service</span></span>|<span data-ttu-id="8352b-146">服务</span><span class="sxs-lookup"><span data-stu-id="8352b-146">Service</span></span>|<span data-ttu-id="8352b-147">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="8352b-147">SSO Administrators</span></span>|  
|<span data-ttu-id="8352b-148">SSO master secret</span><span class="sxs-lookup"><span data-stu-id="8352b-148">SSO master secret</span></span>|<span data-ttu-id="8352b-149">服务</span><span class="sxs-lookup"><span data-stu-id="8352b-149">Service</span></span>|<span data-ttu-id="8352b-150">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="8352b-150">SSO Administrators</span></span>|  
|<span data-ttu-id="8352b-151">BizTalk administrator</span><span class="sxs-lookup"><span data-stu-id="8352b-151">BizTalk administrator</span></span>|<span data-ttu-id="8352b-152">用户</span><span class="sxs-lookup"><span data-stu-id="8352b-152">User</span></span>|<span data-ttu-id="8352b-153">BizTalk Administrators</span><span class="sxs-lookup"><span data-stu-id="8352b-153">BizTalk Administrators</span></span><br /><br /> <span data-ttu-id="8352b-154">SSO Affiliate Administrators</span><span class="sxs-lookup"><span data-stu-id="8352b-154">SSO Affiliate Administrators</span></span>|  
|<span data-ttu-id="8352b-155">BizTalk operator</span><span class="sxs-lookup"><span data-stu-id="8352b-155">BizTalk operator</span></span>|<span data-ttu-id="8352b-156">用户</span><span class="sxs-lookup"><span data-stu-id="8352b-156">User</span></span>|<span data-ttu-id="8352b-157">BizTalk Operators</span><span class="sxs-lookup"><span data-stu-id="8352b-157">BizTalk Operators</span></span>|  
|<span data-ttu-id="8352b-158">BizTalk Processing 1</span><span class="sxs-lookup"><span data-stu-id="8352b-158">BizTalk Processing 1</span></span>|<span data-ttu-id="8352b-159">服务</span><span class="sxs-lookup"><span data-stu-id="8352b-159">Service</span></span>|<span data-ttu-id="8352b-160">BizTalk Processing Host Users 1</span><span class="sxs-lookup"><span data-stu-id="8352b-160">BizTalk Processing Host Users 1</span></span>|  
|<span data-ttu-id="8352b-161">BizTalk 处理 2**注意：** 可以在你的环境中每个处理主机创建多个帐户。</span><span class="sxs-lookup"><span data-stu-id="8352b-161">BizTalk Processing 2 **Note:**  You can create multiple accounts for each processing host in your environment.</span></span>|<span data-ttu-id="8352b-162">服务</span><span class="sxs-lookup"><span data-stu-id="8352b-162">Service</span></span>|<span data-ttu-id="8352b-163">BizTalk Processing Host Users 1</span><span class="sxs-lookup"><span data-stu-id="8352b-163">BizTalk Processing Host Users 1</span></span>|  
|<span data-ttu-id="8352b-164">BizTalk Tracking</span><span class="sxs-lookup"><span data-stu-id="8352b-164">BizTalk Tracking</span></span>|<span data-ttu-id="8352b-165">服务</span><span class="sxs-lookup"><span data-stu-id="8352b-165">Service</span></span>|<span data-ttu-id="8352b-166">BizTalk Tracking Host Users</span><span class="sxs-lookup"><span data-stu-id="8352b-166">BizTalk Tracking Host Users</span></span>|  
|<span data-ttu-id="8352b-167">SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="8352b-167">SOAP adapter</span></span>|<span data-ttu-id="8352b-168">服务</span><span class="sxs-lookup"><span data-stu-id="8352b-168">Service</span></span>|<span data-ttu-id="8352b-169">BizTalk SOAP Users </span><span class="sxs-lookup"><span data-stu-id="8352b-169">BizTalk SOAP Users</span></span>|  
|<span data-ttu-id="8352b-170">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="8352b-170">HTTP adapter</span></span>|<span data-ttu-id="8352b-171">服务</span><span class="sxs-lookup"><span data-stu-id="8352b-171">Service</span></span>|<span data-ttu-id="8352b-172">BizTalk HTTP Users</span><span class="sxs-lookup"><span data-stu-id="8352b-172">BizTalk HTTP Users</span></span>|  
|<span data-ttu-id="8352b-173">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="8352b-173">Rule Engine Update Service</span></span>|<span data-ttu-id="8352b-174">服务</span><span class="sxs-lookup"><span data-stu-id="8352b-174">Service</span></span>||  
|<span data-ttu-id="8352b-175">安装</span><span class="sxs-lookup"><span data-stu-id="8352b-175">Installation</span></span>|<span data-ttu-id="8352b-176">用户</span><span class="sxs-lookup"><span data-stu-id="8352b-176">User</span></span>|<span data-ttu-id="8352b-177">SSO Administrators（只用于配置主密钥服务器）</span><span class="sxs-lookup"><span data-stu-id="8352b-177">SSO Administrators (only for configuring the master secret server)</span></span><br /><br /> <span data-ttu-id="8352b-178">本地管理员</span><span class="sxs-lookup"><span data-stu-id="8352b-178">local Administrators</span></span><br /><br /> <span data-ttu-id="8352b-179">sysadmin SQL Server 角色</span><span class="sxs-lookup"><span data-stu-id="8352b-179">sysadmin SQL Server Role</span></span><br /><br /> <span data-ttu-id="8352b-180">OLAP Administrator</span><span class="sxs-lookup"><span data-stu-id="8352b-180">OLAP Administrator</span></span>|  
|<span data-ttu-id="8352b-181">BAM Application pool</span><span class="sxs-lookup"><span data-stu-id="8352b-181">BAM Application pool</span></span>|<span data-ttu-id="8352b-182">服务</span><span class="sxs-lookup"><span data-stu-id="8352b-182">Service</span></span>|<span data-ttu-id="8352b-183">IIS_WPG</span><span class="sxs-lookup"><span data-stu-id="8352b-183">IIS_WPG</span></span>|  
|<span data-ttu-id="8352b-184">BAM Management</span><span class="sxs-lookup"><span data-stu-id="8352b-184">BAM Management</span></span>|<span data-ttu-id="8352b-185">服务</span><span class="sxs-lookup"><span data-stu-id="8352b-185">Service</span></span>|<span data-ttu-id="8352b-186">IIS_WPG</span><span class="sxs-lookup"><span data-stu-id="8352b-186">IIS_WPG</span></span>|  
|<span data-ttu-id="8352b-187">BAM Notification</span><span class="sxs-lookup"><span data-stu-id="8352b-187">BAM Notification</span></span>|<span data-ttu-id="8352b-188">服务</span><span class="sxs-lookup"><span data-stu-id="8352b-188">Service</span></span>|<span data-ttu-id="8352b-189">SQLServer2005NotificationServicesUser$\<**ComputerName**\></span><span class="sxs-lookup"><span data-stu-id="8352b-189">SQLServer2005NotificationServicesUser$\<**ComputerName**\></span></span>|  
  
 <span data-ttu-id="8352b-190">下表列出了建议域管理员在公司域的域控制器中创建的帐户：</span><span class="sxs-lookup"><span data-stu-id="8352b-190">The following table lists the recommended accounts for the domain administrator to create in the domain controller of the corporate domain.</span></span>  
  
|<span data-ttu-id="8352b-191">帐户名</span><span class="sxs-lookup"><span data-stu-id="8352b-191">Account name</span></span>|<span data-ttu-id="8352b-192">类型</span><span class="sxs-lookup"><span data-stu-id="8352b-192">Type</span></span>|  
|------------------|----------|  
|<span data-ttu-id="8352b-193">SharePoint administrator</span><span class="sxs-lookup"><span data-stu-id="8352b-193">SharePoint administrator</span></span>|<span data-ttu-id="8352b-194">用户</span><span class="sxs-lookup"><span data-stu-id="8352b-194">User</span></span>|  
|<span data-ttu-id="8352b-195">SharePoint Site credential</span><span class="sxs-lookup"><span data-stu-id="8352b-195">SharePoint Site credential</span></span>|<span data-ttu-id="8352b-196">用户</span><span class="sxs-lookup"><span data-stu-id="8352b-196">User</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8352b-197">请参阅</span><span class="sxs-lookup"><span data-stu-id="8352b-197">See Also</span></span>  
 <span data-ttu-id="8352b-198">[大型分布式体系结构](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="8352b-198">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="8352b-199">[最低安全用户权限](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="8352b-199">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 <span data-ttu-id="8352b-200">[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="8352b-200">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="8352b-201">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="8352b-201">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)