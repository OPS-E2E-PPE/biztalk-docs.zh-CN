---
title: 如何使用查找的 BAM 数据扩充 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, data lookups
ms.assetid: 8d10659e-97d6-4cd1-9b4d-307afd43c763
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d27a44d67ce7b95e06e07fd2be425688733b7bc8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385064"
---
# <a name="how-to-enrich-bam-data-using-lookups"></a><span data-ttu-id="eeb6b-102">如何使用查找的 BAM 数据扩充</span><span class="sxs-lookup"><span data-stu-id="eeb6b-102">How to Enrich BAM Data Using Lookups</span></span>
<span data-ttu-id="eeb6b-103">有些情况下在其中在操作时可用的数据不包含出于报告目的所需的一切。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-103">There are cases in which the data that is available at operation time does not contain everything you need for reporting purposes.</span></span> <span data-ttu-id="eeb6b-104">例如，你可能会在运行时有 ProductID 但没有 ProductName。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-104">For example, you may have a ProductID but not a ProductName at runtime.</span></span> <span data-ttu-id="eeb6b-105">由于 BAM 活动表示独立于数据的实际收集方式的抽象，它应包含名为你想要查看报告"ProductName"中的最后一个数据的项。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-105">Since the BAM Activity represents an abstraction independent of how the data is actually collected, it should contain an item named as the final data that you want to see in the report "ProductName".</span></span> <span data-ttu-id="eeb6b-106">就像任何其他项，您可以使用此如里程碑组、 持续时间、 维度和度量值的解释性结构中。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-106">Just like any other item, you can use this in interpretive constructs such as milestone groups, durations, dimensions, and measures.</span></span> <span data-ttu-id="eeb6b-107">由于 ProductName 不在运行时可用，则必须获取足以执行查找，如 ProductID 一些其他数据。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-107">Since the ProductName is not available at runtime, you must get some additional data that is sufficient for performing a lookup, such as the ProductID.</span></span>  
  
 <span data-ttu-id="eeb6b-108">您应该收集同一列中，而不是报告所需的数据中的数据。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-108">You should collect the data in the same column, instead of the data that you need for reports.</span></span> <span data-ttu-id="eeb6b-109">例如，应该在运行时收集 ProductID 而不是 ProductName。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-109">For example, you should collect the ProductID instead of ProductName at runtime.</span></span> <span data-ttu-id="eeb6b-110">如果需要更多的列，也可以在活动中创建多个项，但不是在任何视图中使用它们。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-110">If more columns are required, you may create more items in the activity but not use them in any View.</span></span>  
  
### <a name="to-enrich-bam-data-via-lookups"></a><span data-ttu-id="eeb6b-111">通过查找的 BAM 数据扩充</span><span class="sxs-lookup"><span data-stu-id="eeb6b-111">To enrich BAM data via lookups</span></span>  
  
1.  <span data-ttu-id="eeb6b-112">部署 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-112">Deploy your BAM definition.</span></span>  
  
2.  <span data-ttu-id="eeb6b-113">在 SQL Server Management Studio 中，添加包含所需服务器作为远程服务器的数据的服务器。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-113">In SQL Server Management Studio, add the server that contains the data of interest as a remote server.</span></span>  
  
3.  <span data-ttu-id="eeb6b-114">找到名为 BAM_AN_ 的数据分析包`<View Name>`。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-114">Locate the data analysis package named BAM_AN_`<View Name>`.</span></span> <span data-ttu-id="eeb6b-115">例如如果视图为 SalesMgr，这将为 BAM_AN_SalesMgr。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-115">For example if the view is SalesMgr, this will be BAM_AN_SalesMgr.</span></span>  
  
4.  <span data-ttu-id="eeb6b-116">设置缩放放大的视图的包 （例如 100%)</span><span class="sxs-lookup"><span data-stu-id="eeb6b-116">Set the zoom to magnify the view of the package (e.g. 100%)</span></span>  
  
5.  <span data-ttu-id="eeb6b-117">在查找中添加要使用的 SQL 连接。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-117">Add a SQL connection that you will be using in the lookups.</span></span>  
  
