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
ms.openlocfilehash: 493f0e9e095a5de8b1fc57eec658981ea3befa88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401569"
---
# <a name="windows-accounts-for-a-secure-distributed-biztalk-server-deployment"></a><span data-ttu-id="048f3-102">Windows 帐户安全分布式 BizTalk Server 部署</span><span class="sxs-lookup"><span data-stu-id="048f3-102">Windows Accounts for a Secure Distributed BizTalk Server Deployment</span></span>
<span data-ttu-id="048f3-103">有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="048f3-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="048f3-104">本部分提供有关分布式 BizTalk Server 环境中创建 Windows 组和帐户的建议。</span><span class="sxs-lookup"><span data-stu-id="048f3-104">This section provides recommendations for creating Windows groups and accounts in a distributed BizTalk Server environment.</span></span> <span data-ttu-id="048f3-105">组和帐户名称是基于组和帐户的功能的建议。</span><span class="sxs-lookup"><span data-stu-id="048f3-105">The group and account names are suggestions based on the function of the groups and accounts.</span></span> <span data-ttu-id="048f3-106">您可以选择这些组和帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="048f3-106">You can choose the name of these groups and accounts.</span></span> <span data-ttu-id="048f3-107">有关分布式 BizTalk Server 体系结构的详细信息，请参阅[大型分布式体系结构](../core/large-distributed-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="048f3-107">For more information about distributed BizTalk Server architectures, see [Large Distributed Architecture](../core/large-distributed-architecture.md).</span></span>  
  
## <a name="windows-groups-for-a-secure-distributed-biztalk-server-deployment"></a><span data-ttu-id="048f3-108">Windows 组安全分布式 BizTalk Server 部署</span><span class="sxs-lookup"><span data-stu-id="048f3-108">Windows Groups for a Secure Distributed BizTalk Server Deployment</span></span>  
 <span data-ttu-id="048f3-109">以下列表介绍了建议的域管理员在数据层中的域控制器中创建的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="048f3-109">The following list describes the recommended Windows groups for the domain administrator to create in the domain controller in the data tier.</span></span>  
  
- <span data-ttu-id="048f3-110">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="048f3-110">SSO Administrators</span></span>  
  
- <span data-ttu-id="048f3-111">SSO 关联管理员</span><span class="sxs-lookup"><span data-stu-id="048f3-111">SSO Affiliate Administrators</span></span>  
  
- <span data-ttu-id="048f3-112">BizTalk Server Administrators</span><span class="sxs-lookup"><span data-stu-id="048f3-112">BizTalk Server Administrators</span></span>  
  
- <span data-ttu-id="048f3-113">BizTalk Server Operators</span><span class="sxs-lookup"><span data-stu-id="048f3-113">BizTalk Server Operators</span></span>  
  
  <span data-ttu-id="048f3-114">有关 BizTalk Server 使用的 Windows 组的完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="048f3-114">For complete information about the Windows groups that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
  <span data-ttu-id="048f3-115">除了以前的域组下, 表列出了特定于域管理员在数据层中的域控制器中创建的安全部署的其他组。</span><span class="sxs-lookup"><span data-stu-id="048f3-115">In addition to the previous domain groups, the following table lists additional groups specific to secure deployment for the domain administrator to create in the domain controller in the data tier.</span></span>  
  
