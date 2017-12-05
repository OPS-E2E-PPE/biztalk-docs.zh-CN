---
title: "如何重新生成实时数据工作簿 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bd3a3fa-a550-4363-bbc0-2153226509ad
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3e98ac5f02363c02ff422f44397fbf1f0e3b4c0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-regenerate-the-live-data-workbook"></a><span data-ttu-id="c0964-102">如何重新生成实时数据工作簿</span><span class="sxs-lookup"><span data-stu-id="c0964-102">How to Regenerate the Live Data Workbook</span></span>
<span data-ttu-id="c0964-103">在 BAM 实时数据工作簿丢失或损坏时，可使用 BAM 管理实用程序重新生成工作簿。</span><span class="sxs-lookup"><span data-stu-id="c0964-103">In cases where the BAM live data workbook has been lost or corrupted, you can regenerate the workbook using the BAM Management utiprolity.</span></span> <span data-ttu-id="c0964-104">从升级时，此过程也是有用[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]到 BizTalk Server 中，因为实时数据有关的工作簿[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]与 BizTalk Server 不兼容。</span><span class="sxs-lookup"><span data-stu-id="c0964-104">This process is also useful when you are upgrading from [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] to BizTalk Server, since live data workbooks for [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] are not compatible with BizTalk Server.</span></span>  
  
 <span data-ttu-id="c0964-105">常规步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="c0964-105">The general steps are as follows:</span></span>  
  
-   <span data-ttu-id="c0964-106">使用 BAM 管理实用程序从 BAM 数据库中检索 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="c0964-106">Retrieve the BAM definition from the BAM database using the BAM Management utility.</span></span>  
  
-   <span data-ttu-id="c0964-107">重新创建数据透视表。</span><span class="sxs-lookup"><span data-stu-id="c0964-107">Re-create the PivotTable reports.</span></span> <span data-ttu-id="c0964-108">由于 get-defxml 命令完成的 XML 检索仅包含活动和视图，因此必须使用用于 Excel 的 BAM 加载项重新创建数据透视表。</span><span class="sxs-lookup"><span data-stu-id="c0964-108">Since the XML retrieval by the get-defxml command contains only the activities and views, you must re-create the PivotTable reports using the BAM Add-in for Excel.</span></span>  
  
-   <span data-ttu-id="c0964-109">重命名数据透视表。</span><span class="sxs-lookup"><span data-stu-id="c0964-109">Rename the PivotTable reports.</span></span> <span data-ttu-id="c0964-110">此步骤是必需的如果要从升级[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]给 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="c0964-110">This step is necessary if you are upgrading from [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] to BizTalk Server.</span></span> <span data-ttu-id="c0964-111">这是必要自[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]，BAM 存储名称的 BAM 工作簿的两个集： 显示名称和内部名称。</span><span class="sxs-lookup"><span data-stu-id="c0964-111">This is necessary since in [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)], BAM stores two sets of names for BAM workbooks: a display name and an internal name.</span></span> <span data-ttu-id="c0964-112">在检索 BAM 定义时，XML 包含工作簿的内部名称。</span><span class="sxs-lookup"><span data-stu-id="c0964-112">When you retrieve the BAM definition, the XML contains the internal name for the workbook.</span></span> <span data-ttu-id="c0964-113">必须重命名数据透视表，以确保实时数据工作簿可正确地连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="c0964-113">You must rename the PivotTable reports to ensure that the live data workbook has the correct connection to the database.</span></span>  
  
-   <span data-ttu-id="c0964-114">使用 BAM 管理实用程序重新生成实时数据工作簿。</span><span class="sxs-lookup"><span data-stu-id="c0964-114">Regenerate the live data workbook using the BAM Management utility.</span></span>  
  
### <a name="to-retrieve-the-bam-definition"></a><span data-ttu-id="c0964-115">检索 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="c0964-115">To retrieve the BAM definition</span></span>  
  
1.  <span data-ttu-id="c0964-116">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c0964-116">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="c0964-117">在命令提示符下，导航到以下目录：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="c0964-117">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="c0964-118">类型： **bm.exe get defxml-FileName:abc.xml**</span><span class="sxs-lookup"><span data-stu-id="c0964-118">Type: **bm.exe get-defxml -FileName:abc.xml**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c0964-119">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="c0964-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-re-create-the-pivottable-reports"></a><span data-ttu-id="c0964-120">重新创建数据透视表</span><span class="sxs-lookup"><span data-stu-id="c0964-120">To re-create the PivotTable reports</span></span>  
  
1.  <span data-ttu-id="c0964-121">单击**启动**，指向**所有程序**，指向**Microsoft Office**，然后单击**Microsoft Office Excel**。</span><span class="sxs-lookup"><span data-stu-id="c0964-121">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2.  <span data-ttu-id="c0964-122">单击**外接程序**选项卡上，然后选择**导入 XML**从**BAM**下拉列表中的**菜单命令**组。</span><span class="sxs-lookup"><span data-stu-id="c0964-122">Click the **Add-Ins** tab, and then select **Import XML** from the **BAM** drop-down list in the **Menu Commands** group.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c0964-123">如果**外接程序**选项卡上不存在，请按照中的说明[步骤 1: BAM 外接程序添加到 Microsoft Office Excel](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)若要添加的 BAM 外接程序。</span><span class="sxs-lookup"><span data-stu-id="c0964-123">If the **Add-Ins** tab is not present, follow the instructions in [Step 1: Add the BAM Add-In to Microsoft Office Excel](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448) to add the BAM add-in.</span></span>  
  
