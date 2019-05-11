---
title: 管理远程活动的分布式的导航 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cf6e0c2-ea72-4621-9ca7-fa43e404ec46
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49922065cc0f388439f6d089eb043d221a702ba8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380306"
---
# <a name="managing-distributed-navigation-of-remote-activities"></a><span data-ttu-id="340f1-102">管理远程活动的分布式的导航</span><span class="sxs-lookup"><span data-stu-id="340f1-102">Managing Distributed Navigation of Remote Activities</span></span>
<span data-ttu-id="340f1-103">远程活动的分布式的导航是业务用户导航到并查看其他 BAM 数据库中存在的活动的过程。</span><span class="sxs-lookup"><span data-stu-id="340f1-103">Distributed navigation of remote activities is the process by which a business user navigates to and views activities that exist in separate BAM databases.</span></span> <span data-ttu-id="340f1-104">在配置 BAM 基础结构，以提供分布式的导航时，远程活动都可以访问 BAM 门户中的业务用户。</span><span class="sxs-lookup"><span data-stu-id="340f1-104">When you configure the BAM infrastructure to provide distributed navigation, the remote activity is accessible to the business user in the BAM portal.</span></span> <span data-ttu-id="340f1-105">当用户单击该活动时，活动是在远程 BAM 门户网站上打开。</span><span class="sxs-lookup"><span data-stu-id="340f1-105">When the user clicks the activity, the activity is opened on the remote BAM portal.</span></span> <span data-ttu-id="340f1-106">此时用户到远程 BAM 门户传输透明且无缝的方式，并像用户的主数据存储于存在活动可以导航到活动搜索、 聚合和警报管理活动。</span><span class="sxs-lookup"><span data-stu-id="340f1-106">At this point the user has been transferred in a transparent and seamless manner to the remote BAM portal and can navigate to the activity search, aggregations, and alert management for the activity as if the activity existed on the user's home data store.</span></span>  
  
## <a name="why-use-distributed-navigation-of-activities-and-documents"></a><span data-ttu-id="340f1-107">为什么要使用活动和文档的分布式的的导航？</span><span class="sxs-lookup"><span data-stu-id="340f1-107">Why Use Distributed Navigation of Activities and Documents?</span></span>  
 <span data-ttu-id="340f1-108">分布式的导航，组织可以保留而无需在单个位置的活动上同意对部门 BAM 数据库的控制。</span><span class="sxs-lookup"><span data-stu-id="340f1-108">Distributed navigation allows organizations to retain control of departmental BAM databases without having to agree on a single location for the activities.</span></span> <span data-ttu-id="340f1-109">此外，还可以更好的性能从 BAM 数据库分散在整个环境的活动的系统负载。</span><span class="sxs-lookup"><span data-stu-id="340f1-109">This also allows for better performance from your BAM databases by distributing the system load of the activities throughout your environment.</span></span>  
  
 <span data-ttu-id="340f1-110">下图说明了在其中分布式的导航满足的需求的业务用户能够轻松访问由一家公司中其他部门管理的活动的方案。</span><span class="sxs-lookup"><span data-stu-id="340f1-110">The following figure illustrates a scenario in which distributed navigation addresses the needs of the business user to have easy access to activities that are managed by separate departments in a company.</span></span> <span data-ttu-id="340f1-111">这些部门管理员负责维护特定于该部门的业务流程的控制。</span><span class="sxs-lookup"><span data-stu-id="340f1-111">The administrators in those departments maintain control of the business processes specific to that department.</span></span>  
  
 <span data-ttu-id="340f1-112">在此方案中有以下利益干系人：</span><span class="sxs-lookup"><span data-stu-id="340f1-112">In this scenario there are the following stakeholders:</span></span>  
  
- <span data-ttu-id="340f1-113">掌管销售部门的基础结构的管理员。</span><span class="sxs-lookup"><span data-stu-id="340f1-113">An administrator who owns the infrastructure for the sales department.</span></span> <span data-ttu-id="340f1-114">管理员是负责的可用性和安全部门的数据。</span><span class="sxs-lookup"><span data-stu-id="340f1-114">The administrator is solely responsible for the availability and security of the department’s data.</span></span>  
  
- <span data-ttu-id="340f1-115">掌管货运部门的基础结构的管理员。</span><span class="sxs-lookup"><span data-stu-id="340f1-115">An administrator who owns the infrastructure for the shipping department.</span></span> <span data-ttu-id="340f1-116">他是满足销售的需求。</span><span class="sxs-lookup"><span data-stu-id="340f1-116">He is responsible for meeting the needs of the sales.</span></span>  
  
