---
title: 在 Excel 中定义业务活动和视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating business activities
- monitoring business activities [BAM], creating business activities
ms.assetid: 000532f0-cb9a-40ac-a6c5-a8bd4e49f8d0
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1516cab2ac18000fd010bf48fcc140512b67dffc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390290"
---
# <a name="defining-business-activities-and-views-in-excel"></a><span data-ttu-id="9a012-102">在 Excel 中定义业务活动和视图</span><span class="sxs-lookup"><span data-stu-id="9a012-102">Defining Business Activities and Views in Excel</span></span>
<span data-ttu-id="9a012-103">创建任何 BAM 解决方案的第一步是确定感兴趣的哪些数据以及应如何解释这些数据。</span><span class="sxs-lookup"><span data-stu-id="9a012-103">Your first step in creating any BAM solution is to identify what data you're interested in and how that data should be interpreted.</span></span> <span data-ttu-id="9a012-104">若要执行此操作，您使用 BAM 外接程序 excel。</span><span class="sxs-lookup"><span data-stu-id="9a012-104">To do this, you use the BAM Add-in for Excel.</span></span> <span data-ttu-id="9a012-105">外接程序，可通过定义业务活动来定义所需的数据的愿望。</span><span class="sxs-lookup"><span data-stu-id="9a012-105">The add-in allows you to define a wish-list of the data of interest by defining a business activity.</span></span> <span data-ttu-id="9a012-106">此外可以为不同类别的业务用户定义数据的解释方式以及所示的方式。</span><span class="sxs-lookup"><span data-stu-id="9a012-106">You can also define the way the data should be interpreted and shown to different categories of business users.</span></span>  
  
 <span data-ttu-id="9a012-107">BAM 外接程序还可以定义聚合。</span><span class="sxs-lookup"><span data-stu-id="9a012-107">The BAM Add-in also enables you to define aggregations.</span></span>  
  
 <span data-ttu-id="9a012-108">此外可以重命名活动项，例如，其中，某些用户熟悉的术语与活动中的相应数据项的名称不匹配。</span><span class="sxs-lookup"><span data-stu-id="9a012-108">You can also rename activity items, for example, where the terminology some users are familiar with does not match the names of the corresponding data items in the activity.</span></span> <span data-ttu-id="9a012-109">有关这一种解释是视图所在不同的语言。</span><span class="sxs-lookup"><span data-stu-id="9a012-109">One explanation for this is where the view is in a different language.</span></span>  
  
 <span data-ttu-id="9a012-110">完成活动定义后，Excel 将生成随机预览数据，可用于定义所需的图表和其他表示形式。</span><span class="sxs-lookup"><span data-stu-id="9a012-110">After you complete the activity definition, Excel generates random preview data that you can use to define the desired charts and other means of presentation.</span></span> <span data-ttu-id="9a012-111">有关预览数据的详细信息，请参阅[如何使用该数据透视表](../core/how-to-use-the-pivottable.md)。</span><span class="sxs-lookup"><span data-stu-id="9a012-111">For more information about preview data, see [How to Use the PivotTable](../core/how-to-use-the-pivottable.md).</span></span>  
  
 <span data-ttu-id="9a012-112">已完成的活动定义用于定义数据点和业务流程运行时收集所需的事件。</span><span class="sxs-lookup"><span data-stu-id="9a012-112">The completed activity definition defines the data points and events that you need collected when a business process is run.</span></span> <span data-ttu-id="9a012-113">可以从各种源获取 BAM 外接程序。</span><span class="sxs-lookup"><span data-stu-id="9a012-113">You can get the BAM Add-in from a variety of sources.</span></span>  
  
 <span data-ttu-id="9a012-114">你可以安装在过程外接程序 XLA BAM[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="9a012-114">You can install the BAM Add-in XLA during the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="9a012-115">有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)</span><span class="sxs-lookup"><span data-stu-id="9a012-115">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)</span></span>  
  
 <span data-ttu-id="9a012-116">BAM。XLA 文件安装在以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="9a012-116">The BAM.XLA file is installed in one of the following locations:</span></span>  
  
- <span data-ttu-id="9a012-117">如果在计算机上未安装 Microsoft Office，则将 BAM.xla 安装到 files\microsoft BizTalk Server 20*xx*\ExcelDir\ 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9a012-117">If Microsoft Office is not installed on the computer, then the BAM.xla is installed to the \Program Files\Microsoft BizTalk Server 20*xx*\ExcelDir\ folder.</span></span>  
  
