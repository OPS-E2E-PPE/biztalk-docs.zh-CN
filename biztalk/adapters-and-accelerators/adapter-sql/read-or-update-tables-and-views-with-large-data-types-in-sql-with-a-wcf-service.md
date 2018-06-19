---
title: 在上运行操作表和视图使用 SQL 使用 WCF 服务模型中的大型数据类型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d33e17c-e09e-4a57-9acc-43095e67ed8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1da0def828c1dbfa8511dc61b529fa02cb53ca5a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967123"
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="10971-102">在上运行操作表和视图使用 SQL 使用 WCF 服务模型中的大型数据类型</span><span class="sxs-lookup"><span data-stu-id="10971-102">Run Operations on Tables and Views with Large Data Types in SQL using the WCF Service Model</span></span>
<span data-ttu-id="10971-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使适配器客户端读取和更新的大型数据类型列中的数据，它是、 varchar （max）、 nvarchar 或 varbinary （max）。</span><span class="sxs-lookup"><span data-stu-id="10971-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to read and update data in columns of large data types, that is, varchar(max), nvarchar(max), or varbinary(max).</span></span> <span data-ttu-id="10971-104">若要从这类列读取数据，适配器客户端可以使用选择的操作。</span><span class="sxs-lookup"><span data-stu-id="10971-104">To read data from such columns, adapter clients can use the Select operation.</span></span> <span data-ttu-id="10971-105">若要插入或更新到此类列的数据，该适配器都公开一组\<*column_name* \>操作，其中\< *column_name* \>是的名称类型 varchar （max）、 nvarchar 或 varbinary （max） 列。</span><span class="sxs-lookup"><span data-stu-id="10971-105">To insert or update data into such columns, the adapter exposes a Set\<*column_name*\> operation, where \<*column_name*\> is the name of the column of type varchar(max), nvarchar(max), or varbinary(max).</span></span>  
  
 <span data-ttu-id="10971-106">此外，在 SQL Server 中，你可以存储非结构化的数据，例如文本文档和图像的 varbinay(max) 列。</span><span class="sxs-lookup"><span data-stu-id="10971-106">Additionally, in SQL Server, you can have the varbinay(max) column store unstructured data such as text documents and images.</span></span> <span data-ttu-id="10971-107">此类非结构化的数据称为 FILESTREAM 数据。</span><span class="sxs-lookup"><span data-stu-id="10971-107">Such unstructured data is called FILESTREAM data.</span></span> <span data-ttu-id="10971-108">FILESTREAM 数据可以存储为文件系统上的文件。</span><span class="sxs-lookup"><span data-stu-id="10971-108">FILESTREAM data can be stored as files on the file system.</span></span> <span data-ttu-id="10971-109">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使客户端 FILESTREAM 数据输入到类型 varbinary （max） 列。</span><span class="sxs-lookup"><span data-stu-id="10971-109">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables the client to enter FILESTREAM data into columns of type varbinary(max).</span></span> <span data-ttu-id="10971-110">[FILESTREAM 存储](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server)提供了更多信息。</span><span class="sxs-lookup"><span data-stu-id="10971-110">[FILESTREAM storage](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server) has more information.</span></span> 
  
 <span data-ttu-id="10971-111">本主题提供必须执行某些任务有关的信息的计算机上运行 SQL Server 和运行适配器客户端将无法插入或更新 FILESTREAM 数据的计算机。</span><span class="sxs-lookup"><span data-stu-id="10971-111">This topic provides information about certain tasks you must perform on the computer running SQL Server and the computer running the adapter client to be able to insert or update FILESTREAM data.</span></span> <span data-ttu-id="10971-112">本主题还说明了执行组\<*column_name* \>操作插入 FILESTREAM 数据。</span><span class="sxs-lookup"><span data-stu-id="10971-112">This topic also provides instructions on performing Set\<*column_name*\> operations to insert FILESTREAM data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10971-113">如果您正在执行包含的用户定义类型的列的表上的操作，请确保您参考[对表和视图使用了 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="10971-113">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="10971-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="10971-114">Prerequisites</span></span>  
 <span data-ttu-id="10971-115">在运行 SQL Server 的计算机和运行适配器客户端的计算机上，必须执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="10971-115">You must perform the following tasks on the computer running SQL Server and the computer running the adapter client.</span></span>  
  
