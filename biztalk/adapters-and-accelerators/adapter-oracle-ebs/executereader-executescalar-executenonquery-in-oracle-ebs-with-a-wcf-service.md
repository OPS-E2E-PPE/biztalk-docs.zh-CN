---
title: "ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作中使用 WCF 服务模型的 Oracle E-business Suite |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54c42db1-9a4d-4003-af69-f75ff48b575a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaffcdc59cd6093feababc8319c1f9f1964a0d05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="19594-102">在使用 WCF 服务模型的 Oracle E-business Suite ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作</span><span class="sxs-lookup"><span data-stu-id="19594-102">ExecuteReader, ExecuteScalar, or ExecuteNonQuery operations in Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="19594-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]如公开泛型操作**ExecuteNonQuery**， **ExecuteReader**，和**ExecuteScalar**。</span><span class="sxs-lookup"><span data-stu-id="19594-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes generic operations such as **ExecuteNonQuery**, **ExecuteReader**, and **ExecuteScalar**.</span></span> <span data-ttu-id="19594-104">这些操作可用于在 Oracle E-business Suite 上执行任何语句。</span><span class="sxs-lookup"><span data-stu-id="19594-104">You can use these operations to execute any statement on Oracle E-Business Suite.</span></span> <span data-ttu-id="19594-105">这些操作因响应为语句所获取的类型而异。</span><span class="sxs-lookup"><span data-stu-id="19594-105">These operations differ based on the kind of response you get for the statement.</span></span> <span data-ttu-id="19594-106">有关如何适配器支持这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="19594-106">For more information about how the adapter supports these operations, see [Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span></span>  
  
 <span data-ttu-id="19594-107">本主题演示如何执行**ExecuteReader**操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 WCF 服务模型。</span><span class="sxs-lookup"><span data-stu-id="19594-107">This topic demonstrates how to perform an **ExecuteReader** operation using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] using the WCF service model.</span></span> <span data-ttu-id="19594-108">你可以按照同一套执行本主题中所述的过程**ExecuteNonQuery**和**ExecuteScalar**操作。</span><span class="sxs-lookup"><span data-stu-id="19594-108">You can follow the same set of procedures described in this topic to perform **ExecuteNonQuery** and **ExecuteScalar** operations.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="19594-109">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="19594-109">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="19594-110">本主题中的示例执行**ExecuteReader**操作以执行 MS_SAMPLE_EMPLOYEE 接口表选择操作。</span><span class="sxs-lookup"><span data-stu-id="19594-110">The example in this topic performs an **ExecuteReader** operation to perform a SELECT operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="19594-111">通过运行这些示例使用提供的脚本创建表。</span><span class="sxs-lookup"><span data-stu-id="19594-111">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="19594-112">有关示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="19594-112">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="19594-113">示例中， **ExecuteReader**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="19594-113">A sample, **ExecuteReader**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="19594-114">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="19594-114">The WCF Client Class</span></span>  
 <span data-ttu-id="19594-115">调用泛型操作 （ExecuteNonQuery、 ExecuteReader 或 ExecuteScalar） 使用的生成 WCF 客户端的名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]下表中列出。</span><span class="sxs-lookup"><span data-stu-id="19594-115">The name of the WCF client generated for invoking generic operations (ExecuteNonQuery, ExecuteReader, or ExecuteScalar) using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="19594-116">操作</span><span class="sxs-lookup"><span data-stu-id="19594-116">Operations</span></span>|<span data-ttu-id="19594-117">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="19594-117">WCF Client Name</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="19594-118">ExecuteNonQuery、 ExecuteReader 或 ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="19594-118">ExecuteNonQuery, ExecuteReader, or ExecuteScalar</span></span>|<span data-ttu-id="19594-119">GenericOperation_Client</span><span class="sxs-lookup"><span data-stu-id="19594-119">GenericOperation_Client</span></span>|  
  
