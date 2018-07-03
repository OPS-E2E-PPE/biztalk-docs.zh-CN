---
title: 组和服务帐户的访问控制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- access control, service accounts
- user accounts, default accounts
- service accounts, security
- user accounts, unsupported
- access control, groups
- service accounts, access control
- groups, access control
- groups, security
ms.assetid: 411a7bfa-6675-4d09-9e37-83e2941df3c6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da1bb9a52bef2e81729a8b566e4af4dcbed89c2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021787"
---
# <a name="access-control-for-groups-and-service-accounts"></a><span data-ttu-id="b370b-102">组和服务帐户的访问控制</span><span class="sxs-lookup"><span data-stu-id="b370b-102">Access Control for Groups and Service Accounts</span></span>
<span data-ttu-id="b370b-103">每个 BizTalk 主机实例在用户创建服务帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="b370b-103">Each BizTalk Host instance runs under a user-created service account.</span></span> <span data-ttu-id="b370b-104">必须提供的服务帐户并且他们的密码时创建主机实例的计算机上。</span><span class="sxs-lookup"><span data-stu-id="b370b-104">You must provide the service accounts and their passwords at the time you create the host instance on a computer.</span></span> <span data-ttu-id="b370b-105">然后，BizTalk Server 可确保帐户具有完成其工作的每个这些服务帐户添加到本地或域 Windows 组，反过来，它将添加到 SQL Server 数据库角色特定于该主机所需的最低用户权限。</span><span class="sxs-lookup"><span data-stu-id="b370b-105">BizTalk Server then ensures that the accounts have the minimum user rights needed to do their jobs by adding each of these service accounts to a local or domain Windows group that, in turn, it adds to the SQL Server Database role specific to that host.</span></span>  
  
 <span data-ttu-id="b370b-106">这种方法提供了以下好处：</span><span class="sxs-lookup"><span data-stu-id="b370b-106">This approach offers the following benefits:</span></span>  
  
- <span data-ttu-id="b370b-107">您可以为每个主机实例的服务不同的服务帐户，因此可以更改每个主机实例的密码，而无需使服务器脱机。</span><span class="sxs-lookup"><span data-stu-id="b370b-107">You can give each host instance a distinct service account, making it possible to change the passwords for each host instance without having to take servers offline.</span></span> <span data-ttu-id="b370b-108">您可以执行密码滚动更新，而无需中断服务。</span><span class="sxs-lookup"><span data-stu-id="b370b-108">You can perform rolling password updates without interrupting service.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="b370b-109">受信任验证主机和不受信任验证主机不能使用相同的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="b370b-109">You cannot use the same service account for hosts that are authentication trusted and hosts that are not authentication trusted.</span></span>  
  
- <span data-ttu-id="b370b-110">如果你授予对本地资源用户权限或在 Microsoft SQL Server™ 级别的域组，可以添加和减去服务帐户，而无需更改的用户权限授予在 SQL Server 中，因此降低了管理负担和总拥有成本。</span><span class="sxs-lookup"><span data-stu-id="b370b-110">If you grant resource user rights to the local or domain group at the Microsoft SQL Server™ level, you can add and subtract service accounts without having to change the user rights granted in SQL Server, thus reducing your management burden and total cost of ownership.</span></span>  
  
  <span data-ttu-id="b370b-111">若要确保服务帐户具有完成其作业所需的最低用户权限，BizTalk Server 创建的服务帐户的 SQL Server 数据库角色不是在所有 BizTalk Server 数据库上完全相同。</span><span class="sxs-lookup"><span data-stu-id="b370b-111">To ensure that the service accounts have the minimum user rights they need to do their jobs, the SQL Server Database roles that BizTalk Server creates for the service accounts are not identical on all the BizTalk Server databases.</span></span> <span data-ttu-id="b370b-112">有关管理和跟踪数据库，所有主机实例服务帐户需要访问相同的 SQL Server 对象，因此 BizTalk Server 创建名为 BTS_Host_User 的单个 SQL Server 数据库角色。</span><span class="sxs-lookup"><span data-stu-id="b370b-112">For the Management and Tracking databases, all of the host instance service accounts need access to the same SQL Server objects, so BizTalk Server created a single SQL Server Database role named BTS_Host_User.</span></span> <span data-ttu-id="b370b-113">BizTalk 将添加到此 SQL Server 数据库角色的 BizTalk 主机创建的所有 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="b370b-113">BizTalk adds all the Windows groups created for BizTalk hosts to this SQL Server Database role.</span></span>  
  
  <span data-ttu-id="b370b-114">MessageBox 数据库中，对于每个主机具有一些专用于该主机的资源。</span><span class="sxs-lookup"><span data-stu-id="b370b-114">For the MessageBox database, each host has some resources dedicated to that host.</span></span> <span data-ttu-id="b370b-115">BizTalk Server 创建的 SQL Server 数据库角色，每个主机，名为 BTS_\<*主机名*\>用户 （_u)，并添加到其各自的 SQL Server 数据库角色的每个主机的 Windows 组，以阻止访问的一个通过另一台主机的主机资源。</span><span class="sxs-lookup"><span data-stu-id="b370b-115">BizTalk Server creates a SQL Server Database role per host, named BTS_\<*hostname*\>_User, and adds the Windows group for each host to its respective SQL Server Database role in order to block access of one host resources by another host.</span></span>  
  
## <a name="accounts-not-supported-by-biztalk-server"></a><span data-ttu-id="b370b-116">BizTalk Server 不支持的帐户</span><span class="sxs-lookup"><span data-stu-id="b370b-116">Accounts not supported by BizTalk Server</span></span>  
 <span data-ttu-id="b370b-117">BizTalk Server 不支持使用任何以下内置 Windows 帐户：</span><span class="sxs-lookup"><span data-stu-id="b370b-117">BizTalk Server does not support using any of the following built-in Windows accounts:</span></span>  
  
-   <span data-ttu-id="b370b-118">NT_AUTHORITY\NetworkService</span><span class="sxs-lookup"><span data-stu-id="b370b-118">NT_AUTHORITY\NetworkService</span></span>  
  
-   <span data-ttu-id="b370b-119">LocalSystem</span><span class="sxs-lookup"><span data-stu-id="b370b-119">LocalSystem</span></span>  
  
-   <span data-ttu-id="b370b-120">NT_AUTHORITY\LocalService</span><span class="sxs-lookup"><span data-stu-id="b370b-120">NT_AUTHORITY\LocalService</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b370b-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="b370b-121">See Also</span></span>  
 <span data-ttu-id="b370b-122">[管理角色的访问控制](../core/access-control-for-administrative-roles.md) </span><span class="sxs-lookup"><span data-stu-id="b370b-122">[Access Control for Administrative Roles](../core/access-control-for-administrative-roles.md) </span></span>  
 <span data-ttu-id="b370b-123">[最低安全用户权限](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="b370b-123">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 <span data-ttu-id="b370b-124">[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="b370b-124">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="b370b-125">访问控制和数据安全性</span><span class="sxs-lookup"><span data-stu-id="b370b-125">Access Control and Data Security</span></span>](../core/access-control-and-data-security.md)