---
title: "如何搜索订阅 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Query tab [Administration Console], subscriptions
- Query tab [Administration Console], searching
- subscriptions, viewing
- subscriptions, searching
ms.assetid: 95f8fd20-2750-412b-a67b-18976e7706e2
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1830a4c1dddfa3dcfc2a1177b69410dd8ee0ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-subscriptions"></a><span data-ttu-id="54bad-102">如何搜索订阅</span><span class="sxs-lookup"><span data-stu-id="54bad-102">How to Search for Subscriptions</span></span>
<span data-ttu-id="54bad-103">你可以使用**查询**在 BizTalk Server 管理控制台中以搜索订阅的选项卡。</span><span class="sxs-lookup"><span data-stu-id="54bad-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for subscriptions.</span></span> <span data-ttu-id="54bad-104">当希望查看系统中定义的所有订阅时，这就非常有用。</span><span class="sxs-lookup"><span data-stu-id="54bad-104">This is useful when you want to review all of the subscriptions defined in the system.</span></span> <span data-ttu-id="54bad-105">在排除路由故障时，您可以查看是不是由于某些订阅未正确设置而导致了路由故障。</span><span class="sxs-lookup"><span data-stu-id="54bad-105">When troubleshooting routing failures, you can review subscriptions to see if any of them are improperly configured, thereby causing the routing failure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="54bad-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="54bad-106">Prerequisites</span></span>  
 <span data-ttu-id="54bad-107">若要执行此过程，则必须以 BizTalk Server Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="54bad-107">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  
  
### <a name="to-search-for-subscriptions"></a><span data-ttu-id="54bad-108">搜索订阅</span><span class="sxs-lookup"><span data-stu-id="54bad-108">To search for subscriptions</span></span>  
  
1.  <span data-ttu-id="54bad-109">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="54bad-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="54bad-110">在控制台树中，展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”，然后单击“BizTalk 组”。</span><span class="sxs-lookup"><span data-stu-id="54bad-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="54bad-111">在详细信息窗格中，单击**新查询**选项卡。</span><span class="sxs-lookup"><span data-stu-id="54bad-111">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="54bad-112">在**查询表达式**组中，在**值**列中，选择**订阅**从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="54bad-112">In the **Query Expression** group, in the **Value** column, select **Subscriptions** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="54bad-113">在**字段名称**旁边星号的空下拉列表框中的列，(**\***)，选择一个或多个以下：</span><span class="sxs-lookup"><span data-stu-id="54bad-113">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="54bad-114">项</span><span class="sxs-lookup"><span data-stu-id="54bad-114">Item</span></span>|<span data-ttu-id="54bad-115">Description</span><span class="sxs-lookup"><span data-stu-id="54bad-115">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="54bad-116">**最大匹配数**</span><span class="sxs-lookup"><span data-stu-id="54bad-116">**Maximum Matches**</span></span>|<span data-ttu-id="54bad-117">要显示的匹配数。</span><span class="sxs-lookup"><span data-stu-id="54bad-117">The number of matches to display.</span></span>|  
    |<span data-ttu-id="54bad-118">**服务实例 ID**</span><span class="sxs-lookup"><span data-stu-id="54bad-118">**Service Instance ID**</span></span>|<span data-ttu-id="54bad-119">您可以按服务实例 ID 对订阅进行筛选。</span><span class="sxs-lookup"><span data-stu-id="54bad-119">You can filter subscriptions by service instance ID.</span></span>|  
    |<span data-ttu-id="54bad-120">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="54bad-120">**Service Name**</span></span>|<span data-ttu-id="54bad-121">您可以按服务名对订阅进行筛选。</span><span class="sxs-lookup"><span data-stu-id="54bad-121">You can filter subscriptions by service name.</span></span>|  
    |<span data-ttu-id="54bad-122">**订阅类型**</span><span class="sxs-lookup"><span data-stu-id="54bad-122">**Subscription Type**</span></span>|<span data-ttu-id="54bad-123">您可以按“激活订阅”或“实例订阅”对订阅进行筛选。</span><span class="sxs-lookup"><span data-stu-id="54bad-123">You can filter subscriptions by Activation Subscription or Instance Subscription.</span></span>|  
  
6.  <span data-ttu-id="54bad-124">完成**值**列的适合于所选内容所做中**字段名称**列。</span><span class="sxs-lookup"><span data-stu-id="54bad-124">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="54bad-125">继续向视情况而定查询添加更多的行，通过完成**字段名称**，**运算符**，和**值**columns 和 then click**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="54bad-125">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54bad-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54bad-126">See Also</span></span>  
 [<span data-ttu-id="54bad-127">使用管理控制台的查询选项卡</span><span class="sxs-lookup"><span data-stu-id="54bad-127">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)