6.  <span data-ttu-id="eeb6b-118">在步骤"清除过渡数据库"后找到转换数据任务。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-118">Locate the transform data task after the step "Cleanup Staging".</span></span> <span data-ttu-id="eeb6b-119">这是在其中将数据从主导入到星数据库。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-119">This is where you move the data from the PrimaryImport to the StarSchema database.</span></span> <span data-ttu-id="eeb6b-120">有两个实例的此任务 — 一个用于已完成的活动，另一个正在进行中。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-120">There are two instances of this task—one for the completed activities, and another for the one that is in progress.</span></span> <span data-ttu-id="eeb6b-121">适用于这两项任务的所有剩余的步骤。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-121">Apply all the rest of the steps to both tasks.</span></span>  
  
7.  <span data-ttu-id="eeb6b-122">单击转换。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-122">Click the transformation.</span></span>  
  
8.  <span data-ttu-id="eeb6b-123">选择查找;添加查找"LookupProductByID"，然后使用查找连接 （请参阅 SQL 联机丛书查找）。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-123">Select Lookups; add your lookup "LookupProductByID" using the lookup connection (see SQL books online for lookups).</span></span> <span data-ttu-id="eeb6b-124">例如，查找是一个简单的表"LookupProduct"，如果具有 ProductID 和 ProductName 列，则查找的文本将是：</span><span class="sxs-lookup"><span data-stu-id="eeb6b-124">If for example the lookup is a simple table "LookupProduct", the with columns ProductID and ProductName, the text of the lookup will be:</span></span>  
  
    ```  
    SELECT ProductName  
    FROM   LookupProduct  
    WHERE ProductID=?  
    ```  
  
9. <span data-ttu-id="eeb6b-125">单击转换选项卡。删除默认数据转换"Transform"，并改为创建 ActiveX 转换。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-125">Click the Transformations tab. Delete the default data transformation "Transform", and create ActiveX transformation instead.</span></span> <span data-ttu-id="eeb6b-126">单击源列，然后添加所有列。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-126">Click Source Columns and add all columns.</span></span> <span data-ttu-id="eeb6b-127">单击目标列并添加所有列。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-127">Click Destination Columns and add all columns.</span></span>  
  
10. <span data-ttu-id="eeb6b-128">单击常规选项卡，然后属性。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-128">Click the General tab, and then Properties.</span></span> <span data-ttu-id="eeb6b-129">这将自动生成的脚本的执行普通复制转换所示：</span><span class="sxs-lookup"><span data-stu-id="eeb6b-129">This results in automatic generation of a script that performs the trivial copy transformation as shown:</span></span>  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("ProductName") = DTSSource("ProductName")  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
11. <span data-ttu-id="eeb6b-130">使用查找，如所示更改值：</span><span class="sxs-lookup"><span data-stu-id="eeb6b-130">Change the value by using the lookup as shown:</span></span>  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("Product")= _  
                      DTSLookups( "LookupProductByID" ).Execute(  _                                  DTSSource("Product"))  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
12. <span data-ttu-id="eeb6b-131">保存并运行包。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-131">Save and then run the package.</span></span>  
  
13. <span data-ttu-id="eeb6b-132">请确保正确的数据最终都会在 OLAP 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-132">Ensure that the correct data ends up in the OLAP cube.</span></span> <span data-ttu-id="eeb6b-133">你应将包保存为 VBScript 或结构化的存储文件，因为它包含自定义代码，而不仅仅是自动生成步骤，可从 BAM。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-133">You should save the package as VBScript or a structured storage file, because it contains your custom code, not just the auto-generated steps from BAM.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eeb6b-134">查找仅适用于使用 DTS 和 OLAP 执行计划的报表。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-134">The lookup works only for the scheduled reports that you perform with DTS and OLAP.</span></span> <span data-ttu-id="eeb6b-135">如果需要比在实时聚合收集了哪些信息不同的数据，然后必须调用 BAM API 之前检索数据。</span><span class="sxs-lookup"><span data-stu-id="eeb6b-135">If you need different data than what is collected in the real-time aggregation, then you must retrieve the data before calling the BAM API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb6b-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="eeb6b-136">See Also</span></span>  
 <span data-ttu-id="eeb6b-137">[使用业务活动监视](../core/using-business-activity-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="eeb6b-137">[Using Business Activity Monitoring](../core/using-business-activity-monitoring.md) </span></span>  
 [<span data-ttu-id="eeb6b-138">部署已本地化的 BAM XML 文件</span><span class="sxs-lookup"><span data-stu-id="eeb6b-138">Deploying Localized BAM XML Files</span></span>](../core/deploying-localized-bam-xml-files.md)