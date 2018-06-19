---
title: 日志传送用户帐户和角色 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2056ea90-5e9f-4501-95d6-18c905db4023
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7dbec7cfa23c8a1e07e32cdf0c3ce7b044651ec
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010598"
---
# <a name="log-shipping-user-accounts-and-roles"></a><span data-ttu-id="1e730-102">日志传送用户帐户和角色</span><span class="sxs-lookup"><span data-stu-id="1e730-102">Log Shipping User Accounts and Roles</span></span>
<span data-ttu-id="1e730-103">BizTalk Server 日志传送都由 SQL Server 代理作业来自动执行还原的备份和日志的过程。</span><span class="sxs-lookup"><span data-stu-id="1e730-103">BizTalk Server log shipping is driven by a SQL Server Agent job to automate the process of restoring backups and logs.</span></span> <span data-ttu-id="1e730-104">不正确的权限可能会导致执行 BizTalk Server 日志传送失败还原操作。</span><span class="sxs-lookup"><span data-stu-id="1e730-104">Incorrect permissions can cause restore operations performed by BizTalk Server log shipping to fail.</span></span> <span data-ttu-id="1e730-105">配置以将数据库还原的用户帐户必须有权承载 BizTalk 管理数据库的生产数据库实例。</span><span class="sxs-lookup"><span data-stu-id="1e730-105">The user account configured to restore databases must have access to the production database instance that hosts the BizTalk Management database.</span></span> <span data-ttu-id="1e730-106">在大多数情况下这意味着，服务帐户为灾难恢复驱动的 BizTalk Server 日志传送作业的 SQL Server 代理作业[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例需要一个登录名和承载对生产数据库实例的权限[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理数据库。</span><span class="sxs-lookup"><span data-stu-id="1e730-106">In most cases this means that the service account for the SQL Server Agent job driving the BizTalk Server log shipping job on the disaster recovery [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance requires a login and permissions on the production database instance that hosts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database.</span></span> <span data-ttu-id="1e730-107">这会假定作为作业所有者已配置 SQL Server 代理服务帐户。</span><span class="sxs-lookup"><span data-stu-id="1e730-107">This assumes that the SQL Server Agent service account is configured as the job owner.</span></span>  
  
 <span data-ttu-id="1e730-108">BizTalk Server 包括一个名为 BTS_BACKUP_USERS，以便配置以将数据库还原的用户帐户不需要 SQL Server 系统管理员权限的 SQL Server 角色。</span><span class="sxs-lookup"><span data-stu-id="1e730-108">BizTalk Server includes a SQL Server role named BTS_BACKUP_USERS so that the user account configured to restore databases does not require SQL Server System Administrators permission.</span></span>  
  
 <span data-ttu-id="1e730-109">在配置时将作为 BizTalk Server 日志传送的一部分执行数据库还原操作的用户帐户，请验证以下方面：</span><span class="sxs-lookup"><span data-stu-id="1e730-109">When configuring the user account that will perform database restore operations as part of BizTalk Server log shipping, please verify the following:</span></span>  
  
-   <span data-ttu-id="1e730-110">配置 SQL Server 代理服务以使用映射的用户在中配置的域帐户下运行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio (在**安全**，**登录名**) 上每个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]还原的数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送作业。</span><span class="sxs-lookup"><span data-stu-id="1e730-110">Configure the SQL Server Agent service to run under a domain account with a mapped user configured in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio (in **Security**, **Logins**) on each [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance that hosts [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases restored by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping jobs.</span></span>  
  
-   <span data-ttu-id="1e730-111">配置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]登录帐户对于此用户，并将此用户分配到每个服务器上的 BizTalk BTS_BACKUP_USERS SQL 角色。</span><span class="sxs-lookup"><span data-stu-id="1e730-111">Configure a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] login account for this user, and assign this user to the BizTalk BTS_BACKUP_USERS SQL role on each server.</span></span>  
  
-   <span data-ttu-id="1e730-112">向此用户分配到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]运行的计算机上的系统管理员角色[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，保存[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理数据库。</span><span class="sxs-lookup"><span data-stu-id="1e730-112">Assign this user to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] System Administrators role on the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database.</span></span>  
  
-   <span data-ttu-id="1e730-113">帐户执行备份和还原操作必须具有读取和写入访问权限 UNC 共享其中创建备份文件。</span><span class="sxs-lookup"><span data-stu-id="1e730-113">The account that performs backup and restore operations must have Read and Write access to the UNC share where backup files are created.</span></span>