- <span data-ttu-id="340f1-117">销售部门中的业务用户。</span><span class="sxs-lookup"><span data-stu-id="340f1-117">A business user in the sales department.</span></span> <span data-ttu-id="340f1-118">业务用户可以查看用户已添加到其中的视图中包含的销售数据的子集。</span><span class="sxs-lookup"><span data-stu-id="340f1-118">The business user sees subsets of the sales data that are included in the views to which the user has been added.</span></span> <span data-ttu-id="340f1-119">由管理员授予业务用户访问视图创建视图。</span><span class="sxs-lookup"><span data-stu-id="340f1-119">The views are created by the administrator who grants the business user access to the view.</span></span> <span data-ttu-id="340f1-120">业务用户的主业务视图是其参与的采购订单活动。</span><span class="sxs-lookup"><span data-stu-id="340f1-120">The business user's primary view of the business is the Purchase Order activity in which she participates.</span></span> <span data-ttu-id="340f1-121">此用户设置以查看由销售部门管理员维护 BAM 门户的主页。</span><span class="sxs-lookup"><span data-stu-id="340f1-121">This user is set up to view the home page of the BAM portal maintained by the administrator of the sales department.</span></span>  
  
  <span data-ttu-id="340f1-122">**在 BAM 中使用分布式的导航**</span><span class="sxs-lookup"><span data-stu-id="340f1-122">**Using Distributed Navigation in BAM**</span></span>  
  
  <span data-ttu-id="340f1-123">![分布式导航方案。](../core/media/bcd-distrbuted-nav-scenario.gif "bcd_distrbuted_nav_scenario")</span><span class="sxs-lookup"><span data-stu-id="340f1-123">![Distrbuted navigation scenario.](../core/media/bcd-distrbuted-nav-scenario.gif "bcd_distrbuted_nav_scenario")</span></span>  
  
  <span data-ttu-id="340f1-124">管理员想要配置其服务器尽可能，独立，如下所示：</span><span class="sxs-lookup"><span data-stu-id="340f1-124">The administrators want to configure their servers to be as independent as possible, as follows:</span></span>  
  
- <span data-ttu-id="340f1-125">销售部门管理员不希望接受订单后，若要停止或业务用户如果传送部门基础结构出现故障会受到影响的查询功能。</span><span class="sxs-lookup"><span data-stu-id="340f1-125">The sales department administrator does not want the acceptance of the orders to stop or the query functionality for his business users to be affected if the shipping department infrastructure is down.</span></span>  
  