-   <span data-ttu-id="10971-116">**运行 SQL Server 的计算机上**</span><span class="sxs-lookup"><span data-stu-id="10971-116">**On the computer running SQL Server**</span></span>  
  
    -   <span data-ttu-id="10971-117">你必须在 SQL Server 实例上启用 FILESTREAM。</span><span class="sxs-lookup"><span data-stu-id="10971-117">You must enable FILESTREAM on the SQL Server instance.</span></span> <span data-ttu-id="10971-118">请参阅[启用和配置 FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream)。</span><span class="sxs-lookup"><span data-stu-id="10971-118">See [Enable and Configure FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream).</span></span>
  
    -   <span data-ttu-id="10971-119">你必须创建启用 FILESTREAM 的数据库。</span><span class="sxs-lookup"><span data-stu-id="10971-119">You must create a FILESTREAM-enabled database.</span></span> <span data-ttu-id="10971-120">请参阅[创建启用 FILESTREAM 的数据库](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database)。</span><span class="sxs-lookup"><span data-stu-id="10971-120">See [Create a FILESTREAM-Enabled Database](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database).</span></span>
  
    -   <span data-ttu-id="10971-121">你必须有一个表以存储 FILESTREAM 数据。</span><span class="sxs-lookup"><span data-stu-id="10971-121">You must have a table for storing FILESTREAM data.</span></span> <span data-ttu-id="10971-122">请参阅[创建表以存储 FILESTREAM 数据](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data)，</span><span class="sxs-lookup"><span data-stu-id="10971-122">See [Create a Table for Storing FILESTREAM Data](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data),</span></span>
  
-   <span data-ttu-id="10971-123">**运行适配器客户端的计算机上**</span><span class="sxs-lookup"><span data-stu-id="10971-123">**On the computer running the adapter client**</span></span>  
  
    -   <span data-ttu-id="10971-124">你必须安装的 SQL 客户端连接 SDK。</span><span class="sxs-lookup"><span data-stu-id="10971-124">You must have the SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="10971-125">你可以通过运行 SQL Server 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。</span><span class="sxs-lookup"><span data-stu-id="10971-125">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="10971-126">适配器使用 sqlncli10.dll，安装 SQL 客户端连接 SDK，与执行 FILESTREAM 操作。</span><span class="sxs-lookup"><span data-stu-id="10971-126">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  
  
 <span data-ttu-id="10971-127">完成这些任务后，你将插入或更新 SQL Server 数据库表中的 FILESTREAM 数据。</span><span class="sxs-lookup"><span data-stu-id="10971-127">After you have completed these tasks, you are all set to insert or update FILESTREAM data in SQL Server database tables.</span></span>  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a><span data-ttu-id="10971-128">本主题演示对大型数据类型执行操作的方式</span><span class="sxs-lookup"><span data-stu-id="10971-128">How This Topic Demonstrates Operations on Large Data Types</span></span>  
 <span data-ttu-id="10971-129">若要演示如何执行集\<*column_name* \>对表较大的数据类型的操作需要一个表，**记录**，具有列**Id**和**文档**:</span><span class="sxs-lookup"><span data-stu-id="10971-129">To demonstrate how to perform Set\<*column_name*\> operations on tables with large data types, take a table, **Records**, that has columns **Id** and **Document**:</span></span>  
  
-   <span data-ttu-id="10971-130">**记录**通过运行这些示例使用提供的 SQL 脚本创建表，并且所有数据。</span><span class="sxs-lookup"><span data-stu-id="10971-130">The **Records** table, with all the data, is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="10971-131">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="10971-131">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
-   <span data-ttu-id="10971-132">**Id**列是 uniqueidentifier 类型，采用 GUID。</span><span class="sxs-lookup"><span data-stu-id="10971-132">The **Id** column is of type uniqueidentifier and takes a GUID.</span></span> <span data-ttu-id="10971-133">假定**Id**列已有一个 GUID`438B7B4C-5491-409F-BCC1-78817C399EC3`。</span><span class="sxs-lookup"><span data-stu-id="10971-133">Assume that the **Id** column already has a GUID ‘`438B7B4C-5491-409F-BCC1-78817C399EC3`’.</span></span>  
  
