---
title: "插入、 更新、 删除或选择接口表和视图使用 WCF 服务模型的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae613c0e-4d9a-4c66-99e4-dd0443f1d495
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fc9e3968b760be10b428e39662ec3d09db490cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="insert-update-delete-or-select-operations-on-interface-tables-and-views-using-the-wcf-service-model"></a><span data-ttu-id="f9619-102">插入、 更新、 删除或选择接口表和视图使用 WCF 服务模型的操作</span><span class="sxs-lookup"><span data-stu-id="f9619-102">Insert, update, delete, or select operations on interface tables and views using the WCF service model</span></span>
<span data-ttu-id="f9619-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]发现一组接口表上的基本 Insert、 Select、 Update 和 Delete 操作。</span><span class="sxs-lookup"><span data-stu-id="f9619-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on interface tables.</span></span> <span data-ttu-id="f9619-104">通过使用这些操作，你可以执行简单的 Insert、 Select、 Update 和 Delete 语句由 WHERE 子句目标接口表限定。</span><span class="sxs-lookup"><span data-stu-id="f9619-104">By using these operations, you can perform simple Insert, Select, Update, and Delete statements qualified by a WHERE clause on a target interface table.</span></span> <span data-ttu-id="f9619-105">本主题将说明了如何使用 WCF 服务模型执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="f9619-105">This topic provides instructions on how to perform these operations using the WCF service model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9619-106">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持仅选择界面视图上的操作。</span><span class="sxs-lookup"><span data-stu-id="f9619-106">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports only Select operations on interface views.</span></span>  
  
 <span data-ttu-id="f9619-107">有关如何适配器支持这些操作的详细信息，请参阅[接口表和接口视图上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)。</span><span class="sxs-lookup"><span data-stu-id="f9619-107">For more information about how the adapter supports these operations, see [Operations on Interface Tables and Interface Views](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="f9619-108">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="f9619-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="f9619-109">本主题中的示例对执行 MS_SAMPLE_EMPLOYEE 接口表操作。</span><span class="sxs-lookup"><span data-stu-id="f9619-109">The example in this topic performs operations on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="f9619-110">通过运行这些示例使用提供的脚本创建表。</span><span class="sxs-lookup"><span data-stu-id="f9619-110">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="f9619-111">有关示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="f9619-111">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="f9619-112">示例中， **Interface_Table_Ops**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="f9619-112">A sample, **Interface_Table_Ops**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="f9619-113">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="f9619-113">The WCF Client Class</span></span>  
 <span data-ttu-id="f9619-114">WCF 客户端生成的基本操作的名称，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]发现基于名称的表或视图，如以下表中列出。</span><span class="sxs-lookup"><span data-stu-id="f9619-114">The name of the WCF client generated for the basic operations that the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers is based on the name of the table or view, as listed in the following table.</span></span>  
  
