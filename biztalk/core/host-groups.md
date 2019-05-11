---
title: 主机组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d92478b-b3a2-4c5a-925e-5495ee481e82
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93e56411a55fefd4c54c1a0583b619e68b868e2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344270"
---
# <a name="host-groups"></a><span data-ttu-id="75cb6-102">主机组</span><span class="sxs-lookup"><span data-stu-id="75cb6-102">Host Groups</span></span>

## <a name="overview"></a><span data-ttu-id="75cb6-103">概述</span><span class="sxs-lookup"><span data-stu-id="75cb6-103">Overview</span></span>
<span data-ttu-id="75cb6-104">主机组是 （默认情况下，名为 BizTalk Application Users 组） 的 Windows 组用于对进程内 BizTalk 主机 （BizTalk Server 中的主机进程） 具有访问权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="75cb6-104">The host group is the Windows group (named the BizTalk Application Users group by default) that you use for accounts with access to the in-process BizTalk hosts (host processes in BizTalk Server).</span></span> <span data-ttu-id="75cb6-105">建议使用一个主机组的每个进程内主机在环境中。</span><span class="sxs-lookup"><span data-stu-id="75cb6-105">It is recommended that you use one host group for each in-process host in your environment.</span></span>  
  
 <span data-ttu-id="75cb6-106">只能将一个主机关联与一个 Windows 组 (称为*主机组*)。</span><span class="sxs-lookup"><span data-stu-id="75cb6-106">You can only associate a host with one Windows group (called a *host group*).</span></span> <span data-ttu-id="75cb6-107">主机组必须在所有相关的 BizTalk Server 数据库中具有 SQL Server 登录名和特权。</span><span class="sxs-lookup"><span data-stu-id="75cb6-107">The host group must have a SQL Server login and privileges in all relevant BizTalk Server databases.</span></span> <span data-ttu-id="75cb6-108">时将主机与主机组相关联，可以授予主机的主机组的权限。</span><span class="sxs-lookup"><span data-stu-id="75cb6-108">When you associate a host with the host group, you grant the host the privileges of the host group.</span></span>  
  
 <span data-ttu-id="75cb6-109">如果你使用配置向导创建主机，并指定要使用的主机的本地 Windows 组，配置向导将自动创建两个 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="75cb6-109">If you use the Configuration Wizard to create hosts, and you specify a local Windows group to use for hosts, the Configuration Wizard automatically creates two Windows groups.</span></span> <span data-ttu-id="75cb6-110">这些组的默认名称是 BizTalk Application Users 组和 BizTalk Isolated Host Users 组。</span><span class="sxs-lookup"><span data-stu-id="75cb6-110">The default names of these groups are the BizTalk Application Users group and the BizTalk Isolated Host Users group.</span></span>  
  
 <span data-ttu-id="75cb6-111">当您创建与主机组相关联的主机的主机实例时，该实例将继承主机组的数据库权限。</span><span class="sxs-lookup"><span data-stu-id="75cb6-111">When you create a host instance of a host associated with the host group, the host instance inherits the database privileges of the host group.</span></span>  
  
 <span data-ttu-id="75cb6-112">主机组是主机 Windows Management Instrumentation (WMI) 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="75cb6-112">The host group is a property of the host Windows Management Instrumentation (WMI) object.</span></span> <span data-ttu-id="75cb6-113">可以更改主机是否存在任何主机的实例所属的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="75cb6-113">You can change the Windows group that a host belongs to if there are no host instances of the host.</span></span>  
  
 <span data-ttu-id="75cb6-114">指定当您创建一个主机时，主机所属的主机组。</span><span class="sxs-lookup"><span data-stu-id="75cb6-114">You specify the host group a host belongs to when you create the host.</span></span> <span data-ttu-id="75cb6-115">BizTalk WMI 提供程序授予权限的主机组对主机拥有 （例如，运行时功能，包括 SQL Server 登录名和数据库用户访问权限所需的 BizTalk Server 权限）。</span><span class="sxs-lookup"><span data-stu-id="75cb6-115">The BizTalk WMI provider grants the privileges that the host group has (for example, the BizTalk Server privileges required for runtime functionality, including SQL Server logins and database user access) to the host.</span></span> <span data-ttu-id="75cb6-116">您必须指定正确的服务帐户 （主机） 时创建的主机实例，以便 BizTalk Server WMI 提供程序的主机组的权限授予主机实例。</span><span class="sxs-lookup"><span data-stu-id="75cb6-116">You must specify the correct service account (host) when you create a host instance, so that the BizTalk Server WMI provider grants the privileges of the host group to the host instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75cb6-117">如果你想要创建本地主机组，可以创建一个本地 Windows 组并将域用户分配为组的成员。</span><span class="sxs-lookup"><span data-stu-id="75cb6-117">If you want to create a local host group, you can create a local Windows group and assign a domain user as a member of the group.</span></span> <span data-ttu-id="75cb6-118">如果为主机指定本地 Windows 组，Windows 组成员，无论是域或本地用户，可以使用作为主机实例登录用户。</span><span class="sxs-lookup"><span data-stu-id="75cb6-118">If you specify a local Windows group for the Host, the Windows group member, whether it is a domain or local user, can be used as the host instance log-on user.</span></span>  

