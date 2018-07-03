---
title: 插入、 更新、 删除或选择对界面表和视图使用 WCF 服务模型的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae613c0e-4d9a-4c66-99e4-dd0443f1d495
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ed57328a925496449ddd73f3c363b32f60dc811
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983470"
---
# <a name="insert-update-delete-or-select-operations-on-interface-tables-and-views-using-the-wcf-service-model"></a><span data-ttu-id="4d99d-102">插入、 更新、 删除或选择对界面表和视图使用 WCF 服务模型的操作</span><span class="sxs-lookup"><span data-stu-id="4d99d-102">Insert, update, delete, or select operations on interface tables and views using the WCF service model</span></span>
<span data-ttu-id="4d99d-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]找到一组基本的 Insert、 Select、 Update 和 Delete 操作上的接口表。</span><span class="sxs-lookup"><span data-stu-id="4d99d-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on interface tables.</span></span> <span data-ttu-id="4d99d-104">通过使用这些操作，你可以执行简单的 Insert、 Select、 Update 和 Delete 语句由目标接口表上的 WHERE 子句限定。</span><span class="sxs-lookup"><span data-stu-id="4d99d-104">By using these operations, you can perform simple Insert, Select, Update, and Delete statements qualified by a WHERE clause on a target interface table.</span></span> <span data-ttu-id="4d99d-105">本主题将说明了如何使用 WCF 服务模型执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="4d99d-105">This topic provides instructions on how to perform these operations using the WCF service model.</span></span>  