|<span data-ttu-id="f9619-115">项目</span><span class="sxs-lookup"><span data-stu-id="f9619-115">Artifact</span></span>|<span data-ttu-id="f9619-116">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="f9619-116">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="f9619-117">接口表</span><span class="sxs-lookup"><span data-stu-id="f9619-117">Interface tables</span></span>|<span data-ttu-id="f9619-118">InterfaceTables_ [APP_NAME] _ [架构]\_[TABLE_NAME] 客户端</span><span class="sxs-lookup"><span data-stu-id="f9619-118">InterfaceTables_[APP_NAME]_[SCHEMA]\_[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="f9619-119">界面视图</span><span class="sxs-lookup"><span data-stu-id="f9619-119">Interface views</span></span>|<span data-ttu-id="f9619-120">InterfaceViews_ [APP_NAME] _ [架构]\_[VIEW_NAME] 客户端</span><span class="sxs-lookup"><span data-stu-id="f9619-120">InterfaceViews_[APP_NAME]_[SCHEMA]\_[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="f9619-121">[APP_NAME] = Oracle E-business Suite 应用程序; 实际名称例如，查找。</span><span class="sxs-lookup"><span data-stu-id="f9619-121">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  
  
 <span data-ttu-id="f9619-122">[架构] = 项目; 的集合例如，应用程序。</span><span class="sxs-lookup"><span data-stu-id="f9619-122">[SCHEMA] = Collection of artifacts; for example, APPS.</span></span>  
  
 <span data-ttu-id="f9619-123">[TABLE_NAME] = 表; 的名称例如，MS_SAMPLE_EMPLOYEE。</span><span class="sxs-lookup"><span data-stu-id="f9619-123">[TABLE_NAME] = The name of the table; for example, MS_SAMPLE_EMPLOYEE.</span></span>  
  
 <span data-ttu-id="f9619-124">[VIEW_NAME] = 视图; 的名称例如，MS_SAMPLE_EMPLOYEE_View。</span><span class="sxs-lookup"><span data-stu-id="f9619-124">[VIEW_NAME] = The name of the view; for example, MS_SAMPLE_EMPLOYEE_View.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="f9619-125">调用对表的操作的方法签名</span><span class="sxs-lookup"><span data-stu-id="f9619-125">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="f9619-126">下表显示在表上的基本操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="f9619-126">The following table shows the method signatures for the basic operations on an table.</span></span> <span data-ttu-id="f9619-127">签名是相同的视图，只不过视图命名空间和名称替换那些表。</span><span class="sxs-lookup"><span data-stu-id="f9619-127">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="f9619-128">运算</span><span class="sxs-lookup"><span data-stu-id="f9619-128">Operation</span></span>|<span data-ttu-id="f9619-129">方法签名</span><span class="sxs-lookup"><span data-stu-id="f9619-129">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="f9619-130">Insert</span><span class="sxs-lookup"><span data-stu-id="f9619-130">Insert</span></span>|<span data-ttu-id="f9619-131">字符串插入 (InsertRecord [] 记录集);</span><span class="sxs-lookup"><span data-stu-id="f9619-131">string Insert(InsertRecord[] RECORDSET);</span></span>|  
|<span data-ttu-id="f9619-132">选择</span><span class="sxs-lookup"><span data-stu-id="f9619-132">Select</span></span>|<span data-ttu-id="f9619-133">SelectRecord [] 选择 （字符串 COLUMN_NAMES，字符串筛选器）;</span><span class="sxs-lookup"><span data-stu-id="f9619-133">SelectRecord[] Select(string COLUMN_NAMES, string FILTER);</span></span>|  
|<span data-ttu-id="f9619-134">Update</span><span class="sxs-lookup"><span data-stu-id="f9619-134">Update</span></span>|<span data-ttu-id="f9619-135">字符串更新 （UpdateRecord 记录集，筛选器字符串）;</span><span class="sxs-lookup"><span data-stu-id="f9619-135">string Update(UpdateRecord RECORDSET, string FILTER);</span></span>|  
|<span data-ttu-id="f9619-136">DELETE</span><span class="sxs-lookup"><span data-stu-id="f9619-136">Delete</span></span>|<span data-ttu-id="f9619-137">字符串删除 （字符串筛选器）;</span><span class="sxs-lookup"><span data-stu-id="f9619-137">string Delete(string FILTER);</span></span>|  
  
 <span data-ttu-id="f9619-138">例如，下面的代码演示生成 WCF 客户端类的方法签名的删除、 插入、 选择和更新下的默认应用架构的 MS_SAMPLE_EMPLOYEE 接口表上的操作。</span><span class="sxs-lookup"><span data-stu-id="f9619-138">As an example, the following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the MS_SAMPLE_EMPLOYEE interface table under the default APPS schema.</span></span>  
  
```  
public partial class InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient : System.ServiceModel.ClientBase<InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE>, InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {      
    public SelectRecord[] Select(string COLUMN_NAMES, string FILTER);  
  
    public string Insert(InsertRecord[] RECORDSET);  
  
    public string Update(UpdateRecord RECORDSET, string FILTER);  
  
    public string Delete(string FILTER);  
}  
```  
  
 <span data-ttu-id="f9619-139">在此代码段， **InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient**是 WCF 中的类的生成的 OracleEBSBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f9619-139">In this snippet, **InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-table-operations"></a><span data-ttu-id="f9619-140">参数用于表操作</span><span class="sxs-lookup"><span data-stu-id="f9619-140">Parameters for Table Operations</span></span>  
 <span data-ttu-id="f9619-141">本部分提供每个表操作所需的参数</span><span class="sxs-lookup"><span data-stu-id="f9619-141">This section provides the parameters required by each table operation</span></span>  
  
 <span data-ttu-id="f9619-142">**选择操作**</span><span class="sxs-lookup"><span data-stu-id="f9619-142">**Select Operation**</span></span>  
  
|<span data-ttu-id="f9619-143">COLUMN_NAMES</span><span class="sxs-lookup"><span data-stu-id="f9619-143">COLUMN_NAMES</span></span>|<span data-ttu-id="f9619-144">FILTER</span><span class="sxs-lookup"><span data-stu-id="f9619-144">FILTER</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="f9619-145">以逗号分隔的目标; 中的列名称列表例如，"EMP_NO，指定内容"。</span><span class="sxs-lookup"><span data-stu-id="f9619-145">A comma-delimited list of column names in the target; for example, "EMP_NO, DESIGNATION".</span></span> <span data-ttu-id="f9619-146">列列表指定应在结果集中返回目标的列。</span><span class="sxs-lookup"><span data-stu-id="f9619-146">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="f9619-147">未指定列列表中的列将设置为其.NET 默认值中返回的记录集。</span><span class="sxs-lookup"><span data-stu-id="f9619-147">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="f9619-148">对于 nillable 列，此值是**null**。</span><span class="sxs-lookup"><span data-stu-id="f9619-148">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="f9619-149">指定的查询; 的目标行的 WHERE 子句的内容例如，"指定内容 = '经理'"。</span><span class="sxs-lookup"><span data-stu-id="f9619-149">The contents of a WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="f9619-150">你可以将此参数设置为**null**返回目标的所有行。</span><span class="sxs-lookup"><span data-stu-id="f9619-150">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="f9619-151">选择操作的返回值是一个强类型化结果集包含指定的列和行。</span><span class="sxs-lookup"><span data-stu-id="f9619-151">The return value for a Select operation is a strongly-typed result set that contains the specified columns and rows.</span></span>  
  
 <span data-ttu-id="f9619-152">**插入操作**</span><span class="sxs-lookup"><span data-stu-id="f9619-152">**Insert Operation**</span></span>  
  
|<span data-ttu-id="f9619-153">插入操作类型</span><span class="sxs-lookup"><span data-stu-id="f9619-153">Insert operation type</span></span>|<span data-ttu-id="f9619-154">记录集</span><span class="sxs-lookup"><span data-stu-id="f9619-154">RECORDSET</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="f9619-155">多个记录</span><span class="sxs-lookup"><span data-stu-id="f9619-155">Multiple record</span></span>|<span data-ttu-id="f9619-156">应插入到表的 INSERTRECORDS 的集合。</span><span class="sxs-lookup"><span data-stu-id="f9619-156">A collection of INSERTRECORDS that should be inserted into the table.</span></span>|  
  
 <span data-ttu-id="f9619-157">插入操作的返回值是插入的行数。</span><span class="sxs-lookup"><span data-stu-id="f9619-157">The return value for an Insert operation is the number of rows inserted.</span></span>  
  
 <span data-ttu-id="f9619-158">**更新操作**</span><span class="sxs-lookup"><span data-stu-id="f9619-158">**Update Operation**</span></span>  
  
|<span data-ttu-id="f9619-159">记录集</span><span class="sxs-lookup"><span data-stu-id="f9619-159">RECORDSET</span></span>|<span data-ttu-id="f9619-160">FILTER</span><span class="sxs-lookup"><span data-stu-id="f9619-160">FILTER</span></span>|  
|---------------|------------|  
|<span data-ttu-id="f9619-161">应在表中更新的记录的集合。</span><span class="sxs-lookup"><span data-stu-id="f9619-161">A collection of records that should be updated in the table.</span></span>|<span data-ttu-id="f9619-162">指定的查询; 的目标行的 WHERE 子句的内容例如，"指定内容 = '经理'"。</span><span class="sxs-lookup"><span data-stu-id="f9619-162">The contents of a WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="f9619-163">你可以将此参数设置为**null**返回目标的所有行。</span><span class="sxs-lookup"><span data-stu-id="f9619-163">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="f9619-164">对于更新操作的返回值是更新的行数。</span><span class="sxs-lookup"><span data-stu-id="f9619-164">The return value for an Update operation is the number of rows updated.</span></span>  
  
 <span data-ttu-id="f9619-165">**删除操作**</span><span class="sxs-lookup"><span data-stu-id="f9619-165">**Delete Operation**</span></span>  
  
 <span data-ttu-id="f9619-166">删除操作将作为输入的 WHERE 子句，指定要删除的行。</span><span class="sxs-lookup"><span data-stu-id="f9619-166">The Delete operation takes as input a WHERE clause that specifies the rows to be deleted.</span></span> <span data-ttu-id="f9619-167">删除操作的返回值是删除的行数。</span><span class="sxs-lookup"><span data-stu-id="f9619-167">The return value for a Delete operation is the number of rows deleted.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-interface-tables-and-interface-views"></a><span data-ttu-id="f9619-168">创建 WCF 客户端来调用接口表上的操作和接口视图</span><span class="sxs-lookup"><span data-stu-id="f9619-168">Creating a WCF Client to Invoke Operations on Interface Tables and Interface Views</span></span>  
 <span data-ttu-id="f9619-169">泛型组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="f9619-169">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF channel model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="f9619-170">本部分介绍如何创建 WCF 客户端来调用基本插入、 选择、 更新接口表上的删除操作。</span><span class="sxs-lookup"><span data-stu-id="f9619-170">This section describes how to create a WCF client to invoke basic Insert, Select, Update, Delete operations on an interface table.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a><span data-ttu-id="f9619-171">若要创建的 WCF 客户端，以对表执行操作</span><span class="sxs-lookup"><span data-stu-id="f9619-171">To create a WCF client to perform operations on tables</span></span>  
  
1.  <span data-ttu-id="f9619-172">在 Visual Studio 中创建 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="f9619-172">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="f9619-173">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="f9619-173">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="f9619-174">生成 WCF 客户端类插入、 选择、 更新和删除 MS_SAMPLE_EMPLOYEE 接口表上的操作。</span><span class="sxs-lookup"><span data-stu-id="f9619-174">Generate the WCF client class for the Insert, Select, Update, and Delete operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="f9619-175">有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="f9619-175">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f9619-176">在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。</span><span class="sxs-lookup"><span data-stu-id="f9619-176">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="f9619-177">在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="f9619-177">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="f9619-178">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="f9619-178">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  <span data-ttu-id="f9619-179">打开 Program.cs 文件并创建客户端，如下面的代码段中所述。</span><span class="sxs-lookup"><span data-stu-id="f9619-179">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
    InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient client = new InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient(binding, address);  
    ```  
  
     <span data-ttu-id="f9619-180">在此代码段，`InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="f9619-180">In this snippet, `InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="f9619-181">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f9619-181">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9619-182">在此代码段，则显式应用程序代码中指定的绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="f9619-182">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="f9619-183">你可以从还生成的应用程序配置文件 app.config，使用这些值[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f9619-183">You can use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="f9619-184">指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="f9619-184">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="f9619-185">为客户端设置的凭据。</span><span class="sxs-lookup"><span data-stu-id="f9619-185">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  <span data-ttu-id="f9619-186">由于您正在执行对接口表的操作，必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="f9619-186">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="f9619-187">在此示例中，若要设置应用程序上下文中，你指定**OracleUserName**， **OraclePassword**，和**OracleEBSResponsibilityName**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="f9619-187">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="f9619-188">有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="f9619-188">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  <span data-ttu-id="f9619-189">下面的代码段中所述，请打开客户端：</span><span class="sxs-lookup"><span data-stu-id="f9619-189">Open the client as described in the snippet below:</span></span>  
  
    ```  
    try  
    {  
       Console.WriteLine("Opening Client...");  
       client.Open();  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    ```  
  
9. <span data-ttu-id="f9619-190">调用 MS_SAMPLE_EMPLOYEE 表上的插入操作。</span><span class="sxs-lookup"><span data-stu-id="f9619-190">Invoke the Insert operation on the MS_SAMPLE_EMPLOYEE table.</span></span>  
  
    ```  
    Console.WriteLine("The application will insert a record in the MS_SAMPLE_EMPLOYEE interface table");  
  
    // The date values cannot contain time zone information. Hence, you must use  
    // DateTimeKind.Unspecified to not include the time zone information.  
    DateTime date = new DateTime(DateTime.Now.Ticks, DateTimeKind.Unspecified);  
  
    string result;  
  
    InsertRecord[] recordSet = new InsertRecord[1];  
  
    EMP_NO__COMPLEX_TYPE emp_no = new EMP_NO__COMPLEX_TYPE();  
    emp_no.Value = "10007";  
  
    NAME__COMPLEX_TYPE name = new NAME__COMPLEX_TYPE();  
    name.Value = "John Smith";  
  
    DESIGNATION__COMPLEX_TYPE desig = new DESIGNATION__COMPLEX_TYPE();  
    desig.Value = "Manager";  
  
    SALARY__COMPLEX_TYPE salary = new SALARY__COMPLEX_TYPE();  
    salary.Value = "500000";  
  
    JOIN_DATE__COMPLEX_TYPE doj = new JOIN_DATE__COMPLEX_TYPE();  
    doj.Value = date;  
  
    recordSet[0] = new InsertRecord();  
    recordSet[0].EMP_NO = emp_no;  
    recordSet[0].NAME = name;  
    recordSet[0].DESIGNATION = desig;  
    recordSet[0].SALARY = salary;  
    recordSet[0].JOIN_DATE = doj;  
  
    try  
    {  
       result = client.Insert(recordSet);   
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    Console.WriteLine("Number of records inserted= " + result);  
    Console.WriteLine("Press any key to continue...");  
    Console.ReadLine();  
  
    ```  
  
     <span data-ttu-id="f9619-191">你可以替换前面的代码段，来执行选择、 更新或删除操作以及。</span><span class="sxs-lookup"><span data-stu-id="f9619-191">You can replace the preceding code snippet to perform Select, Update, or Delete operations as well.</span></span> <span data-ttu-id="f9619-192">你还可以将代码片段，可在单个应用程序中执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="f9619-192">You can also append the code snippets to perform all operation in a single application.</span></span> <span data-ttu-id="f9619-193">有关如何执行这些操作的代码段，请参阅[选择操作](#BKMK_Select)，[更新操作](#BKMK_Update)，和[删除操作](#BKMK_Delete)分别。</span><span class="sxs-lookup"><span data-stu-id="f9619-193">For code snippets on how to perform these operations, see [Select Operation](#BKMK_Select), [Update Operation](#BKMK_Update), and [Delete Operation](#BKMK_Delete) respectively.</span></span>  
  
10. <span data-ttu-id="f9619-194">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="f9619-194">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. <span data-ttu-id="f9619-195">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="f9619-195">Build the project and then run it.</span></span> <span data-ttu-id="f9619-196">应用程序在 MS_SAMPLE_EMPLOYEE 表中插入一条记录。</span><span class="sxs-lookup"><span data-stu-id="f9619-196">The application inserts a record in the MS_SAMPLE_EMPLOYEE table.</span></span>  
  
###  <span data-ttu-id="f9619-197"><a name="BKMK_Select"></a>选择操作</span><span class="sxs-lookup"><span data-stu-id="f9619-197"><a name="BKMK_Select"></a> Select Operation</span></span>  
 <span data-ttu-id="f9619-198">下面的代码演示了面向 MS_SAMPLE_EMPLOYEE 接口表选择操作。</span><span class="sxs-lookup"><span data-stu-id="f9619-198">The following code shows a Select operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="f9619-199">选择操作选择的最新记录插入到表。</span><span class="sxs-lookup"><span data-stu-id="f9619-199">The Select operation selects the last record inserted into the table.</span></span> <span data-ttu-id="f9619-200">返回的记录写入控制台。</span><span class="sxs-lookup"><span data-stu-id="f9619-200">The returned record is written to the console.</span></span>  
  
```  
Console.WriteLine("The application will now select the last inserted record");  
SelectRecord[] selectRecords;  
try  
{  
   selectRecords = client.Select("*", "WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("The details of the newly added employee are:");  
Console.WriteLine("********************************************");  
for (int i = 0; i < selectRecords.Length; i++)  
{  
   Console.WriteLine("Employee ID         : " + selectRecords[i].EMP_NO);  
   Console.WriteLine("Employee Name       : " + selectRecords[i].NAME);  
   Console.WriteLine("Employee Desigation : " + selectRecords[i].DESIGNATION);  
   Console.WriteLine("Employee Salary     : " + selectRecords[i].SALARY);  
   Console.WriteLine();  
}  
Console.WriteLine("********************************************");  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###  <span data-ttu-id="f9619-201"><a name="BKMK_Update"></a>更新操作</span><span class="sxs-lookup"><span data-stu-id="f9619-201"><a name="BKMK_Update"></a> Update Operation</span></span>  
 <span data-ttu-id="f9619-202">下面的代码演示了面向 MS_SAMPLE_EMPLOYEE 接口表的更新操作。</span><span class="sxs-lookup"><span data-stu-id="f9619-202">The following code shows an Update operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
```  
Console.WriteLine("The application will now update the employee name in the newly inserted record");  
string recordsUpdated;  
UpdateRecord updateRecordSet = new UpdateRecord();  
updateRecordSet.NAME = "Tom Smith";  
updateRecordSet.DESIGNATION = "Accountant";  
  
try  
{  
   recordsUpdated = client.Update(updateRecordSet, "WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("No of records updated: " + recordsUpdated);  
Console.WriteLine("Press any key to continue...");  
Console.ReadLine();  
```  
  
###  <span data-ttu-id="f9619-203"><a name="BKMK_Delete"></a>删除操作</span><span class="sxs-lookup"><span data-stu-id="f9619-203"><a name="BKMK_Delete"></a> Delete Operation</span></span>  
 <span data-ttu-id="f9619-204">下面的代码演示了面向 MS_SAMPLE_EMPLOYEE 接口表的删除操作。</span><span class="sxs-lookup"><span data-stu-id="f9619-204">The following code shows a Delete operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
```  
Console.WriteLine("The sample will now delete the record that it first inserted");  
string deletedRecords;  
try  
{  
   deletedRecords = client.Delete("WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
Console.WriteLine("No of records deleted: " + deletedRecords);  
Console.WriteLine("Press any key to exit...");  
Console.ReadLine();  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9619-205">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9619-205">See Also</span></span>  
 [<span data-ttu-id="f9619-206">开发 Oracle E-business Suite 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="f9619-206">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)