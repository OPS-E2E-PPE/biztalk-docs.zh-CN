---
title: 重新生成实时数据工作簿 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bd3a3fa-a550-4363-bbc0-2153226509ad
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c62686c15c2e0b04576ca3175fb22d52a71922
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987406"
---
# <a name="regenerate-the-live-data-workbook"></a><span data-ttu-id="e32bc-102">重新生成实时数据工作簿</span><span class="sxs-lookup"><span data-stu-id="e32bc-102">Regenerate the Live Data Workbook</span></span>
<span data-ttu-id="e32bc-103">在 BAM 实时数据工作簿丢失或损坏时，可使用 BAM 管理实用程序重新生成工作簿。</span><span class="sxs-lookup"><span data-stu-id="e32bc-103">In cases where the BAM live data workbook has been lost or corrupted, you can regenerate the workbook using the BAM Management utiprolity.</span></span> <span data-ttu-id="e32bc-104">此过程时，还从升级从早期的 BizTalk Server 版本。</span><span class="sxs-lookup"><span data-stu-id="e32bc-104">This process is also useful when you are upgrading from from previous BizTalk Server versions.</span></span>
  
 <span data-ttu-id="e32bc-105">常规步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="e32bc-105">The general steps are as follows:</span></span>  
  
-   <span data-ttu-id="e32bc-106">使用 BAM 管理实用程序从 BAM 数据库中检索 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="e32bc-106">Retrieve the BAM definition from the BAM database using the BAM Management utility.</span></span>  
  
-   <span data-ttu-id="e32bc-107">重新创建数据透视表。</span><span class="sxs-lookup"><span data-stu-id="e32bc-107">Re-create the PivotTable reports.</span></span> <span data-ttu-id="e32bc-108">由于 get-defxml 命令完成的 XML 检索仅包含活动和视图，因此必须使用用于 Excel 的 BAM 加载项重新创建数据透视表。</span><span class="sxs-lookup"><span data-stu-id="e32bc-108">Since the XML retrieval by the get-defxml command contains only the activities and views, you must re-create the PivotTable reports using the BAM Add-in for Excel.</span></span>  
  
-   <span data-ttu-id="e32bc-109">重命名数据透视表。</span><span class="sxs-lookup"><span data-stu-id="e32bc-109">Rename the PivotTable reports.</span></span> <span data-ttu-id="e32bc-110">如果从以前的 BizTalk Server 版本进行升级，则可能需要采用此步骤。</span><span class="sxs-lookup"><span data-stu-id="e32bc-110">This step may be necessary if you are upgrading from a previous BizTalk Server version.</span></span> <span data-ttu-id="e32bc-111">在某些版本中，BAM 存储两组 BAM 工作簿的名称： 显示名称和内部名称。</span><span class="sxs-lookup"><span data-stu-id="e32bc-111">With some versions, BAM stores two sets of names for BAM workbooks: a display name and an internal name.</span></span> <span data-ttu-id="e32bc-112">在检索 BAM 定义时，XML 包含工作簿的内部名称。</span><span class="sxs-lookup"><span data-stu-id="e32bc-112">When you retrieve the BAM definition, the XML contains the internal name for the workbook.</span></span> <span data-ttu-id="e32bc-113">必须重命名数据透视表，以确保实时数据工作簿可正确地连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="e32bc-113">You must rename the PivotTable reports to ensure that the live data workbook has the correct connection to the database.</span></span>  
  
-   <span data-ttu-id="e32bc-114">使用 BAM 管理实用程序重新生成实时数据工作簿。</span><span class="sxs-lookup"><span data-stu-id="e32bc-114">Regenerate the live data workbook using the BAM Management utility.</span></span>  
  
## <a name="retrieve-the-bam-definition"></a><span data-ttu-id="e32bc-115">检索 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="e32bc-115">Retrieve the BAM definition</span></span>  
  
1. <span data-ttu-id="e32bc-116">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e32bc-116">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="e32bc-117">在命令提示符处，导航到以下目录： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking。</span><span class="sxs-lookup"><span data-stu-id="e32bc-117">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking.</span></span>  
  
3. <span data-ttu-id="e32bc-118">类型： **bm.exe get defxml-FileName:abc.xml**</span><span class="sxs-lookup"><span data-stu-id="e32bc-118">Type: **bm.exe get-defxml -FileName:abc.xml**</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e32bc-119">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="e32bc-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="recreate-the-pivottable-reports"></a><span data-ttu-id="e32bc-120">重新创建数据透视表报表</span><span class="sxs-lookup"><span data-stu-id="e32bc-120">Recreate the PivotTable reports</span></span>  
  
1. <span data-ttu-id="e32bc-121">单击**启动**，依次指向**所有程序**，指向**Microsoft Office**，然后单击**Microsoft Office Excel**。</span><span class="sxs-lookup"><span data-stu-id="e32bc-121">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2. <span data-ttu-id="e32bc-122">单击**外接程序**选项卡，然后选择**导入 XML**从**BAM**下拉列表中的**菜单命令**组。</span><span class="sxs-lookup"><span data-stu-id="e32bc-122">Click the **Add-Ins** tab, and then select **Import XML** from the **BAM** drop-down list in the **Menu Commands** group.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e32bc-123">如果**外接程序**选项卡上不存在，请按照中的说明[步骤 1： 将 BAM 外接程序添加到 Microsoft Office Excel](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)若要添加的 BAM 外接程序。</span><span class="sxs-lookup"><span data-stu-id="e32bc-123">If the **Add-Ins** tab is not present, follow the instructions in [Step 1: Add the BAM Add-In to Microsoft Office Excel](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448) to add the BAM add-in.</span></span>  
  
