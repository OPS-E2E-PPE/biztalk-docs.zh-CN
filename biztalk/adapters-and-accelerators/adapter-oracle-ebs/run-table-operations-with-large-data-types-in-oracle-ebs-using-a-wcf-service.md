---
title: 完成对表中使用 WCF 服务模型的 Oracle E-business Suite 的较大的数据类型的操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93ba3191-d234-424a-b2da-dcf384df4985
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 720da748059d3fe3da376ea42495a2587577f5ee
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967587"
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="cee18-102">完成对表中使用 WCF 服务模型的 Oracle E-business Suite 的较大的数据类型的操作</span><span class="sxs-lookup"><span data-stu-id="cee18-102">Complete operations on tables with large data types in Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="cee18-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端可以执行对接口表和视图的较大的数据类型，如 BLOB、 CLOB、 NCLOB、 和 BFILE 操作。</span><span class="sxs-lookup"><span data-stu-id="cee18-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enables adapter clients to perform operations on interface tables and views with large data types such as BLOB, CLOB, NCLOB, and BFILE.</span></span>  
  
-   <span data-ttu-id="cee18-104">列类型的适配器 BLOB、 CLOB、 和 NCLOB，使客户端可以读取，以及更新数据。</span><span class="sxs-lookup"><span data-stu-id="cee18-104">For columns of type BLOB, CLOB, and NCLOB, the adapter enables clients to read as well as update data.</span></span> <span data-ttu-id="cee18-105">适配器公开 Read_\<*LOBColName* \>和 Update_\<*LOBColName* \>操作来读取和更新数据分别，其中\<*LOBColName* \>是具有较大的数据类型列的名称。</span><span class="sxs-lookup"><span data-stu-id="cee18-105">The adapter exposes Read_\<*LOBColName*\> and Update_\<*LOBColName*\> operations to read and update data respectively, where \<*LOBColName*\> is the name of column with large data type.</span></span> <span data-ttu-id="cee18-106">如果没有具有单个接口表中的较大的数据类型的多个列，适配器将公开为许多读取和更新接口该表的操作。</span><span class="sxs-lookup"><span data-stu-id="cee18-106">If there is more than one column with large data type in a single interface table, the adapter exposes as many read and update operations for that interface table.</span></span>  
  
