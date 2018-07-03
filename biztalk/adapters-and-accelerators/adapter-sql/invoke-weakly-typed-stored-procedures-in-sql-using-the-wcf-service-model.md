---
title: 调用弱类型在 SQL 中使用 WCF 服务模型的存储过程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aaf74a40-4c03-4a4a-9b91-c21babe154fa
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cc2e477aaf5ee113f6479559c23d184e91d905f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012070"
---
# <a name="invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="d2215-102">调用弱类型在 SQL 中使用 WCF 服务模型的存储过程</span><span class="sxs-lookup"><span data-stu-id="d2215-102">Invoke Weakly-typed Stored Procedures in SQL using the WCF Service Model</span></span>
<span data-ttu-id="d2215-103">当您调用下列出的过程**过程**中的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，输出是一个数据集数组的形式。</span><span class="sxs-lookup"><span data-stu-id="d2215-103">When you invoke a procedure listed under the **Procedures** node in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], the output is in the form of a DataSet array.</span></span> <span data-ttu-id="d2215-104">本主题提供有关如何创建 WCF 客户端以调用存储的过程返回的数据集数组的 SQL Server 中的说明。</span><span class="sxs-lookup"><span data-stu-id="d2215-104">This topic provides instructions on how to create a WCF client to invoke a stored procedure in SQL Server that returns a DataSet array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2215-105">如果您正在执行对具有用户定义类型的列的表操作，请确保您参考[对表和视图使用 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发应用程序之前。</span><span class="sxs-lookup"><span data-stu-id="d2215-105">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) before you start developing your application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="d2215-106">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="d2215-106">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="d2215-107">本主题中的示例使用 GET_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="d2215-107">The example in this topic uses the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="d2215-108">此存储的过程将员工 ID 作为输入参数并返回相应的所有列的员工与该 id。</span><span class="sxs-lookup"><span data-stu-id="d2215-108">This stored procedure takes an employee ID as an input parameter and returns all the corresponding columns for the employee with that ID.</span></span> <span data-ttu-id="d2215-109">通过运行这些示例提供的 SQL 脚本，创建 GET_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="d2215-109">The GET_EMP_DETAILS stored procedure is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="d2215-110">有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="d2215-110">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="d2215-111">示例中， **Execute_StoredProc**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="d2215-111">A sample, **Execute_StoredProc**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="d2215-112">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="d2215-112">The WCF Client Class</span></span>  
 <span data-ttu-id="d2215-113">为调用存储的过程在生成 WCF 客户端的名称**过程**节点使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]下表中列出。</span><span class="sxs-lookup"><span data-stu-id="d2215-113">The name of the WCF client generated for invoking stored procedures under the **Procedures** node using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="d2215-114">SQL Server 数据库项目</span><span class="sxs-lookup"><span data-stu-id="d2215-114">SQL Server Database Artifact</span></span>|<span data-ttu-id="d2215-115">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="d2215-115">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="d2215-116">过程 (下**过程**节点)</span><span class="sxs-lookup"><span data-stu-id="d2215-116">Procedure (under the **Procedures** node)</span></span>|<span data-ttu-id="d2215-117">Procedures_ [schema] 客户端</span><span class="sxs-lookup"><span data-stu-id="d2215-117">Procedures_[schema]Client</span></span>|  
  
 <span data-ttu-id="d2215-118">[架构] 是该过程所属的架构;例如，"dbo"。</span><span class="sxs-lookup"><span data-stu-id="d2215-118">[schema] is the schema to which the procedure belongs; for example “dbo”.</span></span>  
  
### <a name="method-signature-for-invoking-stored-procedures"></a><span data-ttu-id="d2215-119">用于调用存储的过程的方法签名</span><span class="sxs-lookup"><span data-stu-id="d2215-119">Method Signature for Invoking Stored Procedures</span></span>  
 <span data-ttu-id="d2215-120">下表显示了用于调用存储的过程所公开的方法的签名。</span><span class="sxs-lookup"><span data-stu-id="d2215-120">The following table shows the signature for the method exposed to invoke the stored procedures.</span></span>  
  