### <a name="method-signature-for-invoking-generic-operations"></a><span data-ttu-id="19594-120">调用泛型操作的方法签名</span><span class="sxs-lookup"><span data-stu-id="19594-120">Method Signature for Invoking Generic Operations</span></span>  
 <span data-ttu-id="19594-121">下表显示了要调用的泛型操作所公开的方法的签名。</span><span class="sxs-lookup"><span data-stu-id="19594-121">The following table shows the signature for the method exposed to invoke the generic operations.</span></span>  
  
|<span data-ttu-id="19594-122">运算</span><span class="sxs-lookup"><span data-stu-id="19594-122">Operation</span></span>|<span data-ttu-id="19594-123">方法签名</span><span class="sxs-lookup"><span data-stu-id="19594-123">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="19594-124">ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="19594-124">ExecuteNonQuery</span></span>|<span data-ttu-id="19594-125">int ExecuteNonQuery （字符串查询，string [] OutputRefCursorNames，出 System.Data.DataSet [] OutputRefCursors）</span><span class="sxs-lookup"><span data-stu-id="19594-125">int ExecuteNonQuery(string Query, string[] OutputRefCursorNames, out System.Data.DataSet[] OutputRefCursors)</span></span>|  
|<span data-ttu-id="19594-126">ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="19594-126">ExecuteReader</span></span>|<span data-ttu-id="19594-127">System.Data.DataSet ExecuteReader(string Query)</span><span class="sxs-lookup"><span data-stu-id="19594-127">System.Data.DataSet ExecuteReader(string Query)</span></span>|  
|<span data-ttu-id="19594-128">ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="19594-128">ExecuteScalar</span></span>|<span data-ttu-id="19594-129">字符串 ExecuteScalar(string Query)</span><span class="sxs-lookup"><span data-stu-id="19594-129">string ExecuteScalar(string Query)</span></span>|  
  
 <span data-ttu-id="19594-130">例如，泛型操作方法的签名所示下面的代码段。</span><span class="sxs-lookup"><span data-stu-id="19594-130">As an example, the signature for the generic operation methods is shown in the following code snippet.</span></span>  
  
