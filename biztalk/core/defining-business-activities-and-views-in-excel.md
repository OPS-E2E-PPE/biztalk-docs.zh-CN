---
title: 在 Excel 中定义的业务活动和视图 |Microsoft 文档
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
ms.openlocfilehash: 91b9d3b213a6a6429759c0bb0d826798afa36da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239677"
---
# <a name="defining-business-activities-and-views-in-excel"></a><span data-ttu-id="284ef-102">在 Excel 中定义业务活动和视图</span><span class="sxs-lookup"><span data-stu-id="284ef-102">Defining Business Activities and Views in Excel</span></span>
<span data-ttu-id="284ef-103">创建任何 BAM 解决方案的第一步都是确定感兴趣的数据以及如何解释这些数据。</span><span class="sxs-lookup"><span data-stu-id="284ef-103">Your first step in creating any BAM solution is to identify what data you're interested in and how that data should be interpreted.</span></span> <span data-ttu-id="284ef-104">为此，可使用适用于 Excel 的 BAM 外接程序。</span><span class="sxs-lookup"><span data-stu-id="284ef-104">To do this, you use the BAM Add-in for Excel.</span></span> <span data-ttu-id="284ef-105">使用该外接程序，可以通过定义业务活动来确定要使用的感兴趣数据的列表。</span><span class="sxs-lookup"><span data-stu-id="284ef-105">The add-in allows you to define a wish-list of the data of interest by defining a business activity.</span></span> <span data-ttu-id="284ef-106">还可以定义数据的解释方式以及呈现给不同类别的业务用户时的显示方式。</span><span class="sxs-lookup"><span data-stu-id="284ef-106">You can also define the way the data should be interpreted and shown to different categories of business users.</span></span>  
  
 <span data-ttu-id="284ef-107">使用 BAM 外接程序还可以定义聚合。</span><span class="sxs-lookup"><span data-stu-id="284ef-107">The BAM Add-in also enables you to define aggregations.</span></span>  
  
 <span data-ttu-id="284ef-108">您还能够重命名活动项，例如，在某些用户熟悉的术语与活动中相应数据项的名称不匹配时需要重命名。</span><span class="sxs-lookup"><span data-stu-id="284ef-108">You can also rename activity items, for example, where the terminology some users are familiar with does not match the names of the corresponding data items in the activity.</span></span> <span data-ttu-id="284ef-109">原因之一可能是视图的语言不同。</span><span class="sxs-lookup"><span data-stu-id="284ef-109">One explanation for this is where the view is in a different language.</span></span>  
  
 <span data-ttu-id="284ef-110">完成活动定义后，Excel 将生成随机预览数据，使用这些数据可以定义需要的图表和其他表示形式。</span><span class="sxs-lookup"><span data-stu-id="284ef-110">After you complete the activity definition, Excel generates random preview data that you can use to define the desired charts and other means of presentation.</span></span> <span data-ttu-id="284ef-111">有关预览数据的详细信息，请参阅[如何使用数据透视表](../core/how-to-use-the-pivottable.md)。</span><span class="sxs-lookup"><span data-stu-id="284ef-111">For more information about preview data, see [How to Use the PivotTable](../core/how-to-use-the-pivottable.md).</span></span>  
  
 <span data-ttu-id="284ef-112">完成的活动定义可定义业务流程运行过程中需要收集的数据点和事件。</span><span class="sxs-lookup"><span data-stu-id="284ef-112">The completed activity definition defines the data points and events that you need collected when a business process is run.</span></span> <span data-ttu-id="284ef-113">您可以通过各种渠道获得 BAM 外接程序。</span><span class="sxs-lookup"><span data-stu-id="284ef-113">You can get the BAM Add-in from a variety of sources.</span></span>  
  
 <span data-ttu-id="284ef-114">你可以安装在外接程序 XLA BAM[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="284ef-114">You can install the BAM Add-in XLA during the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="284ef-115">有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 的安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)</span><span class="sxs-lookup"><span data-stu-id="284ef-115">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)</span></span>  
  
 <span data-ttu-id="284ef-116">BAM。XLA 文件安装在以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="284ef-116">The BAM.XLA file is installed in one of the following locations:</span></span>  
  
-   <span data-ttu-id="284ef-117">如果在计算机上未安装 Microsoft Office，则 BAM.xla 安装到 files\microsoft BizTalk Server 20*xx*\ExcelDir\ 文件夹。</span><span class="sxs-lookup"><span data-stu-id="284ef-117">If Microsoft Office is not installed on the computer, then the BAM.xla is installed to the \Program Files\Microsoft BizTalk Server 20*xx*\ExcelDir\ folder.</span></span>  
  
