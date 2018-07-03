---
title: 通过使用 WCF 服务模型中调用 SQL Server 中的表值函数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48688bcc-36b4-4cc1-b078-17e7a5e1cf8c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4243973f6e6b04cddec14261d5b1acedff4b9e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989158"
---
# <a name="invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model"></a><span data-ttu-id="deb98-102">通过使用 WCF 服务模型中调用 SQL Server 中的表值函数</span><span class="sxs-lookup"><span data-stu-id="deb98-102">Invoke Table-Valued Functions in SQL Server by Using the WCF Service Model</span></span>
<span data-ttu-id="deb98-103">可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].NET 应用程序使用 WCF 服务模型来调用 SQL Server 中的表值函数中。</span><span class="sxs-lookup"><span data-stu-id="deb98-103">You can use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a .NET application using the WCF service model to invoke table-valued functions in SQL Server.</span></span> <span data-ttu-id="deb98-104">该适配器将表值函数公开为可以直接在 SQL Server 调用的方法。</span><span class="sxs-lookup"><span data-stu-id="deb98-104">The adapter exposes the table-valued functions as methods that can be invoked directly on SQL Server.</span></span> <span data-ttu-id="deb98-105">有关如何在适配器支持标量函数的详细信息，请参阅[Execute Table-Valued 函数中使用 SQL 适配器的 SQL Server](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="deb98-105">For more information about how the adapter supports scalar functions, see [Execute Table-Valued Functions in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
 <span data-ttu-id="deb98-106">本主题演示如何在 SQL Server 数据库 TVF_EMPLOYEE 函数调用。</span><span class="sxs-lookup"><span data-stu-id="deb98-106">This topic demonstrates how to invoke the TVF_EMPLOYEE function in a SQL Server database.</span></span> <span data-ttu-id="deb98-107">TVF_EMPLOYEE 函数采用指定的某位员工的**员工**表，并返回该员工记录。</span><span class="sxs-lookup"><span data-stu-id="deb98-107">The TVF_EMPLOYEE function takes the designation of an employee in the **Employee** table and returns the record for the employee.</span></span> <span data-ttu-id="deb98-108">TVF_EMPLOYEE 函数和**员工**通过运行这些示例提供的 SQL 脚本创建表。</span><span class="sxs-lookup"><span data-stu-id="deb98-108">The TVF_EMPLOYEE function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="deb98-109">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="deb98-109">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="deb98-110">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="deb98-110">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="deb98-111">本主题中的示例在调用 TVF_EMPLOYEE 表值函数**员工**表。</span><span class="sxs-lookup"><span data-stu-id="deb98-111">The example in this topic invoked the TVF_EMPLOYEE table-valued function on the **Employee** table.</span></span> <span data-ttu-id="deb98-112">TVF_EMPLOYEE 函数和**员工**通过运行这些示例提供的 SQL 脚本创建表。</span><span class="sxs-lookup"><span data-stu-id="deb98-112">TVF_EMPLOYEE function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="deb98-113">示例中， **TableFunction_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="deb98-113">A sample, **TableFunction_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span> <span data-ttu-id="deb98-114">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="deb98-114">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="deb98-115">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="deb98-115">The WCF Client Class</span></span>  
 <span data-ttu-id="deb98-116">生成用于调用标量函数中使用 SQL Server 的 WCF 客户端名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]下表中列出。</span><span class="sxs-lookup"><span data-stu-id="deb98-116">The name of the WCF client generated for invoking the scalar function in SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="deb98-117">SQL Server 数据库项目</span><span class="sxs-lookup"><span data-stu-id="deb98-117">SQL Server Database Artifact</span></span>|<span data-ttu-id="deb98-118">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="deb98-118">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="deb98-119">表值函数</span><span class="sxs-lookup"><span data-stu-id="deb98-119">Table-valued function</span></span>|<span data-ttu-id="deb98-120">客户端 TableValuedFunctions_ [架构]</span><span class="sxs-lookup"><span data-stu-id="deb98-120">TableValuedFunctions_[SCHEMA]Client</span></span>|  
  
 <span data-ttu-id="deb98-121">[架构] = 集合的 SQL Server 项目;例如，dbo。</span><span class="sxs-lookup"><span data-stu-id="deb98-121">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
### <a name="method-signature-for-invoking-table-valued-functions"></a><span data-ttu-id="deb98-122">用于调用表值函数的方法签名</span><span class="sxs-lookup"><span data-stu-id="deb98-122">Method Signature for Invoking Table-valued Functions</span></span>  
 <span data-ttu-id="deb98-123">下表显示了对表的基本操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="deb98-123">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="deb98-124">签名是相同的视图，只不过视图命名空间和名称替换这些表。</span><span class="sxs-lookup"><span data-stu-id="deb98-124">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="deb98-125">运算</span><span class="sxs-lookup"><span data-stu-id="deb98-125">Operation</span></span>|<span data-ttu-id="deb98-126">方法签名</span><span class="sxs-lookup"><span data-stu-id="deb98-126">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="deb98-127">表值函数名称</span><span class="sxs-lookup"><span data-stu-id="deb98-127">Table-valued function name</span></span>|<span data-ttu-id="deb98-128">公共 [NAMESPACE] [FUNCTION_NAME] [] [FUNCTION_NAME] (param1，参数 2，...\)</span><span class="sxs-lookup"><span data-stu-id="deb98-128">public [NAMESPACE][FUNCTION_NAME][] [FUNCTION_NAME](param1, param2, …\)</span></span>|  
  
 <span data-ttu-id="deb98-129">[NAMESPACE] = 命名空间，例如，schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE</span><span class="sxs-lookup"><span data-stu-id="deb98-129">[NAMESPACE] = The namespace, for example, schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE</span></span>  
  
 <span data-ttu-id="deb98-130">[FUNCTION_NAME] = 表值函数的名称。</span><span class="sxs-lookup"><span data-stu-id="deb98-130">[FUNCTION_NAME] = Name of the table-valued function.</span></span>  
  
 <span data-ttu-id="deb98-131">例如，下面的代码演示的方法签名，用于为生成 WCF 客户端类**TVF_EMPLOYEE**在 dbo 架构中，它将员工指定为参数并返回该雇员的标量函数记录。</span><span class="sxs-lookup"><span data-stu-id="deb98-131">As an example, the following code shows the method signatures for a WCF client class generated for the **TVF_EMPLOYEE** scalar functions, in the dbo schema, which takes the employee designation as a parameter and returns the employee record.</span></span>  
  
```  
public partial class TableValuedFunctions_dboClient : System.ServiceModel.ClientBase<TableValuedFunctions_dbo>, TableValuedFunctions_dbo {      
    public schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] TVF_EMPLOYEE(string emp_desig);  
}  
```  
  
 <span data-ttu-id="deb98-132">此代码片段**TableValuedFunctions_dboClient**是 WCF 中的类的生成的 SqlAdapterBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="deb98-132">In this snippet, **TableValuedFunctions_dboClient** is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-invoking-table-valued-functions"></a><span data-ttu-id="deb98-133">调用表值函数的参数</span><span class="sxs-lookup"><span data-stu-id="deb98-133">Parameters for Invoking Table-valued Functions</span></span>  
 <span data-ttu-id="deb98-134">通过公开的方法的参数[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]调用表值函数将与 SQL Server 中的函数定义中定义的参数相同。</span><span class="sxs-lookup"><span data-stu-id="deb98-134">The parameters for the methods exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to invoke a table-valued function are the same as the parameters defined in the function definition in SQL Server.</span></span> <span data-ttu-id="deb98-135">例如，调用 TVF_EMPLOYEE 表值函数的参数相当 emp_desig，员工的代码。</span><span class="sxs-lookup"><span data-stu-id="deb98-135">For example, the parameter for invoking the TVF_EMPLOYEE table-valued function is emp_desig and takes an employee’s designation.</span></span>  
  
 <span data-ttu-id="deb98-136">同样，对于表值函数的返回值是与 SQL Server 中的函数定义中定义的返回值相同。</span><span class="sxs-lookup"><span data-stu-id="deb98-136">Again, the return value for a table-valued function is same as the return value defined in the function definition in SQL Server.</span></span> <span data-ttu-id="deb98-137">例如，TVF_EMPLOYEE 函数的返回值是一个数组类型 schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE [] 的记录。</span><span class="sxs-lookup"><span data-stu-id="deb98-137">For example, the return value for the TVF_EMPLOYEE function is an array of records of type schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[].</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-table-valued-functions"></a><span data-ttu-id="deb98-138">创建 WCF 客户端调用表值函数</span><span class="sxs-lookup"><span data-stu-id="deb98-138">Creating a WCF Client to Invoke Table-valued Functions</span></span>  
 <span data-ttu-id="deb98-139">通用组对 SQL Server 使用 WCF 客户端执行操作所需的操作涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](overview-of-the-wcf-service-model-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="deb98-139">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="deb98-140">本部分介绍如何创建 WCF 客户端以调用**TVF_EMPLOYEE**表值函数。</span><span class="sxs-lookup"><span data-stu-id="deb98-140">This section describes how to create a WCF client to invoke the **TVF_EMPLOYEE** table-valued function.</span></span>  
  
 
1. <span data-ttu-id="deb98-141">创建 Visual C# 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsVStudioNoVersion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="deb98-141">Create a Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsVStudioNoVersion-md.md)].</span></span> <span data-ttu-id="deb98-142">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="deb98-142">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="deb98-143">生成的 WCF 客户端类**TVF_EMPLOYEE**标量函数。</span><span class="sxs-lookup"><span data-stu-id="deb98-143">Generate the WCF client class for the **TVF_EMPLOYEE** scalar function.</span></span> <span data-ttu-id="deb98-144">有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="deb98-144">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
3. <span data-ttu-id="deb98-145">在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="deb98-145">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4. <span data-ttu-id="deb98-146">打开 Program.cs，并创建一个客户端，如下面的代码段中所述。</span><span class="sxs-lookup"><span data-stu-id="deb98-146">Open the Program.cs and create a client as described in the snippet below.</span></span>  
  
   ```  
  
             TableValuedFunctions_dboClient client = new TableValuedFunctions_dboClient("SqlAdapterBinding_TableValuedFunctions_dbo");  
   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  
  
    <span data-ttu-id="deb98-147">在此代码段，`TableValuedFunctions_dboClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="deb98-147">In this snippet, `TableValuedFunctions_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="deb98-148">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="deb98-148">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="deb98-149">`SqlAdapterBinding_TableValuedFunctions_dbo` 客户端终结点配置的名称，并在 app.config 中定义。此文件也由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="deb98-149">`SqlAdapterBinding_TableValuedFunctions_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="deb98-150">在此片段中，您使用的绑定和终结点地址从配置文件。</span><span class="sxs-lookup"><span data-stu-id="deb98-150">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="deb98-151">在代码中，可以显式指定这些值。</span><span class="sxs-lookup"><span data-stu-id="deb98-151">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="deb98-152">然后指定客户端绑定的不同方法的详细信息，请参阅[为 SQL 适配器配置客户端绑定](configure-a-client-binding-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="deb98-152">For more information on the different ways of specifying then client binding, see [Configure a Client Binding for the SQL Adapter](configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5. <span data-ttu-id="deb98-153">打开客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="deb98-153">Open the client as described in the snippet below:</span></span>  
  
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
  
6. <span data-ttu-id="deb98-154">调用**TVF_EMPLOYEE**函数以检索具有指定的"管理器"的所有员工记录。</span><span class="sxs-lookup"><span data-stu-id="deb98-154">Invoke the **TVF_EMPLOYEE** function to retrieve all the employee records having the “Manager” designation.</span></span>  
  
   ```  
   Console.WriteLine("Invoking the TVF_EMPLOYEE function");  
   schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] emp_details;  
   string emp_designation = "Manager";  
  
   try  
   {  
       emp_details = client.TVF_EMPLOYEE(emp_designation);  
   }  
   catch (Exception e)  
   {  
       Console.WriteLine("Exception: " + e.Message);  
       throw;  
   }  
   Console.WriteLine("The details for the employee with the 'Manager' designation are:");  
   Console.WriteLine("*******************************************************************");  
   for (int i = 0; i < emp_details.Length; i++)  
   {  
       Console.WriteLine("Employee ID        : " + emp_details[i].Employee_ID);  
       Console.WriteLine("Employee Name      : " + emp_details[i].Name);  
       Console.WriteLine("Employee Desigation: " + emp_details[i].Designation);  
       Console.WriteLine("Employee Salary    : " + emp_details[i].Salary);  
       Console.WriteLine();  
   }  
   ```  
  
7. <span data-ttu-id="deb98-155">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="deb98-155">Close the client as described in the snippet below:</span></span>  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. <span data-ttu-id="deb98-156">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="deb98-156">Build the project and then run it.</span></span> <span data-ttu-id="deb98-157">应用程序显示雇员 ID、 名称和具有"Manager"指定的所有员工的工资数据交换。</span><span class="sxs-lookup"><span data-stu-id="deb98-157">The application displays the employee ID, name, and salary of all the employees with a “Manager” designation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb98-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="deb98-158">See Also</span></span>  
[<span data-ttu-id="deb98-159">使用 WCF 服务模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="deb98-159">Develop applications using the WCF Service model</span></span>](develop-sql-applications-using-the-wcf-service-model.md)