|<span data-ttu-id="d2215-121">运算</span><span class="sxs-lookup"><span data-stu-id="d2215-121">Operation</span></span>|<span data-ttu-id="d2215-122">方法签名</span><span class="sxs-lookup"><span data-stu-id="d2215-122">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="d2215-123">过程名称</span><span class="sxs-lookup"><span data-stu-id="d2215-123">Procedure name</span></span>|<span data-ttu-id="d2215-124">System.Data.DataSet [] [procedure_name] (param1，参数 2，...\)</span><span class="sxs-lookup"><span data-stu-id="d2215-124">System.Data.DataSet[] [procedure_name](param1, param2, …\)</span></span>|  
  
 <span data-ttu-id="d2215-125">[过程名称] 是过程; 的名称例如 GET_EMP_DETAILS</span><span class="sxs-lookup"><span data-stu-id="d2215-125">[procedure_name] is the name of the procedure; for example GET_EMP_DETAILS</span></span>  
  
 <span data-ttu-id="d2215-126">例如，要调用 GET_EMP_DETAILS 过程的方法的签名所示下面的代码段。</span><span class="sxs-lookup"><span data-stu-id="d2215-126">As an example, the signature for the method to invoke the GET_EMP_DETAILS procedure is shown in the following code snippet.</span></span>  
  
```  
public partial class Procedures_dboClient : System.ServiceModel.ClientBase<Procedures_dbo>, Procedures_dbo {  
  public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue);  
}  
```  
  
 <span data-ttu-id="d2215-127">此代码片段</span><span class="sxs-lookup"><span data-stu-id="d2215-127">In this snippet,</span></span>  
  
-   <span data-ttu-id="d2215-128">`Procedures_dboClient` 是 WCF 客户端类的名称。</span><span class="sxs-lookup"><span data-stu-id="d2215-128">`Procedures_dboClient` is the name of the WCF client class.</span></span> <span data-ttu-id="d2215-129">在此示例中，您可以使用此类创建的客户端来调用存储的过程。</span><span class="sxs-lookup"><span data-stu-id="d2215-129">In this example, you use this class to create a client to invoke the stored procedure.</span></span>  
  
-   <span data-ttu-id="d2215-130">`public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` 是在此示例中调用的方法来调用存储的过程。</span><span class="sxs-lookup"><span data-stu-id="d2215-130">`public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` is the method that you invoke in this example to invoke the stored procedure.</span></span> <span data-ttu-id="d2215-131">此存储的过程将员工 ID，并返回的数据集数组。</span><span class="sxs-lookup"><span data-stu-id="d2215-131">This stored procedure takes an employee ID and returns a DataSet array.</span></span>  
  
