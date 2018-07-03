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
ms.openlocfilehash: 3770e871e7be022ff7f4597b8d3eb4d8f307cc37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966510"
---
# <a name="how-to-search-for-tracked-service-instances"></a><span data-ttu-id="3d479-102">如何搜索跟踪的服务实例</span><span class="sxs-lookup"><span data-stu-id="3d479-102">How to Search for Tracked Service Instances</span></span>
<span data-ttu-id="3d479-103">可以使用**查询**选项卡中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中搜索所有跟踪的服务实例。</span><span class="sxs-lookup"><span data-stu-id="3d479-103">You can use the **Query** tab in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to search for all tracked service instances.</span></span> <span data-ttu-id="3d479-104">若要查找服务实例，您可以搜索程序集的名称和版本、生存期的开始时间和结束时间、服务类的名称或实例 ID、主机名称、错误代码和服务实例的状态。</span><span class="sxs-lookup"><span data-stu-id="3d479-104">To locate service instances, you can search on the name and version of the assembly, the start and end times of its lifetime, the name or instance ID of the service class, host name, error code, and the state of the service instance.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="3d479-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="3d479-105">Prerequisites</span></span>  
 <span data-ttu-id="3d479-106">若要执行此过程，必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="3d479-106">To perform this procedure, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group.</span></span>  

### <a name="to-search-for-tracked-service-instances"></a><span data-ttu-id="3d479-107">搜索跟踪的服务实例</span><span class="sxs-lookup"><span data-stu-id="3d479-107">To search for tracked service instances</span></span>  

1. <span data-ttu-id="3d479-108">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3d479-108">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

2. <span data-ttu-id="3d479-109">在控制台树中，展开**BizTalk Server 管理**，然后单击 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="3d479-109">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  

3. <span data-ttu-id="3d479-110">在详细信息窗格中，单击**新查询**选项卡。</span><span class="sxs-lookup"><span data-stu-id="3d479-110">In the details pane, click the **New Query** tab.</span></span>  

4. <span data-ttu-id="3d479-111">在中**查询表达式**组中，在**值**列中，选择**跟踪的服务实例**从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="3d479-111">In the **Query Expression** group, in the **Value** column, select **Tracked Service Instances** from the drop-down list box.</span></span>  

5. <span data-ttu-id="3d479-112">在中**字段名**列，星号旁边的空下拉列表框中 (\* *\\* \* \*)，选择一个或多项操作：</span><span class="sxs-lookup"><span data-stu-id="3d479-112">In the **Field Name** column, in the empty drop-down list box next to the asterisk (\*\*\\*\*\*), select one or more of the following:</span></span>  


   |          <span data-ttu-id="3d479-113">项</span><span class="sxs-lookup"><span data-stu-id="3d479-113">Item</span></span>           |                     <span data-ttu-id="3d479-114">Description</span><span class="sxs-lookup"><span data-stu-id="3d479-114">Description</span></span>                      |
   |-------------------------|------------------------------------------------------|
   |    <span data-ttu-id="3d479-115">**程序集名称**</span><span class="sxs-lookup"><span data-stu-id="3d479-115">**Assembly Name**</span></span>    |    <span data-ttu-id="3d479-116">服务实例的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="3d479-116">Name of the assembly for the service instance.</span></span>    |
   |  <span data-ttu-id="3d479-117">**程序集版本**</span><span class="sxs-lookup"><span data-stu-id="3d479-117">**Assembly Version**</span></span>   |           <span data-ttu-id="3d479-118">服务实例的版本。</span><span class="sxs-lookup"><span data-stu-id="3d479-118">Version of the service instance.</span></span>           |
   |      <span data-ttu-id="3d479-119">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="3d479-119">**End Time**</span></span>       |          <span data-ttu-id="3d479-120">服务实例的结束时间。</span><span class="sxs-lookup"><span data-stu-id="3d479-120">End time of the service instance.</span></span>           |
   |     <span data-ttu-id="3d479-121">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="3d479-121">**Error Code**</span></span>      | <span data-ttu-id="3d479-122">与服务实例相关联的任何错误代码。</span><span class="sxs-lookup"><span data-stu-id="3d479-122">Any error code associated with the service instance.</span></span> |
   |      <span data-ttu-id="3d479-123">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="3d479-123">**Host Name**</span></span>      |        <span data-ttu-id="3d479-124">服务实例的主机名称。</span><span class="sxs-lookup"><span data-stu-id="3d479-124">The host name of the service instance.</span></span>        |
   |   <span data-ttu-id="3d479-125">**最大匹配数**</span><span class="sxs-lookup"><span data-stu-id="3d479-125">**Maximum Matches**</span></span>   |          <span data-ttu-id="3d479-126">要显示的匹配数。</span><span class="sxs-lookup"><span data-stu-id="3d479-126">The number of matches to display.</span></span>           |
   |    <span data-ttu-id="3d479-127">**服务类**</span><span class="sxs-lookup"><span data-stu-id="3d479-127">**Service Class**</span></span>    |          <span data-ttu-id="3d479-128">服务实例的类别。</span><span class="sxs-lookup"><span data-stu-id="3d479-128">The class of the service instance.</span></span>          |
   | <span data-ttu-id="3d479-129">**服务实例 ID**</span><span class="sxs-lookup"><span data-stu-id="3d479-129">**Service Instance ID**</span></span> |               <span data-ttu-id="3d479-130">服务实例 ID。</span><span class="sxs-lookup"><span data-stu-id="3d479-130">The service instance ID.</span></span>               |
   |    <span data-ttu-id="3d479-131">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="3d479-131">**Service Name**</span></span>     |          <span data-ttu-id="3d479-132">服务实例的名称。</span><span class="sxs-lookup"><span data-stu-id="3d479-132">The name of the service instance.</span></span>           |
   |     <span data-ttu-id="3d479-133">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="3d479-133">**Start Time**</span></span>      |       <span data-ttu-id="3d479-134">服务实例的开始时间。</span><span class="sxs-lookup"><span data-stu-id="3d479-134">The start time of the service instance.</span></span>        |
   |        <span data-ttu-id="3d479-135">**State**</span><span class="sxs-lookup"><span data-stu-id="3d479-135">**State**</span></span>        |          <span data-ttu-id="3d479-136">服务实例的状态。</span><span class="sxs-lookup"><span data-stu-id="3d479-136">The state of the service instance.</span></span>          |


6. <span data-ttu-id="3d479-137">完成**值**根据需要将所选内容中所做的列**字段名**列。</span><span class="sxs-lookup"><span data-stu-id="3d479-137">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  

7. <span data-ttu-id="3d479-138">继续将其他行添加到作为相应的查询，通过完成**字段名**，**运算符**，并**值**列，并单击**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="3d479-138">Continue adding additional lines to the query as appropriate by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3d479-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d479-139">See Also</span></span>  
 [<span data-ttu-id="3d479-140">使用管理控制台的“查询”选项卡</span><span class="sxs-lookup"><span data-stu-id="3d479-140">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)