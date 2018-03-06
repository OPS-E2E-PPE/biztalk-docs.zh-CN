---
title: "主机组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d92478b-b3a2-4c5a-925e-5495ee481e82
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b3132b4084ed0d153895e252c5c64419ce0ac72
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="host-groups"></a><span data-ttu-id="80f71-102">主机组</span><span class="sxs-lookup"><span data-stu-id="80f71-102">Host Groups</span></span>

## <a name="overview"></a><span data-ttu-id="80f71-103">概述</span><span class="sxs-lookup"><span data-stu-id="80f71-103">Overview</span></span>
<span data-ttu-id="80f71-104">主机组是用于对进程内 BizTalk 主机（BizTalk Server 中的主机进程）具有访问权限的帐户的 Windows 组（默认情况下名为 BizTalk Application Users 组）。</span><span class="sxs-lookup"><span data-stu-id="80f71-104">The host group is the Windows group (named the BizTalk Application Users group by default) that you use for accounts with access to the in-process BizTalk hosts (host processes in BizTalk Server).</span></span> <span data-ttu-id="80f71-105">建议对环境中的每个进程内主机分别使用一个主机组。</span><span class="sxs-lookup"><span data-stu-id="80f71-105">It is recommended that you use one host group for each in-process host in your environment.</span></span>  
  
 <span data-ttu-id="80f71-106">你只能将一个 Windows 组与关联的主机 (称为 *主机组*)。</span><span class="sxs-lookup"><span data-stu-id="80f71-106">You can only associate a host with one Windows group (called a *host group*).</span></span> <span data-ttu-id="80f71-107">主机组必须在所有相关 BizTalk Server 数据库中具有 SQL Server 登录名和权限。</span><span class="sxs-lookup"><span data-stu-id="80f71-107">The host group must have a SQL Server login and privileges in all relevant BizTalk Server databases.</span></span> <span data-ttu-id="80f71-108">在将主机与主机组相关联时，会将主机组的权限授予该主机。</span><span class="sxs-lookup"><span data-stu-id="80f71-108">When you associate a host with the host group, you grant the host the privileges of the host group.</span></span>  
  
 <span data-ttu-id="80f71-109">如果使用配置向导创建主机，并指定将为主机使用本地 Windows 组，则配置向导将自动创建两个 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="80f71-109">If you use the Configuration Wizard to create hosts, and you specify a local Windows group to use for hosts, the Configuration Wizard automatically creates two Windows groups.</span></span> <span data-ttu-id="80f71-110">这两个组的默认名称为 BizTalk Application Users 组和 BizTalk Isolated Host Users 组。</span><span class="sxs-lookup"><span data-stu-id="80f71-110">The default names of these groups are the BizTalk Application Users group and the BizTalk Isolated Host Users group.</span></span>  
  
 <span data-ttu-id="80f71-111">在创建与主机组关联的主机的实例时，该实例将继承主机组的数据库权限。</span><span class="sxs-lookup"><span data-stu-id="80f71-111">When you create a host instance of a host associated with the host group, the host instance inherits the database privileges of the host group.</span></span>  
  
 <span data-ttu-id="80f71-112">主机组是主机 Windows 管理规范 (WMI) 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="80f71-112">The host group is a property of the host Windows Management Instrumentation (WMI) object.</span></span> <span data-ttu-id="80f71-113">如果主机没有实例，则可以更改该主机所属的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="80f71-113">You can change the Windows group that a host belongs to if there are no host instances of the host.</span></span>  
  
 <span data-ttu-id="80f71-114">在创建主机时指定主机所属的主机组。</span><span class="sxs-lookup"><span data-stu-id="80f71-114">You specify the host group a host belongs to when you create the host.</span></span> <span data-ttu-id="80f71-115">BizTalk WMI 提供程序会将主机组拥有的权限（例如，运行时功能所需的 BizTalk Server 权限，包括 SQL Server 登录和数据库用户访问）授予该主机。</span><span class="sxs-lookup"><span data-stu-id="80f71-115">The BizTalk WMI provider grants the privileges that the host group has (for example, the BizTalk Server privileges required for runtime functionality, including SQL Server logins and database user access) to the host.</span></span> <span data-ttu-id="80f71-116">在创建主机实例时，必须指定正确的服务帐户（主机），以便 BizTalk Server WMI 提供程序将主机组的权限授予该主机实例。</span><span class="sxs-lookup"><span data-stu-id="80f71-116">You must specify the correct service account (host) when you create a host instance, so that the BizTalk Server WMI provider grants the privileges of the host group to the host instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80f71-117">若要创建本地主机组，可以创建一个本地 Windows 组，然后分配一个域用户作为该组的成员。</span><span class="sxs-lookup"><span data-stu-id="80f71-117">If you want to create a local host group, you can create a local Windows group and assign a domain user as a member of the group.</span></span> <span data-ttu-id="80f71-118">如果为主机指定本地 Windows 组，则该 Windows 组成员（无论是域用户还是本地用户）可以用作主机实例登录用户。</span><span class="sxs-lookup"><span data-stu-id="80f71-118">If you specify a local Windows group for the Host, the Windows group member, whether it is a domain or local user, can be used as the host instance log-on user.</span></span>  

