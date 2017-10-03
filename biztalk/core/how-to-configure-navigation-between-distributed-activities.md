---
title: "如何配置之间的导航分布式活动 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f8faf0a-eb06-4383-932d-4106306d6cf3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88c0a1cf8d82ee5cd4e48e176b5b7f633101d8c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-navigation-between-distributed-activities"></a><span data-ttu-id="bb36b-102">如何配置分布式活动之间的导航</span><span class="sxs-lookup"><span data-stu-id="bb36b-102">How to Configure Navigation Between Distributed Activities</span></span>
<span data-ttu-id="bb36b-103">利用分布式导航，用户可以查看远程 BAM 部署中的活动。</span><span class="sxs-lookup"><span data-stu-id="bb36b-103">Distributed navigation allows users to view activities that exist in remote BAM deployments.</span></span> <span data-ttu-id="bb36b-104">当启用分布式的导航时，一台计算机上 BAM 门户的用户将能够查看活动上的另一个部署的 BAM 门户中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bb36b-104">When you enable distributed navigation, users of the BAM portal on one computer will be able to view activities in the BAM portal on another deployment of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="bb36b-105">本主题中的过程介绍了如何在以下情形中启用分布式导航：</span><span class="sxs-lookup"><span data-stu-id="bb36b-105">The procedure in this topic describes how to enable distributed navigation in the following scenario:</span></span>  
  
