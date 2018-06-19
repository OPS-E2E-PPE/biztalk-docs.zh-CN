---
title: 如何丰富 BAM 数据使用查找 |Microsoft 文档
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
ms.openlocfilehash: 43b42b42158bc3b3c179d624340a97a890072a17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253909"
---
# <a name="how-to-enrich-bam-data-using-lookups"></a><span data-ttu-id="65b20-102">如何使用查找 BAM 数据扩充</span><span class="sxs-lookup"><span data-stu-id="65b20-102">How to Enrich BAM Data Using Lookups</span></span>
<span data-ttu-id="65b20-103">在某些情况下，操作时可用的数据并不包含报告所需的全部信息。</span><span class="sxs-lookup"><span data-stu-id="65b20-103">There are cases in which the data that is available at operation time does not contain everything you need for reporting purposes.</span></span> <span data-ttu-id="65b20-104">例如，在运行时，可能有 ProductID 但没有 ProductName。</span><span class="sxs-lookup"><span data-stu-id="65b20-104">For example, you may have a ProductID but not a ProductName at runtime.</span></span> <span data-ttu-id="65b20-105">由于 BAM 活动表示的是与数据的实际收集方式无关的抽象概念，因此应包含要在报告“ProductName”中看到的称为最终数据的项。</span><span class="sxs-lookup"><span data-stu-id="65b20-105">Since the BAM Activity represents an abstraction independent of how the data is actually collected, it should contain an item named as the final data that you want to see in the report "ProductName".</span></span> <span data-ttu-id="65b20-106">与任何其他项一样，您也可以在解释性结构（如里程碑组、持续时间、维度和度量）中使用此项。</span><span class="sxs-lookup"><span data-stu-id="65b20-106">Just like any other item, you can use this in interpretive constructs such as milestone groups, durations, dimensions, and measures.</span></span> <span data-ttu-id="65b20-107">由于 ProductName 运行时不可用，因此您必须获得其他执行查找所需的数据，如 ProductID。</span><span class="sxs-lookup"><span data-stu-id="65b20-107">Since the ProductName is not available at runtime, you must get some additional data that is sufficient for performing a lookup, such as the ProductID.</span></span>  
  
 <span data-ttu-id="65b20-108">您应该收集同一列中的数据，而不是报告所需的数据。</span><span class="sxs-lookup"><span data-stu-id="65b20-108">You should collect the data in the same column, instead of the data that you need for reports.</span></span> <span data-ttu-id="65b20-109">例如，应该在运行时收集 ProductID 而不是 ProductName。</span><span class="sxs-lookup"><span data-stu-id="65b20-109">For example, you should collect the ProductID instead of ProductName at runtime.</span></span> <span data-ttu-id="65b20-110">如果需要多列，可以在活动中创建多个项，但不要在任何视图中使用它们。</span><span class="sxs-lookup"><span data-stu-id="65b20-110">If more columns are required, you may create more items in the activity but not use them in any View.</span></span>  
  
### <a name="to-enrich-bam-data-via-lookups"></a><span data-ttu-id="65b20-111">通过查找丰富 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="65b20-111">To enrich BAM data via lookups</span></span>  
  
1.  <span data-ttu-id="65b20-112">部署 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="65b20-112">Deploy your BAM definition.</span></span>  
  
2.  <span data-ttu-id="65b20-113">在 SQL Server Management Studio 中，添加包含感兴趣数据的服务器作为远程服务器。</span><span class="sxs-lookup"><span data-stu-id="65b20-113">In SQL Server Management Studio, add the server that contains the data of interest as a remote server.</span></span>  
  
3.  <span data-ttu-id="65b20-114">找到名为 BAM_AN_`<View Name>` 的数据分析包。</span><span class="sxs-lookup"><span data-stu-id="65b20-114">Locate the data analysis package named BAM_AN_`<View Name>`.</span></span> <span data-ttu-id="65b20-115">例如，如果视图为 SalesMgr，则该包名为 BAM_AN_SalesMgr。</span><span class="sxs-lookup"><span data-stu-id="65b20-115">For example if the view is SalesMgr, this will be BAM_AN_SalesMgr.</span></span>  
  
4.  <span data-ttu-id="65b20-116">设置包视图的放大比例（例如 100%）</span><span class="sxs-lookup"><span data-stu-id="65b20-116">Set the zoom to magnify the view of the package (e.g. 100%)</span></span>  
  
5.  <span data-ttu-id="65b20-117">添加要在查找中使用的 SQL 连接。</span><span class="sxs-lookup"><span data-stu-id="65b20-117">Add a SQL connection that you will be using in the lookups.</span></span>  
  
