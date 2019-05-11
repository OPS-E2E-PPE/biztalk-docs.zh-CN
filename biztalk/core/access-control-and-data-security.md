---
title: 访问控制和数据安全 |Microsoft Docs
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
ms.openlocfilehash: e34babf08ccc18d0e20165b5f3a39914ad7324e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362255"
---
# <a name="access-control-and-data-security"></a><span data-ttu-id="698c0-102">访问控制和数据安全性</span><span class="sxs-lookup"><span data-stu-id="698c0-102">Access Control and Data Security</span></span>
<span data-ttu-id="698c0-103">BizTalk Server 使用最低用户权限; 限制对其进程和数据库的访问您可以通过使用 Microsoft Windows Server 中的功能来帮助系统中的重要数据的安全。</span><span class="sxs-lookup"><span data-stu-id="698c0-103">BizTalk Server limits access to its processes and databases by using minimum user rights; you can help secure important data in the system by using features from Microsoft Windows Server.</span></span> <span data-ttu-id="698c0-104">出于安全原因，BizTalk Server Administrators 和 BizTalk 主机不应具有比执行其作业所需的更多的用户权限。</span><span class="sxs-lookup"><span data-stu-id="698c0-104">For security reasons, BizTalk Server Administrators and BizTalk Hosts should not have more user rights than necessary to perform their jobs.</span></span>  
  
 <span data-ttu-id="698c0-105">BizTalk 控制管理对使用 SQL 角色，从而控制数据通过工具或直接通过数据库访问的数据访问。</span><span class="sxs-lookup"><span data-stu-id="698c0-105">BizTalk controls Administrative access to data using SQL roles, thereby controlling access to data both via tools and directly via the database.</span></span> <span data-ttu-id="698c0-106">使用 Host User 组和帐户控制 BizTalk 主机访问数据。</span><span class="sxs-lookup"><span data-stu-id="698c0-106">BizTalk Host access to data is controlled using Host User groups and accounts.</span></span>  
  
 <span data-ttu-id="698c0-107">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，有两种管理角色： BizTalk Server 管理器和 BizTalk Server 操作员。</span><span class="sxs-lookup"><span data-stu-id="698c0-107">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], there are two Administrative Roles: the BizTalk Server Administrator, and the BizTalk Server Operator.</span></span> <span data-ttu-id="698c0-108">无论，只要创建 BizTalk Server 数据库通过安装还是 BizTalk Server 管理控制台，BizTalk Server 会自动在该数据库中创建这两种管理角色的 SQL 角色。</span><span class="sxs-lookup"><span data-stu-id="698c0-108">Anytime you create a BizTalk Server database through installation or the BizTalk Server Administration Console, BizTalk Server automatically creates SQL roles for both these administrative roles in that database.</span></span> <span data-ttu-id="698c0-109">BizTalk Server 授予每个角色，以及分配给该角色，任何 SQL Server 登录名的 SQL Server 对象 （表、 视图、 存储的过程等） 对该数据库执行管理任务上的管理员所需的最低用户权限。</span><span class="sxs-lookup"><span data-stu-id="698c0-109">BizTalk Server grants each role, and any SQL Server login assigned to the role, the minimum user rights needed by administrators on the SQL Server objects (tables, views, stored procedures, etc) to perform administrative tasks on that database.</span></span>  
  
 <span data-ttu-id="698c0-110">BizTalk Server 管理员是高权限角色，有权访问配置数据和跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="698c0-110">The BizTalk Server Administrator is a high privilege role with access to configuration and tracking data.</span></span> <span data-ttu-id="698c0-111">BizTalk Server 操作员是低权限角色，仅有权监视和故障排除操作。</span><span class="sxs-lookup"><span data-stu-id="698c0-111">The BizTalk Server Operator is a low privilege role with access only to monitoring and troubleshooting actions.</span></span> <span data-ttu-id="698c0-112">这后一种角色可以查看服务状态和消息流和可以启动或停止应用程序以及终止和恢复服务实例，但不能更改配置或查看消息属性和内容。</span><span class="sxs-lookup"><span data-stu-id="698c0-112">This latter role can view service state and message flow and can start or stop applications and terminate and resume service instances, but cannot change configuration or view message properties and content.</span></span>  
  
 <span data-ttu-id="698c0-113">同样，BizTalk Server 数据库中创建每个用户组的 SQL 角色的每个主机，并且授予此角色的用户组来执行该主机的任务所需的最低用户权限。</span><span class="sxs-lookup"><span data-stu-id="698c0-113">Similarly, BizTalk Server creates in each database a SQL role for the user group for each host, and grants this role the minimum user rights it needs for the user group to perform tasks for that host.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="698c0-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="698c0-114">In This Section</span></span>  
  
-   [<span data-ttu-id="698c0-115">Windows 组和 BizTalk Server 中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="698c0-115">Windows Groups and User Accounts in BizTalk Server</span></span>](../core/windows-groups-and-user-accounts-in-biztalk-server.md)  
  
-   [<span data-ttu-id="698c0-116">组和服务帐户的访问控制</span><span class="sxs-lookup"><span data-stu-id="698c0-116">Access Control for Groups and Service Accounts</span></span>](../core/access-control-for-groups-and-service-accounts.md)  
  
-   [<span data-ttu-id="698c0-117">管理角色的访问控制</span><span class="sxs-lookup"><span data-stu-id="698c0-117">Access Control for Administrative Roles</span></span>](../core/access-control-for-administrative-roles.md)  
  
-   [<span data-ttu-id="698c0-118">对业务信息的访问控制</span><span class="sxs-lookup"><span data-stu-id="698c0-118">Access Control to Business Information</span></span>](../core/access-control-to-business-information.md)  
  
-   [<span data-ttu-id="698c0-119">最低安全用户权限</span><span class="sxs-lookup"><span data-stu-id="698c0-119">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)