-   <span data-ttu-id="10971-134">**文档**列属于类型 varbinary （max）。</span><span class="sxs-lookup"><span data-stu-id="10971-134">The **Document** column is of type VARBINARY(MAX).</span></span> <span data-ttu-id="10971-135">若要更新**文档**列中，适配器公开**SetDocument**操作。</span><span class="sxs-lookup"><span data-stu-id="10971-135">To update the **Document** column, the adapter exposes the **SetDocument** operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10971-136">对于 SQL Server，为了演示 FILESTREAM 操作，假定**文档**列可以存储 FILESTREAM 数据。</span><span class="sxs-lookup"><span data-stu-id="10971-136">For SQL Server, to demonstrate FILESTREAM operations, assume that the **Document** column can store FILESTREAM data.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="10971-137">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="10971-137">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="10971-138">本主题中的示例执行操作**记录**表。</span><span class="sxs-lookup"><span data-stu-id="10971-138">The example in this topic performs operations on the **Records** table.</span></span> <span data-ttu-id="10971-139">**记录**通过运行这些示例使用提供的 SQL 脚本创建表。</span><span class="sxs-lookup"><span data-stu-id="10971-139">The **Records** table is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="10971-140">有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="10971-140">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="10971-141">示例中， **Records_FILESTREAM_Op**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="10971-141">A sample, **Records_FILESTREAM_Op**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="10971-142">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="10971-142">The WCF Client Class</span></span>  
 <span data-ttu-id="10971-143">为对大型数据的操作生成 WCF 客户端的名称类型[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]发现，基于名称的表或视图，如以下表中列出。</span><span class="sxs-lookup"><span data-stu-id="10971-143">The name of the WCF client generated for the operations on large data types that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers, is based on the name of the table or view, as listed in the following table.</span></span>  
  