- <span data-ttu-id="9a012-118">如果安装 Microsoft Office，则将 BAM.xla 安装中 \Program Files\Microsoft 网络*xx*\Library\ 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9a012-118">If Microsoft Office is installed, the BAM.xla is installed in the \Program Files\Microsoft Office\OFFICE*xx*\Library\ folder.</span></span>  
  
  <span data-ttu-id="9a012-119">此外可以从另一台计算机上的共享文件夹到您的计算机复制将 BAM.xla。</span><span class="sxs-lookup"><span data-stu-id="9a012-119">You can also copy the BAM.xla to your computer from a shared folder on another computer.</span></span> <span data-ttu-id="9a012-120">然后可以通过从复制到其中的位置选择它来注册 XLA。</span><span class="sxs-lookup"><span data-stu-id="9a012-120">You can then register the XLA by selecting it from the location to which you copied it.</span></span>  
  
  <span data-ttu-id="9a012-121">若要启用 BAM 外接程序在 Excel 菜单工具栏上，单击**文件**菜单，然后单击**选项**，然后单击**外接程序**。选择**业务活动监视**，然后单击**转**，在 Ad 接窗口中，选中复选框旁边**业务活动监视**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9a012-121">To enable the BAM Add-in on the Excel menu toolbar, click the **File** menu, then click **Options**, and then click **Add-Ins**. Select **Business Activity Monitoring**, then click **GO**, In the Ad-ins window, select the check box next to **Business Activity Monitoring**, and then click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a012-122">使用 BAM 外接程序，不能包含两个实例加载到同一进程中运行 Excel。</span><span class="sxs-lookup"><span data-stu-id="9a012-122">Using the BAM Add-in precludes running Excel with two instances loaded into the same process.</span></span>  <span data-ttu-id="9a012-123">当使用外接程序，在同一进程中的多个实例可能会发生以下情况下：</span><span class="sxs-lookup"><span data-stu-id="9a012-123">When using the add-in, multiple instances in the same process can occur in the following situations:</span></span>  
>   
>  <span data-ttu-id="9a012-124">具有的 Excel 电子表格打开与 BAM 外接程序启用时，并双击不同的 Excel 电子表格，Excel 尝试将电子表格加载到当前正在运行的实例。</span><span class="sxs-lookup"><span data-stu-id="9a012-124">When you have an Excel spreadsheet open with the BAM Add-in enabled, and you double-click a different Excel spreadsheet, Excel attempts to load the spreadsheet into the currently running instance.</span></span>  
>   
>  <span data-ttu-id="9a012-125">Excel 电子表格打开后，使用 BAM 外接程序已启用，并使用文件 / 打开菜单选项加载另一个 Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="9a012-125">When you have an Excel spreadsheet open, with the BAM Add-in enabled, and you use the File/Open menu option to load another Excel spreadsheet.</span></span>  
  
 <span data-ttu-id="9a012-126">您不能使用外接程序正确地在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="9a012-126">You cannot use the add-in properly in such situations.</span></span> <span data-ttu-id="9a012-127">若要打开多个 Excel 电子表格具有 BAM 外接程序启用时，必须打开 Excel 的新副本并将电子表格加载到该 Excel 实例。</span><span class="sxs-lookup"><span data-stu-id="9a012-127">To open multiple Excel spreadsheets when you have the BAM Add-in enabled, you must open a new copy of Excel and load the spreadsheet into that instance of Excel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a012-128">在 Excel 中使用 BAM.xla 时，你可能会收到错误"此工作簿已丢失了其 VBA 项目、 ActiveX 控件和任何其他与可编程序相关的功能。"</span><span class="sxs-lookup"><span data-stu-id="9a012-128">When you use BAM.xla in Excel, you may get the error “This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.”</span></span> <span data-ttu-id="9a012-129">有关错误的详细信息，请参阅[故障排除 BAM](../core/troubleshooting-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="9a012-129">For more information about the error, see [Troubleshooting BAM](../core/troubleshooting-bam.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a012-130">本节内容</span><span class="sxs-lookup"><span data-stu-id="9a012-130">In This Section</span></span>  
  
-   [<span data-ttu-id="9a012-131">如何定义业务活动</span><span class="sxs-lookup"><span data-stu-id="9a012-131">How to Define a Business Activity</span></span>](../core/how-to-define-a-business-activity.md)  
  
-   [<span data-ttu-id="9a012-132">定义 BAM 视图</span><span class="sxs-lookup"><span data-stu-id="9a012-132">Defining a BAM View</span></span>](../core/defining-a-bam-view.md)  
  
## <a name="see-also"></a><span data-ttu-id="9a012-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a012-133">See Also</span></span>  
 [<span data-ttu-id="9a012-134">使用 BAM 监视业务活动</span><span class="sxs-lookup"><span data-stu-id="9a012-134">Monitoring Business Activities with BAM</span></span>](../core/monitoring-business-activities-with-bam.md)