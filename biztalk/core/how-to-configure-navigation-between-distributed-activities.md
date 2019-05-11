---
title: 如何配置之间的导航分布式活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f8faf0a-eb06-4383-932d-4106306d6cf3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd43576f9571cd34aa69f6f666fca6777434cf4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341287"
---
# <a name="how-to-configure-navigation-between-distributed-activities"></a><span data-ttu-id="2c2a2-102">如何配置分布式活动之间的导航</span><span class="sxs-lookup"><span data-stu-id="2c2a2-102">How to Configure Navigation Between Distributed Activities</span></span>
<span data-ttu-id="2c2a2-103">分布式的导航，用户可以查看远程 BAM 部署中存在的活动。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-103">Distributed navigation allows users to view activities that exist in remote BAM deployments.</span></span> <span data-ttu-id="2c2a2-104">启用分布式的导航时，一台计算机上的 BAM 门户的用户将能够查看 BAM 门户上的另一个部署中的活动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-104">When you enable distributed navigation, users of the BAM portal on one computer will be able to view activities in the BAM portal on another deployment of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2c2a2-105">本主题中的过程描述如何能够在以下方案中的分布式的导航：</span><span class="sxs-lookup"><span data-stu-id="2c2a2-105">The procedure in this topic describes how to enable distributed navigation in the following scenario:</span></span>  
  
- <span data-ttu-id="2c2a2-106">销售部门的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署在计算机 1 上。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-106">A sales department with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployed on computer 1.</span></span>  
  
- <span data-ttu-id="2c2a2-107">运输部门的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署在计算机 2 上。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-107">A shipping department with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployed on computer 2.</span></span>  
  
- <span data-ttu-id="2c2a2-108">名为 myBusinessView 视图名为部署在计算机 1 上的销售数据的活动。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-108">A view called myBusinessView with an activity called Sales Data deployed on computer 1.</span></span>  
  
- <span data-ttu-id="2c2a2-109">名为 myBusinessView 视图名为安装在计算机 2 传送数据的活动。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-109">A view called myBusinessView with an activity called Shipping Data installed on computer 2.</span></span>  
  
- <span data-ttu-id="2c2a2-110">销售部门的企业的业务用户需要两台计算机上看到活动。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-110">A business user in the sales department with a business need to see the activities on both computers.</span></span>  
  
### <a name="how-to-set-up-distributed-navigation-for-remote-activities"></a><span data-ttu-id="2c2a2-111">如何设置为远程活动的分布式导航</span><span class="sxs-lookup"><span data-stu-id="2c2a2-111">How to set up distributed navigation for remote activities</span></span>  
  
1.  <span data-ttu-id="2c2a2-112">计算机 1 的管理员授予业务用户对计算机 1 上的 myBusinessView 视图的访问。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-112">The administrator of computer 1 grants the business user access to the myBusinessView view on computer 1.</span></span> <span data-ttu-id="2c2a2-113">使用 bm.exe 命令中，按如下所示：**添加帐户-AccountName:\<帐户名称\>的视图：** myBusinessView</span><span class="sxs-lookup"><span data-stu-id="2c2a2-113">You use the bm.exe command, as follows: **add-account -AccountName:\<account name\> -View:** myBusinessView</span></span>  
  
2.  <span data-ttu-id="2c2a2-114">计算机 1 上的管理员通过按如下所示运行启用引用命令，来启用分布式的导航： **bm.exe 启用引用-TargetServer:** computer2 **-TargetDatabase:\<目标数据库\>**</span><span class="sxs-lookup"><span data-stu-id="2c2a2-114">The administrator on computer 1 enables distributed navigation by running the enable reference command, as follows: **bm.exe enable-reference -TargetServer:** computer2 **-TargetDatabase:\<target database\>**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c2a2-115">通常的帐户访问 BAM Web services 部门间用于将不同的计算机上不同。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-115">Typically the account used between departments for BAM Web services access will be different on different computers.</span></span> <span data-ttu-id="2c2a2-116">因此，在这种情况下计算机 1 的管理员必须添加计算机 1 的 Web 服务模拟帐户到计算机 2 的 BAM 主导入数据库的 BAM_ManagementWS 角色。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-116">Therefore, in this scenario the administrator of computer 1 must add the Web services Impersonation account of computer 1 to the BAM_ManagementWS role of the BAM Primary Import database for computer 2.</span></span> <span data-ttu-id="2c2a2-117">详细信息，请参阅"查看和修改角色成员身份"网址[ http://go.microsoft.com/fwlink/?LinkId=66990 ](http://go.microsoft.com/fwlink/?LinkId=66990)。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-117">For more information, see "Viewing and Modifying Role Memberships" at [http://go.microsoft.com/fwlink/?LinkId=66990](http://go.microsoft.com/fwlink/?LinkId=66990).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c2a2-118">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
3.  <span data-ttu-id="2c2a2-119">计算机 2 的管理员授予业务用户对计算机使用在步骤 1 中记下的 BM.exe 命令 2 上的 myBusinessView 视图的访问。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-119">The administrator of computer 2 grants the business user access to the myBusinessView view on computer 2 using the BM.exe command as noted in step 1.</span></span>  
  
## <a name="results-of-setting-up-distributed-navigation"></a><span data-ttu-id="2c2a2-120">设置分布式导航的结果</span><span class="sxs-lookup"><span data-stu-id="2c2a2-120">Results of Setting Up Distributed Navigation</span></span>  
 <span data-ttu-id="2c2a2-121">启用分布式的导航时添加到两台计算机上的视图的用户将看到其主页门户的我的视图窗格中的两台计算机上部署的视图的活动。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-121">When distributed navigation is enabled the users added to the views on both computers will see the activities for the views deployed on both computers in the My Views pane of their home portal.</span></span> <span data-ttu-id="2c2a2-122">当这些用户单击托管在远程部署的活动时，它们将无缝地定向到所在的门户的托管活动，并能够查看它好像在自己的默认门户上的活动。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-122">When these users click an activity that is hosted on a remote deployment, they are seamlessly directed to the portal on which that activity is hosted and they are able to view the activity as if it were on their default portal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c2a2-123">可以在这两个方向上启用分布式的导航。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-123">Distributed navigation can be enabled in both directions.</span></span> <span data-ttu-id="2c2a2-124">要共享远程活动的两台计算机上执行以上过程启用任何一台计算机上的门户的业务用户可以使用分布式的导航。</span><span class="sxs-lookup"><span data-stu-id="2c2a2-124">Following the procedure above on both computers that are sharing remote activities enables business users of the portals on either computer to use distributed navigation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c2a2-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c2a2-125">See Also</span></span>  
 <span data-ttu-id="2c2a2-126">[管理远程活动的分布式的导航](../core/managing-distributed-navigation-of-remote-activities.md) </span><span class="sxs-lookup"><span data-stu-id="2c2a2-126">[Managing Distributed Navigation of Remote Activities](../core/managing-distributed-navigation-of-remote-activities.md) </span></span>  
 [<span data-ttu-id="2c2a2-127">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="2c2a2-127">BAM Portal</span></span>](../core/bam-portal.md)