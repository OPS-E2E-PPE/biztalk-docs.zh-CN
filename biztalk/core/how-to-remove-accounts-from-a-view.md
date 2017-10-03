---
title: "如何从视图中删除帐户 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], security
- managing [BAM], deleting accounts from views
- Remove-Account command [BAM]
ms.assetid: b74a64a0-ddb3-45d2-add7-6261c31be0f0
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80c0909a5544334cd9f0f8540ff5a4c357b851e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-accounts-from-a-view"></a><span data-ttu-id="d7bf6-102">如何从视图中删除帐户</span><span class="sxs-lookup"><span data-stu-id="d7bf6-102">How to Remove Accounts from a View</span></span>
<span data-ttu-id="d7bf6-103">管理员使用**删除帐户**命令以从 BAM 视图中删除用户，以防止未经授权的访问的 BAM Excel 电子表格视图。</span><span class="sxs-lookup"><span data-stu-id="d7bf6-103">Administrators use the **remove-account** command to remove users from BAM views and protect BAM Excel Spreadsheet views from unauthorized access.</span></span>  
  
 <span data-ttu-id="d7bf6-104">有关查看 BAM 视图的信息，请参阅[如何列表 BAM 视图](../core/how-to-list-bam-views.md)。</span><span class="sxs-lookup"><span data-stu-id="d7bf6-104">For information about viewing BAM views, see [How to List BAM Views](../core/how-to-list-bam-views.md).</span></span>  
  
### <a name="to-remove-an-account-from-a-view"></a><span data-ttu-id="d7bf6-105">若要从视图中删除帐户</span><span class="sxs-lookup"><span data-stu-id="d7bf6-105">To remove an account from a view</span></span>  
  
1.  <span data-ttu-id="d7bf6-106">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d7bf6-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="d7bf6-107">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking</span><span class="sxs-lookup"><span data-stu-id="d7bf6-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking</span></span>  
  
3.  <span data-ttu-id="d7bf6-108">类型**bm 删除帐户 AccountName:\<帐户名称 >-视图：\<视图名称 >**。</span><span class="sxs-lookup"><span data-stu-id="d7bf6-108">Type **bm remove-account -AccountName:\<account name> -View:\<view name>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7bf6-109">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="d7bf6-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="d7bf6-110">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="d7bf6-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7bf6-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7bf6-111">See Also</span></span>  
 <span data-ttu-id="d7bf6-112">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="d7bf6-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="d7bf6-113">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="d7bf6-113">BAM Management Utility</span></span>](../core/bam-management-utility.md)