|<span data-ttu-id="048f3-116">组名 （建议）</span><span class="sxs-lookup"><span data-stu-id="048f3-116">Group name (suggested)</span></span>|<span data-ttu-id="048f3-117">用途</span><span class="sxs-lookup"><span data-stu-id="048f3-117">Purpose</span></span>|  
|------------------------------|-------------|  
|<span data-ttu-id="048f3-118">处理 BizTalk 主机用户 1</span><span class="sxs-lookup"><span data-stu-id="048f3-118">BizTalk Processing Host Users 1</span></span>|<span data-ttu-id="048f3-119">用来处理消息的特定进程内主机的主机实例进行分组。</span><span class="sxs-lookup"><span data-stu-id="048f3-119">Group for the host instances of a specific in-process host that you use for processing messages.</span></span> <span data-ttu-id="048f3-120">创建一个组的每个进程内主机在 BizTalk Server 环境中用于处理消息。</span><span class="sxs-lookup"><span data-stu-id="048f3-120">Create a group for each in-process host that you use for processing messages in your BizTalk Server environment.</span></span>|  
|<span data-ttu-id="048f3-121">BizTalk 发送主机用户 1</span><span class="sxs-lookup"><span data-stu-id="048f3-121">BizTalk Send Host Users 1</span></span>|<span data-ttu-id="048f3-122">用于发送消息的特定进程内主机的主机实例的组。</span><span class="sxs-lookup"><span data-stu-id="048f3-122">Group for the host instance of a specific in-process host that you use for sending messages.</span></span> <span data-ttu-id="048f3-123">为用于发送消息，BizTalk Server 环境中每个进程内主机创建一个组。</span><span class="sxs-lookup"><span data-stu-id="048f3-123">Create a group for each in-process host that you use for sending messages in your BizTalk Server environment.</span></span>|  
|<span data-ttu-id="048f3-124">BizTalk 接收主机用户 1</span><span class="sxs-lookup"><span data-stu-id="048f3-124">BizTalk Receive Host Users 1</span></span>|<span data-ttu-id="048f3-125">用来接收消息的特定进程内主机的主机实例的组。</span><span class="sxs-lookup"><span data-stu-id="048f3-125">Group for the host instance of a specific in-process host that you use for receiving messages.</span></span> <span data-ttu-id="048f3-126">为使用 BizTalk Server 环境中接收消息的每个进程内主机创建一个组。</span><span class="sxs-lookup"><span data-stu-id="048f3-126">Create a group for each in-process host that you use for receiving messages in your BizTalk Server environment.</span></span>|  
|<span data-ttu-id="048f3-127">BizTalk 跟踪主机用户</span><span class="sxs-lookup"><span data-stu-id="048f3-127">BizTalk Tracking Host Users</span></span>|<span data-ttu-id="048f3-128">用于专门进行跟踪的 BizTalk 主机组。</span><span class="sxs-lookup"><span data-stu-id="048f3-128">Group for the BizTalk host that you dedicate for tracking.</span></span>|  
|<span data-ttu-id="048f3-129">BizTalk SOAP Users</span><span class="sxs-lookup"><span data-stu-id="048f3-129">BizTalk SOAP Users</span></span>|<span data-ttu-id="048f3-130">用于 SOAP 适配器的独立主机的主机实例的组。</span><span class="sxs-lookup"><span data-stu-id="048f3-130">Group for the host instances of the isolated host you use for the SOAP adapter.</span></span>|  
|<span data-ttu-id="048f3-131">BizTalk HTTP 用户</span><span class="sxs-lookup"><span data-stu-id="048f3-131">BizTalk HTTP Users</span></span>|<span data-ttu-id="048f3-132">用于为 HTTP 适配器使用独立的主机的主机实例的组。</span><span class="sxs-lookup"><span data-stu-id="048f3-132">Group for the host instances of the isolated hosts you use for the HTTP adapter.</span></span>|  
  
 <span data-ttu-id="048f3-133">域管理员必须在服务接口域的域控制器中创建以下组：</span><span class="sxs-lookup"><span data-stu-id="048f3-133">The domain administrator must create the following groups in the domain controller of the service interfaces domain:</span></span>  
  
-   <span data-ttu-id="048f3-134">BizTalk BAM 门户用户</span><span class="sxs-lookup"><span data-stu-id="048f3-134">BizTalk BAM Portal Users</span></span>  
  
## <a name="windows-user-or-service-accounts-for-a-secure-distributed-biztalk-server-deployment"></a><span data-ttu-id="048f3-135">Windows 用户或服务帐户的安全分布式的 BizTalk Server 部署</span><span class="sxs-lookup"><span data-stu-id="048f3-135">Windows User or Service Accounts for a Secure Distributed BizTalk Server Deployment</span></span>  
 <span data-ttu-id="048f3-136">下表列出了建议域管理员创建的数据域的域控制器中使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="048f3-136">The following table lists the recommended accounts for the domain administrator to create in the domain controller of the data domain.</span></span> <span data-ttu-id="048f3-137">域管理员必须确保帐户是所指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="048f3-137">The domain administrator must ensure the accounts are members of the groups indicated.</span></span>  
  
 <span data-ttu-id="048f3-138">有关 BizTalk Server 使用的用户帐户的完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="048f3-138">For complete information about the user accounts that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
