---
title: 调用 SQL 使用 WCF 服务模型中的强类型化存储过程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d56df5f6-b046-4fe4-a5b4-b29906093beb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 591dd1c42913f44e148cb0c68a084d55f78c4d93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223981"
---
# <a name="invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model"></a><span data-ttu-id="be8d2-102">调用 SQL 使用 WCF 服务模型中的强类型化存储过程</span><span class="sxs-lookup"><span data-stu-id="be8d2-102">Invoke Strongly-typed Stored Procedures in SQL using WCF Service Model</span></span>
<span data-ttu-id="be8d2-103">当您调用下列出的过程**Strongly-Typed 过程**中的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，输出为强类型化结果集的形式。</span><span class="sxs-lookup"><span data-stu-id="be8d2-103">When you invoke a procedure listed under the **Strongly-Typed Procedures** node in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], the output is in the form of a strongly-typed result set.</span></span> <span data-ttu-id="be8d2-104">本主题将说明了如何创建 WCF 客户端来调用 SQL Server 中存储返回强类型化结果集的过程。</span><span class="sxs-lookup"><span data-stu-id="be8d2-104">This topic provides instructions on how to create a WCF client to invoke stored procedures in SQL Server that return a strongly-typed result set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be8d2-105">如果您正在执行包含的用户定义类型的列的表上的操作，请确保您参考[对表和视图使用用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发你的应用程序之前。</span><span class="sxs-lookup"><span data-stu-id="be8d2-105">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) before you start developing your application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="be8d2-106">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="be8d2-106">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="be8d2-107">本主题中的示例使用 GET_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="be8d2-107">The example in this topic uses the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="be8d2-108">此存储的过程采用雇员 ID 作为输入参数并返回具有该 ID 员工所有对应的列</span><span class="sxs-lookup"><span data-stu-id="be8d2-108">This stored procedure takes an employee ID as an input parameter and returns all the corresponding columns for the employee with that ID.</span></span> <span data-ttu-id="be8d2-109">通过运行这些示例使用提供的 SQL 脚本创建 GET_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="be8d2-109">The GET_EMP_DETAILS stored procedure is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="be8d2-110">有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="be8d2-110">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="be8d2-111">示例中， **Execute_TypedStoredProcedure**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="be8d2-111">A sample, **Execute_TypedStoredProcedure**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="be8d2-112">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="be8d2-112">The WCF Client Class</span></span>  
 <span data-ttu-id="be8d2-113">为调用下的存储的过程生成 WCF 客户端的名称**Strongly-Typed 过程**节点使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]下表中列出。</span><span class="sxs-lookup"><span data-stu-id="be8d2-113">The name of the WCF client generated for invoking stored procedures under the **Strongly-Typed Procedures** node using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="be8d2-114">SQL Server 数据库项目</span><span class="sxs-lookup"><span data-stu-id="be8d2-114">SQL Server Database Artifact</span></span>|<span data-ttu-id="be8d2-115">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="be8d2-115">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="be8d2-116">过程 (下**Strongly-Typed 过程**节点)</span><span class="sxs-lookup"><span data-stu-id="be8d2-116">Procedure (under the **Strongly-Typed Procedures** node)</span></span>|<span data-ttu-id="be8d2-117">TypedProcedures_ [架构] 客户端</span><span class="sxs-lookup"><span data-stu-id="be8d2-117">TypedProcedures_[schema]Client</span></span>|  
  
 <span data-ttu-id="be8d2-118">[架构] 是该过程所属的架构;例如，"dbo"。</span><span class="sxs-lookup"><span data-stu-id="be8d2-118">[schema] is the schema to which the procedure belongs; for example “dbo”.</span></span>  
  
### <a name="method-signature-for-invoking-stored-procedures"></a><span data-ttu-id="be8d2-119">调用存储的过程的方法签名</span><span class="sxs-lookup"><span data-stu-id="be8d2-119">Method Signature for Invoking Stored Procedures</span></span>  
 <span data-ttu-id="be8d2-120">下表显示了要调用的存储的过程所公开的方法的签名。</span><span class="sxs-lookup"><span data-stu-id="be8d2-120">The following table shows the signature for the method exposed to invoke the stored procedures.</span></span>  
  