-   <span data-ttu-id="cee18-107">对于类型 BFILE 列，适配器客户端只能读取的数据。</span><span class="sxs-lookup"><span data-stu-id="cee18-107">For columns of type BFILE, adapter clients can only read data.</span></span> <span data-ttu-id="cee18-108">适配器公开 Read_\<*LOBColName* \>操作从 BFILE 类型的列读取数据。</span><span class="sxs-lookup"><span data-stu-id="cee18-108">The adapter exposes Read_\<*LOBColName*\> operation to read data from columns of BFILE type.</span></span> <span data-ttu-id="cee18-109">如果没有具有单个接口表中的较大的数据类型的多个列，该适配器将公开许多读取接口表的操作。</span><span class="sxs-lookup"><span data-stu-id="cee18-109">If there is more than one column with large data type in a single interface table, the adapter exposes as many read operations for the interface table.</span></span>  
  
 <span data-ttu-id="cee18-110">有关这些操作的详细信息，请参阅[接口表、 界面视图、 表和包含 LOB 数据的视图上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="cee18-110">For more information about these operations, see [Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="cee18-111">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="cee18-111">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="cee18-112">本主题中的示例更新的客户数据库表中的 BLOB 列 （照片），然后从同一列中检索数据。</span><span class="sxs-lookup"><span data-stu-id="cee18-112">The example in this topic updates a BLOB column (PHOTO) in the CUSTOMER database table and then retrieves the data from the same column.</span></span> <span data-ttu-id="cee18-113">通过运行这些示例使用提供的脚本创建表。</span><span class="sxs-lookup"><span data-stu-id="cee18-113">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="cee18-114">有关示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="cee18-114">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="cee18-115">示例中， **LargeDataTypes_ServiceModel**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="cee18-115">A sample, **LargeDataTypes_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cee18-116">本主题列出更新和读取基数据库表中的较大的数据类型的列的详细的任务。</span><span class="sxs-lookup"><span data-stu-id="cee18-116">This topic lists detailed tasks for updating and reading columns of large data types in a base database table.</span></span> <span data-ttu-id="cee18-117">你必须为更新和读取列接口表中的大型数据类型执行相同的任务集。</span><span class="sxs-lookup"><span data-stu-id="cee18-117">You must perform the same set of tasks for updating and reading columns of large data types in an interface table.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="cee18-118">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="cee18-118">The WCF Client Class</span></span>  
 <span data-ttu-id="cee18-119">为具有较大的数据类型由对表操作生成 WCF 客户端的名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]基于表的名称，如以下表中列出。</span><span class="sxs-lookup"><span data-stu-id="cee18-119">The name of the WCF client generated for the operations on tables with large data types by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is based on the name of the table, as listed in the following table.</span></span>  
  
|<span data-ttu-id="cee18-120">项目</span><span class="sxs-lookup"><span data-stu-id="cee18-120">Artifact</span></span>|<span data-ttu-id="cee18-121">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="cee18-121">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="cee18-122">接口表</span><span class="sxs-lookup"><span data-stu-id="cee18-122">Interface tables</span></span>|<span data-ttu-id="cee18-123">InterfaceTables_ [APP_NAME] _ [架构]\_[TABLE_NAME] 客户端</span><span class="sxs-lookup"><span data-stu-id="cee18-123">InterfaceTables_[APP_NAME]_[SCHEMA]\_[TABLE_NAME]Client</span></span>|  
  
 <span data-ttu-id="cee18-124">[APP_NAME] = Oracle E-business Suite 应用程序; 实际名称例如，查找。</span><span class="sxs-lookup"><span data-stu-id="cee18-124">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  
  
 <span data-ttu-id="cee18-125">[架构] = 项目; 的集合例如，应用程序。</span><span class="sxs-lookup"><span data-stu-id="cee18-125">[SCHEMA] = Collection of artifacts; for example, APPS.</span></span>  
  
 <span data-ttu-id="cee18-126">[TABLE_NAME] = 表; 的名称例如，MS_SAMPLE_EMPLOYEE。</span><span class="sxs-lookup"><span data-stu-id="cee18-126">[TABLE_NAME] = The name of the table; for example, MS_SAMPLE_EMPLOYEE.</span></span>  
  
 <span data-ttu-id="cee18-127">[VIEW_NAME] = 视图; 的名称例如，MS_SAMPLE_EMPLOYEE_View。</span><span class="sxs-lookup"><span data-stu-id="cee18-127">[VIEW_NAME] = The name of the view; for example, MS_SAMPLE_EMPLOYEE_View.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="cee18-128">调用对表的操作的方法签名</span><span class="sxs-lookup"><span data-stu-id="cee18-128">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="cee18-129">下表显示对表的基本操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="cee18-129">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="cee18-130">签名是相同的视图，只不过视图命名空间和名称替换那些表。</span><span class="sxs-lookup"><span data-stu-id="cee18-130">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="cee18-131">运算</span><span class="sxs-lookup"><span data-stu-id="cee18-131">Operation</span></span>|<span data-ttu-id="cee18-132">方法签名</span><span class="sxs-lookup"><span data-stu-id="cee18-132">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="cee18-133">Update_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="cee18-133">Update_\<*column_name*\></span></span>|<span data-ttu-id="cee18-134">公共 void Update_\<*column_name*\>（字符串筛选器，byte [] 数据）;</span><span class="sxs-lookup"><span data-stu-id="cee18-134">public void Update_\<*column_name*\>(string FILTER, byte[] DATA);</span></span>|  
|<span data-ttu-id="cee18-135">Read_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="cee18-135">Read_\<*column_name*\></span></span>|<span data-ttu-id="cee18-136">公共 System.IO.Stream Read_\<*column_name*\>（字符串筛选器）;</span><span class="sxs-lookup"><span data-stu-id="cee18-136">public System.IO.Stream Read_\<*column_name*\>(string FILTER);</span></span>|  
  
 <span data-ttu-id="cee18-137">例如，下面的代码演示的方法签名的应用程序架构下的客户数据库表上的 Update_PHOTO 和 Read_PHOTO 操作生成的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="cee18-137">As an example, the following code shows the method signatures for a WCF client class generated for the Update_PHOTO and Read_PHOTO operations on the CUSTOMER database table under the APPS schema.</span></span>  
  
```  
public partial class Tables_APPS_CUSTOMERClient : System.ServiceModel.ClientBase<Tables_APPS_CUSTOMER>, Tables_APPS_CUSTOMER {      
  
    public void Update_PHOTO(string FILTER, byte[] DATA);  
  
    public System.IO.Stream Read_PHOTO(string FILTER);  
}  
```  
  
 <span data-ttu-id="cee18-138">在此代码段， **Tables_APPS_CUSTOMERClient**是 WCF 中的类的生成的 OracleEBSBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cee18-138">In this snippet, **Tables_APPS_CUSTOMERClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="cee18-139">Update_PHOTO 和 Read_PHOTO 是可以调用更新和读取表中的较大的数据类型的列的方法。</span><span class="sxs-lookup"><span data-stu-id="cee18-139">Update_PHOTO and Read_PHOTO are methods that can be invoked to update and read columns of large data types in a table.</span></span>  
  
### <a name="parameters-for-table-operations"></a><span data-ttu-id="cee18-140">参数用于表操作</span><span class="sxs-lookup"><span data-stu-id="cee18-140">Parameters for Table Operations</span></span>  
 <span data-ttu-id="cee18-141">本部分提供所需的 Update_ 参数\<*column_name* \>和 Read_\<*column_name* \>操作。</span><span class="sxs-lookup"><span data-stu-id="cee18-141">This section provides the parameters required by the Update_\<*column_name*\> and Read_\<*column_name*\> operation.</span></span>  
  
|<span data-ttu-id="cee18-142">操作名称</span><span class="sxs-lookup"><span data-stu-id="cee18-142">Operation name</span></span>|<span data-ttu-id="cee18-143">Parameters</span><span class="sxs-lookup"><span data-stu-id="cee18-143">Parameters</span></span>|  
|--------------------|----------------|  
|<span data-ttu-id="cee18-144">Update_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="cee18-144">Update_\<*column_name*\></span></span>|<span data-ttu-id="cee18-145">需要以下参数：</span><span class="sxs-lookup"><span data-stu-id="cee18-145">Requires the following parameters:</span></span><br /><br /> <span data-ttu-id="cee18-146">-   `string FILTER`.</span><span class="sxs-lookup"><span data-stu-id="cee18-146">-   `string FILTER`.</span></span> <span data-ttu-id="cee18-147">此参数必须包含 where 子句指示针对其数据的更新的记录。</span><span class="sxs-lookup"><span data-stu-id="cee18-147">This parameter must contain the where clause that denotes the record for which data has to be updated.</span></span> <span data-ttu-id="cee18-148">例如， `"WHERE Name='Mindy Martin'"`。</span><span class="sxs-lookup"><span data-stu-id="cee18-148">For example, `"WHERE Name='Mindy Martin'"`.</span></span><br /><span data-ttu-id="cee18-149">-   `byte[] DATA`.</span><span class="sxs-lookup"><span data-stu-id="cee18-149">-   `byte[] DATA`.</span></span> <span data-ttu-id="cee18-150">包含要更新的大型数据类型列中的数据的字节数组。</span><span class="sxs-lookup"><span data-stu-id="cee18-150">Contains a byte array of data to be update in a column of large data type.</span></span>|  
|<span data-ttu-id="cee18-151">Read_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="cee18-151">Read_\<*column_name*\></span></span>|<span data-ttu-id="cee18-152">需要以下参数：</span><span class="sxs-lookup"><span data-stu-id="cee18-152">Requires the following parameters:</span></span><br /><br /> <span data-ttu-id="cee18-153">-   `string FILTER`.</span><span class="sxs-lookup"><span data-stu-id="cee18-153">-   `string FILTER`.</span></span> <span data-ttu-id="cee18-154">此参数必须包含 where 子句，它表示具有要读取数据的记录。</span><span class="sxs-lookup"><span data-stu-id="cee18-154">This parameter must contain the where clause that denotes the record from which the data has to be read.</span></span> <span data-ttu-id="cee18-155">例如， `"WHERE Name='Mindy Martin'"`。</span><span class="sxs-lookup"><span data-stu-id="cee18-155">For example, `"WHERE Name='Mindy Martin'"`.</span></span>|  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-with-columns-of-large-data-types"></a><span data-ttu-id="cee18-156">创建 WCF 客户端来调用对具有较大的数据类型的列的表的操作</span><span class="sxs-lookup"><span data-stu-id="cee18-156">Creating a WCF Client to Invoke Operations on Tables with Columns of Large Data Types</span></span>  
 <span data-ttu-id="cee18-157">泛型组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="cee18-157">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="cee18-158">本部分介绍如何创建 WCF 客户端来调用 Update_PHOTO 和 Read_PHOTO 客户数据库表上的操作。</span><span class="sxs-lookup"><span data-stu-id="cee18-158">This section describes how to create a WCF client to invoke Update_PHOTO and Read_PHOTO operations on a CUSTOMER database table.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="cee18-159">若要创建 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="cee18-159">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="cee18-160">在 Visual Studio 中创建 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="cee18-160">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="cee18-161">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="cee18-161">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="cee18-162">生成 WCF 客户端类上的客户数据库表的 Update_PHOTO 和 Read_PHOTO 操作。</span><span class="sxs-lookup"><span data-stu-id="cee18-162">Generate the WCF client class for the Update_PHOTO and Read_PHOTO operations on the CUSTOMER database table.</span></span> <span data-ttu-id="cee18-163">有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="cee18-163">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cee18-164">在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。</span><span class="sxs-lookup"><span data-stu-id="cee18-164">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="cee18-165">在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`和`Microsoft.ServiceModel.Channels`， `System.Transactions`。</span><span class="sxs-lookup"><span data-stu-id="cee18-165">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`, `System.Transactions`.</span></span>  
  
4.  <span data-ttu-id="cee18-166">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="cee18-166">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
    -   `System.Transactions`  
  
    -   `System.IO`  
  
5.  <span data-ttu-id="cee18-167">打开 Program.cs 文件并创建客户端，如下面的代码段中所述。</span><span class="sxs-lookup"><span data-stu-id="cee18-167">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              Tables_APPS_CUSTOMERClient client = new Tables_APPS_CUSTOMERClient("OracleEBSBinding_Tables_APPS_CUSTOMER");  
  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="cee18-168">在此代码段，`Tables_APPS_CUSTOMERClient`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="cee18-168">In this snippet, `Tables_APPS_CUSTOMERClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="cee18-169">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cee18-169">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cee18-170">在此代码段，你可以使用的绑定和终结点地址从配置文件 app.config。你还可显式指定这些值在代码中。</span><span class="sxs-lookup"><span data-stu-id="cee18-170">In this snippet, you use the binding and endpoint address from the configuration file app.config. You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="cee18-171">指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="cee18-171">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="cee18-172">为客户端设置的凭据。</span><span class="sxs-lookup"><span data-stu-id="cee18-172">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cee18-173">在此示例中，你将要对数据库表的操作。</span><span class="sxs-lookup"><span data-stu-id="cee18-173">In this example, you are performing operations on a database table.</span></span> <span data-ttu-id="cee18-174">但是，如果您正在执行对接口表的操作，则必须设置应用程序上下文通过指定的相应值**OracleUserName**， **OraclePassword**，和**OracleEBSResponsibilityName**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cee18-174">However, if you are performing operations on an interface table, you must set the application context by specifying appropriate values for the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="cee18-175">打开客户端之前，必须指定这些绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cee18-175">You must specify these binding properties before opening the client.</span></span> <span data-ttu-id="cee18-176">有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="cee18-176">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
7.  <span data-ttu-id="cee18-177">下面的代码段中所述，请打开客户端：</span><span class="sxs-lookup"><span data-stu-id="cee18-177">Open the client as described in the snippet below:</span></span>  
  
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
  
8.  <span data-ttu-id="cee18-178">调用对 CUSTOMER 表的 Update_PHOTO 操作。</span><span class="sxs-lookup"><span data-stu-id="cee18-178">Invoke the Update_PHOTO operation on the CUSTOMER table.</span></span>  
  
     <span data-ttu-id="cee18-179">Update_PHOTO 操作需要要更新的数据的字节数组。</span><span class="sxs-lookup"><span data-stu-id="cee18-179">The Update_PHOTO operation requires a byte array for the data to be updated.</span></span> <span data-ttu-id="cee18-180">在此代码段中，你可以使用 FileStream 类创建的照片，SamplePhoto.jpg 的字节数组。</span><span class="sxs-lookup"><span data-stu-id="cee18-180">In this code snippet, you use the FileStream class to create a byte array for a photo, SamplePhoto.jpg.</span></span> <span data-ttu-id="cee18-181">此应用程序工作，必须文件复制到项目的 bin 目录中。</span><span class="sxs-lookup"><span data-stu-id="cee18-181">For this application to work, the file must be copied to the project’s bin directory.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cee18-182">Update_PHOTO 操作必须执行在事务中，因此**UseAmbientTransaction**绑定属性必须设置为**true** ，必须在执行该 Update_PHOTO 操作事务范围。</span><span class="sxs-lookup"><span data-stu-id="cee18-182">The Update_PHOTO operation must be performed in a transaction, so the **UseAmbientTransaction** binding property must be set to **true** and the Update_PHOTO operation must be performed within a transaction scope.</span></span> <span data-ttu-id="cee18-183">你可以设置**UseAmbientTransaction** app.config 中或通过将其显式设置为应用程序中绑定属性`binding.UseAmbientTransaction = true`。</span><span class="sxs-lookup"><span data-stu-id="cee18-183">You can set the **UseAmbientTransaction** binding property either in the app.config or by explicitly setting it in your application as `binding.UseAmbientTransaction = true`.</span></span> <span data-ttu-id="cee18-184">请注意，是否您在代码中显式指定的绑定属性，则必须这样在打开客户端之前。</span><span class="sxs-lookup"><span data-stu-id="cee18-184">Note that if you are specifying the binding property explicitly in the code, you must do so before opening the client.</span></span>  
  
    ```  
    byte[] photo;  
  
    using (FileStream fs = new FileStream("SamplePhoto.jpg", FileMode.Open))  
    {  
        try  
        {  
            Console.WriteLine("Reading the photo");  
            int count = 0;  
            photo = new byte[fs.Length];  
            while ((count += fs.Read(photo, count, (int)(((fs.Length - count) > 4096) ? 4096 : fs.Length - count))) < fs.Length) ;  
        }  
        catch(Exception ex)  
        {  
            Console.WriteLine("Exception: " + ex.Message);  
            throw;  
        }  
    }  
  
    Console.WriteLine("Updating data for the 'PHOTO' column");  
    // Invoking the Update_PHOTO operation inside a transaction scope  
    using (TransactionScope tx = new TransactionScope())  
    {  
        string filter = "WHERE Name='Mindy Martin'";  
        client.Update_PHOTO(filter, photo);  
        tx.Complete();  
    }  
  
    ```  
  
9. <span data-ttu-id="cee18-185">调用对 CUSTOMER 表的 Read_PHOTO 操作。</span><span class="sxs-lookup"><span data-stu-id="cee18-185">Invoke the Read_PHOTO operation on the CUSTOMER table.</span></span>  
  
     <span data-ttu-id="cee18-186">Read_PHOTO 提供 System.IO.Stream 形式的输出。</span><span class="sxs-lookup"><span data-stu-id="cee18-186">The Read_PHOTO gives the output in the form of System.IO.Stream.</span></span> <span data-ttu-id="cee18-187">适配器客户端必须实现 FileStream 类来从 Read_PHOTO 操作中读取数据。</span><span class="sxs-lookup"><span data-stu-id="cee18-187">The adapter client must implement the FileStream class to read the data from Read_PHOTO operation.</span></span> <span data-ttu-id="cee18-188">Read_PHOTO 操作完成后，文件 PhotoCopy.jpg 复制项目的 bin 目录下。</span><span class="sxs-lookup"><span data-stu-id="cee18-188">After the Read_PHOTO operation is complete, a file PhotoCopy.jpg is copied under the project’s bin directory.</span></span>  
  
    ```  
    using (FileStream fs = new FileStream("PhotoCopy.jpg", FileMode.Create))  
    {  
        Console.WriteLine("Reading photo data");  
        String ReadFilter = "WHERE NAME='Mindy Martin'";  
        Stream photoStream = client.Read_PHOTO(ReadFilter);  
        Console.WriteLine("Photo data read -- writing to PhotoCopy.jpg");  
  
        int count;  
        int length = 0;  
        byte[] buffer = new byte[4096];  
        while ((count = photoStream.Read(buffer, 0, 4096)) > 0)  
        {  
            fs.Write(buffer, 0, count);  
            length+=count;  
        }  
        Console.WriteLine("{0} bytes written to PhotoCopy.jpg", length);  
    }  
  
    Console.WriteLine("Photo updated and read back -- Hit <RETURN> to end");  
    Console.ReadLine();  
    ```  
  
10. <span data-ttu-id="cee18-189">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="cee18-189">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. <span data-ttu-id="cee18-190">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="cee18-190">Build the project and then run it.</span></span> <span data-ttu-id="cee18-191">应用程序更新 CUSTOMER 表的照片列，然后读照片列的内容。</span><span class="sxs-lookup"><span data-stu-id="cee18-191">The application updates the PHOTO column of the CUSTOMER table and then reads the content of the PHOTO column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cee18-192">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cee18-192">See Also</span></span>  
 [<span data-ttu-id="cee18-193">开发 Oracle E-business Suite 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="cee18-193">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)