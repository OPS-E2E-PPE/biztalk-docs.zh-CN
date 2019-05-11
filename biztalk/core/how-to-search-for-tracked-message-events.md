---
title: 如何搜索跟踪的消息事件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18df4cf7-c307-4175-926c-9be9f30b29ed
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fabfa18a4dda37d1d2e59361d74b4ecc147a1703
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334785"
---
# <a name="how-to-search-for-tracked-message-events"></a><span data-ttu-id="46099-102">跟踪的消息事件</span><span class="sxs-lookup"><span data-stu-id="46099-102">How to Search for Tracked Message Events</span></span>
<span data-ttu-id="46099-103">可以使用**新查询**选项卡中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来搜索跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="46099-103">You can use the **New Query** tab in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to search for tracked message events.</span></span>  <span data-ttu-id="46099-104">从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台可以启用消息正文和消息属性跟踪。</span><span class="sxs-lookup"><span data-stu-id="46099-104">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console you can enable message body and message property tracking.</span></span> <span data-ttu-id="46099-105">在查询结果窗格可以查看有关消息事件，包括架构信息、 事件类型、 服务实例 ID 和所生成消息的所有升级的属性的信息。</span><span class="sxs-lookup"><span data-stu-id="46099-105">In the Query Results pane you can view information about the message event, including schema information, event type, service instance ID, and all the promoted properties for the generated message.</span></span>  

> [!NOTE]
>  <span data-ttu-id="46099-106">若要查看实际消息正文，可以调用**消息的详细信息**上下文菜单，然后转到"消息部分"选项卡，或保存该消息从结果列表中查看通过调用**将保存到文件**从上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="46099-106">In order to view the actual message body, you can invoke the **Message Details** context menu and go to the “Message Parts” tab, or save the message from the result list view by invoking **Save to File** from the context menu.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="46099-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="46099-107">Prerequisites</span></span>  
 <span data-ttu-id="46099-108">若要执行此过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Operators 组。</span><span class="sxs-lookup"><span data-stu-id="46099-108">To perform this procedure, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group.</span></span>  

### <a name="to-search-for-tracked-message-items"></a><span data-ttu-id="46099-109">若要搜索跟踪的消息项</span><span class="sxs-lookup"><span data-stu-id="46099-109">To search for tracked message items</span></span>  

1. <span data-ttu-id="46099-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="46099-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

2. <span data-ttu-id="46099-111">在控制台树中，展开**BizTalk Server 管理**，然后单击 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="46099-111">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  

3. <span data-ttu-id="46099-112">在详细信息窗格中，单击**新查询**选项卡。</span><span class="sxs-lookup"><span data-stu-id="46099-112">In the details pane, click the **New Query** tab.</span></span>  

4. <span data-ttu-id="46099-113">在中**查询表达式**组中，在**值**列中，选择**跟踪的消息事件**从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="46099-113">In the **Query Expression** group, in the **Value** column, select **Tracked Message Events** from the drop-down list box.</span></span>  

5. <span data-ttu-id="46099-114">在中**字段名**列，星号旁边的空下拉列表框中 (\* *\\* \* \*)，选择一个或多项操作：</span><span class="sxs-lookup"><span data-stu-id="46099-114">In the **Field Name** column, in the empty drop-down list box next to the asterisk (\*\*\\*\*\*), select one or more of the following:</span></span>  


   |                        <span data-ttu-id="46099-115">项</span><span class="sxs-lookup"><span data-stu-id="46099-115">Item</span></span>                         |                                              <span data-ttu-id="46099-116">Description</span><span class="sxs-lookup"><span data-stu-id="46099-116">Description</span></span>                                               |
   |-----------------------------------------------------|--------------------------------------------------------------------------------------------------------|
   |                  <span data-ttu-id="46099-117">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="46099-117">**Creation Time**</span></span>                  |                                   <span data-ttu-id="46099-118">创建消息的时间。</span><span class="sxs-lookup"><span data-stu-id="46099-118">The time the message was created.</span></span>                                    |
   |                   <span data-ttu-id="46099-119">**事件类型**</span><span class="sxs-lookup"><span data-stu-id="46099-119">**Event Type**</span></span>                    |                                    <span data-ttu-id="46099-120">被跟踪的事件类型。</span><span class="sxs-lookup"><span data-stu-id="46099-120">The type of event being tracked.</span></span>                                    |
   |                 <span data-ttu-id="46099-121">**最大匹配数**</span><span class="sxs-lookup"><span data-stu-id="46099-121">**Maximum Matches**</span></span>                 |                                   <span data-ttu-id="46099-122">若要显示的匹配项的数目。</span><span class="sxs-lookup"><span data-stu-id="46099-122">The number of matches to display.</span></span>                                    |
   |                      <span data-ttu-id="46099-123">**参与方**</span><span class="sxs-lookup"><span data-stu-id="46099-123">**Party**</span></span>                      |                                <span data-ttu-id="46099-124">组织发送该消息。</span><span class="sxs-lookup"><span data-stu-id="46099-124">The organization that sent the message.</span></span>                                 |
   |                      <span data-ttu-id="46099-125">**端口**</span><span class="sxs-lookup"><span data-stu-id="46099-125">**Port**</span></span>                       |                                 <span data-ttu-id="46099-126">用来处理该消息的端口。</span><span class="sxs-lookup"><span data-stu-id="46099-126">The port used to process the message.</span></span>                                  |
   |                   <span data-ttu-id="46099-127">**架构名称**</span><span class="sxs-lookup"><span data-stu-id="46099-127">**Schema Name**</span></span>                   |                                <span data-ttu-id="46099-128">消息所用的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="46099-128">Name of the schema used by the message.</span></span>                                 |
   |               <span data-ttu-id="46099-129">**服务实例 ID**</span><span class="sxs-lookup"><span data-stu-id="46099-129">**Service Instance ID**</span></span>               |                             <span data-ttu-id="46099-130">用于消息的服务实例 ID。</span><span class="sxs-lookup"><span data-stu-id="46099-130">The service instance ID used for the message.</span></span>                              |
   |                       <span data-ttu-id="46099-131">**URI**</span><span class="sxs-lookup"><span data-stu-id="46099-131">**URI**</span></span>                       |                                     <span data-ttu-id="46099-132">用于消息的 URI。</span><span class="sxs-lookup"><span data-stu-id="46099-132">The URI used for the message.</span></span>                                      |
   | <span data-ttu-id="46099-133">**\<选择跟踪的属性的架构名称\>**</span><span class="sxs-lookup"><span data-stu-id="46099-133">**\<Select a Schema Name for Tracked Properties\>**</span></span> | <span data-ttu-id="46099-134">当你选择的架构时，有资格在查询中使用该架构中的任何升级的属性。</span><span class="sxs-lookup"><span data-stu-id="46099-134">When you select a schema, any promoted properties in that schema are eligible to be used in the query.</span></span> |


6. <span data-ttu-id="46099-135">完成**值**根据需要将所选内容中所做的列**字段名**列。</span><span class="sxs-lookup"><span data-stu-id="46099-135">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  

7. <span data-ttu-id="46099-136">继续将其他行添加到作为相应的查询，通过完成**字段名**，**运算符**，并**值**列，并单击**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="46099-136">Continue adding additional lines to the query as appropriate by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="46099-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="46099-137">See Also</span></span>  
 [<span data-ttu-id="46099-138">使用管理控制台的“查询”选项卡</span><span class="sxs-lookup"><span data-stu-id="46099-138">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)