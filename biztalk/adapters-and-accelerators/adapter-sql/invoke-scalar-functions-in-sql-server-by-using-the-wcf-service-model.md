---
title: "使用 WCF 服务模型调用 SQL Server 中的标量函数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a331e275-3c81-41a8-9ba1-3a801ebc259a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a04904f1170644498d49670104a842b4c8f9dd2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model"></a><span data-ttu-id="90b59-102">使用 WCF 服务模型调用 SQL Server 中的标量函数</span><span class="sxs-lookup"><span data-stu-id="90b59-102">Invoke Scalar Functions in SQL Server by Using the WCF Service Model</span></span>
<span data-ttu-id="90b59-103">你可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在.NET 应用程序中使用 WCF 服务模型调用 SQL Server 中的标量函数。</span><span class="sxs-lookup"><span data-stu-id="90b59-103">You can use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a .NET application using the WCF service model to invoke scalar functions in SQL Server.</span></span> <span data-ttu-id="90b59-104">适配器将标量函数公开为可以直接在 SQL Server 调用的方法。</span><span class="sxs-lookup"><span data-stu-id="90b59-104">The adapter exposes the scalar functions as methods that can be invoked directly on SQL Server.</span></span> <span data-ttu-id="90b59-105">有关如何适配器支持标量函数的详细信息，请参阅[执行 SQL Server 使用的 SQL 适配器中的标量函数](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="90b59-105">For more information about how the adapter supports scalar functions, see [Execute Scalar Functions in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
## <a name="how-this-topic-demonstrates-invoking-scalar-functions-using-the-wcf-service-model"></a><span data-ttu-id="90b59-106">如何本主题演示如何调用使用 WCF 服务模型的标量函数</span><span class="sxs-lookup"><span data-stu-id="90b59-106">How This Topic Demonstrates Invoking Scalar Functions Using the WCF Service Model</span></span>  
 <span data-ttu-id="90b59-107">本主题演示如何调用中的 SQL Server 数据库的 GET_EMP_ID 函数。</span><span class="sxs-lookup"><span data-stu-id="90b59-107">This topic demonstrates how to invoke the GET_EMP_ID function in a SQL Server database.</span></span> <span data-ttu-id="90b59-108">GET_EMP_ID 函数采用的某位员工的指定**员工**表并返回相应的员工 id。</span><span class="sxs-lookup"><span data-stu-id="90b59-108">The GET_EMP_ID function takes the designation of an employee in the **Employee** table and returns the corresponding employee ID.</span></span> <span data-ttu-id="90b59-109">GET_EMP_ID 函数和**员工**通过运行这些示例使用提供的 SQL 脚本创建表。</span><span class="sxs-lookup"><span data-stu-id="90b59-109">The GET_EMP_ID function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="90b59-110">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="90b59-110">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="90b59-111">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="90b59-111">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="90b59-112">本主题中的示例调用 GET_EMP_ID 标量函数对员工表。</span><span class="sxs-lookup"><span data-stu-id="90b59-112">The example in this topic invoked the GET_EMP_ID scalar function on the Employee table.</span></span> <span data-ttu-id="90b59-113">GET_EMP_ID 函数和**员工**通过运行这些示例使用提供的 SQL 脚本创建表。</span><span class="sxs-lookup"><span data-stu-id="90b59-113">The GET_EMP_ID function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="90b59-114">示例中， **ScalarFunction_ServiceModel**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="90b59-114">A sample, **ScalarFunction_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span> <span data-ttu-id="90b59-115">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="90b59-115">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="90b59-116">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="90b59-116">The WCF Client Class</span></span>  
 <span data-ttu-id="90b59-117">为调用中使用 SQL Server 的标量函数生成 WCF 客户端的名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]下表中列出。</span><span class="sxs-lookup"><span data-stu-id="90b59-117">The name of the WCF client generated for invoking the scalar function in SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="90b59-118">SQL Server 数据库项目</span><span class="sxs-lookup"><span data-stu-id="90b59-118">SQL Server Database Artifact</span></span>|<span data-ttu-id="90b59-119">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="90b59-119">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="90b59-120">标量函数</span><span class="sxs-lookup"><span data-stu-id="90b59-120">Scalar function</span></span>|<span data-ttu-id="90b59-121">ScalarFunctions_ [架构] 客户端</span><span class="sxs-lookup"><span data-stu-id="90b59-121">ScalarFunctions_[SCHEMA]Client</span></span>|  
  
 <span data-ttu-id="90b59-122">[架构] = SQL Server 集合项目;例如，dbo。</span><span class="sxs-lookup"><span data-stu-id="90b59-122">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
### <a name="method-signature-for-invoking-scalar-functions"></a><span data-ttu-id="90b59-123">方法调用标量函数的签名</span><span class="sxs-lookup"><span data-stu-id="90b59-123">Method Signature for Invoking Scalar Functions</span></span>  
 <span data-ttu-id="90b59-124">下表显示对表的基本操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="90b59-124">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="90b59-125">签名是相同的视图，只不过视图命名空间和名称替换那些表。</span><span class="sxs-lookup"><span data-stu-id="90b59-125">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="90b59-126">运算</span><span class="sxs-lookup"><span data-stu-id="90b59-126">Operation</span></span>|<span data-ttu-id="90b59-127">方法签名</span><span class="sxs-lookup"><span data-stu-id="90b59-127">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="90b59-128">标量函数名称</span><span class="sxs-lookup"><span data-stu-id="90b59-128">Scalar function name</span></span>|<span data-ttu-id="90b59-129">公共*< return_type >**< scalar_function_name >*(param1，param2，...)</span><span class="sxs-lookup"><span data-stu-id="90b59-129">public *<return_type>**<scalar_function_name>*(param1, param2, …)</span></span>|  
  
 <span data-ttu-id="90b59-130">\<*retrun_type* \> = 在函数定义中定义的返回类型</span><span class="sxs-lookup"><span data-stu-id="90b59-130">\<*retrun_type*\> = Return type defined in the function definition</span></span>  
  
 <span data-ttu-id="90b59-131">\<*scalar_function_name* \> = 标量函数的名称。</span><span class="sxs-lookup"><span data-stu-id="90b59-131">\<*scalar_function_name*\> = Name of the scalar function.</span></span>  
  
 <span data-ttu-id="90b59-132">例如，下面的代码演示方法签名，用于生成 WCF 客户端类**GET_EMP_ID**标量函数，在 dbo 架构中，它将作为参数员工指定内容并返回员工 ID （整数）。</span><span class="sxs-lookup"><span data-stu-id="90b59-132">As an example, the following code shows the method signatures for a WCF client class generated for the **GET_EMP_ID** scalar functions, in the dbo schema, which takes the employee designation as a parameter and returns an employee ID (integer).</span></span>  
  
```  
public partial class ScalarFunctions_dboClient : System.ServiceModel.ClientBase<ScalarFunctions_dbo>, ScalarFunctions_dbo {      
    public System.Nullable<int> GET_EMP_ID(string emp_desig);  
}  
```  
  
 <span data-ttu-id="90b59-133">在此代码段， **ScalarFunctions_dboClient**是 WCF 中的类的生成的 SqlAdapterBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="90b59-133">In this snippet, **ScalarFunctions_dboClient** is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-invoking-scalar-functions"></a><span data-ttu-id="90b59-134">调用标量函数的参数</span><span class="sxs-lookup"><span data-stu-id="90b59-134">Parameters for Invoking Scalar Functions</span></span>  
 <span data-ttu-id="90b59-135">通过公开的方法的参数[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]来调用一个标量函数都作为 SQL Server 中的标量函数定义中定义的参数相同。</span><span class="sxs-lookup"><span data-stu-id="90b59-135">The parameters for the methods exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to invoke a scalar function are the same as the parameters defined in the scalar function definition in SQL Server.</span></span> <span data-ttu-id="90b59-136">例如，调用 GET_EMP_ID 标量函数的参数是 emp_desig 并且充分员工的代码。</span><span class="sxs-lookup"><span data-stu-id="90b59-136">For example, the parameter for invoking the GET_EMP_ID scalar function is emp_desig and takes an employee’s designation.</span></span>  
  
 <span data-ttu-id="90b59-137">同样，一个标量函数的返回值是与 SQL Server 中的标量函数定义中定义的返回值相同。</span><span class="sxs-lookup"><span data-stu-id="90b59-137">Again, the return value for a scalar function is same as the return value defined in the scalar function definition in SQL Server.</span></span> <span data-ttu-id="90b59-138">例如，GET_EMP_ID 函数的返回值是整数类型的员工的 ID。</span><span class="sxs-lookup"><span data-stu-id="90b59-138">For example, the return value for the GET_EMP_ID function is an employee’s ID of type integer.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-scalar-functions"></a><span data-ttu-id="90b59-139">创建 WCF 客户端调用标量函数</span><span class="sxs-lookup"><span data-stu-id="90b59-139">Creating a WCF Client to Invoke Scalar Functions</span></span>  
 <span data-ttu-id="90b59-140">泛型的执行 SQL Server 使用 WCF 客户端上的操作所需的操作集涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="90b59-140">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="90b59-141">本部分介绍如何创建 WCF 客户端来调用**GET_EMP_ID**标量函数。</span><span class="sxs-lookup"><span data-stu-id="90b59-141">This section describes how to create a WCF client to invoke the **GET_EMP_ID** scalar function.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="90b59-142">若要创建 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="90b59-142">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="90b59-143">创建 Visual C# 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="90b59-143">Create a Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="90b59-144">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="90b59-144">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="90b59-145">生成的 WCF 客户端类**GET_EMP_ID**标量函数。</span><span class="sxs-lookup"><span data-stu-id="90b59-145">Generate the WCF client class for the **GET_EMP_ID** scalar function.</span></span> <span data-ttu-id="90b59-146">有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="90b59-146">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
3.  <span data-ttu-id="90b59-147">在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="90b59-147">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="90b59-148">打开 Program.cs，如下面的代码段中所述创建客户端。</span><span class="sxs-lookup"><span data-stu-id="90b59-148">Open the Program.cs and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              ScalarFunctions_dboClient client = new ScalarFunctions_dboClient("SqlAdapterBinding_ScalarFunctions_dbo");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="90b59-149">在此代码段，`ScalarFunctions_dboClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="90b59-149">In this snippet, `ScalarFunctions_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="90b59-150">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="90b59-150">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="90b59-151">`SqlAdapterBinding_ScalarFunctions_dbo`是客户端终结点配置的名称，并在 app.config 中定义。此文件也会生成由[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="90b59-151">`SqlAdapterBinding_ScalarFunctions_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90b59-152">在此代码段中，你使用的绑定和终结点地址从配置文件。</span><span class="sxs-lookup"><span data-stu-id="90b59-152">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="90b59-153">你还可显式指定这些值在代码中。</span><span class="sxs-lookup"><span data-stu-id="90b59-153">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="90b59-154">然后指定客户端绑定的不同方法的详细信息，请参阅[为该 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="90b59-154">For more information on the different ways of specifying then client binding, see [Configure  a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5.  <span data-ttu-id="90b59-155">下面的代码段中所述，请打开客户端：</span><span class="sxs-lookup"><span data-stu-id="90b59-155">Open the client as described in the snippet below:</span></span>  
  
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
  
6.  <span data-ttu-id="90b59-156">调用**GET_EMP_ID**函数可检索与指定为"Manager"员工的 ID。</span><span class="sxs-lookup"><span data-stu-id="90b59-156">Invoke the **GET_EMP_ID** function to retrieve the ID for an employee with the designation as “Manager”.</span></span>  
  
    ```  
    Console.WriteLine("Invoking the GET_EMP_ID function");  
    string emp_designation = "Manager";  
    try  
    {  
          System.Nullable<int> emp_id = client.GET_EMP_ID(emp_designation);  
          Console.WriteLine("The Employee ID for the employee with 'Manager' designation is:" + emp_id);  
    }  
    catch (Exception e)  
    {  
          Console.WriteLine("Exception: " + e.Message);  
          throw;  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="90b59-157">为简单起见，**员工**表具有只有一个员工具有"Manager"标志。</span><span class="sxs-lookup"><span data-stu-id="90b59-157">For the sake of simplicity, the **Employee** table has only one employee with “Manager” designation.</span></span> <span data-ttu-id="90b59-158">如果您的目标表具有更多员工使用相同的代码，则必须相应地定义函数。</span><span class="sxs-lookup"><span data-stu-id="90b59-158">If your target table has more employees with the same designation, you must define the function accordingly.</span></span>  
  
7.  <span data-ttu-id="90b59-159">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="90b59-159">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  <span data-ttu-id="90b59-160">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="90b59-160">Build the project and then run it.</span></span> <span data-ttu-id="90b59-161">应用程序将显示带有"Manager"标志的员工的员工 ID。</span><span class="sxs-lookup"><span data-stu-id="90b59-161">The application displays the employee ID of the employee with the designation of “Manager”.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b59-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90b59-162">See Also</span></span>  
[<span data-ttu-id="90b59-163">使用 WCF 服务模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="90b59-163">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)