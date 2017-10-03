---
title: "配置 EDI 和 AS2 状态报告 |Microsoft 文档"
description: "创建 EDI 或 AS2 状态报告查询表达式中，并选择要在 BizTalk Server 中的报表中显示的数据"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6490864d-f1e6-4932-aefb-c332a595aad7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 833e3c6c26cdac57d7cc57d828b66a66b9eb37f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-an-edi-and-as2-status-report"></a><span data-ttu-id="9851b-103">配置 EDI 和 AS2 状态报表</span><span class="sxs-lookup"><span data-stu-id="9851b-103">Configure an EDI and AS2 Status Report</span></span>
<span data-ttu-id="9851b-104">已启用 EDI 或 AS2 状态报告，你显示的状态报告后你需要从**EDI 状态报告**或**EDIINT 状态报告**部分**组中心数据库**选项卡**组概述**页面[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="9851b-104">After you have enabled EDI or AS2 status reports, you display the status report you want from the **EDI Status Reports** or **EDIINT Status Reports** section of the **Group Hub** tab of the **Group Overview** page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="9851b-105">在所显示的状态报告中将看到一组默认数据。</span><span class="sxs-lookup"><span data-stu-id="9851b-105">When you display a status report, you will see a default set of data.</span></span> <span data-ttu-id="9851b-106">您可以配置状态报告的如下方面：</span><span class="sxs-lookup"><span data-stu-id="9851b-106">You can configure the following aspects of the status reports:</span></span>  
  
-   <span data-ttu-id="9851b-107">查询表达式：运行查询表达式可确定要报告的状态的数据范围，例如，日期范围、数据方向（接收或发送）或者状态值（“已接受”、“已拒绝”、“所有”等）</span><span class="sxs-lookup"><span data-stu-id="9851b-107">The query expression that is run to determine the range of data that status is reported for, for example, the date range, the direction of the data (receive or send), or the status value (Accepted, Rejected, All, etc.)</span></span>  
  
-   <span data-ttu-id="9851b-108">显示在状态报告窗格中的数据类型：由报告中的数据列确定。</span><span class="sxs-lookup"><span data-stu-id="9851b-108">The type of data displayed in the status report pane, as determined by the data columns in the report.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9851b-109">如果启用了状态报告，则所有状态都将保存在存储区中。</span><span class="sxs-lookup"><span data-stu-id="9851b-109">Whenever status reporting is enabled, all status will be saved in storage.</span></span> <span data-ttu-id="9851b-110">通过自定义查询表达式或状态列，可以定义要显示的保存数据。</span><span class="sxs-lookup"><span data-stu-id="9851b-110">By customizing the query expression or status columns, you are defining which saved data is displayed.</span></span>  
  
 <span data-ttu-id="9851b-111">五个不同的 EDI 和 AS2 状态报表才可用 (请参阅[类型的 EDI 和 AS2 状态报告](../core/types-of-edi-and-as2-status-reports.md))。</span><span class="sxs-lookup"><span data-stu-id="9851b-111">Five different EDI and AS2 status reports are available (see [Types of EDI and AS2 Status Reports](../core/types-of-edi-and-as2-status-reports.md)).</span></span> <span data-ttu-id="9851b-112">即使每个报告的数据有所不同，每个报告的配置方式也是相同的。</span><span class="sxs-lookup"><span data-stu-id="9851b-112">The way that you configure each report is the same, even though the data for each report is different.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9851b-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="9851b-113">Prerequisites</span></span>  
 <span data-ttu-id="9851b-114">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="9851b-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="configure-the-status-report-query-expression"></a><span data-ttu-id="9851b-115">配置状态报表查询表达式</span><span class="sxs-lookup"><span data-stu-id="9851b-115">Configure the status report query expression</span></span>  
  
1.  <span data-ttu-id="9851b-116">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk 组**节点以查看**组概述**窗格。</span><span class="sxs-lookup"><span data-stu-id="9851b-116">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **BizTalk Group** node to see the **Group Overview** pane.</span></span>  
  
2.  <span data-ttu-id="9851b-117">在底部**组中心数据库**选项卡中**组概述**窗格中，单击你想要配置，如状态报表**EDI 交换和关联 ACK 状态**。</span><span class="sxs-lookup"><span data-stu-id="9851b-117">At the bottom of the **Group Hub** tab in the **Group Overview** pane, click the status report that you want to configure, such as **EDI Interchange and Correlated ACK Status**.</span></span>  
  
3.  <span data-ttu-id="9851b-118">在**查询表达式**区域状态报表窗格中，验证是否所有你想要定义查询的筛选条件都存在。</span><span class="sxs-lookup"><span data-stu-id="9851b-118">In the **Query Expression** area of the status report pane, verify that all filter criteria that you want to define for the query are present.</span></span> <span data-ttu-id="9851b-119">否则，请单击在空行中的向下箭头**字段名称**底部的查询表达式中，然后选择你想要添加到查询表达式的条件的任何筛选的列。</span><span class="sxs-lookup"><span data-stu-id="9851b-119">If not, click the down arrow in the empty row in the **Field Name** column at the bottom of the query expression, and select any filter criteria that you want to add to the query expression.</span></span> <span data-ttu-id="9851b-120">你可以通过选择行，然后单击删除筛选器条件行**删除**键盘上的按钮。</span><span class="sxs-lookup"><span data-stu-id="9851b-120">You can delete a filter criteria row by selecting the row and clicking the **Delete** button on the keyboard.</span></span>  
  
4.  <span data-ttu-id="9851b-121">验证筛选表达式的值是否符合预期。</span><span class="sxs-lookup"><span data-stu-id="9851b-121">Verify that the values for the filter expressions are as desired.</span></span> <span data-ttu-id="9851b-122">否则，请单击向下的箭头**运算符**列以选择一个查询操作，并输入中的相应值**值**列。</span><span class="sxs-lookup"><span data-stu-id="9851b-122">If not, click the down arrow for the **Operator** column to select a query operation, and enter the appropriate value in the **Value** column.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9851b-123">中所述的运算符和值可用于在查询表达式中的筛选条件[类型的 EDI 和 AS2 状态报告](../core/types-of-edi-and-as2-status-reports.md)和**EDI AS2 状态报表 UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="9851b-123">The operators and values available for filter criteria in the query expressions are described in [Types of EDI and AS2 Status Reports](../core/types-of-edi-and-as2-status-reports.md) and the **EDI-AS2 Status Reports UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
5.  <span data-ttu-id="9851b-124">若要运行查询，显示根据筛选器条件中，状态报表单击**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="9851b-124">To run the query, displaying the status report according to the filter criteria, click **Run Query**.</span></span>  
  
6.  <span data-ttu-id="9851b-125">若要将查询表达式另存为.btq 文件，请单击**另存为**、 指定的文件夹并输入文件名，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="9851b-125">To save a query expression as a .btq file, click **Save As**, specify the folder and enter a filename, and then click **Save**.</span></span>  
  
7.  <span data-ttu-id="9851b-126">若要打开已保存的.btq 文件，请单击**打开查询**。</span><span class="sxs-lookup"><span data-stu-id="9851b-126">To open a saved .btq file, click **Open Query**.</span></span>  
  
## <a name="configure-the-type-of-data-displayed-in-the-status-report-pane"></a><span data-ttu-id="9851b-127">配置状态报表窗格中显示的数据的类型</span><span class="sxs-lookup"><span data-stu-id="9851b-127">Configure the type of data displayed in the status report pane</span></span>  
  
1.  <span data-ttu-id="9851b-128">右键单击状态报表窗格中，状态结果区域，然后单击**添加/删除列**。</span><span class="sxs-lookup"><span data-stu-id="9851b-128">Right-click the status results area of the status report pane, and then click **Add/Remove Columns**.</span></span>  
  
2.  <span data-ttu-id="9851b-129">若要将一种状态类别添加到显示的列列表，请单击中的列**可用列**列表，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="9851b-129">To add a status category to the displayed columns list, click a column in the **Available columns** list, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="9851b-130">若要从显示的列列表中删除一种状态类别，请单击中的列**显示的列**列表，，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="9851b-130">To remove a status category from the displayed columns list, click a column in the **Displayed columns** list, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9851b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9851b-131">See Also</span></span>  
 <span data-ttu-id="9851b-132">[监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="9851b-132">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="9851b-133">[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="9851b-133">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 <span data-ttu-id="9851b-134">[启用 EDI 和 AS2 状态报表](../core/enabling-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="9851b-134">[Enabling EDI and AS2 Status Reports](../core/enabling-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="9851b-135">显示的 EDI 或 AS2 状态报表</span><span class="sxs-lookup"><span data-stu-id="9851b-135">Displaying an EDI or AS2 Status Report</span></span>](../core/displaying-an-edi-or-as2-status-report.md)