## <a name="required-permissions"></a><span data-ttu-id="75cb6-119">所需的权限</span><span class="sxs-lookup"><span data-stu-id="75cb6-119">Required permissions</span></span>  
 <span data-ttu-id="75cb6-120">主机组需要以下权限：</span><span class="sxs-lookup"><span data-stu-id="75cb6-120">The host group requires the following privileges:</span></span>  
  
-   <span data-ttu-id="75cb6-121">它必须是以下数据库中的 BTS_HOST_USERS SQL Server 角色的成员：</span><span class="sxs-lookup"><span data-stu-id="75cb6-121">It must be a member of the BTS_HOST_USERS SQL Server role in the following databases:</span></span>  
  
    -   <span data-ttu-id="75cb6-122">BizTalk 管理</span><span class="sxs-lookup"><span data-stu-id="75cb6-122">BizTalk Management</span></span> 
  
    -   <span data-ttu-id="75cb6-123">MessageBox</span><span class="sxs-lookup"><span data-stu-id="75cb6-123">MessageBox</span></span>  
  
    -   <span data-ttu-id="75cb6-124">规则引擎</span><span class="sxs-lookup"><span data-stu-id="75cb6-124">Rule Engine</span></span>  
  
    -   <span data-ttu-id="75cb6-125">跟踪</span><span class="sxs-lookup"><span data-stu-id="75cb6-125">Tracking</span></span>  
  
    -   <span data-ttu-id="75cb6-126">BAM 主导入</span><span class="sxs-lookup"><span data-stu-id="75cb6-126">BAM Primary Import</span></span>  
  
-   <span data-ttu-id="75cb6-127">它必须属于 BTS_\<进程内主机名称\>（_u） MessageBox 数据库的 SQL Server 角色</span><span class="sxs-lookup"><span data-stu-id="75cb6-127">It must be a member of the BTS_\<in-process host name\>_USERS SQL Server role for the MessageBox database</span></span>  
  
-   <span data-ttu-id="75cb6-128">它必须是 BAM 主导入数据库中的 BAM_EVENT_WRITER SQL Server 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="75cb6-128">It must be a member of the BAM_EVENT_WRITER SQL Server role in the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75cb6-129">如果为跟踪主机指定一个主机，BizTalk Server 管理自动从跟踪数据库的 SQL Server 角色中删除 BizTalk 主机组。</span><span class="sxs-lookup"><span data-stu-id="75cb6-129">If you designate a host as a tracking host, BizTalk Server Administration automatically removes the BizTalk Host group from the SQL Server roles for the Tracking database.</span></span> <span data-ttu-id="75cb6-130">从 BizTalk 管理数据库和 MessageBox 数据库的 SQL Server 角色，必须手动删除 BizTalk 主机组。</span><span class="sxs-lookup"><span data-stu-id="75cb6-130">You must manually remove the BizTalk Host group from the SQL Server roles for the BizTalk Management database and the MessageBox database.</span></span> <span data-ttu-id="75cb6-131">有关将主机指定为跟踪主机的信息，请参阅[修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="75cb6-131">For information about designating a host as a tracking host, see [Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75cb6-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="75cb6-132">See Also</span></span>  
 [<span data-ttu-id="75cb6-133">实体</span><span class="sxs-lookup"><span data-stu-id="75cb6-133">Entities</span></span>](../core/entities.md)