## <a name="create-a-wcf-client-to-invoke-a-stored-procedure-in-sql-server"></a><span data-ttu-id="d2215-132">创建 WCF 客户端以调用 SQL Server 中的存储的过程</span><span class="sxs-lookup"><span data-stu-id="d2215-132">Create a WCF Client to Invoke a Stored Procedure in SQL Server</span></span>  
 <span data-ttu-id="d2215-133">通用组对 SQL Server 使用 WCF 客户端执行操作所需的操作涉及到一组任务中所述[与适配器的 WCF 服务模型概述](overview-of-the-wcf-service-model-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d2215-133">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the Adapter](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="d2215-134">具体而言，本部分介绍如何创建调用存储的过程的结果集是数据集的数组的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="d2215-134">This section specifically describes how to create a WCF client that invokes a stored procedure, the result set for which is a DataSet array.</span></span> <span data-ttu-id="d2215-135">在本主题中，例如，你将调用 GET_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="d2215-135">In this topic, as an example, you invoke the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="d2215-136">通过运行与每个示例提供的 SQL 脚本来创建此存储的过程。</span><span class="sxs-lookup"><span data-stu-id="d2215-136">This stored procedure is created by running the SQL script provided with each sample.</span></span>  
  
  
1. <span data-ttu-id="d2215-137">在 Visual Studio 中创建一个 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="d2215-137">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="d2215-138">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="d2215-138">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="d2215-139">生成 GET_EMP_DETAILS 存储过程的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="d2215-139">Generate the WCF client class for the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="d2215-140">请确保选择下的过程**过程**节点。</span><span class="sxs-lookup"><span data-stu-id="d2215-140">Make sure you select the procedure under the **Procedures** node.</span></span> <span data-ttu-id="d2215-141">有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="d2215-141">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="d2215-142">生成 WCF 客户端类之前，请确保设置**EnableBizTalkCompatibilityMode**属性绑定到 false。</span><span class="sxs-lookup"><span data-stu-id="d2215-142">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3. <span data-ttu-id="d2215-143">在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="d2215-143">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4. <span data-ttu-id="d2215-144">打开 Program.cs 文件，如下面的代码段中所述创建客户端。</span><span class="sxs-lookup"><span data-stu-id="d2215-144">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
   ```  
  
             Procedures_dboClient client = new Procedures_dboClient("SqlAdapterBinding_Procedures_dbo");  
  
   client.ClientCredentials.UserName.UserName = "<Enter username here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  
  
    <span data-ttu-id="d2215-145">在此代码段，`Procedures_dboClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="d2215-145">In this snippet, `Procedures_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="d2215-146">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d2215-146">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="d2215-147">`SqlAdapterBinding_Procedures_dbo` 客户端终结点配置的名称，并在 app.config 中定义。此文件也由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="d2215-147">`SqlAdapterBinding_Procedures_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d2215-148">在此片段中，您使用的绑定和终结点地址从配置文件。</span><span class="sxs-lookup"><span data-stu-id="d2215-148">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="d2215-149">在代码中，可以显式指定这些值。</span><span class="sxs-lookup"><span data-stu-id="d2215-149">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="d2215-150">指定客户端绑定的不同方法的详细信息，请参阅[为 SQL 适配器配置客户端绑定](configure-a-client-binding-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d2215-150">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5. <span data-ttu-id="d2215-151">打开客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="d2215-151">Open the client as described in the snippet below:</span></span>  
  
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
  
6. <span data-ttu-id="d2215-152">调用 GET_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="d2215-152">Invoke the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="d2215-153">调用 GET_EMP_DETAILS 过程之前，必须添加`System.Data`到你的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d2215-153">Before you invoke the GET_EMP_DETAILS procedure, you must add the `System.Data` namespace to your code.</span></span>  
  
   ```  
   DataSet[] dataArray;  
   int returnCode;  
  
   try  
   {  
      Console.WriteLine("Calling a stored procedure...");  
      dataArray = client.GET_EMP_DETAILS(10001, out returnCode);  //Invoke the stored procedure  
   }  
   catch (Exception ex)  
   {  
      Console.WriteLine("Exception: " + ex.Message);  
      throw;  
   }  
   Console.WriteLine("The details for the employee with ID '10001' are:");  
   Console.WriteLine("*************************************************");  
  
   foreach (DataSet dataSet in dataArray)  
   {  
      foreach (DataTable tab in dataArray[0].Tables)  
      {  
         foreach (DataRow row in tab.Rows)  
         {  
            for (int i = 0; i < tab.Columns.Count; i++)  
            {  
               Console.WriteLine(row[i]);  
            }  
         }  
      }  
   }  
   Console.WriteLine("*************************************************");  
  
   ```  
  
7. <span data-ttu-id="d2215-154">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="d2215-154">Close the client as described in the snippet below:</span></span>  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. <span data-ttu-id="d2215-155">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="d2215-155">Build the project and then run it.</span></span> <span data-ttu-id="d2215-156">员工，为你的 pr 详细信息</span><span class="sxs-lookup"><span data-stu-id="d2215-156">The details for the employee, for which you pr</span></span>
9. <span data-ttu-id="d2215-157">ovided ID，将显示在控制台上。</span><span class="sxs-lookup"><span data-stu-id="d2215-157">ovided the ID, are displayed on the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2215-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2215-158">See Also</span></span>  
[<span data-ttu-id="d2215-159">使用 WCF 服务模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="d2215-159">Develop applications using the WCF Service model</span></span>](develop-sql-applications-using-the-wcf-service-model.md)