- <span data-ttu-id="340f1-126">货运部门的管理员不希望他部门受到影响的销售部门中的性能问题。</span><span class="sxs-lookup"><span data-stu-id="340f1-126">The shipping department administrator does not want his department to be affected by performance problems in the sales department.</span></span> <span data-ttu-id="340f1-127">他希望业务用户能够了解发货的进度即使销售部门将不可用。</span><span class="sxs-lookup"><span data-stu-id="340f1-127">He wants his business users to be able to follow the progress of the shipments, even if the sales department is unavailable.</span></span>  
  
  <span data-ttu-id="340f1-128">分布式导航的目标是业务最终用户提供他们有权访问到的每个视图的访问权限。</span><span class="sxs-lookup"><span data-stu-id="340f1-128">The goal of distributed navigation is to provide the business end user with access to every view to which they have permissions.</span></span>  
  
  <span data-ttu-id="340f1-129">例如，销售数据库中定义视图 A 和 B。</span><span class="sxs-lookup"><span data-stu-id="340f1-129">For example, views A and B are defined in the sales database.</span></span> <span data-ttu-id="340f1-130">货运部门定义了视图 C。</span><span class="sxs-lookup"><span data-stu-id="340f1-130">The shipping department has view C defined.</span></span> <span data-ttu-id="340f1-131">业务用户有权查看所有这些操作，并访问特定于销售部门在 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="340f1-131">The business user has permission to view all of these, and accesses the BAM portal specific to the sales department.</span></span> <span data-ttu-id="340f1-132">允许业务用户查看视图 A、 B 和 C 中的**我的视图**门户的框架通过建立至少一个从销售数据库向货运数据库的单向信任。</span><span class="sxs-lookup"><span data-stu-id="340f1-132">Allowing the business user to see views A, B, and C in the **MyViews** frame of the portal is accomplished by establishing at least a one-way trust from the sales database to the shipping database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="340f1-133">Power 业务用户，如管理器或分析师所定义的类别的业务用户可以查看指定的数据的权限。</span><span class="sxs-lookup"><span data-stu-id="340f1-133">The permissions for the category of business user that can see specified data are defined by the power business user, such as a manager or analyst.</span></span> <span data-ttu-id="340f1-134">管理员仅将用户添加到现有组或 BAM 视图。</span><span class="sxs-lookup"><span data-stu-id="340f1-134">The administrators only add users to existing groups or BAM views.</span></span>  
  
 <span data-ttu-id="340f1-135">BAM 活动的分布式的导航还允许用户查看和访问分布式的活动的关系。</span><span class="sxs-lookup"><span data-stu-id="340f1-135">Distributed navigation of BAM activities also allows the user to see and access distributed activity relationships.</span></span> <span data-ttu-id="340f1-136">如果已使用分布式的导航彼此相关的两个不同的 BAM 数据库的活动实例，远程相关的活动显示为本地活动实例的活动详细信息中的相关活动。</span><span class="sxs-lookup"><span data-stu-id="340f1-136">When there are activity instances on two different BAM databases that have been related to each other using distributed navigation, the remote related activity is displayed as a related activity in the activity details of the local activity instance.</span></span> <span data-ttu-id="340f1-137">单击相关的活动打开远程门户上的活动的活动详细信息页。</span><span class="sxs-lookup"><span data-stu-id="340f1-137">Clicking the related activity opens the activity details page for the activity on the remote portal.</span></span> <span data-ttu-id="340f1-138">有关相关活动的 BAM 门户，请参阅中的活动搜索结果页的详细信息[相关活动](../core/related-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="340f1-138">For more information about the related activities of the activity search results page in the BAM portal, a see [Related Activities](../core/related-activities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="340f1-139">对于每台计算机可以位于不同 BAM 数据库中的相关的活动的用户，必须启用所有 BAM 数据库之间的双向分布式的导航。</span><span class="sxs-lookup"><span data-stu-id="340f1-139">For users on each computer to see related activities located in different BAM databases, you must enable two-way distributed navigation between all the BAM databases.</span></span>  
  
 <span data-ttu-id="340f1-140">如果启用配置分布式的导航时的两个主导入数据库之间的单向分布式的导航，用户将在导航过程中有不同。</span><span class="sxs-lookup"><span data-stu-id="340f1-140">If you enable one-way distributed navigation between two Primary Import databases when you configure distributed navigation, users will have an asymmetrical experience during the navigation.</span></span>  
  
 <span data-ttu-id="340f1-141">用户体验不会这样，用户将看到不同的活动;但是，当用户钻取的实例级数据，应显示相关的实例的部分将为空。</span><span class="sxs-lookup"><span data-stu-id="340f1-141">The user experience will be such that the user will see the different activities; however, when the user drills into the instance-level data, the section where related instances are displayed will be empty.</span></span> <span data-ttu-id="340f1-142">若要解决此问题，必须配置分布式的导航路径，返回到用户本地 BAM 门户服务器。</span><span class="sxs-lookup"><span data-stu-id="340f1-142">To resolve this issue, you must configure the distributed navigation path back to the home BAM portal server for the user.</span></span>  
  
 <span data-ttu-id="340f1-143">例如，考虑以下方案：</span><span class="sxs-lookup"><span data-stu-id="340f1-143">For example, consider the following scenario:</span></span>  
  
- <span data-ttu-id="340f1-144">具有计算机 1 您有一个名为采购订单活动和一个名为 SalesManager 视图。</span><span class="sxs-lookup"><span data-stu-id="340f1-144">You have Computer 1 on which you have an activity called Purchase Order and a view called SalesManager.</span></span>  
  
- <span data-ttu-id="340f1-145">必须对其具有名为发货订单的活动和一个名为 SalesManager 视图计算机 2</span><span class="sxs-lookup"><span data-stu-id="340f1-145">You have Computer 2 on which you have an activity called Shipping Order and a view called SalesManager</span></span>  
  
- <span data-ttu-id="340f1-146">添加一个计算机 1 上名为采购订单到 PO_1 活动</span><span class="sxs-lookup"><span data-stu-id="340f1-146">You add an activity called PO_1 to Purchase Order on Computer 1</span></span>  
  
- <span data-ttu-id="340f1-147">添加名为发货订单 SO_1 为在计算机 2 上的活动</span><span class="sxs-lookup"><span data-stu-id="340f1-147">You add an activity called SO_1 to Shipping Order on Computer 2</span></span>  
  
- <span data-ttu-id="340f1-148">在计算机 2 上添加的关系，SO_1 对 PurchaseOrder PO_1 活动上发货订单</span><span class="sxs-lookup"><span data-stu-id="340f1-148">On Computer 2 you add the relationship,  SO_1 to the PurchaseOrder PO_1 Activity on Shipping Order</span></span>  
  
- <span data-ttu-id="340f1-149">向下用户钻取到 SO_1 活动从计算机 1 SO_1 活动时，可发现</span><span class="sxs-lookup"><span data-stu-id="340f1-149">When a user drills down into the SO_1 activity from Computer 1 the SO_1 activity is discoverable</span></span>  
  
- <span data-ttu-id="340f1-150">如果用户 so_1 时在计算机 2，PO_1 活动将不可见</span><span class="sxs-lookup"><span data-stu-id="340f1-150">If the user drills down the SO_1 on Computer 2, the PO_1 activity is not visible</span></span>  
  
  <span data-ttu-id="340f1-151">若要纠正这个问题，您需要在计算机 1 上添加关系。</span><span class="sxs-lookup"><span data-stu-id="340f1-151">To rectify this, you will need to add the relationship on Computer 1.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="340f1-152">本节内容</span><span class="sxs-lookup"><span data-stu-id="340f1-152">In This Section</span></span>  
  
-   [<span data-ttu-id="340f1-153">如何配置分布式活动之间的导航</span><span class="sxs-lookup"><span data-stu-id="340f1-153">How to Configure Navigation Between Distributed Activities</span></span>](../core/how-to-configure-navigation-between-distributed-activities.md)  
  
## <a name="see-also"></a><span data-ttu-id="340f1-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="340f1-154">See Also</span></span>  
 [<span data-ttu-id="340f1-155">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="340f1-155">Managing BAM</span></span>](../core/managing-bam.md)