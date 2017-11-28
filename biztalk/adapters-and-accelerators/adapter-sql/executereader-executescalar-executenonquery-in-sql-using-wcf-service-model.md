---
title: "ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery SQL 使用 WCF 服务模型中的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62f166af-b657-491b-b20d-1ae7886f27ce
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f886463e2b38b358e5f6a9da8b7e67aabdc9c3ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-sql-using-wcf-service-model"></a><span data-ttu-id="bf590-102">ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery SQL 使用 WCF 服务模型中的操作</span><span class="sxs-lookup"><span data-stu-id="bf590-102">ExecuteReader, ExecuteScalar, or ExecuteNonQuery operations in SQL using WCF Service Model</span></span>
<span data-ttu-id="bf590-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]如公开泛型的 SQL Server 操作**ExecuteNonQuery**， **ExecuteReader**，和**ExecuteScalar**。</span><span class="sxs-lookup"><span data-stu-id="bf590-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes generic SQL Server operations such as **ExecuteNonQuery**, **ExecuteReader**, and **ExecuteScalar**.</span></span> <span data-ttu-id="bf590-104">这些操作可用于 SQL Server 数据库执行任何 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="bf590-104">You can use these operations to execute any SQL statement on a SQL Server database.</span></span> <span data-ttu-id="bf590-105">这些操作因响应为 SQL 语句所获取的类型而异。</span><span class="sxs-lookup"><span data-stu-id="bf590-105">These operations differ based on the kind of response you get for the SQL statement.</span></span> <span data-ttu-id="bf590-106">有关如何适配器支持这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="bf590-106">For more information about how the adapter supports these operations, see [Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span></span>  
  
 <span data-ttu-id="bf590-107">本主题演示如何执行**ExecuteReader**操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用 WCF 服务模型。</span><span class="sxs-lookup"><span data-stu-id="bf590-107">This topic demonstrates how to perform an **ExecuteReader** operation using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the WCF service model.</span></span> <span data-ttu-id="bf590-108">你可以按照同一套执行本主题中所述的过程**ExecuteNonQuery**和**ExecuteScalar**操作。</span><span class="sxs-lookup"><span data-stu-id="bf590-108">You can follow the same set of procedures described in this topic to perform **ExecuteNonQuery** and **ExecuteScalar** operations.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="bf590-109">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="bf590-109">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="bf590-110">本主题中的示例使用**ExecuteReader**操作执行 ADD_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="bf590-110">The example in this topic uses the **ExecuteReader** operation to execute the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="bf590-111">此存储的过程将记录添加到员工表，并返回记录的员工 ID。</span><span class="sxs-lookup"><span data-stu-id="bf590-111">This stored procedure adds a record to the Employee table and returns the employee ID for the record.</span></span> <span data-ttu-id="bf590-112">通过运行这些示例使用提供的 SQL 脚本创建 ADD_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="bf590-112">The ADD_EMP_DETAILS stored procedure is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="bf590-113">有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="bf590-113">For more information about samples, see [Adapter samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="bf590-114">示例中， **Execute_Reader**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="bf590-114">A sample, **Execute_Reader**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="bf590-115">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="bf590-115">The WCF Client Class</span></span>  
 <span data-ttu-id="bf590-116">调用泛型操作 （ExecuteNonQuery、 ExecuteReader 或 ExecuteScalar） 使用的生成 WCF 客户端的名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]下表中列出。</span><span class="sxs-lookup"><span data-stu-id="bf590-116">The name of the WCF client generated for invoking generic operations (ExecuteNonQuery, ExecuteReader, or ExecuteScalar) using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="bf590-117">操作</span><span class="sxs-lookup"><span data-stu-id="bf590-117">Operations</span></span>|<span data-ttu-id="bf590-118">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="bf590-118">WCF Client Name</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="bf590-119">ExecuteNonQuery、 ExecuteReader 或 ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="bf590-119">ExecuteNonQuery, ExecuteReader, or ExecuteScalar</span></span>|<span data-ttu-id="bf590-120">GenericTableOpClient</span><span class="sxs-lookup"><span data-stu-id="bf590-120">GenericTableOpClient</span></span>|  
  
### <a name="method-signature-for-invoking-generic-operations"></a><span data-ttu-id="bf590-121">调用泛型操作的方法签名</span><span class="sxs-lookup"><span data-stu-id="bf590-121">Method Signature for Invoking Generic Operations</span></span>  
 <span data-ttu-id="bf590-122">下表显示了要调用的泛型操作所公开的方法的签名。</span><span class="sxs-lookup"><span data-stu-id="bf590-122">The following table shows the signature for the method exposed to invoke the generic operations.</span></span>  
  
|<span data-ttu-id="bf590-123">运算</span><span class="sxs-lookup"><span data-stu-id="bf590-123">Operation</span></span>|<span data-ttu-id="bf590-124">方法签名</span><span class="sxs-lookup"><span data-stu-id="bf590-124">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="bf590-125">ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="bf590-125">ExecuteNonQuery</span></span>|<span data-ttu-id="bf590-126">int ExecuteNonQuery （字符串查询）</span><span class="sxs-lookup"><span data-stu-id="bf590-126">int ExecuteNonQuery(string Query)</span></span>|  
|<span data-ttu-id="bf590-127">ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="bf590-127">ExecuteReader</span></span>|<span data-ttu-id="bf590-128">System.Data.DataSet [] ExecuteReader （字符串查询）</span><span class="sxs-lookup"><span data-stu-id="bf590-128">System.Data.DataSet[] ExecuteReader(string Query)</span></span>|  
|<span data-ttu-id="bf590-129">ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="bf590-129">ExecuteScalar</span></span>|<span data-ttu-id="bf590-130">字符串 ExecuteScalar(string Query)</span><span class="sxs-lookup"><span data-stu-id="bf590-130">string ExecuteScalar(string Query)</span></span>|  
  
 <span data-ttu-id="bf590-131">例如，泛型操作方法的签名所示下面的代码段。</span><span class="sxs-lookup"><span data-stu-id="bf590-131">As an example, the signature for the generic operation methods is shown in the following code snippet.</span></span>  
  
```  
public partial class GenericTableOpClient : System.ServiceModel.ClientBase<GenericTableOp>, GenericTableOp {  
  public int ExecuteNonQuery(string Query);  
  public System.Data.DataSet[] ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  
  
 <span data-ttu-id="bf590-132">在此代码段</span><span class="sxs-lookup"><span data-stu-id="bf590-132">In this snippet,</span></span>  
  
-   <span data-ttu-id="bf590-133">`GenericTableOpClient`是类的名称。</span><span class="sxs-lookup"><span data-stu-id="bf590-133">`GenericTableOpClient` is the name of the class.</span></span> <span data-ttu-id="bf590-134">在此示例中，你可以使用此类创建客户端以调用的泛型操作，ExecuteReader。</span><span class="sxs-lookup"><span data-stu-id="bf590-134">In this example, you use this class to create a client to invoke the generic operation, ExecuteReader.</span></span>  
  
-   <span data-ttu-id="bf590-135">`public System.Data.DataSet[] ExecuteReader(string Query)`是你在此示例中调用 ADD_EMP_DETAILS 调用的方法存储过程。</span><span class="sxs-lookup"><span data-stu-id="bf590-135">`public System.Data.DataSet[] ExecuteReader(string Query)` is the method that you invoke in this example to invoke the ADD_EMP_DETAILS stored procedure.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a><span data-ttu-id="bf590-136">创建 WCF 客户端以调用 ExecuteReader 操作</span><span class="sxs-lookup"><span data-stu-id="bf590-136">Creating a WCF Client to Invoke an ExecuteReader Operation</span></span>  
 <span data-ttu-id="bf590-137">泛型的执行 SQL Server 使用 WCF 客户端上的操作所需的操作集涉及到一组任务中所述[与 SQL 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="bf590-137">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF channel model with the SQL adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="bf590-138">本节具体介绍如何创建时，将调用一个 WCF 客户端**ExecuteReader**操作执行 ADD_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="bf590-138">This section specifically describes how to create a WCF client that invokes an **ExecuteReader** operation to execute the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="bf590-139">此存储的过程是通过运行与每个示例提供的 SQL 脚本创建的。</span><span class="sxs-lookup"><span data-stu-id="bf590-139">This stored procedure is created by running the SQL script provided with each sample.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a><span data-ttu-id="bf590-140">若要创建 WCF 客户端以调用 ExecuteReader 操作</span><span class="sxs-lookup"><span data-stu-id="bf590-140">To create a WCF client to invoke ExecuteReader operation</span></span>  
  
1.  <span data-ttu-id="bf590-141">在 Visual Studio 中创建 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="bf590-141">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="bf590-142">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf590-142">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="bf590-143">生成的 WCF 客户端类**ExecuteReader**泛型操作。</span><span class="sxs-lookup"><span data-stu-id="bf590-143">Generate the WCF client class for the **ExecuteReader** generic operation.</span></span> <span data-ttu-id="bf590-144">当你连接到 SQL Server 数据库使用时，此操作才可用根节点下[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bf590-144">This operation is available under the root node when you connect to the SQL Server database using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="bf590-145">有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="bf590-145">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="bf590-146">在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。</span><span class="sxs-lookup"><span data-stu-id="bf590-146">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="bf590-147">在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="bf590-147">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="bf590-148">打开 Program.cs 文件并创建客户端，如下面的代码段中所述。</span><span class="sxs-lookup"><span data-stu-id="bf590-148">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
  
            GenericTableOpClient client = new GenericTableOpClient("SqlAdapterBinding_GenericTableOp");  
    client.ClientCredentials.UserName.UserName = "<Enter username here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="bf590-149">在此代码段，`GenericTableOpClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="bf590-149">In this snippet, `GenericTableOpClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="bf590-150">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bf590-150">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="bf590-151">`SqlAdapterBinding_GenericTableOp`是客户端终结点配置的名称，并在 app.config 中定义。此文件也会生成由[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="bf590-151">`SqlAdapterBinding_GenericTableOp` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf590-152">在此代码段中，你使用的绑定和终结点地址从配置文件。</span><span class="sxs-lookup"><span data-stu-id="bf590-152">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="bf590-153">你还可显式指定这些值在代码中。</span><span class="sxs-lookup"><span data-stu-id="bf590-153">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="bf590-154">指定客户端绑定的不同方法的详细信息，请参阅[为该 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="bf590-154">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5.  <span data-ttu-id="bf590-155">下面的代码段中所述，请打开客户端：</span><span class="sxs-lookup"><span data-stu-id="bf590-155">Open the client as described in the snippet below:</span></span>  
  
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
  
6.  <span data-ttu-id="bf590-156">调用**ExecuteReader** ADD_EMP_DETAILS 操作存储过程。</span><span class="sxs-lookup"><span data-stu-id="bf590-156">Invoke the **ExecuteReader** operation for the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="bf590-157">调用 ExecuteReader 操作之前，必须添加`System.Data`到你的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="bf590-157">Before you invoke the ExecuteReader operation, you must add the `System.Data` namespace to your code.</span></span>  
  
    ```  
    string query = "EXEC ADD_EMP_DETAILS 'Tom Smith', 'Manager', 500000";  
    DataSet[] dsArray = client.ExecuteReader(query);  
  
    Console.WriteLine("Invoking the ADD_EMP_DETAILS stored procedure using ExecuteReader");  
    Console.WriteLine("*****************************************************");  
    foreach (DataSet dataSet in dsArray)  
    {  
       foreach (DataTable tab in dsArray[0].Tables)  
       {  
           foreach (DataRow row in tab.Rows)  
           {  
              for (int i = 0; i < tab.Columns.Count; i++)  
              {  
                 Console.WriteLine("The ID for the newly added employee is : " + row[i]);  
              }  
           }  
        }  
    }  
    Console.WriteLine("*****************************************************");  
  
    ```  
  
7.  <span data-ttu-id="bf590-158">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="bf590-158">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  <span data-ttu-id="bf590-159">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="bf590-159">Build the project and then run it.</span></span> <span data-ttu-id="bf590-160">新插入的员工的员工 ID 显示在控制台中。</span><span class="sxs-lookup"><span data-stu-id="bf590-160">The employee ID of the newly inserted employee is displayed on the console.</span></span>