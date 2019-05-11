---
title: 配置 EDI 和 AS2 状态报告 |Microsoft Docs
description: 创建 EDI 或 AS2 状态报告查询表达式中，并选择想要在 BizTalk Server 中的报表中显示的数据
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6490864d-f1e6-4932-aefb-c332a595aad7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce12c33570189f8436752d1741957f51779d25d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391369"
---
# <a name="configure-an-edi-and-as2-status-report"></a><span data-ttu-id="9e891-103">配置 EDI 和 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="9e891-103">Configure an EDI and AS2 Status Report</span></span>
<span data-ttu-id="9e891-104">已启用 EDI 或 AS2 状态报告，可显示状态报告后你想从**EDI 状态报告**或**EDIINT 状态报告**一部分**组中心**选项卡**组概述**页中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="9e891-104">After you have enabled EDI or AS2 status reports, you display the status report you want from the **EDI Status Reports** or **EDIINT Status Reports** section of the **Group Hub** tab of the **Group Overview** page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="9e891-105">显示的状态报告，你将看到默认值的数据集。</span><span class="sxs-lookup"><span data-stu-id="9e891-105">When you display a status report, you will see a default set of data.</span></span> <span data-ttu-id="9e891-106">你可以配置状态报告的以下方面：</span><span class="sxs-lookup"><span data-stu-id="9e891-106">You can configure the following aspects of the status reports:</span></span>  
  
- <span data-ttu-id="9e891-107">用于运行以确定报告的状态，例如数据、 日期范围、 数据方向的范围的查询表达式 （接收或发送） 或者状态值 （接受，将被拒绝，所有等。）</span><span class="sxs-lookup"><span data-stu-id="9e891-107">The query expression that is run to determine the range of data that status is reported for, for example, the date range, the direction of the data (receive or send), or the status value (Accepted, Rejected, All, etc.)</span></span>  
  
- <span data-ttu-id="9e891-108">显示在状态报告窗格中，由报表中的数据列的数据类型。</span><span class="sxs-lookup"><span data-stu-id="9e891-108">The type of data displayed in the status report pane, as determined by the data columns in the report.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="9e891-109">每当启用状态报告后，所有状态都将都保存在存储中。</span><span class="sxs-lookup"><span data-stu-id="9e891-109">Whenever status reporting is enabled, all status will be saved in storage.</span></span> <span data-ttu-id="9e891-110">通过自定义查询表达式或状态列，可以定义显示的已保存的数据。</span><span class="sxs-lookup"><span data-stu-id="9e891-110">By customizing the query expression or status columns, you are defining which saved data is displayed.</span></span>  
  
  <span data-ttu-id="9e891-111">五个不同的 EDI 和 AS2 状态报告 (请参阅[类型的 EDI 和 AS2 状态报告](../core/types-of-edi-and-as2-status-reports.md))。</span><span class="sxs-lookup"><span data-stu-id="9e891-111">Five different EDI and AS2 status reports are available (see [Types of EDI and AS2 Status Reports](../core/types-of-edi-and-as2-status-reports.md)).</span></span> <span data-ttu-id="9e891-112">配置每个报表的方式是相同的即使每个报表的数据不同。</span><span class="sxs-lookup"><span data-stu-id="9e891-112">The way that you configure each report is the same, even though the data for each report is different.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e891-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="9e891-113">Prerequisites</span></span>  
 <span data-ttu-id="9e891-114">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="9e891-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="configure-the-status-report-query-expression"></a><span data-ttu-id="9e891-115">配置状态报告查询表达式</span><span class="sxs-lookup"><span data-stu-id="9e891-115">Configure the status report query expression</span></span>  
  
1. <span data-ttu-id="9e891-116">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk 组**节点以查看**组概述**窗格。</span><span class="sxs-lookup"><span data-stu-id="9e891-116">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **BizTalk Group** node to see the **Group Overview** pane.</span></span>  
  
2. <span data-ttu-id="9e891-117">在底部**组中心**选项卡**组概述**窗格中，单击你想要配置，如在状态报告**EDI 交换和相关 ACK 状态**。</span><span class="sxs-lookup"><span data-stu-id="9e891-117">At the bottom of the **Group Hub** tab in the **Group Overview** pane, click the status report that you want to configure, such as **EDI Interchange and Correlated ACK Status**.</span></span>  
  
