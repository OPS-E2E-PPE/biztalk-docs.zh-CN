---
title: 域组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9adc090e-e18c-46b6-b985-49b200d42966
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afa529aa98f0eee379f4e2000970549ab9305a20
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389318"
---
# <a name="domain-groups-in-biztalk"></a><span data-ttu-id="60aa0-102">在 BizTalk 中的域组</span><span class="sxs-lookup"><span data-stu-id="60aa0-102">Domain Groups in BizTalk</span></span>
<span data-ttu-id="60aa0-103">BizTalk Server 支持单个和多计算机配置中的域组和用户帐户。</span><span class="sxs-lookup"><span data-stu-id="60aa0-103">BizTalk Server supports domain group and user accounts in both single and multiple computer configurations.</span></span> <span data-ttu-id="60aa0-104">对于多计算机配置，必须遵守的要求和安装指南中的多服务器环境注意事项本部分中提供。</span><span class="sxs-lookup"><span data-stu-id="60aa0-104">For multiple computer configurations, you must observe the requirements provided in this section and in the Considerations for Multiserver Environments in the Installation Guide.</span></span> <span data-ttu-id="60aa0-105">有关详细信息，请参阅[安装概述](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="60aa0-105">For more information, see the [installation overview](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="60aa0-106">开始之前</span><span class="sxs-lookup"><span data-stu-id="60aa0-106">Before you begin</span></span>
-   <span data-ttu-id="60aa0-107">如果你的 BizTalk Server 配置为使用域组，必须手动创建组，然后再配置 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="60aa0-107">If you use domain groups for your BizTalk Server configuration, you must manually create the groups before you configure BizTalk Server.</span></span> <span data-ttu-id="60aa0-108">配置管理器无法创建域组。</span><span class="sxs-lookup"><span data-stu-id="60aa0-108">The Configuration Manager cannot create domain groups.</span></span>  
  
-   <span data-ttu-id="60aa0-109">创建域组和/或用户帐户之后, 将用户帐户添加到根据在组隶属关系的适当组[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="60aa0-109">After creating domain groups and/or user accounts, add user accounts to the proper groups according to the group affiliations in [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="60aa0-110">使用 **\<DomainName\>\\< 用户名\>** 指定 Configuration Manager 中的域帐户信息时。</span><span class="sxs-lookup"><span data-stu-id="60aa0-110">Use **\<DomainName\>\\<UserName\>** when specifying domain account information in the Configuration Manager.</span></span>  
  
-   <span data-ttu-id="60aa0-111">BizTalk Server 的所有聚类分析方案要求使用域帐户。</span><span class="sxs-lookup"><span data-stu-id="60aa0-111">BizTalk Server requires domain accounts for all clustering scenarios.</span></span> <span data-ttu-id="60aa0-112">使用 SQL Server 群集或群集的 SSO 服务器 （主密钥服务器），不能使用本地帐户。</span><span class="sxs-lookup"><span data-stu-id="60aa0-112">You cannot use local accounts with clustered SQL Server or clustered SSO Server (master secret server).</span></span>  
  
-   <span data-ttu-id="60aa0-113">安装和配置 BizTalk Server 的管理员必须是以下组的成员：SSO Administrators （仅当配置主密钥服务器）;本地管理员;sysadmin SQL Server 角色;OLAP 管理员。</span><span class="sxs-lookup"><span data-stu-id="60aa0-113">The administrator installing and configuring BizTalk Server must be a member of the following groups: SSO Administrators (only when configuring the master secret server); local Administrators; sysadmin SQL Server role; OLAP Administrators.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60aa0-114">如果在 SSO Administrators 和 SSO Affiliate Administrators，配置过程中指定域组，并且有足够的特权，可以自动创建的域组。</span><span class="sxs-lookup"><span data-stu-id="60aa0-114">You can create the domain group automatically if you specify a domain group during configuration for the SSO Administrators and SSO Affiliate Administrators, and you have sufficient privileges.</span></span> <span data-ttu-id="60aa0-115">如果你没有足够的权限，请确保这些组已存在。</span><span class="sxs-lookup"><span data-stu-id="60aa0-115">If you do not have sufficient privileges, ensure that these groups already exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60aa0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="60aa0-116">See Also</span></span>  
 <span data-ttu-id="60aa0-117">[本地组](../core/local-groups.md) </span><span class="sxs-lookup"><span data-stu-id="60aa0-117">[Local Groups](../core/local-groups.md) </span></span>  
 <span data-ttu-id="60aa0-118">[安装概述](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md) </span><span class="sxs-lookup"><span data-stu-id="60aa0-118">[Installation Overview](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md) </span></span>  
 [<span data-ttu-id="60aa0-119">Windows 组和 BizTalk Server 中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="60aa0-119">Windows Groups and User Accounts in BizTalk Server</span></span>](../core/windows-groups-and-user-accounts-in-biztalk-server.md)