|<span data-ttu-id="be8d2-121">运算</span><span class="sxs-lookup"><span data-stu-id="be8d2-121">Operation</span></span>|<span data-ttu-id="be8d2-122">方法签名</span><span class="sxs-lookup"><span data-stu-id="be8d2-122">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="be8d2-123">过程名称</span><span class="sxs-lookup"><span data-stu-id="be8d2-123">Procedure name</span></span>|<span data-ttu-id="be8d2-124">[PROC_NS][procedure_name](param1，param2，...\)</span><span class="sxs-lookup"><span data-stu-id="be8d2-124">[PROC_NS] [procedure_name](param1, param2, …\)</span></span>|  
  
 <span data-ttu-id="be8d2-125">[PROC_NS] 是过程的命名空间;例如 schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0]</span><span class="sxs-lookup"><span data-stu-id="be8d2-125">[PROC_NS] is the procedure namespace; for example schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[]</span></span>  
  
 <span data-ttu-id="be8d2-126">[procedure_name] 是过程; 的名称例如 GET_EMP_DETAILS</span><span class="sxs-lookup"><span data-stu-id="be8d2-126">[procedure_name] is the name of the procedure; for example GET_EMP_DETAILS</span></span>  
  
 <span data-ttu-id="be8d2-127">例如，要调用 GET_EMP_DETAILS 过程的方法的签名所示下面的代码段。</span><span class="sxs-lookup"><span data-stu-id="be8d2-127">As an example, the signature for the method to invoke the GET_EMP_DETAILS procedure is shown in the following code snippet.</span></span>  
  
```  
public partial class TypedProcedures_dboClient : System.ServiceModel.ClientBase<TypedProcedures_dbo>, TypedProcedures_dbo{  
public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[]   
  GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue);  
}  
```  
  
 <span data-ttu-id="be8d2-128">在此代码段</span><span class="sxs-lookup"><span data-stu-id="be8d2-128">In this snippet,</span></span>  
  
-   <span data-ttu-id="be8d2-129">`TypedProcedures_dboClient`是类的名称。</span><span class="sxs-lookup"><span data-stu-id="be8d2-129">`TypedProcedures_dboClient` is the name of the class.</span></span> <span data-ttu-id="be8d2-130">在此示例中，你可以使用此类创建客户端来调用存储的过程。</span><span class="sxs-lookup"><span data-stu-id="be8d2-130">In this example, you use this class to create a client to invoke the stored procedure.</span></span>  
  
