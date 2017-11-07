---
title: "在还原目标系统后解决登录问题 |Microsoft 文档"
description: "将 SQL Server 登录脚本来解决在 BizTalk Server 中的孤立的用户日志传送"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9232ca3-dadb-4b3c-8ec4-4e307c32d2e5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 559302718c9fe504c9c264de92f6a4af161d91f9
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="resolving-login-issues-after-restoring-the-destination-system"></a><span data-ttu-id="3e655-103">在还原目标系统后解决登录问题</span><span class="sxs-lookup"><span data-stu-id="3e655-103">Resolving Login Issues After Restoring the Destination System</span></span>

## <a name="orphaned-users"></a><span data-ttu-id="3e655-104">孤立的用户</span><span class="sxs-lookup"><span data-stu-id="3e655-104">Orphaned users</span></span>
<span data-ttu-id="3e655-105">根据如何在部署过程配置的源系统，"孤立"用户可能需要解析。</span><span class="sxs-lookup"><span data-stu-id="3e655-105">Depending on how the source system was configured during deployment, "orphaned" users may need to be resolved.</span></span> <span data-ttu-id="3e655-106">孤立的数据库用户是不具有相应安全的用户登录名[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3e655-106">An orphaned database user is a user who does not have a corresponding security login in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="3e655-107">使系统联机使用之前创建这些用户的相应登录名[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]SQL Management Studio (在**安全**，**登录名**)。</span><span class="sxs-lookup"><span data-stu-id="3e655-107">Create corresponding logins for these users before bringing the system online using the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SQL Management Studio (in **Security**, **Logins**).</span></span> <span data-ttu-id="3e655-108">你可以在任何时刻，创建这些登录名，但我们建议你创建它们时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置日志传送。</span><span class="sxs-lookup"><span data-stu-id="3e655-108">You can create these logins at any point, but we recommend that you create them when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping is configured.</span></span>  
  
 <span data-ttu-id="3e655-109">创建的登录名应该对应于的 Windows 帐户和组时使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]源系统和任何登录名已手动创建并在任何已配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-创建角色。</span><span class="sxs-lookup"><span data-stu-id="3e655-109">The logins that are created should correspond to the Windows accounts and groups that were used when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] was configured on the source system and to any logins that were manually created and used in any [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-created role.</span></span> <span data-ttu-id="3e655-110">如果这些登录名对应于本地 Windows 帐户或组、 帐户和组必须先创建然后才能添加登录名。</span><span class="sxs-lookup"><span data-stu-id="3e655-110">If these logins correspond to local Windows accounts or groups, the accounts and groups must first be created before the login can be added.</span></span> <span data-ttu-id="3e655-111">如果未更改的 BizTalk server 的计算机名称，然后解决与本地帐户和组的登录名关联的用户。</span><span class="sxs-lookup"><span data-stu-id="3e655-111">If the computer name for the BizTalk server is not changed, then resolve the users associated with the logins for the local accounts and groups.</span></span>  
  
 <span data-ttu-id="3e655-112">配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送，你可以[KB 918992: SQL Server 实例间传输登录名和密码](https://support.microsoft.com/help/918992/how-to-transfer-logins-and-passwords-between-instances-of-sql-server)创建将必要的登录名添加到目标服务器的脚本。</span><span class="sxs-lookup"><span data-stu-id="3e655-112">When configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping, you can [KB 918992: Transfer the logins and the passwords between instances of SQL Server](https://support.microsoft.com/help/918992/how-to-transfer-logins-and-passwords-between-instances-of-sql-server) to create a script that adds the necessary logins to the destination server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e655-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e655-113">See Also</span></span>  
 [<span data-ttu-id="3e655-114">日志传送疑难解答</span><span class="sxs-lookup"><span data-stu-id="3e655-114">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)
