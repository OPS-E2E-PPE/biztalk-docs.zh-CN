---
title: 如何搜索跟踪的服务实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6337df9-8c2e-4d4a-a64b-cc040f83bd91
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ff8801c272859e6a138fcb1e4e618226de10a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383980"
---
# <a name="how-to-search-for-tracked-service-instances"></a><span data-ttu-id="cd448-102">如何搜索跟踪的服务实例</span><span class="sxs-lookup"><span data-stu-id="cd448-102">How to Search for Tracked Service Instances</span></span>
<span data-ttu-id="cd448-103">可以使用**查询**选项卡中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中搜索所有跟踪的服务实例。</span><span class="sxs-lookup"><span data-stu-id="cd448-103">You can use the **Query** tab in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to search for all tracked service instances.</span></span> <span data-ttu-id="cd448-104">若要查找服务实例，可以搜索名称和版本的程序集，其生存期、 名称或实例 ID 的服务类、 主机名、 错误代码和服务实例的状态的开始和结束时间。</span><span class="sxs-lookup"><span data-stu-id="cd448-104">To locate service instances, you can search on the name and version of the assembly, the start and end times of its lifetime, the name or instance ID of the service class, host name, error code, and the state of the service instance.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="cd448-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="cd448-105">Prerequisites</span></span>  
 <span data-ttu-id="cd448-106">若要执行此过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Operators 组。</span><span class="sxs-lookup"><span data-stu-id="cd448-106">To perform this procedure, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group.</span></span>  

### <a name="to-search-for-tracked-service-instances"></a><span data-ttu-id="cd448-107">若要搜索跟踪的服务实例</span><span class="sxs-lookup"><span data-stu-id="cd448-107">To search for tracked service instances</span></span>  

1. <span data-ttu-id="cd448-108">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cd448-108">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

2. <span data-ttu-id="cd448-109">在控制台树中，展开**BizTalk Server 管理**，然后单击 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="cd448-109">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  

3. <span data-ttu-id="cd448-110">在详细信息窗格中，单击**新查询**选项卡。</span><span class="sxs-lookup"><span data-stu-id="cd448-110">In the details pane, click the **New Query** tab.</span></span>  

4. <span data-ttu-id="cd448-111">在中**查询表达式**组中，在**值**列中，选择**跟踪的服务实例**从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="cd448-111">In the **Query Expression** group, in the **Value** column, select **Tracked Service Instances** from the drop-down list box.</span></span>  

5. <span data-ttu-id="cd448-112">在中**字段名**列，星号旁边的空下拉列表框中 (\* *\\* \* \*)，选择一个或多项操作：</span><span class="sxs-lookup"><span data-stu-id="cd448-112">In the **Field Name** column, in the empty drop-down list box next to the asterisk (\*\*\\*\*\*), select one or more of the following:</span></span>  


   |          <span data-ttu-id="cd448-113">项</span><span class="sxs-lookup"><span data-stu-id="cd448-113">Item</span></span>           |                     <span data-ttu-id="cd448-114">Description</span><span class="sxs-lookup"><span data-stu-id="cd448-114">Description</span></span>                      |
   |-------------------------|------------------------------------------------------|
   |    <span data-ttu-id="cd448-115">**程序集名称**</span><span class="sxs-lookup"><span data-stu-id="cd448-115">**Assembly Name**</span></span>    |    <span data-ttu-id="cd448-116">服务实例的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="cd448-116">Name of the assembly for the service instance.</span></span>    |
   |  <span data-ttu-id="cd448-117">**程序集版本**</span><span class="sxs-lookup"><span data-stu-id="cd448-117">**Assembly Version**</span></span>   |           <span data-ttu-id="cd448-118">服务实例的版本。</span><span class="sxs-lookup"><span data-stu-id="cd448-118">Version of the service instance.</span></span>           |
   |      <span data-ttu-id="cd448-119">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="cd448-119">**End Time**</span></span>       |          <span data-ttu-id="cd448-120">服务实例的结束时间。</span><span class="sxs-lookup"><span data-stu-id="cd448-120">End time of the service instance.</span></span>           |
   |     <span data-ttu-id="cd448-121">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="cd448-121">**Error Code**</span></span>      | <span data-ttu-id="cd448-122">与服务实例相关联的任何错误代码。</span><span class="sxs-lookup"><span data-stu-id="cd448-122">Any error code associated with the service instance.</span></span> |
   |      <span data-ttu-id="cd448-123">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="cd448-123">**Host Name**</span></span>      |        <span data-ttu-id="cd448-124">服务实例的主机名。</span><span class="sxs-lookup"><span data-stu-id="cd448-124">The host name of the service instance.</span></span>        |
   |   <span data-ttu-id="cd448-125">**最大匹配数**</span><span class="sxs-lookup"><span data-stu-id="cd448-125">**Maximum Matches**</span></span>   |          <span data-ttu-id="cd448-126">若要显示的匹配项的数目。</span><span class="sxs-lookup"><span data-stu-id="cd448-126">The number of matches to display.</span></span>           |
   |    <span data-ttu-id="cd448-127">**服务类**</span><span class="sxs-lookup"><span data-stu-id="cd448-127">**Service Class**</span></span>    |          <span data-ttu-id="cd448-128">服务实例的类。</span><span class="sxs-lookup"><span data-stu-id="cd448-128">The class of the service instance.</span></span>          |
   | <span data-ttu-id="cd448-129">**服务实例 ID**</span><span class="sxs-lookup"><span data-stu-id="cd448-129">**Service Instance ID**</span></span> |               <span data-ttu-id="cd448-130">服务实例 id。</span><span class="sxs-lookup"><span data-stu-id="cd448-130">The service instance ID.</span></span>               |
   |    <span data-ttu-id="cd448-131">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="cd448-131">**Service Name**</span></span>     |          <span data-ttu-id="cd448-132">服务实例的名称。</span><span class="sxs-lookup"><span data-stu-id="cd448-132">The name of the service instance.</span></span>           |
   |     <span data-ttu-id="cd448-133">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="cd448-133">**Start Time**</span></span>      |       <span data-ttu-id="cd448-134">服务实例的开始时间。</span><span class="sxs-lookup"><span data-stu-id="cd448-134">The start time of the service instance.</span></span>        |
   |        <span data-ttu-id="cd448-135">**状态**</span><span class="sxs-lookup"><span data-stu-id="cd448-135">**State**</span></span>        |          <span data-ttu-id="cd448-136">服务实例的状态。</span><span class="sxs-lookup"><span data-stu-id="cd448-136">The state of the service instance.</span></span>          |


6. <span data-ttu-id="cd448-137">完成**值**根据需要将所选内容中所做的列**字段名**列。</span><span class="sxs-lookup"><span data-stu-id="cd448-137">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  

7. <span data-ttu-id="cd448-138">继续将其他行添加到作为相应的查询，通过完成**字段名**，**运算符**，并**值**列，并单击**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="cd448-138">Continue adding additional lines to the query as appropriate by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="cd448-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd448-139">See Also</span></span>  
 [<span data-ttu-id="cd448-140">使用管理控制台的“查询”选项卡</span><span class="sxs-lookup"><span data-stu-id="cd448-140">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)