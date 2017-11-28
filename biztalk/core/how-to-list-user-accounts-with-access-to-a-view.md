---
title: "如何列出用户帐户具有访问权限添加到视图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user accounts, BAM
- managing [BAM], user accounts
- Get-Accounts utility [BAM]
ms.assetid: 690fb45a-6de0-489e-9ddd-e88e29413c16
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 099a2b8f3d914297529a192def9e5c23a49d31af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-list-user-accounts-with-access-to-a-view"></a><span data-ttu-id="17fc3-102">如何列出具有视图访问权限的用户帐户</span><span class="sxs-lookup"><span data-stu-id="17fc3-102">How to List User Accounts With Access to a View</span></span>
<span data-ttu-id="17fc3-103">管理员使用**get 帐户**BAM 管理实用程序命令，以便获取列表视图角色，这意味着所有的用户帐户有权访问指定的视图的所有用户帐户。</span><span class="sxs-lookup"><span data-stu-id="17fc3-103">Administrators use the **get-accounts** BAM Management utility command to get a list all user accounts for a view role, meaning all user accounts with access to the specified view.</span></span>  
  
 <span data-ttu-id="17fc3-104">有关查看 BAM 视图的信息，请参阅[如何列表 BAM 视图](../core/how-to-list-bam-views.md)。</span><span class="sxs-lookup"><span data-stu-id="17fc3-104">For information about viewing BAM views, see [How to List BAM Views](../core/how-to-list-bam-views.md).</span></span>  
  
### <a name="to-list-user-accounts-with-access-to-a-view"></a><span data-ttu-id="17fc3-105">列出具有视图访问权限的用户帐户</span><span class="sxs-lookup"><span data-stu-id="17fc3-105">To list user accounts with access to a view</span></span>  
  
1.  <span data-ttu-id="17fc3-106">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="17fc3-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="17fc3-107">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking</span><span class="sxs-lookup"><span data-stu-id="17fc3-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking</span></span>  
  
3.  <span data-ttu-id="17fc3-108">类型**bm get 帐户的视图：\<视图名称 >**。</span><span class="sxs-lookup"><span data-stu-id="17fc3-108">Type **bm get-accounts -View:\<view name>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="17fc3-109">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="17fc3-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="17fc3-110">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="17fc3-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17fc3-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17fc3-111">See Also</span></span>  
 <span data-ttu-id="17fc3-112">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="17fc3-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="17fc3-113">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="17fc3-113">BAM Management Utility</span></span>](../core/bam-management-utility.md)