3.  <span data-ttu-id="c0964-124">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪文件夹并选择 abc.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="c0964-124">Navigate to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking folder and select the abc.xml file.</span></span>  
  
4.  <span data-ttu-id="c0964-125">根据您的定义重新创建数据透视表。</span><span class="sxs-lookup"><span data-stu-id="c0964-125">Re-create your PivotTable reports based on your definition.</span></span>  
  
5.  <span data-ttu-id="c0964-126">保存该工作簿。</span><span class="sxs-lookup"><span data-stu-id="c0964-126">Save the workbook.</span></span> <span data-ttu-id="c0964-127">若要执行此操作，请单击**文件**菜单，，然后单击**另存为**键入 mynewbook.xls 时提示输入文件名称。</span><span class="sxs-lookup"><span data-stu-id="c0964-127">To do this, click the **File** menu, and then click **Save As** and type mynewbook.xls when prompted for a file name.</span></span>  
  
### <a name="to-rename-the-pivottable-reports-optional"></a><span data-ttu-id="c0964-128">重命名数据透视表（可选）</span><span class="sxs-lookup"><span data-stu-id="c0964-128">To rename the PivotTable reports (optional)</span></span>  
  
1.  <span data-ttu-id="c0964-129">打开时检索的 BAM 定义，通过单击使用记事本创建 abc.xml 文件**启动**、 单击**运行**，键入记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\abc.xml，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c0964-129">Open the abc.xml file that you created when you retrieved the BAM definitions using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\abc.xml, and then clicking **OK**.</span></span>  
  
2.  <span data-ttu-id="c0964-130">找到\<标题\>标记下\<BAMDefinition\>\\< 扩展\>\\< OWC\>\\< PivotTableView\> \\< 数据透视表\>\\< 数据透视视图\>\\< 标签\>。</span><span class="sxs-lookup"><span data-stu-id="c0964-130">Locate the \<Caption\> tag under \<BAMDefinition\>\\<Extension\>\\<OWC\>\\<PivotTableView\>\\<PivotTable\>\\<PivotView\>\\<Label\>.</span></span> <span data-ttu-id="c0964-131">此标记的内容是某个数据透视表的内部名称。</span><span class="sxs-lookup"><span data-stu-id="c0964-131">The content of this tag is the internal name for one of your PivotTable reports.</span></span> <span data-ttu-id="c0964-132">可以通过查找下一步中找到其他数据透视表报告的内部名称\<标题\>标记。</span><span class="sxs-lookup"><span data-stu-id="c0964-132">You can find the internal name for the other PivotTable reports by locating the next \<Caption\> tag.</span></span> <span data-ttu-id="c0964-133">打开**mynewbook.xls**并使用位于重命名你的数据透视表报告的名称。</span><span class="sxs-lookup"><span data-stu-id="c0964-133">Open **mynewbook.xls** and use the names you located to rename your PivotTable reports.</span></span>  
  
3.  <span data-ttu-id="c0964-134">保存已更新的工作簿。</span><span class="sxs-lookup"><span data-stu-id="c0964-134">Save the updated workbook.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c0964-135">你必须遵循此过程，仅当您正在从升级[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]给 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="c0964-135">You must follow this procedure only if you are upgrading from [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] to BizTalk Server.</span></span>  
  
### <a name="to-regenerate-the-bam-live-data-workbook"></a><span data-ttu-id="c0964-136">重新生成 BAM 实时数据工作簿</span><span class="sxs-lookup"><span data-stu-id="c0964-136">To regenerate the BAM live data workbook</span></span>  
  
1.  <span data-ttu-id="c0964-137">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c0964-137">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="c0964-138">在命令提示符下，导航到以下目录：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="c0964-138">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="c0964-139">类型： **bm.exe 重新生成 livedataworkbook-WorkbookName:mynewbook.xls**</span><span class="sxs-lookup"><span data-stu-id="c0964-139">Type: **bm.exe regenerate-livedataworkbook -WorkbookName:mynewbook.xls**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c0964-140">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="c0964-140">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0964-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0964-141">See Also</span></span>  
 <span data-ttu-id="c0964-142">[管理 BAM](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="c0964-142">[Managing BAM](../core/managing-bam.md) </span></span>  
 <span data-ttu-id="c0964-143">[BAM 管理实用工具](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="c0964-143">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="c0964-144">[使用 for Excel 的 BAM 外接程序的要求](../core/requirements-for-using-the-bam-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="c0964-144">[Requirements for Using the BAM Add-In for Excel](../core/requirements-for-using-the-bam-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="c0964-145">步骤 1: BAM 外接程序添加到 Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="c0964-145">Step 1: Add the BAM Add-In to Microsoft Office Excel</span></span>](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)