|<span data-ttu-id="048f3-139">帐户名称 （示例）</span><span class="sxs-lookup"><span data-stu-id="048f3-139">Account name (example)</span></span>|<span data-ttu-id="048f3-140">类型</span><span class="sxs-lookup"><span data-stu-id="048f3-140">Type</span></span>|<span data-ttu-id="048f3-141">组的成员</span><span class="sxs-lookup"><span data-stu-id="048f3-141">Member of group</span></span>|  
|------------------------------|----------|---------------------|  
|<span data-ttu-id="048f3-142">SSO 管理员</span><span class="sxs-lookup"><span data-stu-id="048f3-142">SSO administrator</span></span>|<span data-ttu-id="048f3-143">“用户”</span><span class="sxs-lookup"><span data-stu-id="048f3-143">User</span></span>|<span data-ttu-id="048f3-144">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="048f3-144">SSO Administrators</span></span>|  
|<span data-ttu-id="048f3-145">SSO 服务</span><span class="sxs-lookup"><span data-stu-id="048f3-145">SSO service</span></span>|<span data-ttu-id="048f3-146">服务</span><span class="sxs-lookup"><span data-stu-id="048f3-146">Service</span></span>|<span data-ttu-id="048f3-147">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="048f3-147">SSO Administrators</span></span>|  
|<span data-ttu-id="048f3-148">SSO 主密钥</span><span class="sxs-lookup"><span data-stu-id="048f3-148">SSO master secret</span></span>|<span data-ttu-id="048f3-149">服务</span><span class="sxs-lookup"><span data-stu-id="048f3-149">Service</span></span>|<span data-ttu-id="048f3-150">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="048f3-150">SSO Administrators</span></span>|  
|<span data-ttu-id="048f3-151">BizTalk 管理员</span><span class="sxs-lookup"><span data-stu-id="048f3-151">BizTalk administrator</span></span>|<span data-ttu-id="048f3-152">“用户”</span><span class="sxs-lookup"><span data-stu-id="048f3-152">User</span></span>|<span data-ttu-id="048f3-153">BizTalk 管理员</span><span class="sxs-lookup"><span data-stu-id="048f3-153">BizTalk Administrators</span></span><br /><br /> <span data-ttu-id="048f3-154">SSO 关联管理员</span><span class="sxs-lookup"><span data-stu-id="048f3-154">SSO Affiliate Administrators</span></span>|  
|<span data-ttu-id="048f3-155">BizTalk 操作员</span><span class="sxs-lookup"><span data-stu-id="048f3-155">BizTalk operator</span></span>|<span data-ttu-id="048f3-156">“用户”</span><span class="sxs-lookup"><span data-stu-id="048f3-156">User</span></span>|<span data-ttu-id="048f3-157">BizTalk 操作员</span><span class="sxs-lookup"><span data-stu-id="048f3-157">BizTalk Operators</span></span>|  
|<span data-ttu-id="048f3-158">BizTalk 处理 1</span><span class="sxs-lookup"><span data-stu-id="048f3-158">BizTalk Processing 1</span></span>|<span data-ttu-id="048f3-159">服务</span><span class="sxs-lookup"><span data-stu-id="048f3-159">Service</span></span>|<span data-ttu-id="048f3-160">处理 BizTalk 主机用户 1</span><span class="sxs-lookup"><span data-stu-id="048f3-160">BizTalk Processing Host Users 1</span></span>|  
|<span data-ttu-id="048f3-161">BizTalk 处理 2**注意：** 在您的环境中，可以为每个处理主机创建多个帐户。</span><span class="sxs-lookup"><span data-stu-id="048f3-161">BizTalk Processing 2 **Note:**  You can create multiple accounts for each processing host in your environment.</span></span>|<span data-ttu-id="048f3-162">服务</span><span class="sxs-lookup"><span data-stu-id="048f3-162">Service</span></span>|<span data-ttu-id="048f3-163">处理 BizTalk 主机用户 1</span><span class="sxs-lookup"><span data-stu-id="048f3-163">BizTalk Processing Host Users 1</span></span>|  
|<span data-ttu-id="048f3-164">BizTalk 跟踪</span><span class="sxs-lookup"><span data-stu-id="048f3-164">BizTalk Tracking</span></span>|<span data-ttu-id="048f3-165">服务</span><span class="sxs-lookup"><span data-stu-id="048f3-165">Service</span></span>|<span data-ttu-id="048f3-166">BizTalk 跟踪主机用户</span><span class="sxs-lookup"><span data-stu-id="048f3-166">BizTalk Tracking Host Users</span></span>|  
|<span data-ttu-id="048f3-167">SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="048f3-167">SOAP adapter</span></span>|<span data-ttu-id="048f3-168">服务</span><span class="sxs-lookup"><span data-stu-id="048f3-168">Service</span></span>|<span data-ttu-id="048f3-169">BizTalk SOAP Users</span><span class="sxs-lookup"><span data-stu-id="048f3-169">BizTalk SOAP Users</span></span>|  
|<span data-ttu-id="048f3-170">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="048f3-170">HTTP adapter</span></span>|<span data-ttu-id="048f3-171">服务</span><span class="sxs-lookup"><span data-stu-id="048f3-171">Service</span></span>|<span data-ttu-id="048f3-172">BizTalk HTTP 用户</span><span class="sxs-lookup"><span data-stu-id="048f3-172">BizTalk HTTP Users</span></span>|  
|<span data-ttu-id="048f3-173">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="048f3-173">Rule Engine Update Service</span></span>|<span data-ttu-id="048f3-174">服务</span><span class="sxs-lookup"><span data-stu-id="048f3-174">Service</span></span>||  
|<span data-ttu-id="048f3-175">安装</span><span class="sxs-lookup"><span data-stu-id="048f3-175">Installation</span></span>|<span data-ttu-id="048f3-176">“用户”</span><span class="sxs-lookup"><span data-stu-id="048f3-176">User</span></span>|<span data-ttu-id="048f3-177">SSO Administrators （只用于配置主密钥服务器）</span><span class="sxs-lookup"><span data-stu-id="048f3-177">SSO Administrators (only for configuring the master secret server)</span></span><br /><br /> <span data-ttu-id="048f3-178">本地管理员</span><span class="sxs-lookup"><span data-stu-id="048f3-178">local Administrators</span></span><br /><br /> <span data-ttu-id="048f3-179">sysadmin SQL Server 角色</span><span class="sxs-lookup"><span data-stu-id="048f3-179">sysadmin SQL Server Role</span></span><br /><br /> <span data-ttu-id="048f3-180">OLAP 管理员</span><span class="sxs-lookup"><span data-stu-id="048f3-180">OLAP Administrator</span></span>|  
|<span data-ttu-id="048f3-181">BAM 应用程序池</span><span class="sxs-lookup"><span data-stu-id="048f3-181">BAM Application pool</span></span>|<span data-ttu-id="048f3-182">服务</span><span class="sxs-lookup"><span data-stu-id="048f3-182">Service</span></span>|<span data-ttu-id="048f3-183">IIS_WPG</span><span class="sxs-lookup"><span data-stu-id="048f3-183">IIS_WPG</span></span>|  
|<span data-ttu-id="048f3-184">BAM 管理</span><span class="sxs-lookup"><span data-stu-id="048f3-184">BAM Management</span></span>|<span data-ttu-id="048f3-185">服务</span><span class="sxs-lookup"><span data-stu-id="048f3-185">Service</span></span>|<span data-ttu-id="048f3-186">IIS_WPG</span><span class="sxs-lookup"><span data-stu-id="048f3-186">IIS_WPG</span></span>|  
|<span data-ttu-id="048f3-187">BAM 通知</span><span class="sxs-lookup"><span data-stu-id="048f3-187">BAM Notification</span></span>|<span data-ttu-id="048f3-188">服务</span><span class="sxs-lookup"><span data-stu-id="048f3-188">Service</span></span>|<span data-ttu-id="048f3-189">SQLServer2005NotificationServicesUser$\<**ComputerName**\></span><span class="sxs-lookup"><span data-stu-id="048f3-189">SQLServer2005NotificationServicesUser$\<**ComputerName**\></span></span>|  
  
 <span data-ttu-id="048f3-190">下表列出了建议使用域管理员在企业域一部分的域控制器中创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="048f3-190">The following table lists the recommended accounts for the domain administrator to create in the domain controller of the corporate domain.</span></span>  
  