|<span data-ttu-id="10971-144">SQL Server 数据库项目</span><span class="sxs-lookup"><span data-stu-id="10971-144">SQL Server Database Artifact</span></span>|<span data-ttu-id="10971-145">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="10971-145">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="10971-146">表</span><span class="sxs-lookup"><span data-stu-id="10971-146">Table</span></span>|<span data-ttu-id="10971-147">TableOp_ [架构] _ [TABLE_NAME] 客户端</span><span class="sxs-lookup"><span data-stu-id="10971-147">TableOp_[Schema]_[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="10971-148">视图</span><span class="sxs-lookup"><span data-stu-id="10971-148">View</span></span>|<span data-ttu-id="10971-149">ViewOp_ [架构] _ [VIEW_NAME] 客户端</span><span class="sxs-lookup"><span data-stu-id="10971-149">ViewOp_[Schema]_[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="10971-150">[架构] = SQL Server 集合项目;例如，dbo。</span><span class="sxs-lookup"><span data-stu-id="10971-150">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-columns-of-large-data-types"></a><span data-ttu-id="10971-151">调用在较大的数据类型的列上的操作的方法签名</span><span class="sxs-lookup"><span data-stu-id="10971-151">Method Signature for Invoking Operations on Columns of Large Data Types</span></span>  
 <span data-ttu-id="10971-152">下表显示对表的基本操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="10971-152">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="10971-153">签名是相同的视图，只不过视图命名空间和名称替换那些表。</span><span class="sxs-lookup"><span data-stu-id="10971-153">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="10971-154">运算</span><span class="sxs-lookup"><span data-stu-id="10971-154">Operation</span></span>|<span data-ttu-id="10971-155">方法签名</span><span class="sxs-lookup"><span data-stu-id="10971-155">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="10971-156">设置\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="10971-156">Set\<*column_name*\></span></span>|<span data-ttu-id="10971-157">公共 void 集\<*column_name*\>（字符串筛选器，byte [] 数据）;</span><span class="sxs-lookup"><span data-stu-id="10971-157">public void Set\<*column_name*\>(string Filter, byte[] Data);</span></span>|  
  
 <span data-ttu-id="10971-158">\<*column_name* \> = 较大的数据类型的列的名称。</span><span class="sxs-lookup"><span data-stu-id="10971-158">\<*column_name*\> = Name of the column of large data type.</span></span>  
  
 <span data-ttu-id="10971-159">例如，下面的代码演示方法签名，用于生成 WCF 客户端类**SetDocument**操作**记录**下的默认"dbo"架构的表。</span><span class="sxs-lookup"><span data-stu-id="10971-159">As an example, the following code shows the method signatures for a WCF client class generated for the **SetDocument** operation on the **Records** table under the default “dbo” schema.</span></span>  
  
```  
public partial class TableOp_dbo_RecordsClient : System.ServiceModel.ClientBase<TableOp_dbo_Records>, TableOp_dbo_Records {      
    public void SetDocument (string Filter, byte[] Data);  
}  
```  
  
 <span data-ttu-id="10971-160">在此代码段， **TableOp_dbo_RecordsClient**是 WCF 中的类的生成的 SqlAdapterBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="10971-160">In this snippet, **TableOp_dbo_RecordsClient** is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-operations-on-columns-of-large-data-types"></a><span data-ttu-id="10971-161">较大的数据类型的列上的操作的参数</span><span class="sxs-lookup"><span data-stu-id="10971-161">Parameters for Operations on Columns of Large Data Types</span></span>  
 <span data-ttu-id="10971-162">本部分提供了通过一组所需的参数\<*column_name* \>操作。</span><span class="sxs-lookup"><span data-stu-id="10971-162">This section provides the parameters required by the Set\<*column_name*\> operation.</span></span>  
  
|<span data-ttu-id="10971-163">参数名称</span><span class="sxs-lookup"><span data-stu-id="10971-163">Parameter name</span></span>|<span data-ttu-id="10971-164">Description</span><span class="sxs-lookup"><span data-stu-id="10971-164">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="10971-165">字符串筛选器</span><span class="sxs-lookup"><span data-stu-id="10971-165">string Filter</span></span>|<span data-ttu-id="10971-166">指定 WHERE 子句基于适配器在其上更新的记录大的数据类型的列。</span><span class="sxs-lookup"><span data-stu-id="10971-166">Specifies the WHERE clause based on which the adapter updates the record for the column of large data type.</span></span>|  
|<span data-ttu-id="10971-167">byte [] 数据</span><span class="sxs-lookup"><span data-stu-id="10971-167">byte[] Data</span></span>|<span data-ttu-id="10971-168">指定必须更新为较大的数据类型的列的值。</span><span class="sxs-lookup"><span data-stu-id="10971-168">Specifies the value that must be updated for the column of large data type.</span></span>|  
  
 <span data-ttu-id="10971-169">集\<*column_name* \>操作不返回任何值。</span><span class="sxs-lookup"><span data-stu-id="10971-169">The Set\<*column_name*\> operation does not return any values.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-columns-of-large-data-types"></a><span data-ttu-id="10971-170">创建 WCF 客户端以调用较大的数据类型的列上的操作</span><span class="sxs-lookup"><span data-stu-id="10971-170">Creating a WCF Client to Invoke Operations on Columns of Large Data Types</span></span>  
 <span data-ttu-id="10971-171">泛型的执行 SQL Server 使用 WCF 客户端上的操作所需的操作集涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="10971-171">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="10971-172">本部分介绍如何创建 WCF 客户端来调用**SetDocument**操作**记录**表。</span><span class="sxs-lookup"><span data-stu-id="10971-172">This section describes how to create a WCF client to invoke the **SetDocument** operation on the **Records** table.</span></span> <span data-ttu-id="10971-173">适配器公开**SetDocument**操作，以更新中的较大的数据类型的列的数据。</span><span class="sxs-lookup"><span data-stu-id="10971-173">The adapter exposes the **SetDocument** operation to update data in columns of large data types.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="10971-174">若要创建 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="10971-174">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="10971-175">在 Visual Studio 中创建 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="10971-175">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="10971-176">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="10971-176">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="10971-177">生成的 WCF 客户端类**SetDocument**操作**记录**表。</span><span class="sxs-lookup"><span data-stu-id="10971-177">Generate the WCF client class for the **SetDocument** operation on the **Records** table.</span></span> <span data-ttu-id="10971-178">有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="10971-178">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
3.  <span data-ttu-id="10971-179">在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`， `Microsoft.ServiceModel.Channels`，和`System.Transactions`。</span><span class="sxs-lookup"><span data-stu-id="10971-179">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, and `System.Transactions`.</span></span>  
  
4.  <span data-ttu-id="10971-180">打开 Program.cs 文件并添加`System.Transactions`命名空间。</span><span class="sxs-lookup"><span data-stu-id="10971-180">Open the Program.cs file and add the `System.Transactions` namespace.</span></span>  
  
5.  <span data-ttu-id="10971-181">在 Program.cs 中，如下面的代码段中所述创建客户端。</span><span class="sxs-lookup"><span data-stu-id="10971-181">In the Program.cs, create a client as described in the snippet below.</span></span>  
  
    ```  
  
              TableOp_dbo_RecordsClient client = new TableOp_dbo_RecordsClient("SqlAdapterBinding_TableOp_dbo_Records");  
    client.ClientCredentials.UserName.UserName = "";  
    client.ClientCredentials.UserName.Password = "";  
  
    ```  
  
     <span data-ttu-id="10971-182">在此代码段，`TableOp_dbo_RecordsClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="10971-182">In this snippet, `TableOp_dbo_RecordsClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="10971-183">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="10971-183">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="10971-184">`SqlAdapterBinding_TableOp_dbo_Records`是客户端终结点配置的名称，并在 app.config 中定义。此文件也会生成由[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="10971-184">`SqlAdapterBinding_TableOp_dbo_Records` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="10971-185">若要对 FILESTREAM 数据执行操作，必须始终连接到 SQL Server 使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="10971-185">To perform operations on FILESTREAM data, you must always connect to SQL Server using Windows authentication.</span></span> <span data-ttu-id="10971-186">若要使用 Windows 身份验证进行连接，必须提供有空的用户名和密码，如前面的代码段中所示。</span><span class="sxs-lookup"><span data-stu-id="10971-186">To connect using Windows authentication, you must provide empty username and password, as shown in the preceding snippet.</span></span> <span data-ttu-id="10971-187">此外，在使用 Windows 身份验证连接到 SQL Server，你必须已执行的步骤中所述[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="10971-187">Also, before using Windows authentication to connect to SQL Server, you must have performed the steps mentioned in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10971-188">在此代码段中，你使用的绑定和终结点地址从配置文件。</span><span class="sxs-lookup"><span data-stu-id="10971-188">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="10971-189">你还可显式指定这些值在代码中。</span><span class="sxs-lookup"><span data-stu-id="10971-189">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="10971-190">指定客户端绑定的不同方法的详细信息，请参阅[为该 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="10971-190">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
6.  <span data-ttu-id="10971-191">下面的代码段中所述，请打开客户端：</span><span class="sxs-lookup"><span data-stu-id="10971-191">Open the client as described in the snippet below:</span></span>  
  
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
  
7.  <span data-ttu-id="10971-192">调用**SetDocument**操作**记录**表。</span><span class="sxs-lookup"><span data-stu-id="10971-192">Invoke the **SetDocument** operation on the **Records** table.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="10971-193">集 *< column_name >* 必须始终在事务中执行操作。</span><span class="sxs-lookup"><span data-stu-id="10971-193">The Set *<column_name>* operations must always be performed in a transaction.</span></span> <span data-ttu-id="10971-194">若要确保此操作，请集 *< column_name >* 必须在事务范围内调用操作和**UseAmbientTransaction**绑定属性必须设置为**true**app.config 中。</span><span class="sxs-lookup"><span data-stu-id="10971-194">To ensure this, the Set *<column_name>* operation must be invoked within a transaction scope and the **UseAmbientTransaction** binding property must be set to **true** in the app.config.</span></span>  
  
    ```  
    using (TransactionScope tx = new TransactionScope())  
    {  
        string filter = "WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'";  
        byte[] data = ASCIIEncoding.ASCII.GetBytes("Sample data");  
        client.SetDocument(filter, data);  
        tx.Complete();  
    }  
    ```  
  
     <span data-ttu-id="10971-195">在这里，应用程序将字符串"示例数据"转换为 base64 编码的字符串，并满足筛选条件的记录中对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="10971-195">Here, the application converts the string “Sample data” into a base64 encoded string, and updates it in the record that satisfies the filter criteria.</span></span>  
  
8.  <span data-ttu-id="10971-196">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="10971-196">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
9. <span data-ttu-id="10971-197">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="10971-197">Build the project and then run it.</span></span> <span data-ttu-id="10971-198">应用程序更新**文档**中的列**记录**表。</span><span class="sxs-lookup"><span data-stu-id="10971-198">The application updates the **Document** column in the **Records** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10971-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10971-199">See Also</span></span>  
[<span data-ttu-id="10971-200">使用 WCF 服务模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="10971-200">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)