3. <span data-ttu-id="e32bc-124">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking 文件夹，然后选择 abc.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="e32bc-124">Navigate to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking folder and select the abc.xml file.</span></span>  
  
4. <span data-ttu-id="e32bc-125">根据您的定义重新创建数据透视表。</span><span class="sxs-lookup"><span data-stu-id="e32bc-125">Re-create your PivotTable reports based on your definition.</span></span>  
  
5. <span data-ttu-id="e32bc-126">保存该工作簿。</span><span class="sxs-lookup"><span data-stu-id="e32bc-126">Save the workbook.</span></span> <span data-ttu-id="e32bc-127">若要执行此操作，请单击**文件**菜单，并单击**另存为**和输入文件的名称出现提示时键入 mynewbook.xls。</span><span class="sxs-lookup"><span data-stu-id="e32bc-127">To do this, click the **File** menu, and then click **Save As** and type mynewbook.xls when prompted for a file name.</span></span>  
  
## <a name="rename-the-pivottable-reports-optional"></a><span data-ttu-id="e32bc-128">重命名数据透视表报表 （可选）</span><span class="sxs-lookup"><span data-stu-id="e32bc-128">Rename the PivotTable reports (optional)</span></span>  

> [!NOTE]
> <span data-ttu-id="e32bc-129">此步骤可能仅需要如果从较旧版本的 BizTalk Server 进行升级。</span><span class="sxs-lookup"><span data-stu-id="e32bc-129">This step may only be required if you are upgrading from an older version of BizTalk Server.</span></span> 

1. <span data-ttu-id="e32bc-130">打开在检索 BAM 定义通过使用记事本时创建的 abc.xml 文件**启动**，再单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking\abc.xml，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e32bc-130">Open the abc.xml file that you created when you retrieved the BAM definitions using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking\abc.xml, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="e32bc-131">找到\<标题\>标记下\<BAMDefinition\>\\< 扩展\>\\< OWC\>\\< PivotTableView\> \\< 数据透视表\>\\< PivotView\>\\< 标签\>。</span><span class="sxs-lookup"><span data-stu-id="e32bc-131">Locate the \<Caption\> tag under \<BAMDefinition\>\\<Extension\>\\<OWC\>\\<PivotTableView\>\\<PivotTable\>\\<PivotView\>\\<Label\>.</span></span> <span data-ttu-id="e32bc-132">此标记的内容是某个数据透视表的内部名称。</span><span class="sxs-lookup"><span data-stu-id="e32bc-132">The content of this tag is the internal name for one of your PivotTable reports.</span></span> <span data-ttu-id="e32bc-133">可以通过查找下一步找到的其他数据透视表报表的内部名称\<标题\>标记。</span><span class="sxs-lookup"><span data-stu-id="e32bc-133">You can find the internal name for the other PivotTable reports by locating the next \<Caption\> tag.</span></span> <span data-ttu-id="e32bc-134">打开**mynewbook.xls**并使用位于重命名数据透视表的名称。</span><span class="sxs-lookup"><span data-stu-id="e32bc-134">Open **mynewbook.xls** and use the names you located to rename your PivotTable reports.</span></span>  
  
3. <span data-ttu-id="e32bc-135">保存已更新的工作簿。</span><span class="sxs-lookup"><span data-stu-id="e32bc-135">Save the updated workbook.</span></span>    
 
  
## <a name="regenerate-the-bam-live-data-workbook"></a><span data-ttu-id="e32bc-136">重新生成 BAM 实时数据工作簿</span><span class="sxs-lookup"><span data-stu-id="e32bc-136">Regenerate the BAM live data workbook</span></span>  

> [!NOTE]
>  <span data-ttu-id="e32bc-137">使用管理权限运行此工具。</span><span class="sxs-lookup"><span data-stu-id="e32bc-137">Run this tool with Administrative privileges.</span></span>  


1. <span data-ttu-id="e32bc-138">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e32bc-138">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="e32bc-139">在命令提示符处，导航到以下目录： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking。</span><span class="sxs-lookup"><span data-stu-id="e32bc-139">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking.</span></span>  
  
3. <span data-ttu-id="e32bc-140">类型： **bm.exe 重新生成 livedataworkbook-WorkbookName:mynewbook.xls**</span><span class="sxs-lookup"><span data-stu-id="e32bc-140">Type: **bm.exe regenerate-livedataworkbook -WorkbookName:mynewbook.xls**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e32bc-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="e32bc-141">See Also</span></span>  
 <span data-ttu-id="e32bc-142">[管理 BAM](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="e32bc-142">[Managing BAM](../core/managing-bam.md) </span></span>  
 <span data-ttu-id="e32bc-143">[BAM 管理实用程序](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="e32bc-143">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="e32bc-144">[使用 excel 的 BAM 外接程序的要求](../core/requirements-for-using-the-bam-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="e32bc-144">[Requirements for Using the BAM Add-In for Excel](../core/requirements-for-using-the-bam-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="e32bc-145">步骤 1： 向 Microsoft Office Excel 的 BAM 外接程序添加</span><span class="sxs-lookup"><span data-stu-id="e32bc-145">Step 1: Add the BAM Add-In to Microsoft Office Excel</span></span>](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)