-   <span data-ttu-id="bb36b-106">与销售部门[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署在 1 台计算机。</span><span class="sxs-lookup"><span data-stu-id="bb36b-106">A sales department with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployed on computer 1.</span></span>  
  
-   <span data-ttu-id="bb36b-107">传送部门[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署在 2 台计算机。</span><span class="sxs-lookup"><span data-stu-id="bb36b-107">A shipping department with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployed on computer 2.</span></span>  
  
-   <span data-ttu-id="bb36b-108">名为 myBusinessView 的视图和名为“销售数据”的活动部署在计算机 1 中。</span><span class="sxs-lookup"><span data-stu-id="bb36b-108">A view called myBusinessView with an activity called Sales Data deployed on computer 1.</span></span>  
  
-   <span data-ttu-id="bb36b-109">名为 myBusinessView 的视图和名为“运输数据”的活动安装在计算机 2 中。</span><span class="sxs-lookup"><span data-stu-id="bb36b-109">A view called myBusinessView with an activity called Shipping Data installed on computer 2.</span></span>  
  
-   <span data-ttu-id="bb36b-110">销售部门中的业务用户因业务需要，必须查看这两台计算机中的活动。</span><span class="sxs-lookup"><span data-stu-id="bb36b-110">A business user in the sales department with a business need to see the activities on both computers.</span></span>  
  
### <a name="how-to-set-up-distributed-navigation-for-remote-activities"></a><span data-ttu-id="bb36b-111">如何为远程活动设置分布式导航</span><span class="sxs-lookup"><span data-stu-id="bb36b-111">How to set up distributed navigation for remote activities</span></span>  
  
1.  <span data-ttu-id="bb36b-112">计算机 1 的管理员授予对计算机 1 上的 myBusinessView 视图的业务用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="bb36b-112">The administrator of computer 1 grants the business user access to the myBusinessView view on computer 1.</span></span> <span data-ttu-id="bb36b-113">按以下方式使用 bm.exe 命令，：**添加帐户 AccountName:\<帐户名称 >-视图：** myBusinessView</span><span class="sxs-lookup"><span data-stu-id="bb36b-113">You use the bm.exe command, as follows: **add-account -AccountName:\<account name> -View:** myBusinessView</span></span>  
  
2.  <span data-ttu-id="bb36b-114">计算机 1 上的管理员，如下所示运行启用引用命令中，通过启用分布式的导航： **bm.exe 启用引用 TargetServer:** computer2 **-TargetDatabase:\<目标数据库 >**</span><span class="sxs-lookup"><span data-stu-id="bb36b-114">The administrator on computer 1 enables distributed navigation by running the enable reference command, as follows: **bm.exe enable-reference -TargetServer:** computer2 **-TargetDatabase:\<target database>**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb36b-115">通常，部门间用于访问 BAM Web Services 的帐户在不同计算机上是不同的。</span><span class="sxs-lookup"><span data-stu-id="bb36b-115">Typically the account used between departments for BAM Web services access will be different on different computers.</span></span> <span data-ttu-id="bb36b-116">因此，在此方案中的计算机 1 管理员必须将添加计算机 1 的 Web 服务模拟帐户到 BAM_ManagementWS 角色计算机 2 的 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="bb36b-116">Therefore, in this scenario the administrator of computer 1 must add the Web services Impersonation account of computer 1 to the BAM_ManagementWS role of the BAM Primary Import database for computer 2.</span></span> <span data-ttu-id="bb36b-117">有关详细信息，请参阅"查看和修改角色成员身份" [http://go.microsoft.com/fwlink/?LinkId=66990](http://go.microsoft.com/fwlink/?LinkId=66990)。</span><span class="sxs-lookup"><span data-stu-id="bb36b-117">For more information, see "Viewing and Modifying Role Memberships" at [http://go.microsoft.com/fwlink/?LinkId=66990](http://go.microsoft.com/fwlink/?LinkId=66990).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb36b-118">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="bb36b-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
3.  <span data-ttu-id="bb36b-119">计算机 2 的管理员授予业务用户访问计算机 2 中的 myBusinessView 视图的权限，同样使用步骤 1 中介绍的 BM.exe 命令。</span><span class="sxs-lookup"><span data-stu-id="bb36b-119">The administrator of computer 2 grants the business user access to the myBusinessView view on computer 2 using the BM.exe command as noted in step 1.</span></span>  
  
## <a name="results-of-setting-up-distributed-navigation"></a><span data-ttu-id="bb36b-120">设置分布式导航的结果</span><span class="sxs-lookup"><span data-stu-id="bb36b-120">Results of Setting Up Distributed Navigation</span></span>  
 <span data-ttu-id="bb36b-121">启用分布式导航后，添加到两台计算机上的视图中的用户将可以在其主页门户的“我的视图”窗格中看到两台计算机上部署的视图的活动。</span><span class="sxs-lookup"><span data-stu-id="bb36b-121">When distributed navigation is enabled the users added to the views on both computers will see the activities for the views deployed on both computers in the My Views pane of their home portal.</span></span> <span data-ttu-id="bb36b-122">这些用户单击的活动远程部署上承载的它们会无缝地将转到门户在其上的托管活动，并才能进行查看的活动，就像它是在其默认门户上。</span><span class="sxs-lookup"><span data-stu-id="bb36b-122">When these users click an activity that is hosted on a remote deployment, they are seamlessly directed to the portal on which that activity is hosted and they are able to view the activity as if it were on their default portal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb36b-123">在两个方向上都可以启用分布式导航。</span><span class="sxs-lookup"><span data-stu-id="bb36b-123">Distributed navigation can be enabled in both directions.</span></span> <span data-ttu-id="bb36b-124">在要共享远程活动的两台计算机上执行以上过程，可以使任一计算机上的门户的业务用户使用分布式导航。</span><span class="sxs-lookup"><span data-stu-id="bb36b-124">Following the procedure above on both computers that are sharing remote activities enables business users of the portals on either computer to use distributed navigation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb36b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb36b-125">See Also</span></span>  
 <span data-ttu-id="bb36b-126">[管理远程活动的分布式的的导航](../core/managing-distributed-navigation-of-remote-activities.md) </span><span class="sxs-lookup"><span data-stu-id="bb36b-126">[Managing Distributed Navigation of Remote Activities](../core/managing-distributed-navigation-of-remote-activities.md) </span></span>  
 [<span data-ttu-id="bb36b-127">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="bb36b-127">BAM Portal</span></span>](../core/bam-portal.md)