-   <span data-ttu-id="284ef-118">如果安装了 Microsoft Office，files\microsoft 网络中安装 BAM.xla*xx*\Library\ 文件夹。</span><span class="sxs-lookup"><span data-stu-id="284ef-118">If Microsoft Office is installed, the BAM.xla is installed in the \Program Files\Microsoft Office\OFFICE*xx*\Library\ folder.</span></span>  
  
 <span data-ttu-id="284ef-119">还可以从其他计算机上的共享文件夹将 BAM.xla 复制到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="284ef-119">You can also copy the BAM.xla to your computer from a shared folder on another computer.</span></span> <span data-ttu-id="284ef-120">然后通过从要复制到的位置选择它以便注册 XLA。</span><span class="sxs-lookup"><span data-stu-id="284ef-120">You can then register the XLA by selecting it from the location to which you copied it.</span></span>  
  
 <span data-ttu-id="284ef-121">若要启用 BAM 外接程序 Excel 菜单工具栏上，单击**文件**菜单，然后单击**选项**，然后单击**外接程序**。选择**业务活动监视**，然后单击**转**，在 Ad 单元窗口中，选中的复选框旁边**业务活动监视**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="284ef-121">To enable the BAM Add-in on the Excel menu toolbar, click the **File** menu, then click **Options**, and then click **Add-Ins**. Select **Business Activity Monitoring**, then click **GO**, In the Ad-ins window, select the check box next to **Business Activity Monitoring**, and then click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="284ef-122">使用 BAM 外接程序可避免两个正在运行的 Excel 实例被加载到同一进程中。</span><span class="sxs-lookup"><span data-stu-id="284ef-122">Using the BAM Add-in precludes running Excel with two instances loaded into the same process.</span></span>  <span data-ttu-id="284ef-123">使用外接程序时，在以下情况下会在同一进程中出现多个实例：</span><span class="sxs-lookup"><span data-stu-id="284ef-123">When using the add-in, multiple instances in the same process can occur in the following situations:</span></span>  
>   
>  <span data-ttu-id="284ef-124">打开一个 Excel 电子表格后，又启用了 BAM 外接程序，然后双击另一个 Excel 电子表格，Excel 会尝试将电子表格加载到当前正在运行的实例。</span><span class="sxs-lookup"><span data-stu-id="284ef-124">When you have an Excel spreadsheet open with the BAM Add-in enabled, and you double-click a different Excel spreadsheet, Excel attempts to load the spreadsheet into the currently running instance.</span></span>  
>   
>  <span data-ttu-id="284ef-125">打开一个 Excel 电子表格后，又启用了 BAM 外接程序，这时使用“文件”/“打开”菜单选项加载另一个 Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="284ef-125">When you have an Excel spreadsheet open, with the BAM Add-in enabled, and you use the File/Open menu option to load another Excel spreadsheet.</span></span>  
  
 <span data-ttu-id="284ef-126">在这种情况下，您不能正常使用外接程序。</span><span class="sxs-lookup"><span data-stu-id="284ef-126">You cannot use the add-in properly in such situations.</span></span> <span data-ttu-id="284ef-127">若要在启用 BAM 外接程序的情况下打开多个 Excel 电子表格，必须先打开一个 Excel 的新副本，然后将电子表格加载到该 Excel 实例中。</span><span class="sxs-lookup"><span data-stu-id="284ef-127">To open multiple Excel spreadsheets when you have the BAM Add-in enabled, you must open a new copy of Excel and load the spreadsheet into that instance of Excel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="284ef-128">当在 Excel 中使用 BAM.xla 时，你可能会收到错误"此工作簿已丢失其 VBA 项目，ActiveX 控件和任何其他可编程性相关的功能。"</span><span class="sxs-lookup"><span data-stu-id="284ef-128">When you use BAM.xla in Excel, you may get the error “This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.”</span></span> <span data-ttu-id="284ef-129">有关错误的详细信息，请参阅[疑难解答 BAM](../core/troubleshooting-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="284ef-129">For more information about the error, see [Troubleshooting BAM](../core/troubleshooting-bam.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="284ef-130">本节内容</span><span class="sxs-lookup"><span data-stu-id="284ef-130">In This Section</span></span>  
  
-   [<span data-ttu-id="284ef-131">如何定义业务活动</span><span class="sxs-lookup"><span data-stu-id="284ef-131">How to Define a Business Activity</span></span>](../core/how-to-define-a-business-activity.md)  
  
-   [<span data-ttu-id="284ef-132">定义 BAM 视图</span><span class="sxs-lookup"><span data-stu-id="284ef-132">Defining a BAM View</span></span>](../core/defining-a-bam-view.md)  
  
## <a name="see-also"></a><span data-ttu-id="284ef-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="284ef-133">See Also</span></span>  
 [<span data-ttu-id="284ef-134">监视与 BAM 业务活动</span><span class="sxs-lookup"><span data-stu-id="284ef-134">Monitoring Business Activities with BAM</span></span>](../core/monitoring-business-activities-with-bam.md)