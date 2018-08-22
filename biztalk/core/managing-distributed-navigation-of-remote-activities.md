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
ms.openlocfilehash: 2be784f72fe5c027f1a481335579ca77bfbea4a0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009918"
---
# <a name="managing-distributed-navigation-of-remote-activities"></a><span data-ttu-id="09f1a-102">管理远程活动的分布式导航</span><span class="sxs-lookup"><span data-stu-id="09f1a-102">Managing Distributed Navigation of Remote Activities</span></span>
<span data-ttu-id="09f1a-103">通过远程活动的分布式导航，业务用户可导航到其他 BAM 数据库上的活动并进行查看。</span><span class="sxs-lookup"><span data-stu-id="09f1a-103">Distributed navigation of remote activities is the process by which a business user navigates to and views activities that exist in separate BAM databases.</span></span> <span data-ttu-id="09f1a-104">只要您对 BAM 基础结构进行配置以提供分布式导航功能，业务用户就可通过 BAM 门户访问远程活动。</span><span class="sxs-lookup"><span data-stu-id="09f1a-104">When you configure the BAM infrastructure to provide distributed navigation, the remote activity is accessible to the business user in the BAM portal.</span></span> <span data-ttu-id="09f1a-105">用户单击活动时，该活动就会在远程 BAM 门户中打开。</span><span class="sxs-lookup"><span data-stu-id="09f1a-105">When the user clicks the activity, the activity is opened on the remote BAM portal.</span></span> <span data-ttu-id="09f1a-106">此时，用户以一种透明且无缝的方式进入远程 BAM 门户，这样用户就可导航到该活动的活动搜索、聚合和警报管理，好像该活动的数据存储在用户本地一样。</span><span class="sxs-lookup"><span data-stu-id="09f1a-106">At this point the user has been transferred in a transparent and seamless manner to the remote BAM portal and can navigate to the activity search, aggregations, and alert management for the activity as if the activity existed on the user's home data store.</span></span>  
  
## <a name="why-use-distributed-navigation-of-activities-and-documents"></a><span data-ttu-id="09f1a-107">对活动和文档使用分布式导航的原因</span><span class="sxs-lookup"><span data-stu-id="09f1a-107">Why Use Distributed Navigation of Activities and Documents?</span></span>  
 <span data-ttu-id="09f1a-108">分布式的导航，组织可以保留而无需在单个位置的活动上同意对部门 BAM 数据库的控制。</span><span class="sxs-lookup"><span data-stu-id="09f1a-108">Distributed navigation allows organizations to retain control of departmental BAM databases without having to agree on a single location for the activities.</span></span> <span data-ttu-id="09f1a-109">此外，还可以更好的性能从 BAM 数据库分散在整个环境的活动的系统负载。</span><span class="sxs-lookup"><span data-stu-id="09f1a-109">This also allows for better performance from your BAM databases by distributing the system load of the activities throughout your environment.</span></span>  
  
 <span data-ttu-id="09f1a-110">在下图介绍的方案中，分布式导航满足了业务用户轻松访问公司中其他部门管理的活动的需求。</span><span class="sxs-lookup"><span data-stu-id="09f1a-110">The following figure illustrates a scenario in which distributed navigation addresses the needs of the business user to have easy access to activities that are managed by separate departments in a company.</span></span> <span data-ttu-id="09f1a-111">这些部门的管理员负责控制特定于其部门的业务流程。</span><span class="sxs-lookup"><span data-stu-id="09f1a-111">The administrators in those departments maintain control of the business processes specific to that department.</span></span>  
  
 <span data-ttu-id="09f1a-112">此方案涉及以下人员：</span><span class="sxs-lookup"><span data-stu-id="09f1a-112">In this scenario there are the following stakeholders:</span></span>  
  