6.  <span data-ttu-id="65b20-118">完成“清除过渡数据库”步骤后，找到相应的转换数据任务。</span><span class="sxs-lookup"><span data-stu-id="65b20-118">Locate the transform data task after the step "Cleanup Staging".</span></span> <span data-ttu-id="65b20-119">过渡数据库是将数据从主导入数据库移至星型架构数据库过程中需要使用的位置。</span><span class="sxs-lookup"><span data-stu-id="65b20-119">This is where you move the data from the PrimaryImport to the StarSchema database.</span></span> <span data-ttu-id="65b20-120">有两个实例，此任务-一个用于已完成的活动，另一个正在进行。</span><span class="sxs-lookup"><span data-stu-id="65b20-120">There are two instances of this task—one for the completed activities, and another for the one that is in progress.</span></span> <span data-ttu-id="65b20-121">为这两项任务执行下述其余步骤。</span><span class="sxs-lookup"><span data-stu-id="65b20-121">Apply all the rest of the steps to both tasks.</span></span>  
  
7.  <span data-ttu-id="65b20-122">单击“转换”。</span><span class="sxs-lookup"><span data-stu-id="65b20-122">Click the transformation.</span></span>  
  
8.  <span data-ttu-id="65b20-123">选择“查找”；使用查找连接添加查找“LookupProductByID”（有关查找的信息，请参阅《SQL 联机丛书》）。</span><span class="sxs-lookup"><span data-stu-id="65b20-123">Select Lookups; add your lookup "LookupProductByID" using the lookup connection (see SQL books online for lookups).</span></span> <span data-ttu-id="65b20-124">例如，如果查找的是一个包含 ProductID 列和 ProductName 列的简单表“LookupProduct”，则查找的文本将为：</span><span class="sxs-lookup"><span data-stu-id="65b20-124">If for example the lookup is a simple table "LookupProduct", the with columns ProductID and ProductName, the text of the lookup will be:</span></span>  
  
    ```  
    SELECT ProductName  
    FROM   LookupProduct  
    WHERE ProductID=?  
    ```  
  
9. <span data-ttu-id="65b20-125">单击“转换”选项卡。删除默认数据转换“Transform”，创建 ActiveX 转换。</span><span class="sxs-lookup"><span data-stu-id="65b20-125">Click the Transformations tab. Delete the default data transformation "Transform", and create ActiveX transformation instead.</span></span> <span data-ttu-id="65b20-126">单击“源列”，然后添加所有列。</span><span class="sxs-lookup"><span data-stu-id="65b20-126">Click Source Columns and add all columns.</span></span> <span data-ttu-id="65b20-127">单击“目标列”，然后添加所有列。</span><span class="sxs-lookup"><span data-stu-id="65b20-127">Click Destination Columns and add all columns.</span></span>  
  
10. <span data-ttu-id="65b20-128">常规选项卡上，依次单击和属性。</span><span class="sxs-lookup"><span data-stu-id="65b20-128">Click the General tab, and then Properties.</span></span> <span data-ttu-id="65b20-129">这将自动生成如下所示的、执行不太重要的复制转换的脚本：</span><span class="sxs-lookup"><span data-stu-id="65b20-129">This results in automatic generation of a script that performs the trivial copy transformation as shown:</span></span>  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("ProductName") = DTSSource("ProductName")  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
11. <span data-ttu-id="65b20-130">使用查找更改值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="65b20-130">Change the value by using the lookup as shown:</span></span>  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("Product")= _  
                      DTSLookups( "LookupProductByID" ).Execute(  _                                  DTSSource("Product"))  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
12. <span data-ttu-id="65b20-131">保存并运行该程序包。</span><span class="sxs-lookup"><span data-stu-id="65b20-131">Save and then run the package.</span></span>  
  
13. <span data-ttu-id="65b20-132">确保正确的数据在 OLAP 多维数据集中结束。</span><span class="sxs-lookup"><span data-stu-id="65b20-132">Ensure that the correct data ends up in the OLAP cube.</span></span> <span data-ttu-id="65b20-133">应该将该程序包保存为 VBScript 或结构化存储文件，因为它还包含您自定义的代码，而不仅仅是 BAM 自动生成的步骤。</span><span class="sxs-lookup"><span data-stu-id="65b20-133">You should save the package as VBScript or a structured storage file, because it contains your custom code, not just the auto-generated steps from BAM.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65b20-134">查找仅适用于使用 DTS 和 OLAP 执行的计划报告。</span><span class="sxs-lookup"><span data-stu-id="65b20-134">The lookup works only for the scheduled reports that you perform with DTS and OLAP.</span></span> <span data-ttu-id="65b20-135">如果需要实时聚合收集的数据以外的其他数据，则在调用 BAM API 之前必须检索这些数据。</span><span class="sxs-lookup"><span data-stu-id="65b20-135">If you need different data than what is collected in the real-time aggregation, then you must retrieve the data before calling the BAM API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b20-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65b20-136">See Also</span></span>  
 <span data-ttu-id="65b20-137">[使用业务活动监视](../core/using-business-activity-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="65b20-137">[Using Business Activity Monitoring](../core/using-business-activity-monitoring.md) </span></span>  
 [<span data-ttu-id="65b20-138">部署本地化的 BAM XML 文件</span><span class="sxs-lookup"><span data-stu-id="65b20-138">Deploying Localized BAM XML Files</span></span>](../core/deploying-localized-bam-xml-files.md)