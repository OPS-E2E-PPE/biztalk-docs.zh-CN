---
title: "如何跟踪的消息事件搜索 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18df4cf7-c307-4175-926c-9be9f30b29ed
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6a3597d0d68dbd79de6c23e7b6d4b222b9c8376
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-search-for-tracked-message-events"></a><span data-ttu-id="d3ff5-102">如何搜索跟踪的消息事件</span><span class="sxs-lookup"><span data-stu-id="d3ff5-102">How to Search for Tracked Message Events</span></span>
<span data-ttu-id="d3ff5-103">你可以使用**新查询**选项卡中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来搜索跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-103">You can use the **New Query** tab in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to search for tracked message events.</span></span>  <span data-ttu-id="d3ff5-104">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，您可以启用消息正文和消息属性跟踪。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-104">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console you can enable message body and message property tracking.</span></span> <span data-ttu-id="d3ff5-105">在“查询结果”窗格中，您可以查看有关消息事件的信息（包括架构信息、事件类型、服务实例 ID，以及生成消息的所有升级属性）。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-105">In the Query Results pane you can view information about the message event, including schema information, event type, service instance ID, and all the promoted properties for the generated message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3ff5-106">若要查看实际消息正文，你可以调用**消息详细信息**上下文菜单，然后转到"消息部分"选项卡，或保存该消息从结果列表查看通过调用**将保存到文件**从上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-106">In order to view the actual message body, you can invoke the **Message Details** context menu and go to the “Message Parts” tab, or save the message from the result list view by invoking **Save to File** from the context menu.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d3ff5-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="d3ff5-107">Prerequisites</span></span>  
 <span data-ttu-id="d3ff5-108">若要执行此过程，必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-108">To perform this procedure, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group.</span></span>  
  
### <a name="to-search-for-tracked-message-items"></a><span data-ttu-id="d3ff5-109">搜索跟踪的消息项</span><span class="sxs-lookup"><span data-stu-id="d3ff5-109">To search for tracked message items</span></span>  
  
1.  <span data-ttu-id="d3ff5-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="d3ff5-111">在控制台树中，展开**BizTalk Server 管理**，然后单击 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-111">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="d3ff5-112">在详细信息窗格中，单击**新查询**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-112">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="d3ff5-113">在**查询表达式**组中，在**值**列中，选择**跟踪消息事件**从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-113">In the **Query Expression** group, in the **Value** column, select **Tracked Message Events** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="d3ff5-114">在**字段名称**旁边星号的空下拉列表框中的列，(**\***)，选择一个或多个以下：</span><span class="sxs-lookup"><span data-stu-id="d3ff5-114">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="d3ff5-115">项</span><span class="sxs-lookup"><span data-stu-id="d3ff5-115">Item</span></span>|<span data-ttu-id="d3ff5-116">Description</span><span class="sxs-lookup"><span data-stu-id="d3ff5-116">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="d3ff5-117">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="d3ff5-117">**Creation Time**</span></span>|<span data-ttu-id="d3ff5-118">创建消息的时间。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-118">The time the message was created.</span></span>|  
    |<span data-ttu-id="d3ff5-119">**事件类型**</span><span class="sxs-lookup"><span data-stu-id="d3ff5-119">**Event Type**</span></span>|<span data-ttu-id="d3ff5-120">被跟踪的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-120">The type of event being tracked.</span></span>|  
    |<span data-ttu-id="d3ff5-121">**最大匹配数**</span><span class="sxs-lookup"><span data-stu-id="d3ff5-121">**Maximum Matches**</span></span>|<span data-ttu-id="d3ff5-122">要显示的匹配数。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-122">The number of matches to display.</span></span>|  
    |<span data-ttu-id="d3ff5-123">**方**</span><span class="sxs-lookup"><span data-stu-id="d3ff5-123">**Party**</span></span>|<span data-ttu-id="d3ff5-124">发送消息的组织。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-124">The organization that sent the message.</span></span>|  
    |<span data-ttu-id="d3ff5-125">**端口**</span><span class="sxs-lookup"><span data-stu-id="d3ff5-125">**Port**</span></span>|<span data-ttu-id="d3ff5-126">用于处理消息的端口。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-126">The port used to process the message.</span></span>|  
    |<span data-ttu-id="d3ff5-127">**架构名称**</span><span class="sxs-lookup"><span data-stu-id="d3ff5-127">**Schema Name**</span></span>|<span data-ttu-id="d3ff5-128">消息所用的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-128">Name of the schema used by the message.</span></span>|  
    |<span data-ttu-id="d3ff5-129">**服务实例 ID**</span><span class="sxs-lookup"><span data-stu-id="d3ff5-129">**Service Instance ID**</span></span>|<span data-ttu-id="d3ff5-130">用于消息的服务实例 ID。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-130">The service instance ID used for the message.</span></span>|  
    |<span data-ttu-id="d3ff5-131">**URI**</span><span class="sxs-lookup"><span data-stu-id="d3ff5-131">**URI**</span></span>|<span data-ttu-id="d3ff5-132">用于消息的 URI。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-132">The URI used for the message.</span></span>|  
    |<span data-ttu-id="d3ff5-133">**\<选择跟踪的属性的架构名称\>**</span><span class="sxs-lookup"><span data-stu-id="d3ff5-133">**\<Select a Schema Name for Tracked Properties\>**</span></span>|<span data-ttu-id="d3ff5-134">当选择架构时，该架构中的任何升级属性都有资格用在查询中。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-134">When you select a schema, any promoted properties in that schema are eligible to be used in the query.</span></span>|  
  
6.  <span data-ttu-id="d3ff5-135">完成**值**列的适合于所选内容所做中**字段名称**列。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-135">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="d3ff5-136">继续向根据查询中添加更多的行，通过完成**字段名称**，**运算符**，和**值**columns 和 then click**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-136">Continue adding additional lines to the query as appropriate by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ff5-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3ff5-137">See Also</span></span>  
 [<span data-ttu-id="d3ff5-138">使用管理控制台的“查询”选项卡</span><span class="sxs-lookup"><span data-stu-id="d3ff5-138">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)