- <span data-ttu-id="09f1a-113">掌管销售部门的基础结构的管理员。</span><span class="sxs-lookup"><span data-stu-id="09f1a-113">An administrator who owns the infrastructure for the sales department.</span></span> <span data-ttu-id="09f1a-114">该管理员全权负责该部门数据的可用性和安全性。</span><span class="sxs-lookup"><span data-stu-id="09f1a-114">The administrator is solely responsible for the availability and security of the department’s data.</span></span>  
  
- <span data-ttu-id="09f1a-115">掌管货运部门的基础结构的管理员。</span><span class="sxs-lookup"><span data-stu-id="09f1a-115">An administrator who owns the infrastructure for the shipping department.</span></span> <span data-ttu-id="09f1a-116">其职责是满足销售的需求。</span><span class="sxs-lookup"><span data-stu-id="09f1a-116">He is responsible for meeting the needs of the sales.</span></span>  
  
- <span data-ttu-id="09f1a-117">销售部门的业务用户。</span><span class="sxs-lookup"><span data-stu-id="09f1a-117">A business user in the sales department.</span></span> <span data-ttu-id="09f1a-118">该业务用户可以查看视图中的销售数据的子集，该用户已经被加入到这些视图。</span><span class="sxs-lookup"><span data-stu-id="09f1a-118">The business user sees subsets of the sales data that are included in the views to which the user has been added.</span></span> <span data-ttu-id="09f1a-119">这些视图是由向业务用户授予访问该视图权限的管理员创建的。</span><span class="sxs-lookup"><span data-stu-id="09f1a-119">The views are created by the administrator who grants the business user access to the view.</span></span> <span data-ttu-id="09f1a-120">该业务用户的主业务视图是其参与的“采购订单”活动。</span><span class="sxs-lookup"><span data-stu-id="09f1a-120">The business user's primary view of the business is the Purchase Order activity in which she participates.</span></span> <span data-ttu-id="09f1a-121">此用户设置为查看由销售部门管理员所维护的 BAM 门户的主页。</span><span class="sxs-lookup"><span data-stu-id="09f1a-121">This user is set up to view the home page of the BAM portal maintained by the administrator of the sales department.</span></span>  
  
  <span data-ttu-id="09f1a-122">**在 BAM 中使用分布式的导航**</span><span class="sxs-lookup"><span data-stu-id="09f1a-122">**Using Distributed Navigation in BAM**</span></span>  
  
  <span data-ttu-id="09f1a-123">![分布式导航方案。](../core/media/bcd-distrbuted-nav-scenario.gif "bcd_distrbuted_nav_scenario")</span><span class="sxs-lookup"><span data-stu-id="09f1a-123">![Distrbuted navigation scenario.](../core/media/bcd-distrbuted-nav-scenario.gif "bcd_distrbuted_nav_scenario")</span></span>  
  
  <span data-ttu-id="09f1a-124">管理员希望其服务器尽可能配置得独立，具体要求如下：</span><span class="sxs-lookup"><span data-stu-id="09f1a-124">The administrators want to configure their servers to be as independent as possible, as follows:</span></span>  
  
- <span data-ttu-id="09f1a-125">销售部门的管理员不希望货运部门的基础结构出现故障时，销售部门也得停止接收订单，或者业务用户的查询功能受到影响。</span><span class="sxs-lookup"><span data-stu-id="09f1a-125">The sales department administrator does not want the acceptance of the orders to stop or the query functionality for his business users to be affected if the shipping department infrastructure is down.</span></span>  
  