## <a name="required-permissions"></a><span data-ttu-id="80f71-119">所需的权限</span><span class="sxs-lookup"><span data-stu-id="80f71-119">Required permissions</span></span>  
 <span data-ttu-id="80f71-120">主机组需要以下权限：</span><span class="sxs-lookup"><span data-stu-id="80f71-120">The host group requires the following privileges:</span></span>  
  
-   <span data-ttu-id="80f71-121">它必须是以下数据库中的 BTS_HOST_USERS SQL Server 角色的成员：</span><span class="sxs-lookup"><span data-stu-id="80f71-121">It must be a member of the BTS_HOST_USERS SQL Server role in the following databases:</span></span>  
  
    -   <span data-ttu-id="80f71-122">BizTalk 管理</span><span class="sxs-lookup"><span data-stu-id="80f71-122">BizTalk Management</span></span> 
  
    -   <span data-ttu-id="80f71-123">MessageBox</span><span class="sxs-lookup"><span data-stu-id="80f71-123">MessageBox</span></span>  
  
    -   <span data-ttu-id="80f71-124">规则引擎</span><span class="sxs-lookup"><span data-stu-id="80f71-124">Rule Engine</span></span>  
  
    -   <span data-ttu-id="80f71-125">跟踪</span><span class="sxs-lookup"><span data-stu-id="80f71-125">Tracking</span></span>  
  
    -   <span data-ttu-id="80f71-126">BAM 主导入</span><span class="sxs-lookup"><span data-stu-id="80f71-126">BAM Primary Import</span></span>  
  
-   <span data-ttu-id="80f71-127">它必须属于 BTS_\<进程内主机名\>（_u） SQL Server 数据库角色的 MessageBox</span><span class="sxs-lookup"><span data-stu-id="80f71-127">It must be a member of the BTS_\<in-process host name\>_USERS SQL Server role for the MessageBox database</span></span>  
  
-   <span data-ttu-id="80f71-128">它必须是 BAM 主导入数据库中的 BAM_EVENT_WRITER SQL Server 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="80f71-128">It must be a member of the BAM_EVENT_WRITER SQL Server role in the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80f71-129">如果将某个主机指定为跟踪主机，对于跟踪数据库，BizTalk Server 管理将自动从 SQL Server 角色中删除 BizTalk 主机组。</span><span class="sxs-lookup"><span data-stu-id="80f71-129">If you designate a host as a tracking host, BizTalk Server Administration automatically removes the BizTalk Host group from the SQL Server roles for the Tracking database.</span></span> <span data-ttu-id="80f71-130">对于 BizTalk 管理数据库和 MessageBox 数据库，必须手动从 SQL Server 角色中删除 BizTalk 主机组。</span><span class="sxs-lookup"><span data-stu-id="80f71-130">You must manually remove the BizTalk Host group from the SQL Server roles for the BizTalk Management database and the MessageBox database.</span></span> <span data-ttu-id="80f71-131">有关作为跟踪主机指定主机的信息，请参阅[修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="80f71-131">For information about designating a host as a tracking host, see [Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f71-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80f71-132">See Also</span></span>  
 [<span data-ttu-id="80f71-133">实体</span><span class="sxs-lookup"><span data-stu-id="80f71-133">Entities</span></span>](../core/entities.md)