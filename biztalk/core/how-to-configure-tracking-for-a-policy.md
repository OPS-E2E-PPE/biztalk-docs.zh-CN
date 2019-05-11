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
ms.openlocfilehash: b6b7b4d2a5b653255398b938431a2ac26c74bcf1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340202"
---
# <a name="how-to-configure-tracking-for-a-policy"></a><span data-ttu-id="53fb0-102">如何配置跟踪的策略</span><span class="sxs-lookup"><span data-stu-id="53fb0-102">How to Configure Tracking for a Policy</span></span>
<span data-ttu-id="53fb0-103">本主题介绍如何使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台配置跟踪的策略。</span><span class="sxs-lookup"><span data-stu-id="53fb0-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administration console to configure tracking for a policy.</span></span> <span data-ttu-id="53fb0-104">你可以选择选项以查看实例数据、 条件、 操作和议程更新管理控制台上组中心页的查询视图中的结果。</span><span class="sxs-lookup"><span data-stu-id="53fb0-104">You can select options to view instance data, results of conditions, actions, and agenda updates in the query views of the administration console Group Hub page.</span></span>  
  
 <span data-ttu-id="53fb0-105">有关创建和使用查询的详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="53fb0-105">For more information about creating and using queries, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span> <span data-ttu-id="53fb0-106">有关消息和服务实例跟踪功能的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。</span><span class="sxs-lookup"><span data-stu-id="53fb0-106">For more information about the message and service instance  tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="53fb0-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="53fb0-107">Prerequisites</span></span>  
 <span data-ttu-id="53fb0-108">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="53fb0-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="53fb0-109">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="53fb0-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-policy"></a><span data-ttu-id="53fb0-110">若要配置跟踪的策略</span><span class="sxs-lookup"><span data-stu-id="53fb0-110">To configure tracking for a policy</span></span>  
  
1. <span data-ttu-id="53fb0-111">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="53fb0-111">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="53fb0-112">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序要为其配置跟踪的策略。</span><span class="sxs-lookup"><span data-stu-id="53fb0-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure tracking for a policy.</span></span>  
  
3. <span data-ttu-id="53fb0-113">单击**策略**，右键单击该策略，单击**属性**，然后单击**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="53fb0-113">Click **Policies**, right-click the policy, click **Properties**, and then click **Tracking**.</span></span>  
  
4. <span data-ttu-id="53fb0-114">下表中所述选择所需的跟踪选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="53fb0-114">Select the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="53fb0-115">使用此选项</span><span class="sxs-lookup"><span data-stu-id="53fb0-115">Use this</span></span>|<span data-ttu-id="53fb0-116">执行的操作</span><span class="sxs-lookup"><span data-stu-id="53fb0-116">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="53fb0-117">**快速活动**</span><span class="sxs-lookup"><span data-stu-id="53fb0-117">**Fast activity**</span></span>|<span data-ttu-id="53fb0-118">选中此复选框可跟踪运行该策略的实例数据。</span><span class="sxs-lookup"><span data-stu-id="53fb0-118">Select this check box to track the instance data on which the policy operates.</span></span>|  
   |<span data-ttu-id="53fb0-119">**条件评估**</span><span class="sxs-lookup"><span data-stu-id="53fb0-119">**Condition evaluation**</span></span>|<span data-ttu-id="53fb0-120">选中此复选框可跟踪所选策略中条件的真/假结果。</span><span class="sxs-lookup"><span data-stu-id="53fb0-120">Select this check box to track the true/false results of conditions in the selected policy.</span></span>|  
   |<span data-ttu-id="53fb0-121">**规则触发**</span><span class="sxs-lookup"><span data-stu-id="53fb0-121">**Rule firings**</span></span>|<span data-ttu-id="53fb0-122">选择此复选框可跟踪该策略最终触发的操作。</span><span class="sxs-lookup"><span data-stu-id="53fb0-122">Select this check box to track the actions started as a result of the policy.</span></span>|  
   |<span data-ttu-id="53fb0-123">**议程更新**</span><span class="sxs-lookup"><span data-stu-id="53fb0-123">**Agenda updates**</span></span>|<span data-ttu-id="53fb0-124">选择此复选框可跟踪议程更新。</span><span class="sxs-lookup"><span data-stu-id="53fb0-124">Select this check box to track updates to the agenda.</span></span> <span data-ttu-id="53fb0-125">议程包含一系列为"true"，并需要触发的操作。</span><span class="sxs-lookup"><span data-stu-id="53fb0-125">The agenda contains a list of actions that are "true" and need to fire.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53fb0-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="53fb0-126">See Also</span></span>  
 [<span data-ttu-id="53fb0-127">管理策略</span><span class="sxs-lookup"><span data-stu-id="53fb0-127">Managing Policies</span></span>](../core/managing-policies.md)