```  
public partial class GenericOperation_Client : System.ServiceModel.ClientBase<GenericOperation_>, GenericOperation_ {  
  public int ExecuteNonQuery(string Query, string[] OutputRefCursorNames, out System.Data.DataSet[] OutputRefCursors);  
  public System.Data.DataSet ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  
  
 <span data-ttu-id="19594-131">在此代码段</span><span class="sxs-lookup"><span data-stu-id="19594-131">In this snippet,</span></span>  
  
-   <span data-ttu-id="19594-132">`GenericOperation_Client`是类的名称。</span><span class="sxs-lookup"><span data-stu-id="19594-132">`GenericOperation_Client` is the name of the class.</span></span> <span data-ttu-id="19594-133">此类用于创建客户端以调用的泛型操作，ExecuteReader。</span><span class="sxs-lookup"><span data-stu-id="19594-133">This class is used to create a client to invoke the generic operation, ExecuteReader.</span></span>  
  
-   <span data-ttu-id="19594-134">`public System.Data.DataSet ExecuteReader(string Query)`是调用 MS_SAMPLE_EMPLOYEE 接口表上执行的 SELECT 语句的方法。</span><span class="sxs-lookup"><span data-stu-id="19594-134">`public System.Data.DataSet ExecuteReader(string Query)` is the method that you invoke to perform a SELECT statement on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a><span data-ttu-id="19594-135">创建 WCF 客户端以调用 ExecuteReader 操作</span><span class="sxs-lookup"><span data-stu-id="19594-135">Creating a WCF Client to Invoke an ExecuteReader Operation</span></span>  
 <span data-ttu-id="19594-136">泛型组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="19594-136">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="19594-137">本部分介绍如何创建 WCF 客户端来调用**ExecuteReader**操作。</span><span class="sxs-lookup"><span data-stu-id="19594-137">This section describes how to create a WCF client to invoke the **ExecuteReader** operation.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a><span data-ttu-id="19594-138">若要创建 WCF 客户端以调用 ExecuteReader 操作</span><span class="sxs-lookup"><span data-stu-id="19594-138">To create a WCF client to invoke ExecuteReader operation</span></span>  
  
1.  <span data-ttu-id="19594-139">在 Visual Studio 中创建 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="19594-139">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="19594-140">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="19594-140">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="19594-141">生成的 WCF 客户端类**ExecuteReader**泛型操作。</span><span class="sxs-lookup"><span data-stu-id="19594-141">Generate the WCF client class for the **ExecuteReader** generic operation.</span></span> <span data-ttu-id="19594-142">此操作时，位于根节点下你连接到 Oracle E-business Suite 使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="19594-142">This operation is available under the root node when you connect to the Oracle E-Business Suite using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="19594-143">有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="19594-143">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="19594-144">在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。</span><span class="sxs-lookup"><span data-stu-id="19594-144">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="19594-145">在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="19594-145">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="19594-146">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="19594-146">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  <span data-ttu-id="19594-147">在 Program.cs 文件中，如下面的代码段中所述创建客户端。</span><span class="sxs-lookup"><span data-stu-id="19594-147">In the Program.cs file, create a client as described in the snippet below.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs-72-11");  
    GenericOperation_Client client = new GenericOperation_Client(binding, address);  
    ```  
  
     <span data-ttu-id="19594-148">在此代码段，`GenericOperation_Client`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="19594-148">In this snippet, `GenericOperation_Client` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="19594-149">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="19594-149">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="19594-150">在此代码段，则显式应用程序代码中指定的绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="19594-150">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="19594-151">你可以从还生成的应用程序配置文件 app.config，使用这些值[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="19594-151">You can use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="19594-152">有关指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="19594-152">For more information about the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="19594-153">为客户端设置的凭据。</span><span class="sxs-lookup"><span data-stu-id="19594-153">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  <span data-ttu-id="19594-154">由于您正在执行对接口表的操作，必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="19594-154">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="19594-155">在此示例中，若要设置应用程序上下文中，你指定**OracleUserName**， **OraclePassword**，和**OracleEBSResponsibilityName**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="19594-155">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="19594-156">有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="19594-156">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  <span data-ttu-id="19594-157">下面的代码段中所述，请打开客户端：</span><span class="sxs-lookup"><span data-stu-id="19594-157">Open the client as described in the snippet below:</span></span>  
  
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
  
9. <span data-ttu-id="19594-158">调用**ExecuteReader**执行 MS_SAMPLE_EMPLOYEE 表上的选择操作的操作。</span><span class="sxs-lookup"><span data-stu-id="19594-158">Invoke the **ExecuteReader** operation for performing the SELECT operation on MS_SAMPLE_EMPLOYEE table.</span></span> <span data-ttu-id="19594-159">调用 ExecuteReader 操作之前，必须添加`System.Data`到你的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="19594-159">Before you invoke the ExecuteReader operation, you must add the `System.Data` namespace to your code.</span></span>  
  
    ```  
    string query = "SELECT * FROM MS_SAMPLE_EMPLOYEE";  
    DataSet ds = client.ExecuteReader(query);  
  
    Console.WriteLine("Invoking the SELECT statement using ExecuteReader");  
    Console.WriteLine("*****************************************************");  
    foreach (DataTable tab in ds.Tables)  
    {  
       foreach (DataRow row in tab.Rows)  
       {  
          Console.WriteLine("The details of the employee are: ");  
          for (int i = 0; i < tab.Columns.Count; i++)  
          {  
             Console.WriteLine(row[i]);  
          }  
          Console.WriteLine();  
       }  
    }  
    Console.WriteLine("*****************************************************");  
    Console.ReadLine();  
  
    ```  
  
10. <span data-ttu-id="19594-160">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="19594-160">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. <span data-ttu-id="19594-161">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="19594-161">Build the project and then run it.</span></span> <span data-ttu-id="19594-162">在控制台上显示 MS_SAMPLE_EMPLOYEE 表中的所有记录。</span><span class="sxs-lookup"><span data-stu-id="19594-162">All the records in the MS_SAMPLE_EMPLOYEE table are displayed on the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19594-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19594-163">See Also</span></span>  
 [<span data-ttu-id="19594-164">开发 Oracle E-business Suite 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="19594-164">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)