-   <span data-ttu-id="be8d2-131">`public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)`是在此示例中调用的方法来调用存储的过程。</span><span class="sxs-lookup"><span data-stu-id="be8d2-131">`public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` is the method that you invoke in this example to invoke the stored procedure.</span></span> <span data-ttu-id="be8d2-132">此存储的过程采用雇员 ID，并返回一个强类型化结果集。</span><span class="sxs-lookup"><span data-stu-id="be8d2-132">This stored procedure takes an employee ID and returns a strongly-typed result set.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-a-stored-procedure-in-sql-server"></a><span data-ttu-id="be8d2-133">创建 WCF 客户端来调用 SQL Server 中的存储的过程</span><span class="sxs-lookup"><span data-stu-id="be8d2-133">Creating a WCF Client to Invoke a Stored Procedure in SQL Server</span></span>  
 <span data-ttu-id="be8d2-134">泛型的执行 SQL Server 使用 WCF 客户端上的操作所需的操作集涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](overview-of-the-wcf-service-model-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="be8d2-134">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="be8d2-135">具体而言，本部分介绍如何创建调用存储的过程中，结果集为强类型的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="be8d2-135">This section specifically describes how to create a WCF client that invokes a stored procedure, the result set for which is strongly-typed.</span></span> <span data-ttu-id="be8d2-136">在本主题中，例如，可以调用 GET_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="be8d2-136">In this topic, as an example, you invoke the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="be8d2-137">此存储的过程是通过运行与每个示例提供的 SQL 脚本创建的。</span><span class="sxs-lookup"><span data-stu-id="be8d2-137">This stored procedure is created by running the SQL script provided with each sample.</span></span>  
  
1.  <span data-ttu-id="be8d2-138">在 Visual Studio 中创建 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="be8d2-138">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="be8d2-139">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="be8d2-139">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="be8d2-140">生成 GET_EMP_DETAILS 存储过程的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="be8d2-140">Generate the WCF client class for the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="be8d2-141">请确保你选择在过程**Strongly-Typed 过程**节点。</span><span class="sxs-lookup"><span data-stu-id="be8d2-141">Make sure you select the procedure under the **Strongly-Typed Procedures** node.</span></span> <span data-ttu-id="be8d2-142">有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="be8d2-142">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="be8d2-143">在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。</span><span class="sxs-lookup"><span data-stu-id="be8d2-143">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="be8d2-144">在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="be8d2-144">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="be8d2-145">打开 Program.cs 文件并创建客户端，如下面的代码段中所述。</span><span class="sxs-lookup"><span data-stu-id="be8d2-145">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              TypedProcedures_dboClient client = new TypedProcedures_dboClient("SqlAdapterBinding_TypedProcedures_dbo");  
    client.ClientCredentials.UserName.UserName = "<Enter username here>";  
    client.ClientCredentials.UserName.Password = "<Enter username here>";  
    ```  
  
     <span data-ttu-id="be8d2-146">在此代码段，`TypedProcedures_dboClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="be8d2-146">In this snippet, `TypedProcedures_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="be8d2-147">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be8d2-147">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="be8d2-148">`SqlAdapterBinding_TypedProcedures_dbo`是客户端终结点配置的名称，并在 app.config 中定义。此文件也会生成由[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="be8d2-148">`SqlAdapterBinding_TypedProcedures_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be8d2-149">在此代码段中，你使用的绑定和终结点地址从配置文件。</span><span class="sxs-lookup"><span data-stu-id="be8d2-149">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="be8d2-150">你还可显式指定这些值在代码中。</span><span class="sxs-lookup"><span data-stu-id="be8d2-150">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="be8d2-151">指定客户端绑定的不同方法的详细信息，请参阅[为该 SQL 适配器配置客户端绑定](configure-a-client-binding-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="be8d2-151">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5.  <span data-ttu-id="be8d2-152">下面的代码段中所述，请打开客户端：</span><span class="sxs-lookup"><span data-stu-id="be8d2-152">Open the client as described in the snippet below:</span></span>  
  
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
  
6.  <span data-ttu-id="be8d2-153">调用 GET_EMP_DETAILS 存储过程，如下面的代码段中所述。</span><span class="sxs-lookup"><span data-stu-id="be8d2-153">Invoke the GET_EMP_DETAILS stored procedure as described in the snippet below.</span></span>  
  
    ```  
    // Create array of type as specified in the method signature  
    schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] resultSet =  
       new schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[1];  
    int returnCode;  
  
    try  
    {  
       Console.WriteLine("Calling a stored procedure...");  
       resultSet = client.GET_EMP_DETAILS(10001, out returnCode);  //Invoke the stored procedure  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    Console.WriteLine("The details for the employee with ID '10001' are:");  
    Console.WriteLine("*************************************************");  
  
    for (int i = 0; i < resultSet.Length; i++)  
       {  
          Console.WriteLine("Employee Name        : " + resultSet[i].Name);  
          Console.WriteLine("Employee Designation : " + resultSet[i].Designation);  
          Console.WriteLine("Employee Salary      : " + resultSet[i].Salary);  
       }  
  
    Console.WriteLine("*************************************************");  
  
    ```  
  
7.  <span data-ttu-id="be8d2-154">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="be8d2-154">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  <span data-ttu-id="be8d2-155">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="be8d2-155">Build the project and then run it.</span></span> <span data-ttu-id="be8d2-156">在控制台上显示名称、 指派应用时，和员工 ID 的薪水。</span><span class="sxs-lookup"><span data-stu-id="be8d2-156">The name, designation, and salary for the employee ID, are displayed on the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be8d2-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be8d2-157">See Also</span></span>  
[<span data-ttu-id="be8d2-158">开发应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="be8d2-158">Develop applications using the WCF Service model</span></span>](develop-sql-applications-using-the-wcf-service-model.md)