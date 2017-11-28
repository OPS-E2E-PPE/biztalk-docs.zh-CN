---
title: "域组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: domain groups
ms.assetid: 9adc090e-e18c-46b6-b985-49b200d42966
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52fc5cc05718aa6d9e0ca89bc48467052fb916a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="domain-groups"></a><span data-ttu-id="26f58-102">域组</span><span class="sxs-lookup"><span data-stu-id="26f58-102">Domain Groups</span></span>
<span data-ttu-id="26f58-103">BizTalk Server 在单计算机配置和多计算机配置中都支持域组和域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="26f58-103">BizTalk Server supports domain group and user accounts in both single and multiple computer configurations.</span></span> <span data-ttu-id="26f58-104">对于多计算机配置，必须满足本部分以及安装指南的“多服务器环境注意事项”中提出的要求。</span><span class="sxs-lookup"><span data-stu-id="26f58-104">For multiple computer configurations, you must observe the requirements provided in this section and in the Considerations for Multiserver Environments in the Installation Guide.</span></span> <span data-ttu-id="26f58-105">有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 的安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。</span><span class="sxs-lookup"><span data-stu-id="26f58-105">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span>  
  
-   <span data-ttu-id="26f58-106">如果你的 BizTalk Server 配置使用域组，则在配置 BizTalk Server 前必须先手动创建这些组。</span><span class="sxs-lookup"><span data-stu-id="26f58-106">If you use domain groups for your BizTalk Server configuration, you must manually create the groups before you configure BizTalk Server.</span></span> <span data-ttu-id="26f58-107">配置管理器无法创建域组。</span><span class="sxs-lookup"><span data-stu-id="26f58-107">The Configuration Manager cannot create domain groups.</span></span>  
  
-   <span data-ttu-id="26f58-108">在创建域组和/或用户帐户后, 将用户帐户添加到适当的组中组隶属关系根据[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="26f58-108">After creating domain groups and/or user accounts, add user accounts to the proper groups according to the group affiliations in [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="26f58-109">使用 **\<DomainName >\\< 用户名\>**时指定 Configuration Manager 中的域帐户信息。</span><span class="sxs-lookup"><span data-stu-id="26f58-109">Use **\<DomainName>\\<UserName\>** when specifying domain account information in the Configuration Manager.</span></span>  
  
-   <span data-ttu-id="26f58-110">对于所有群集方案，BizTalk Server 要求使用域帐户。</span><span class="sxs-lookup"><span data-stu-id="26f58-110">BizTalk Server requires domain accounts for all clustering scenarios.</span></span> <span data-ttu-id="26f58-111">不能将本地帐户用于群集 SQL Server 或群集 SSO 服务器（主密钥服务器）。</span><span class="sxs-lookup"><span data-stu-id="26f58-111">You cannot use local accounts with clustered SQL Server or clustered SSO Server (master secret server).</span></span>  
  
-   <span data-ttu-id="26f58-112">安装和配置 BizTalk Server 的管理员必须是以下组的成员：SSO Administrators（仅当配置主密钥服务器时）、本地 Administrators、sysadmin SQL Server 角色以及 OLAP Administrators。</span><span class="sxs-lookup"><span data-stu-id="26f58-112">The administrator installing and configuring BizTalk Server must be a member of the following groups: SSO Administrators (only when configuring the master secret server); local Administrators; sysadmin SQL Server role; OLAP Administrators.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26f58-113">如果在配置 SSO Administrators 和 SSO Affiliate Administrators 组的过程中指定了域组，并且您具有足够的权限，则会自动创建域组。</span><span class="sxs-lookup"><span data-stu-id="26f58-113">You can create the domain group automatically if you specify a domain group during configuration for the SSO Administrators and SSO Affiliate Administrators, and you have sufficient privileges.</span></span> <span data-ttu-id="26f58-114">如果您没有足够的权限，请确保这些组已存在。</span><span class="sxs-lookup"><span data-stu-id="26f58-114">If you do not have sufficient privileges, ensure that these groups already exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26f58-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26f58-115">See Also</span></span>  
 <span data-ttu-id="26f58-116">[本地组](../core/local-groups.md) </span><span class="sxs-lookup"><span data-stu-id="26f58-116">[Local Groups](../core/local-groups.md) </span></span>  
 <span data-ttu-id="26f58-117">[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span><span class="sxs-lookup"><span data-stu-id="26f58-117">[Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span></span>  
 [<span data-ttu-id="26f58-118">BizTalk Server 中的 Windows 组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="26f58-118">Windows Groups and User Accounts in BizTalk Server</span></span>](../core/windows-groups-and-user-accounts-in-biztalk-server.md)