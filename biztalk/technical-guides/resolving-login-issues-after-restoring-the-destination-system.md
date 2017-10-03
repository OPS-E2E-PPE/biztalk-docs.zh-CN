---
title: "在还原目标系统后解决登录问题 |Microsoft 文档"
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
ms.openlocfilehash: e691e690552f6decb3eed5f55dd17295c21a4efd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="resolving-login-issues-after-restoring-the-destination-system"></a><span data-ttu-id="4c452-102">在还原目标系统后解决登录问题</span><span class="sxs-lookup"><span data-stu-id="4c452-102">Resolving Login Issues After Restoring the Destination System</span></span>
<span data-ttu-id="4c452-103">根据如何在部署过程配置的源系统，"孤立"用户可能需要解析。</span><span class="sxs-lookup"><span data-stu-id="4c452-103">Depending on how the source system was configured during deployment, "orphaned" users may need to be resolved.</span></span> <span data-ttu-id="4c452-104">孤立的数据库用户是不具有相应安全的用户登录名[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c452-104">An orphaned database user is a user who does not have a corresponding security login in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="4c452-105">使系统联机使用之前创建这些用户的相应登录名[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]SQL Management Studio (在**安全**，**登录名**)。</span><span class="sxs-lookup"><span data-stu-id="4c452-105">Create corresponding logins for these users before bringing the system online using the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SQL Management Studio (in **Security**, **Logins**).</span></span> <span data-ttu-id="4c452-106">你可以在任何时刻，创建这些登录名，但我们建议你创建它们时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置日志传送。</span><span class="sxs-lookup"><span data-stu-id="4c452-106">You can create these logins at any point, but we recommend that you create them when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping is configured.</span></span>  
  
 <span data-ttu-id="4c452-107">创建的登录名应该对应于的 Windows 帐户和组时使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]源系统和任何登录名已手动创建并在任何已配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-创建角色。</span><span class="sxs-lookup"><span data-stu-id="4c452-107">The logins that are created should correspond to the Windows accounts and groups that were used when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] was configured on the source system and to any logins that were manually created and used in any [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-created role.</span></span> <span data-ttu-id="4c452-108">如果这些登录名对应于本地 Windows 帐户或组、 帐户和组必须先创建然后才能添加登录名。</span><span class="sxs-lookup"><span data-stu-id="4c452-108">If these logins correspond to local Windows accounts or groups, the accounts and groups must first be created before the login can be added.</span></span> <span data-ttu-id="4c452-109">如果未更改的 BizTalk server 的计算机名称，然后解决与本地帐户和组的登录名关联的用户。</span><span class="sxs-lookup"><span data-stu-id="4c452-109">If the computer name for the BizTalk server is not changed, then resolve the users associated with the logins for the local accounts and groups.</span></span>  
  
 <span data-ttu-id="4c452-110">配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送，请按照 Microsoft 知识库文章 918992 中的步骤[如何传输登录名和密码的 SQL Server 2005 的实例和 SQL Server 2008 之间](http://go.microsoft.com/fwlink/?LinkId=157143)(http://go.microsoft.com/fwlink/？LinkId = 157143) 创建会将必要的登录名添加到目标服务器的脚本。</span><span class="sxs-lookup"><span data-stu-id="4c452-110">When configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping, follow the steps in Microsoft Knowledge Base Article 918992 [How to transfer the logins and the passwords between instances of SQL Server 2005 and SQL Server 2008](http://go.microsoft.com/fwlink/?LinkId=157143) (http://go.microsoft.com/fwlink/?LinkId=157143) to create a script that will add the necessary logins to the destination server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c452-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c452-111">See Also</span></span>  
 [<span data-ttu-id="4c452-112">故障排除日志传送</span><span class="sxs-lookup"><span data-stu-id="4c452-112">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)