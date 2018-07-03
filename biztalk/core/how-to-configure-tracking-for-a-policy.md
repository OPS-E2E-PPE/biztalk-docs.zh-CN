---
title: 如何配置跟踪的策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, tracking
- HAT, policies
- managing [policies], tracking
- tracking, policies
- managing [policies], configuring
- policies, configuring
- configuring [HAT tracking], policies
- tracking, configuring
ms.assetid: f126e541-c183-4544-8b9d-ca07d2af303e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f92e8555c0d644411c165284dd734eb94e6569e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980406"
---
# <a name="how-to-configure-tracking-for-a-policy"></a><span data-ttu-id="55c10-102">如何配置跟踪的策略</span><span class="sxs-lookup"><span data-stu-id="55c10-102">How to Configure Tracking for a Policy</span></span>
<span data-ttu-id="55c10-103">本主题介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台为策略配置跟踪。</span><span class="sxs-lookup"><span data-stu-id="55c10-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administration console to configure tracking for a policy.</span></span> <span data-ttu-id="55c10-104">您可以选择相应的选项，以便在管理控制台上组中心页的查询视图中查看实例数据、条件结果、操作和议程更新。</span><span class="sxs-lookup"><span data-stu-id="55c10-104">You can select options to view instance data, results of conditions, actions, and agenda updates in the query views of the administration console Group Hub page.</span></span>  
  
 <span data-ttu-id="55c10-105">有关创建和使用查询的详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="55c10-105">For more information about creating and using queries, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span> <span data-ttu-id="55c10-106">有关消息和服务实例跟踪功能的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。</span><span class="sxs-lookup"><span data-stu-id="55c10-106">For more information about the message and service instance  tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="55c10-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="55c10-107">Prerequisites</span></span>  
 <span data-ttu-id="55c10-108">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="55c10-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="55c10-109">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="55c10-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-policy"></a><span data-ttu-id="55c10-110">为策略配置跟踪</span><span class="sxs-lookup"><span data-stu-id="55c10-110">To configure tracking for a policy</span></span>  
  
1. <span data-ttu-id="55c10-111">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="55c10-111">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="55c10-112">在控制台树中，展开要为其配置跟踪的策略所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="55c10-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure tracking for a policy.</span></span>  
  
3. <span data-ttu-id="55c10-113">单击**策略**，右键单击该策略，单击**属性**，然后单击**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="55c10-113">Click **Policies**, right-click the policy, click **Properties**, and then click **Tracking**.</span></span>  
  
4. <span data-ttu-id="55c10-114">下表中所述选择所需的跟踪选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="55c10-114">Select the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="55c10-115">使用此选项</span><span class="sxs-lookup"><span data-stu-id="55c10-115">Use this</span></span>|<span data-ttu-id="55c10-116">执行的操作</span><span class="sxs-lookup"><span data-stu-id="55c10-116">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="55c10-117">**快速活动**</span><span class="sxs-lookup"><span data-stu-id="55c10-117">**Fast activity**</span></span>|<span data-ttu-id="55c10-118">选中此复选框可跟踪对其运行该策略的实例数据。</span><span class="sxs-lookup"><span data-stu-id="55c10-118">Select this check box to track the instance data on which the policy operates.</span></span>|  
   |<span data-ttu-id="55c10-119">**条件评估**</span><span class="sxs-lookup"><span data-stu-id="55c10-119">**Condition evaluation**</span></span>|<span data-ttu-id="55c10-120">选中此复选框可跟踪所选策略中条件的真/假结果。</span><span class="sxs-lookup"><span data-stu-id="55c10-120">Select this check box to track the true/false results of conditions in the selected policy.</span></span>|  
   |<span data-ttu-id="55c10-121">**规则触发**</span><span class="sxs-lookup"><span data-stu-id="55c10-121">**Rule firings**</span></span>|<span data-ttu-id="55c10-122">选中此复选框可跟踪该策略最终触发的操作。</span><span class="sxs-lookup"><span data-stu-id="55c10-122">Select this check box to track the actions started as a result of the policy.</span></span>|  
   |<span data-ttu-id="55c10-123">**议程更新**</span><span class="sxs-lookup"><span data-stu-id="55c10-123">**Agenda updates**</span></span>|<span data-ttu-id="55c10-124">选中此复选框可跟踪议程更新。</span><span class="sxs-lookup"><span data-stu-id="55c10-124">Select this check box to track updates to the agenda.</span></span> <span data-ttu-id="55c10-125">议程包含一系列值为“True”并需要触发的操作。</span><span class="sxs-lookup"><span data-stu-id="55c10-125">The agenda contains a list of actions that are "true" and need to fire.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55c10-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="55c10-126">See Also</span></span>  
 [<span data-ttu-id="55c10-127">管理策略</span><span class="sxs-lookup"><span data-stu-id="55c10-127">Managing Policies</span></span>](../core/managing-policies.md)