|<span data-ttu-id="048f3-191">帐户名</span><span class="sxs-lookup"><span data-stu-id="048f3-191">Account name</span></span>|<span data-ttu-id="048f3-192">类型</span><span class="sxs-lookup"><span data-stu-id="048f3-192">Type</span></span>|  
|------------------|----------|  
|<span data-ttu-id="048f3-193">SharePoint 管理员</span><span class="sxs-lookup"><span data-stu-id="048f3-193">SharePoint administrator</span></span>|<span data-ttu-id="048f3-194">“用户”</span><span class="sxs-lookup"><span data-stu-id="048f3-194">User</span></span>|  
|<span data-ttu-id="048f3-195">SharePoint 站点凭据</span><span class="sxs-lookup"><span data-stu-id="048f3-195">SharePoint Site credential</span></span>|<span data-ttu-id="048f3-196">“用户”</span><span class="sxs-lookup"><span data-stu-id="048f3-196">User</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="048f3-197">请参阅</span><span class="sxs-lookup"><span data-stu-id="048f3-197">See Also</span></span>  
 <span data-ttu-id="048f3-198">[大型分布式体系结构](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="048f3-198">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="048f3-199">[最低安全用户权限](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="048f3-199">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 <span data-ttu-id="048f3-200">[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="048f3-200">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="048f3-201">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="048f3-201">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)