3. <span data-ttu-id="9e891-118">在中**查询表达式**区域状态报表窗格中，验证想要定义查询的所有筛选器条件是否存在。</span><span class="sxs-lookup"><span data-stu-id="9e891-118">In the **Query Expression** area of the status report pane, verify that all filter criteria that you want to define for the query are present.</span></span> <span data-ttu-id="9e891-119">如果没有，请单击在空行中的向下箭头**字段名**底部的查询表达式中，并选择你想要添加到查询表达式的条件的任何筛选的列。</span><span class="sxs-lookup"><span data-stu-id="9e891-119">If not, click the down arrow in the empty row in the **Field Name** column at the bottom of the query expression, and select any filter criteria that you want to add to the query expression.</span></span> <span data-ttu-id="9e891-120">可以通过选择行并单击删除筛选条件行**删除**键盘上的按钮。</span><span class="sxs-lookup"><span data-stu-id="9e891-120">You can delete a filter criteria row by selecting the row and clicking the **Delete** button on the keyboard.</span></span>  
  
4. <span data-ttu-id="9e891-121">验证筛选器表达式的值是否为所需。</span><span class="sxs-lookup"><span data-stu-id="9e891-121">Verify that the values for the filter expressions are as desired.</span></span> <span data-ttu-id="9e891-122">如果没有，请单击向下的箭头**运算符**要选择查询操作，并输入相应的值的列**值**列。</span><span class="sxs-lookup"><span data-stu-id="9e891-122">If not, click the down arrow for the **Operator** column to select a query operation, and enter the appropriate value in the **Value** column.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9e891-123">中所述的运算符和值可用于在查询表达式中的筛选器条件[类型的 EDI 和 AS2 状态报告](../core/types-of-edi-and-as2-status-reports.md)并**EDI-AS2 状态报告 UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="9e891-123">The operators and values available for filter criteria in the query expressions are described in [Types of EDI and AS2 Status Reports](../core/types-of-edi-and-as2-status-reports.md) and the **EDI-AS2 Status Reports UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
5. <span data-ttu-id="9e891-124">若要运行查询，显示在状态报告根据筛选条件中，单击**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="9e891-124">To run the query, displaying the status report according to the filter criteria, click **Run Query**.</span></span>  
  
6. <span data-ttu-id="9e891-125">若要查询表达式另存为.btq 文件，请单击**另存为**，指定的文件夹并输入一个文件名，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="9e891-125">To save a query expression as a .btq file, click **Save As**, specify the folder and enter a filename, and then click **Save**.</span></span>  
  
7. <span data-ttu-id="9e891-126">若要打开已保存的.btq 文件，请单击**打开查询**。</span><span class="sxs-lookup"><span data-stu-id="9e891-126">To open a saved .btq file, click **Open Query**.</span></span>  
  
## <a name="configure-the-type-of-data-displayed-in-the-status-report-pane"></a><span data-ttu-id="9e891-127">配置状态报告窗格中显示的数据类型</span><span class="sxs-lookup"><span data-stu-id="9e891-127">Configure the type of data displayed in the status report pane</span></span>  
  
1.  <span data-ttu-id="9e891-128">右键单击状态报告窗格的状态结果区域，然后单击**添加/删除列**。</span><span class="sxs-lookup"><span data-stu-id="9e891-128">Right-click the status results area of the status report pane, and then click **Add/Remove Columns**.</span></span>  
  
2.  <span data-ttu-id="9e891-129">若要将一种状态类别添加到显示的列列表，请单击中的列**可用的列**列表，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="9e891-129">To add a status category to the displayed columns list, click a column in the **Available columns** list, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="9e891-130">若要从显示的列列表中删除状态类别，请单击中的列**显示的列**列表，，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="9e891-130">To remove a status category from the displayed columns list, click a column in the **Displayed columns** list, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e891-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e891-131">See Also</span></span>  
 <span data-ttu-id="9e891-132">[监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="9e891-132">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="9e891-133">[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="9e891-133">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 <span data-ttu-id="9e891-134">[启用 EDI 和 AS2 状态报告](../core/enabling-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="9e891-134">[Enabling EDI and AS2 Status Reports](../core/enabling-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="9e891-135">显示 EDI 或 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="9e891-135">Displaying an EDI or AS2 Status Report</span></span>](../core/displaying-an-edi-or-as2-status-report.md)