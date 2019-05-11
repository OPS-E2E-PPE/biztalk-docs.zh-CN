---
title: 如何列出用户帐户具有访问权限添加到视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, BAM
- managing [BAM], user accounts
- Get-Accounts utility [BAM]
ms.assetid: 690fb45a-6de0-489e-9ddd-e88e29413c16
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32a0ee9ab6d2a429825b0bfc1ea9eb755f91892f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384763"
---
# <a name="how-to-list-user-accounts-with-access-to-a-view"></a><span data-ttu-id="341fe-102">如何列出具有视图访问权限的用户帐户</span><span class="sxs-lookup"><span data-stu-id="341fe-102">How to List User Accounts With Access to a View</span></span>
<span data-ttu-id="341fe-103">管理员使用**get 帐户**BAM 管理实用程序命令，以获得某个视图角色，这意味着有权访问指定的视图的所有用户帐户列表的所有用户帐户。</span><span class="sxs-lookup"><span data-stu-id="341fe-103">Administrators use the **get-accounts** BAM Management utility command to get a list all user accounts for a view role, meaning all user accounts with access to the specified view.</span></span>  
  
 <span data-ttu-id="341fe-104">有关查看 BAM 视图的信息，请参阅[如何列出 BAM 视图](../core/how-to-list-bam-views.md)。</span><span class="sxs-lookup"><span data-stu-id="341fe-104">For information about viewing BAM views, see [How to List BAM Views](../core/how-to-list-bam-views.md).</span></span>  
  
### <a name="to-list-user-accounts-with-access-to-a-view"></a><span data-ttu-id="341fe-105">对列出具有视图访问权限的用户帐户</span><span class="sxs-lookup"><span data-stu-id="341fe-105">To list user accounts with access to a view</span></span>  
  
1. <span data-ttu-id="341fe-106">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="341fe-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="341fe-107">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪</span><span class="sxs-lookup"><span data-stu-id="341fe-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking</span></span>  
  
3. <span data-ttu-id="341fe-108">类型**bm 获取帐户的视图：\<视图名称\>**。</span><span class="sxs-lookup"><span data-stu-id="341fe-108">Type **bm get-accounts -View:\<view name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="341fe-109">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="341fe-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="341fe-110">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="341fe-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="341fe-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="341fe-111">See Also</span></span>  
 <span data-ttu-id="341fe-112">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="341fe-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="341fe-113">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="341fe-113">BAM Management Utility</span></span>](../core/bam-management-utility.md)