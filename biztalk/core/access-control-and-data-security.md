---
title: 访问控制和数据安全 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- access control, BizTalk Server Operator role
- databases, SQL roles
- access control, about access control
- BizTalk Server Administrator role
- databases, access control
- access control
- access control, BizTalk Server Administrator role
- access control, SQL roles
- user accounts, access control
- BizTalk Server Operator role
ms.assetid: f04fd4a3-0f8c-4170-934a-9cc77edd7f34
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11cb00eabf6110de78e2d194e0a25bfac6a3b6b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225637"
---
# <a name="access-control-and-data-security"></a><span data-ttu-id="001c6-102">访问控制和数据安全</span><span class="sxs-lookup"><span data-stu-id="001c6-102">Access Control and Data Security</span></span>
<span data-ttu-id="001c6-103">BizTalk Server 通过使用最低用户权限来限制对其进程和数据库的访问；您可以使用 Microsoft Windows Server 中的功能来确保系统中重要数据的安全。</span><span class="sxs-lookup"><span data-stu-id="001c6-103">BizTalk Server limits access to its processes and databases by using minimum user rights; you can help secure important data in the system by using features from Microsoft Windows Server.</span></span> <span data-ttu-id="001c6-104">为安全起见，BizTalk Server 管理员和 BizTalk 主机所具有的用户权限不应高于执行其作业所需的权限。</span><span class="sxs-lookup"><span data-stu-id="001c6-104">For security reasons, BizTalk Server Administrators and BizTalk Hosts should not have more user rights than necessary to perform their jobs.</span></span>  
  
 <span data-ttu-id="001c6-105">BizTalk 使用 SQL 角色控制对数据的管理访问，因此可通过工具或直接通过数据库控制对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="001c6-105">BizTalk controls Administrative access to data using SQL roles, thereby controlling access to data both via tools and directly via the database.</span></span> <span data-ttu-id="001c6-106">使用 Host User 组和帐户控制 BizTalk 主机对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="001c6-106">BizTalk Host access to data is controlled using Host User groups and accounts.</span></span>  
  
 <span data-ttu-id="001c6-107">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，有两个管理角色： BizTalk 服务器管理员和 BizTalk Server 运算符。</span><span class="sxs-lookup"><span data-stu-id="001c6-107">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], there are two Administrative Roles: the BizTalk Server Administrator, and the BizTalk Server Operator.</span></span> <span data-ttu-id="001c6-108">无论通过安装还是 BizTalk Server 管理控制台，只要创建 BizTalk Server 数据库，BizTalk Server 就会自动为该数据库中的这两种管理角色创建 SQL 角色。</span><span class="sxs-lookup"><span data-stu-id="001c6-108">Anytime you create a BizTalk Server database through installation or the BizTalk Server Administration Console, BizTalk Server automatically creates SQL roles for both these administrative roles in that database.</span></span> <span data-ttu-id="001c6-109">BizTalk Server 会为每个角色以及分配给该角色的任何 SQL Server 登录帐户，授予管理员在该数据库中对 SQL Server 对象（表、视图和存储过程等）执行管理任务时所需的最低用户权限。</span><span class="sxs-lookup"><span data-stu-id="001c6-109">BizTalk Server grants each role, and any SQL Server login assigned to the role, the minimum user rights needed by administrators on the SQL Server objects (tables, views, stored procedures, etc) to perform administrative tasks on that database.</span></span>  
  
 <span data-ttu-id="001c6-110">BizTalk Server 管理员是高权限角色，有权访问配置数据和跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="001c6-110">The BizTalk Server Administrator is a high privilege role with access to configuration and tracking data.</span></span> <span data-ttu-id="001c6-111">BizTalk Server 操作员是低权限角色，仅有权执行监视操作和排除故障操作。</span><span class="sxs-lookup"><span data-stu-id="001c6-111">The BizTalk Server Operator is a low privilege role with access only to monitoring and troubleshooting actions.</span></span> <span data-ttu-id="001c6-112">后一种角色可以查看服务状态和消息流，启动或停止应用程序，以及终止和恢复服务实例；但不能更改配置，也不能查看消息属性和内容。</span><span class="sxs-lookup"><span data-stu-id="001c6-112">This latter role can view service state and message flow and can start or stop applications and terminate and resume service instances, but cannot change configuration or view message properties and content.</span></span>  
  
 <span data-ttu-id="001c6-113">同样，BizTalk Server 会在每个数据库中为每个主机的用户组创建一个 SQL 角色，并将用户组执行该主机上的任务所需的最低用户权限授予此角色。</span><span class="sxs-lookup"><span data-stu-id="001c6-113">Similarly, BizTalk Server creates in each database a SQL role for the user group for each host, and grants this role the minimum user rights it needs for the user group to perform tasks for that host.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="001c6-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="001c6-114">In This Section</span></span>  
  
-   [<span data-ttu-id="001c6-115">BizTalk Server 中的 Windows 组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="001c6-115">Windows Groups and User Accounts in BizTalk Server</span></span>](../core/windows-groups-and-user-accounts-in-biztalk-server.md)  
  
-   [<span data-ttu-id="001c6-116">组和服务帐户的访问控制</span><span class="sxs-lookup"><span data-stu-id="001c6-116">Access Control for Groups and Service Accounts</span></span>](../core/access-control-for-groups-and-service-accounts.md)  
  
-   [<span data-ttu-id="001c6-117">用于管理角色的访问控制</span><span class="sxs-lookup"><span data-stu-id="001c6-117">Access Control for Administrative Roles</span></span>](../core/access-control-for-administrative-roles.md)  
  
-   [<span data-ttu-id="001c6-118">对业务信息的访问控制</span><span class="sxs-lookup"><span data-stu-id="001c6-118">Access Control to Business Information</span></span>](../core/access-control-to-business-information.md)  
  
-   [<span data-ttu-id="001c6-119">最低安全用户权限</span><span class="sxs-lookup"><span data-stu-id="001c6-119">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)