- <span data-ttu-id="09f1a-126">货运部门的管理员也不希望销售部门的系统性能不佳时，自己部门受到影响。</span><span class="sxs-lookup"><span data-stu-id="09f1a-126">The shipping department administrator does not want his department to be affected by performance problems in the sales department.</span></span> <span data-ttu-id="09f1a-127">即时在无法访问销售部门时，他也希望业务用户能够了解发货的进度。</span><span class="sxs-lookup"><span data-stu-id="09f1a-127">He wants his business users to be able to follow the progress of the shipments, even if the sales department is unavailable.</span></span>  
  
  <span data-ttu-id="09f1a-128">分布式导航的目标就是要让业务最终用户能够访问每一个有权访问的视图。</span><span class="sxs-lookup"><span data-stu-id="09f1a-128">The goal of distributed navigation is to provide the business end user with access to every view to which they have permissions.</span></span>  
  
  <span data-ttu-id="09f1a-129">例如，销售数据库中定义了视图 A 和视图 B。</span><span class="sxs-lookup"><span data-stu-id="09f1a-129">For example, views A and B are defined in the sales database.</span></span> <span data-ttu-id="09f1a-130">货运部门定义了视图 C。</span><span class="sxs-lookup"><span data-stu-id="09f1a-130">The shipping department has view C defined.</span></span> <span data-ttu-id="09f1a-131">业务用户有权查看所有这些视图，同时还可访问特定于销售部门的 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="09f1a-131">The business user has permission to view all of these, and accesses the BAM portal specific to the sales department.</span></span> <span data-ttu-id="09f1a-132">允许业务用户查看视图 A、 B 和 C 中的**我的视图**门户的框架通过建立至少一个从销售数据库向货运数据库的单向信任。</span><span class="sxs-lookup"><span data-stu-id="09f1a-132">Allowing the business user to see views A, B, and C in the **MyViews** frame of the portal is accomplished by establishing at least a one-way trust from the sales database to the shipping database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09f1a-133">关于哪类业务用户可以查看指定数据的权限由具有特殊权限的业务用户（如经理或分析员）定义。</span><span class="sxs-lookup"><span data-stu-id="09f1a-133">The permissions for the category of business user that can see specified data are defined by the power business user, such as a manager or analyst.</span></span> <span data-ttu-id="09f1a-134">管理员只负责将用户添加到现有的组或 BAM 视图。</span><span class="sxs-lookup"><span data-stu-id="09f1a-134">The administrators only add users to existing groups or BAM views.</span></span>  
  
 <span data-ttu-id="09f1a-135">BAM 活动的分布式导航还允许用户查看和访问分布式活动的关系。</span><span class="sxs-lookup"><span data-stu-id="09f1a-135">Distributed navigation of BAM activities also allows the user to see and access distributed activity relationships.</span></span> <span data-ttu-id="09f1a-136">当活动实例存在于两个不同的 BAM 数据库中，且这两个数据库已由分布式导航联结到了一起时，远程相关活动在本地活动实例的活动详细信息中显示为相关活动。</span><span class="sxs-lookup"><span data-stu-id="09f1a-136">When there are activity instances on two different BAM databases that have been related to each other using distributed navigation, the remote related activity is displayed as a related activity in the activity details of the local activity instance.</span></span> <span data-ttu-id="09f1a-137">单击相关活动，就会在远程门户上打开该活动的活动详细信息页。</span><span class="sxs-lookup"><span data-stu-id="09f1a-137">Clicking the related activity opens the activity details page for the activity on the remote portal.</span></span> <span data-ttu-id="09f1a-138">有关相关活动的 BAM 门户，请参阅中的活动搜索结果页的详细信息[相关活动](../core/related-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="09f1a-138">For more information about the related activities of the activity search results page in the BAM portal, a see [Related Activities](../core/related-activities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="09f1a-139">为使各计算机上的用户可以看到位于不同 BAM 数据库中的相关活动，您必须在所有 BAM 数据库之间实现双向分布式导航。</span><span class="sxs-lookup"><span data-stu-id="09f1a-139">For users on each computer to see related activities located in different BAM databases, you must enable two-way distributed navigation between all the BAM databases.</span></span>  
  
 <span data-ttu-id="09f1a-140">配置分布式导航时，如果在两个主导入数据库间启用了单向分布式导航，则导航时，不同的用户将看到不同的结果。</span><span class="sxs-lookup"><span data-stu-id="09f1a-140">If you enable one-way distributed navigation between two Primary Import databases when you configure distributed navigation, users will have an asymmetrical experience during the navigation.</span></span>  
  
 <span data-ttu-id="09f1a-141">结果可能是，用户将看到不同的活动；当用户深入到应显示相关实例的实例级数据时，却发现为空。</span><span class="sxs-lookup"><span data-stu-id="09f1a-141">The user experience will be such that the user will see the different activities; however, when the user drills into the instance-level data, the section where related instances are displayed will be empty.</span></span> <span data-ttu-id="09f1a-142">要解决此问题，则必须配置分布式导航路径，使其指向该用户的本地 BAM 门户服务器。</span><span class="sxs-lookup"><span data-stu-id="09f1a-142">To resolve this issue, you must configure the distributed navigation path back to the home BAM portal server for the user.</span></span>  
  
 <span data-ttu-id="09f1a-143">例如，请考虑以下情况：</span><span class="sxs-lookup"><span data-stu-id="09f1a-143">For example, consider the following scenario:</span></span>  
  
- <span data-ttu-id="09f1a-144">您的计算机 1 上有一个名为“采购订单”的活动，还有一个名为“SalesManager”的视图。</span><span class="sxs-lookup"><span data-stu-id="09f1a-144">You have Computer 1 on which you have an activity called Purchase Order and a view called SalesManager.</span></span>  
  
- <span data-ttu-id="09f1a-145">您的计算机 2 上有一个名为“发货订单”的活动，还有一个名为“SalesManager”的视图</span><span class="sxs-lookup"><span data-stu-id="09f1a-145">You have Computer 2 on which you have an activity called Shipping Order and a view called SalesManager</span></span>  
  
- <span data-ttu-id="09f1a-146">您向计算机 1 上的“采购订单”添加名为“PO_1”的活动</span><span class="sxs-lookup"><span data-stu-id="09f1a-146">You add an activity called PO_1 to Purchase Order on Computer 1</span></span>  
  
- <span data-ttu-id="09f1a-147">您向计算机 2 上的“发货订单”添加名为“SO_1”的活动</span><span class="sxs-lookup"><span data-stu-id="09f1a-147">You add an activity called SO_1 to Shipping Order on Computer 2</span></span>  
  
- <span data-ttu-id="09f1a-148">在计算机 2 上，您向“发货订单”添加“SO_1 对 PurchaseOrder PO_1 活动”这一关系</span><span class="sxs-lookup"><span data-stu-id="09f1a-148">On Computer 2 you add the relationship,  SO_1 to the PurchaseOrder PO_1 Activity on Shipping Order</span></span>  
  
- <span data-ttu-id="09f1a-149">当用户从计算机 1 深入到 SO_1 活动时，可看到 SO_1 活动</span><span class="sxs-lookup"><span data-stu-id="09f1a-149">When a user drills down into the SO_1 activity from Computer 1 the SO_1 activity is discoverable</span></span>  
  
- <span data-ttu-id="09f1a-150">如果用户从计算机 2 深入到 SO_1 时，却看不到 PO_1 活动</span><span class="sxs-lookup"><span data-stu-id="09f1a-150">If the user drills down the SO_1 on Computer 2, the PO_1 activity is not visible</span></span>  
  
  <span data-ttu-id="09f1a-151">要纠正这个问题，需要在计算机 1 上添加关系。</span><span class="sxs-lookup"><span data-stu-id="09f1a-151">To rectify this, you will need to add the relationship on Computer 1.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09f1a-152">本节内容</span><span class="sxs-lookup"><span data-stu-id="09f1a-152">In This Section</span></span>  
  
-   [<span data-ttu-id="09f1a-153">如何配置分布式活动之间的导航</span><span class="sxs-lookup"><span data-stu-id="09f1a-153">How to Configure Navigation Between Distributed Activities</span></span>](../core/how-to-configure-navigation-between-distributed-activities.md)  
  
## <a name="see-also"></a><span data-ttu-id="09f1a-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="09f1a-154">See Also</span></span>  
 [<span data-ttu-id="09f1a-155">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="09f1a-155">Managing BAM</span></span>](../core/managing-bam.md)