> [!NOTE]
>  <span data-ttu-id="4d99d-106">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持仅选择界面视图上的操作。</span><span class="sxs-lookup"><span data-stu-id="4d99d-106">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports only Select operations on interface views.</span></span>  

 <span data-ttu-id="4d99d-107">有关适配器如何支持这些操作的详细信息，请参阅[对界面表和界面视图操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)。</span><span class="sxs-lookup"><span data-stu-id="4d99d-107">For more information about how the adapter supports these operations, see [Operations on Interface Tables and Interface Views](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="4d99d-108">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="4d99d-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="4d99d-109">本主题中的示例执行 MS_SAMPLE_EMPLOYEE 接口表的操作。</span><span class="sxs-lookup"><span data-stu-id="4d99d-109">The example in this topic performs operations on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="4d99d-110">通过运行这些示例提供的脚本创建表。</span><span class="sxs-lookup"><span data-stu-id="4d99d-110">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="4d99d-111">有关示例的详细信息，请参阅[适用于 Oracle EBS 适配器示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="4d99d-111">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="4d99d-112">示例中， **Interface_Table_Ops**，后者基于本主题中，还提供与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="4d99d-112">A sample, **Interface_Table_Ops**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  

## <a name="the-wcf-client-class"></a><span data-ttu-id="4d99d-113">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="4d99d-113">The WCF Client Class</span></span>  
 <span data-ttu-id="4d99d-114">WCF 客户端生成的基本操作的名称，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可发现下表中列出基于表或视图的名称。</span><span class="sxs-lookup"><span data-stu-id="4d99d-114">The name of the WCF client generated for the basic operations that the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers is based on the name of the table or view, as listed in the following table.</span></span>  


|     <span data-ttu-id="4d99d-115">项目</span><span class="sxs-lookup"><span data-stu-id="4d99d-115">Artifact</span></span>     |                     <span data-ttu-id="4d99d-116">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="4d99d-116">WCF Client Name</span></span>                      |
|------------------|----------------------------------------------------------|
| <span data-ttu-id="4d99d-117">接口表</span><span class="sxs-lookup"><span data-stu-id="4d99d-117">Interface tables</span></span> | <span data-ttu-id="4d99d-118">[A p p _] InterfaceTables_*[SCHEMA]\\*[TABLE_NAME] 客户端</span><span class="sxs-lookup"><span data-stu-id="4d99d-118">InterfaceTables_[APP_NAME]*[SCHEMA]\\*[TABLE_NAME]Client</span></span> |
| <span data-ttu-id="4d99d-119">界面视图</span><span class="sxs-lookup"><span data-stu-id="4d99d-119">Interface views</span></span>  |  <span data-ttu-id="4d99d-120">[A p p _] InterfaceViews_*[SCHEMA]\\*[VIEW_NAME] 客户端</span><span class="sxs-lookup"><span data-stu-id="4d99d-120">InterfaceViews_[APP_NAME]*[SCHEMA]\\*[VIEW_NAME]Client</span></span>  |

 <span data-ttu-id="4d99d-121">[A p p _] = Oracle E-business Suite 应用程序; 的实际名称例如，查找。</span><span class="sxs-lookup"><span data-stu-id="4d99d-121">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  

 <span data-ttu-id="4d99d-122">[架构] = 集合的项目;例如，应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d99d-122">[SCHEMA] = Collection of artifacts; for example, APPS.</span></span>  

 <span data-ttu-id="4d99d-123">[TABLE_NAME] = 表; 的名称例如，MS_SAMPLE_EMPLOYEE。</span><span class="sxs-lookup"><span data-stu-id="4d99d-123">[TABLE_NAME] = The name of the table; for example, MS_SAMPLE_EMPLOYEE.</span></span>  

 <span data-ttu-id="4d99d-124">[VIEW_NAME] = 视图; 的名称例如，MS_SAMPLE_EMPLOYEE_View。</span><span class="sxs-lookup"><span data-stu-id="4d99d-124">[VIEW_NAME] = The name of the view; for example, MS_SAMPLE_EMPLOYEE_View.</span></span>  

### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="4d99d-125">调用表操作的方法签名</span><span class="sxs-lookup"><span data-stu-id="4d99d-125">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="4d99d-126">下表显示了上一个表的基本操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="4d99d-126">The following table shows the method signatures for the basic operations on an table.</span></span> <span data-ttu-id="4d99d-127">签名是相同的视图，只不过视图命名空间和名称替换这些表。</span><span class="sxs-lookup"><span data-stu-id="4d99d-127">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  

|<span data-ttu-id="4d99d-128">运算</span><span class="sxs-lookup"><span data-stu-id="4d99d-128">Operation</span></span>|<span data-ttu-id="4d99d-129">方法签名</span><span class="sxs-lookup"><span data-stu-id="4d99d-129">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="4d99d-130">Insert</span><span class="sxs-lookup"><span data-stu-id="4d99d-130">Insert</span></span>|<span data-ttu-id="4d99d-131">字符串插入 (InsertRecord [记录集);</span><span class="sxs-lookup"><span data-stu-id="4d99d-131">string Insert(InsertRecord[] RECORDSET);</span></span>|  
|<span data-ttu-id="4d99d-132">选择</span><span class="sxs-lookup"><span data-stu-id="4d99d-132">Select</span></span>|<span data-ttu-id="4d99d-133">SelectRecord [] 选择 (string COLUMN_NAMES，字符串筛选器);</span><span class="sxs-lookup"><span data-stu-id="4d99d-133">SelectRecord[] Select(string COLUMN_NAMES, string FILTER);</span></span>|  
|<span data-ttu-id="4d99d-134">Update</span><span class="sxs-lookup"><span data-stu-id="4d99d-134">Update</span></span>|<span data-ttu-id="4d99d-135">字符串更新 （UpdateRecord 记录集，筛选器字符串）;</span><span class="sxs-lookup"><span data-stu-id="4d99d-135">string Update(UpdateRecord RECORDSET, string FILTER);</span></span>|  
|<span data-ttu-id="4d99d-136">DELETE</span><span class="sxs-lookup"><span data-stu-id="4d99d-136">Delete</span></span>|<span data-ttu-id="4d99d-137">字符串删除 （字符串筛选器）;</span><span class="sxs-lookup"><span data-stu-id="4d99d-137">string Delete(string FILTER);</span></span>|  

 <span data-ttu-id="4d99d-138">例如，下面的代码演示生成的 WCF 客户端类的方法签名，删除操作，插入、 选择和更新的默认应用程序架构下的 MS_SAMPLE_EMPLOYEE 接口表的操作。</span><span class="sxs-lookup"><span data-stu-id="4d99d-138">As an example, the following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the MS_SAMPLE_EMPLOYEE interface table under the default APPS schema.</span></span>  

```  
public partial class InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient : System.ServiceModel.ClientBase<InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE>, InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {      
    public SelectRecord[] Select(string COLUMN_NAMES, string FILTER);  

    public string Insert(InsertRecord[] RECORDSET);  

    public string Update(UpdateRecord RECORDSET, string FILTER);  

    public string Delete(string FILTER);  
}  
```  

 <span data-ttu-id="4d99d-139">此代码片段**InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient**是 WCF 中的类的生成的 OracleEBSBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4d99d-139">In this snippet, **InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

### <a name="parameters-for-table-operations"></a><span data-ttu-id="4d99d-140">用于表操作的参数</span><span class="sxs-lookup"><span data-stu-id="4d99d-140">Parameters for Table Operations</span></span>  
 <span data-ttu-id="4d99d-141">本部分提供了每个表操作所需的参数</span><span class="sxs-lookup"><span data-stu-id="4d99d-141">This section provides the parameters required by each table operation</span></span>  

 <span data-ttu-id="4d99d-142">**选择操作**</span><span class="sxs-lookup"><span data-stu-id="4d99d-142">**Select Operation**</span></span>  

|<span data-ttu-id="4d99d-143">COLUMN_NAMES</span><span class="sxs-lookup"><span data-stu-id="4d99d-143">COLUMN_NAMES</span></span>|<span data-ttu-id="4d99d-144">FILTER</span><span class="sxs-lookup"><span data-stu-id="4d99d-144">FILTER</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="4d99d-145">以逗号分隔的目标; 中的列名称列表例如，"EMP_NO，指定"。</span><span class="sxs-lookup"><span data-stu-id="4d99d-145">A comma-delimited list of column names in the target; for example, "EMP_NO, DESIGNATION".</span></span> <span data-ttu-id="4d99d-146">列列表中指定的目标应在结果集中返回的列。</span><span class="sxs-lookup"><span data-stu-id="4d99d-146">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="4d99d-147">未指定列列表中的列将设置为其返回的记录集的.NET 默认值。</span><span class="sxs-lookup"><span data-stu-id="4d99d-147">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="4d99d-148">对于 nillable 列，此值是**null**。</span><span class="sxs-lookup"><span data-stu-id="4d99d-148">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="4d99d-149">指定查询; 的目标行的 WHERE 子句的内容例如，"名称 = Manager"。</span><span class="sxs-lookup"><span data-stu-id="4d99d-149">The contents of a WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="4d99d-150">可以将此参数设置为**null**返回目标的所有行。</span><span class="sxs-lookup"><span data-stu-id="4d99d-150">You can set this parameter to **null** to return all rows of the target.</span></span>|  

 <span data-ttu-id="4d99d-151">选择操作的返回值是强类型化结果集包含指定的列和行。</span><span class="sxs-lookup"><span data-stu-id="4d99d-151">The return value for a Select operation is a strongly-typed result set that contains the specified columns and rows.</span></span>  

 <span data-ttu-id="4d99d-152">**插入操作**</span><span class="sxs-lookup"><span data-stu-id="4d99d-152">**Insert Operation**</span></span>  

|<span data-ttu-id="4d99d-153">插入操作类型</span><span class="sxs-lookup"><span data-stu-id="4d99d-153">Insert operation type</span></span>|<span data-ttu-id="4d99d-154">记录集</span><span class="sxs-lookup"><span data-stu-id="4d99d-154">RECORDSET</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="4d99d-155">多个记录</span><span class="sxs-lookup"><span data-stu-id="4d99d-155">Multiple record</span></span>|<span data-ttu-id="4d99d-156">应插入到表的 INSERTRECORDS 的集合。</span><span class="sxs-lookup"><span data-stu-id="4d99d-156">A collection of INSERTRECORDS that should be inserted into the table.</span></span>|  

 <span data-ttu-id="4d99d-157">插入操作的返回值是插入的行数。</span><span class="sxs-lookup"><span data-stu-id="4d99d-157">The return value for an Insert operation is the number of rows inserted.</span></span>  

 <span data-ttu-id="4d99d-158">**更新操作**</span><span class="sxs-lookup"><span data-stu-id="4d99d-158">**Update Operation**</span></span>  

|<span data-ttu-id="4d99d-159">记录集</span><span class="sxs-lookup"><span data-stu-id="4d99d-159">RECORDSET</span></span>|<span data-ttu-id="4d99d-160">FILTER</span><span class="sxs-lookup"><span data-stu-id="4d99d-160">FILTER</span></span>|  
|---------------|------------|  
|<span data-ttu-id="4d99d-161">应在表中更新的记录的集合。</span><span class="sxs-lookup"><span data-stu-id="4d99d-161">A collection of records that should be updated in the table.</span></span>|<span data-ttu-id="4d99d-162">指定查询; 的目标行的 WHERE 子句的内容例如，"名称 = Manager"。</span><span class="sxs-lookup"><span data-stu-id="4d99d-162">The contents of a WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="4d99d-163">可以将此参数设置为**null**返回目标的所有行。</span><span class="sxs-lookup"><span data-stu-id="4d99d-163">You can set this parameter to **null** to return all rows of the target.</span></span>|  

 <span data-ttu-id="4d99d-164">对于更新操作的返回值是更新的行数。</span><span class="sxs-lookup"><span data-stu-id="4d99d-164">The return value for an Update operation is the number of rows updated.</span></span>  

 <span data-ttu-id="4d99d-165">**删除操作**</span><span class="sxs-lookup"><span data-stu-id="4d99d-165">**Delete Operation**</span></span>  

 <span data-ttu-id="4d99d-166">删除操作将作为输入的 WHERE 子句，指定要删除的行。</span><span class="sxs-lookup"><span data-stu-id="4d99d-166">The Delete operation takes as input a WHERE clause that specifies the rows to be deleted.</span></span> <span data-ttu-id="4d99d-167">删除操作的返回值是删除的行数。</span><span class="sxs-lookup"><span data-stu-id="4d99d-167">The return value for a Delete operation is the number of rows deleted.</span></span>  

## <a name="creating-a-wcf-client-to-invoke-operations-on-interface-tables-and-interface-views"></a><span data-ttu-id="4d99d-168">创建 WCF 客户端调用操作的接口表和界面视图</span><span class="sxs-lookup"><span data-stu-id="4d99d-168">Creating a WCF Client to Invoke Operations on Interface Tables and Interface Views</span></span>  
 <span data-ttu-id="4d99d-169">通用组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="4d99d-169">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF channel model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="4d99d-170">本部分介绍如何创建 WCF 客户端以调用基本的 Insert、 Select、 Update 在界面表的删除操作。</span><span class="sxs-lookup"><span data-stu-id="4d99d-170">This section describes how to create a WCF client to invoke basic Insert, Select, Update, Delete operations on an interface table.</span></span>  

#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a><span data-ttu-id="4d99d-171">若要创建 WCF 客户端以对表执行操作</span><span class="sxs-lookup"><span data-stu-id="4d99d-171">To create a WCF client to perform operations on tables</span></span>  

1. <span data-ttu-id="4d99d-172">在 Visual Studio 中创建一个 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="4d99d-172">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="4d99d-173">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d99d-173">For this topic, create a console application.</span></span>  

2. <span data-ttu-id="4d99d-174">生成 WCF 客户端类的 Insert、 Select、 Update 和删除 MS_SAMPLE_EMPLOYEE 接口表上的操作。</span><span class="sxs-lookup"><span data-stu-id="4d99d-174">Generate the WCF client class for the Insert, Select, Update, and Delete operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="4d99d-175">有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="4d99d-175">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="4d99d-176">生成 WCF 客户端类之前，请确保设置**EnableBizTalkCompatibilityMode**属性绑定到 false。</span><span class="sxs-lookup"><span data-stu-id="4d99d-176">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  

3. <span data-ttu-id="4d99d-177">在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="4d99d-177">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  

4. <span data-ttu-id="4d99d-178">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="4d99d-178">Open the Program.cs file and add the following namespaces:</span></span>  

   -   `Microsoft.Adapters.OracleEBS`  

   -   `System.ServiceModel`  

5. <span data-ttu-id="4d99d-179">打开 Program.cs 文件，如下面的代码段中所述创建客户端。</span><span class="sxs-lookup"><span data-stu-id="4d99d-179">Open the Program.cs file and create a client as described in the snippet below.</span></span>  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
   InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient client = new InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient(binding, address);  
   ```  

    <span data-ttu-id="4d99d-180">在此代码段，`InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="4d99d-180">In this snippet, `InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="4d99d-181">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4d99d-181">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4d99d-182">此代码片段显式应用程序代码中指定的绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="4d99d-182">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="4d99d-183">您可以使用这些值还生成的应用程序配置文件 app.config 文件中，从[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4d99d-183">You can use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="4d99d-184">指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定适用于 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="4d99d-184">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  

6. <span data-ttu-id="4d99d-185">为客户端设置的凭据。</span><span class="sxs-lookup"><span data-stu-id="4d99d-185">Set the credentials for the client.</span></span>  

   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  

7. <span data-ttu-id="4d99d-186">由于您正在执行的操作在界面表，必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="4d99d-186">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="4d99d-187">在此示例中，若要设置应用程序上下文中，您指定**OracleUserName**， **OraclePassword**，并**OracleEBSResponsibilityName**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="4d99d-187">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="4d99d-188">有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="4d99d-188">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  

   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  

8. <span data-ttu-id="4d99d-189">打开客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="4d99d-189">Open the client as described in the snippet below:</span></span>  

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

9. <span data-ttu-id="4d99d-190">调用 MS_SAMPLE_EMPLOYEE 表上的插入操作。</span><span class="sxs-lookup"><span data-stu-id="4d99d-190">Invoke the Insert operation on the MS_SAMPLE_EMPLOYEE table.</span></span>  

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

     <span data-ttu-id="4d99d-191">您可以替换上述代码段中执行 Select、 Update 或 Delete 操作。</span><span class="sxs-lookup"><span data-stu-id="4d99d-191">You can replace the preceding code snippet to perform Select, Update, or Delete operations as well.</span></span> <span data-ttu-id="4d99d-192">也可以附加代码片段，可在单个应用程序中执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="4d99d-192">You can also append the code snippets to perform all operation in a single application.</span></span> <span data-ttu-id="4d99d-193">有关如何执行这些操作的代码片段，请参阅[选择操作](#BKMK_Select)，[更新操作](#BKMK_Update)，并[删除操作](#BKMK_Delete)分别。</span><span class="sxs-lookup"><span data-stu-id="4d99d-193">For code snippets on how to perform these operations, see [Select Operation](#BKMK_Select), [Update Operation](#BKMK_Update), and [Delete Operation](#BKMK_Delete) respectively.</span></span>  

10. <span data-ttu-id="4d99d-194">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="4d99d-194">Close the client as described in the snippet below:</span></span>  

    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  

11. <span data-ttu-id="4d99d-195">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="4d99d-195">Build the project and then run it.</span></span> <span data-ttu-id="4d99d-196">应用程序在 MS_SAMPLE_EMPLOYEE 表中插入一条记录。</span><span class="sxs-lookup"><span data-stu-id="4d99d-196">The application inserts a record in the MS_SAMPLE_EMPLOYEE table.</span></span>  

###  <a name="BKMK_Select"></a> <span data-ttu-id="4d99d-197">选择操作</span><span class="sxs-lookup"><span data-stu-id="4d99d-197">Select Operation</span></span>  
 <span data-ttu-id="4d99d-198">下面的代码演示了面向 MS_SAMPLE_EMPLOYEE 接口表的选择操作。</span><span class="sxs-lookup"><span data-stu-id="4d99d-198">The following code shows a Select operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="4d99d-199">选择操作选择插入到表中的最后一个记录。</span><span class="sxs-lookup"><span data-stu-id="4d99d-199">The Select operation selects the last record inserted into the table.</span></span> <span data-ttu-id="4d99d-200">返回的记录写入到控制台。</span><span class="sxs-lookup"><span data-stu-id="4d99d-200">The returned record is written to the console.</span></span>  

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

###  <a name="BKMK_Update"></a> <span data-ttu-id="4d99d-201">更新操作</span><span class="sxs-lookup"><span data-stu-id="4d99d-201">Update Operation</span></span>  
 <span data-ttu-id="4d99d-202">下面的代码演示了面向 MS_SAMPLE_EMPLOYEE 接口表的更新操作。</span><span class="sxs-lookup"><span data-stu-id="4d99d-202">The following code shows an Update operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span>  

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

###  <a name="BKMK_Delete"></a> <span data-ttu-id="4d99d-203">删除操作</span><span class="sxs-lookup"><span data-stu-id="4d99d-203">Delete Operation</span></span>  
 <span data-ttu-id="4d99d-204">下面的代码演示了面向 MS_SAMPLE_EMPLOYEE 接口表的删除操作。</span><span class="sxs-lookup"><span data-stu-id="4d99d-204">The following code shows a Delete operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="4d99d-205">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d99d-205">See Also</span></span>  
 [<span data-ttu-id="4d99d-206">开发 Oracle E-business Suite 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="4d99d-206">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)