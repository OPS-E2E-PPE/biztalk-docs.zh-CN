---
title: "域组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9adc090e-e18c-46b6-b985-49b200d42966
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ae4f855b01a7cfcd789e8d8a37e375f9e72c1a7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="domain-groups-in-biztalk"></a><span data-ttu-id="80f6a-102">在 BIzTalk 域组</span><span class="sxs-lookup"><span data-stu-id="80f6a-102">Domain Groups in BIzTalk</span></span>
<span data-ttu-id="80f6a-103">BizTalk Server 在单计算机配置和多计算机配置中都支持域组和域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="80f6a-103">BizTalk Server supports domain group and user accounts in both single and multiple computer configurations.</span></span> <span data-ttu-id="80f6a-104">对于多计算机配置，必须满足本部分以及安装指南的“多服务器环境注意事项”中提出的要求。</span><span class="sxs-lookup"><span data-stu-id="80f6a-104">For multiple computer configurations, you must observe the requirements provided in this section and in the Considerations for Multiserver Environments in the Installation Guide.</span></span> <span data-ttu-id="80f6a-105">有关详细信息，请参阅[安装概述](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="80f6a-105">For more information, see the [installation overview](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="80f6a-106">开始之前</span><span class="sxs-lookup"><span data-stu-id="80f6a-106">Before you begin</span></span>
-   <span data-ttu-id="80f6a-107">如果你的 BizTalk Server 配置使用域组，则在配置 BizTalk Server 前必须先手动创建这些组。</span><span class="sxs-lookup"><span data-stu-id="80f6a-107">If you use domain groups for your BizTalk Server configuration, you must manually create the groups before you configure BizTalk Server.</span></span> <span data-ttu-id="80f6a-108">配置管理器无法创建域组。</span><span class="sxs-lookup"><span data-stu-id="80f6a-108">The Configuration Manager cannot create domain groups.</span></span>  
  
-   <span data-ttu-id="80f6a-109">在创建域组和/或用户帐户后, 将用户帐户添加到适当的组中组隶属关系根据[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="80f6a-109">After creating domain groups and/or user accounts, add user accounts to the proper groups according to the group affiliations in [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="80f6a-110">使用 **\<DomainName\>\\< 用户名\>**时指定 Configuration Manager 中的域帐户信息。</span><span class="sxs-lookup"><span data-stu-id="80f6a-110">Use **\<DomainName\>\\<UserName\>** when specifying domain account information in the Configuration Manager.</span></span>  
  
-   <span data-ttu-id="80f6a-111">对于所有群集方案，BizTalk Server 要求使用域帐户。</span><span class="sxs-lookup"><span data-stu-id="80f6a-111">BizTalk Server requires domain accounts for all clustering scenarios.</span></span> <span data-ttu-id="80f6a-112">不能将本地帐户用于群集 SQL Server 或群集 SSO 服务器（主密钥服务器）。</span><span class="sxs-lookup"><span data-stu-id="80f6a-112">You cannot use local accounts with clustered SQL Server or clustered SSO Server (master secret server).</span></span>  
  
-   <span data-ttu-id="80f6a-113">安装和配置 BizTalk Server 的管理员必须是以下组的成员：SSO Administrators（仅当配置主密钥服务器时）、本地 Administrators、sysadmin SQL Server 角色以及 OLAP Administrators。</span><span class="sxs-lookup"><span data-stu-id="80f6a-113">The administrator installing and configuring BizTalk Server must be a member of the following groups: SSO Administrators (only when configuring the master secret server); local Administrators; sysadmin SQL Server role; OLAP Administrators.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80f6a-114">如果在配置 SSO Administrators 和 SSO Affiliate Administrators 组的过程中指定了域组，并且您具有足够的权限，则会自动创建域组。</span><span class="sxs-lookup"><span data-stu-id="80f6a-114">You can create the domain group automatically if you specify a domain group during configuration for the SSO Administrators and SSO Affiliate Administrators, and you have sufficient privileges.</span></span> <span data-ttu-id="80f6a-115">如果您没有足够的权限，请确保这些组已存在。</span><span class="sxs-lookup"><span data-stu-id="80f6a-115">If you do not have sufficient privileges, ensure that these groups already exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f6a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80f6a-116">See Also</span></span>  
 <span data-ttu-id="80f6a-117">[本地组](../core/local-groups.md) </span><span class="sxs-lookup"><span data-stu-id="80f6a-117">[Local Groups](../core/local-groups.md) </span></span>  
 <span data-ttu-id="80f6a-118">[安装概述](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md) </span><span class="sxs-lookup"><span data-stu-id="80f6a-118">[Installation Overview](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md) </span></span>  
 [<span data-ttu-id="80f6a-119">BizTalk Server 中的 Windows 组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="80f6a-119">Windows Groups and User Accounts in BizTalk Server</span></span>](../core/windows-groups-and-user-accounts-in-biztalk-server.md)