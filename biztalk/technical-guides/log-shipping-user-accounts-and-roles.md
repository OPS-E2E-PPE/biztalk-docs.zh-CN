---
title: "日志传送用户帐户和角色 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2056ea90-5e9f-4501-95d6-18c905db4023
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b19a7d7c87289e07c7ac7a26bacd0c96f9090c9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="log-shipping-user-accounts-and-roles"></a><span data-ttu-id="7d7d3-102">日志传送用户帐户和角色</span><span class="sxs-lookup"><span data-stu-id="7d7d3-102">Log Shipping User Accounts and Roles</span></span>
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="7d7d3-103">日志传送由 SQL Server 代理作业驱动，以自动执行还原的备份和日志的过程。</span><span class="sxs-lookup"><span data-stu-id="7d7d3-103"> log shipping is driven by a SQL Server Agent job to automate the process of restoring backups and logs.</span></span> <span data-ttu-id="7d7d3-104">不正确的权限可能会导致执行还原操作[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]日志传送失败。</span><span class="sxs-lookup"><span data-stu-id="7d7d3-104">Incorrect permissions can cause restore operations performed by [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] log shipping to fail.</span></span> <span data-ttu-id="7d7d3-105">配置以将数据库还原的用户帐户必须有权承载 BizTalk 管理数据库的生产数据库实例。</span><span class="sxs-lookup"><span data-stu-id="7d7d3-105">The user account configured to restore databases must have access to the production database instance that hosts the BizTalk Management database.</span></span> <span data-ttu-id="7d7d3-106">在大多数情况下这意味着，服务帐户用于 SQL Server 代理作业驱动[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]上灾难恢复日志传送作业[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例需要一个登录名和承载对生产数据库实例的权限[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理数据库。</span><span class="sxs-lookup"><span data-stu-id="7d7d3-106">In most cases this means that the service account for the SQL Server Agent job driving the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] log shipping job on the disaster recovery [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance requires a login and permissions on the production database instance that hosts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database.</span></span> <span data-ttu-id="7d7d3-107">这会假定作为作业所有者已配置 SQL Server 代理服务帐户。</span><span class="sxs-lookup"><span data-stu-id="7d7d3-107">This assumes that the SQL Server Agent service account is configured as the job owner.</span></span>  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="7d7d3-108">包括名为 BTS_BACKUP_USERS，以便配置以将数据库还原的用户帐户不需要 SQL Server 系统管理员权限的 SQL Server 角色。</span><span class="sxs-lookup"><span data-stu-id="7d7d3-108"> includes a SQL Server role named BTS_BACKUP_USERS so that the user account configured to restore databases does not require SQL Server System Administrators permission.</span></span>  
  
 <span data-ttu-id="7d7d3-109">配置将作为的一部分执行数据库还原操作的用户帐户时[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]日志传送，请验证以下：</span><span class="sxs-lookup"><span data-stu-id="7d7d3-109">When configuring the user account that will perform database restore operations as part of [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] log shipping, please verify the following:</span></span>  
  
-   <span data-ttu-id="7d7d3-110">配置 SQL Server 代理服务以使用映射的用户在中配置的域帐户下运行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio (在**安全**，**登录名**) 上每个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]还原的数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送作业。</span><span class="sxs-lookup"><span data-stu-id="7d7d3-110">Configure the SQL Server Agent service to run under a domain account with a mapped user configured in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio (in **Security**, **Logins**) on each [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance that hosts [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases restored by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping jobs.</span></span>  
  
-   <span data-ttu-id="7d7d3-111">配置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]登录帐户对于此用户，并将此用户分配到每个服务器上的 BizTalk BTS_BACKUP_USERS SQL 角色。</span><span class="sxs-lookup"><span data-stu-id="7d7d3-111">Configure a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] login account for this user, and assign this user to the BizTalk BTS_BACKUP_USERS SQL role on each server.</span></span>  
  
-   <span data-ttu-id="7d7d3-112">向此用户分配到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]运行的计算机上的系统管理员角色[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，保存[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理数据库。</span><span class="sxs-lookup"><span data-stu-id="7d7d3-112">Assign this user to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] System Administrators role on the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database.</span></span>  
  
-   <span data-ttu-id="7d7d3-113">帐户执行备份和还原操作必须具有读取和写入访问权限 UNC 共享其中创建备份文件。</span><span class="sxs-lookup"><span data-stu-id="7d7d3-113">The account that performs backup and restore operations must have Read and Write access to the UNC share where backup files are created.</span></span>