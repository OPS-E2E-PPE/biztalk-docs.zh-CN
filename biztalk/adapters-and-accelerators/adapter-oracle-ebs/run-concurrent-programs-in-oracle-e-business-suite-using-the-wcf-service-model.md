---
title: 调用并发程序中使用 WCF 服务模型的 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e227c60f-f6fe-40bf-bf41-2784a4428ad0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81f181cfad40c31abc0d5b3517f0d7f8d9c32d7b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002350"
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="551b1-102">调用 Oracle E-business Suite 使用 WCF 服务模型中的并发程序</span><span class="sxs-lookup"><span data-stu-id="551b1-102">Invoke concurrent programs in Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="551b1-103">Oracle E-business Suite 公开您可以执行对 Oracle 应用程序的特定操作的并发程序。</span><span class="sxs-lookup"><span data-stu-id="551b1-103">Oracle E-Business Suite exposes concurrent programs that you can execute to perform specific operations on Oracle applications.</span></span> <span data-ttu-id="551b1-104">每个 Oracle 应用程序一的组标准的并发程序 （即在所有操作都相同） 和某些特定于 Oracle 应用程序的并发程序。</span><span class="sxs-lookup"><span data-stu-id="551b1-104">Each Oracle application has a set of standard concurrent programs (that are same across all operations) and certain concurrent programs that are specific to an Oracle application.</span></span> <span data-ttu-id="551b1-105">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开所有的并发程序作为适配器客户端可以调用的操作。</span><span class="sxs-lookup"><span data-stu-id="551b1-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes all concurrent programs as operations that adapter clients can invoke.</span></span> <span data-ttu-id="551b1-106">有关适配器如何支持并发程序的详细信息，请参阅[操作对并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)。</span><span class="sxs-lookup"><span data-stu-id="551b1-106">For more information about how the adapter supports concurrent programs, see [Operations on Concurrent Programs](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="551b1-107">对于那些不公开其元数据的并发程序，Oracle E-business 适配器公开这些并发程序的每个 100 的可选参数。</span><span class="sxs-lookup"><span data-stu-id="551b1-107">For the concurrent programs that do not expose their metadata, the Oracle E-Business adapter exposes 100 optional parameters for each of these concurrent programs.</span></span> <span data-ttu-id="551b1-108">若要成功调用这些并发程序，用户必须请查阅 Oracle E-business Suite 文档以找出需要一个值，用于并发程序的参数，然后指定它们。</span><span class="sxs-lookup"><span data-stu-id="551b1-108">To invoke these concurrent programs successfully, the user must consult the Oracle E-Business Suite documentation to figure out the parameters for a concurrent program that require a value, and then specify them.</span></span> <span data-ttu-id="551b1-109">此类的并发程序的一个示例是**日记本的导入**(实际名称： **GLLEZL**) 中**总帐**应用程序。</span><span class="sxs-lookup"><span data-stu-id="551b1-109">An example of such a concurrent program is **Journal Import** (actual name: **GLLEZL**) in the **General Ledger** application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="551b1-110">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="551b1-110">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="551b1-111">本主题中的示例调用**MS_SAMPLE_COPY_EMP_DATA**并发程序中后, 跟**Get_Status**并发程序能够了解第一个并发程序的状态。</span><span class="sxs-lookup"><span data-stu-id="551b1-111">The example in this topic invokes the **MS_SAMPLE_COPY_EMP_DATA** concurrent program, followed by the **Get_Status** concurrent program to know the status of the first concurrent program.</span></span> <span data-ttu-id="551b1-112">从这些并发程序中调用**应用程序对象库**应用程序。</span><span class="sxs-lookup"><span data-stu-id="551b1-112">These concurrent programs are invoked from the **Application Object Library** application.</span></span> <span data-ttu-id="551b1-113">**MS_SAMPLE_COPY_EMP_DATA**通过在运行这些示例提供的脚本。</span><span class="sxs-lookup"><span data-stu-id="551b1-113">The **MS_SAMPLE_COPY_EMP_DATA** is created by running the script provided with the samples.</span></span> <span data-ttu-id="551b1-114">有关示例的详细信息，请参阅[适用于 Oracle EBS 适配器示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="551b1-114">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="551b1-115">示例中， **ConcurrentProgram_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="551b1-115">A sample, **ConcurrentProgram_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="551b1-116">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="551b1-116">The WCF Client Class</span></span>  
 <span data-ttu-id="551b1-117">生成用于调用并发程序的 WCF 客户端名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]下表中列出。</span><span class="sxs-lookup"><span data-stu-id="551b1-117">The name of the WCF client generated for invoking the concurrent programs by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="551b1-118">项目</span><span class="sxs-lookup"><span data-stu-id="551b1-118">Artifact</span></span>|<span data-ttu-id="551b1-119">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="551b1-119">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="551b1-120">并发程序</span><span class="sxs-lookup"><span data-stu-id="551b1-120">Concurrent Program</span></span>|<span data-ttu-id="551b1-121">ConcurrentPrograms_ [APP_NAME] 客户端</span><span class="sxs-lookup"><span data-stu-id="551b1-121">ConcurrentPrograms_[APP_NAME]Client</span></span>|  
  
 <span data-ttu-id="551b1-122">[A p p _] = Oracle E-business Suite 应用程序; 的实际名称例如，查找。</span><span class="sxs-lookup"><span data-stu-id="551b1-122">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  
  
### <a name="method-signature-for-invoking-concurrent-programs"></a><span data-ttu-id="551b1-123">用于调用并发程序的方法签名</span><span class="sxs-lookup"><span data-stu-id="551b1-123">Method Signature for Invoking Concurrent Programs</span></span>  
 <span data-ttu-id="551b1-124">下表显示了并发程序的方法签名。</span><span class="sxs-lookup"><span data-stu-id="551b1-124">The following table shows the method signature for the concurrent programs.</span></span>  
  
|<span data-ttu-id="551b1-125">运算</span><span class="sxs-lookup"><span data-stu-id="551b1-125">Operation</span></span>|<span data-ttu-id="551b1-126">方法签名</span><span class="sxs-lookup"><span data-stu-id="551b1-126">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="551b1-127">并发程序</span><span class="sxs-lookup"><span data-stu-id="551b1-127">Concurrent program</span></span>|<span data-ttu-id="551b1-128">公共\<返回类型\>< Concurrent_program_name > （参数 1，参数 2，...）</span><span class="sxs-lookup"><span data-stu-id="551b1-128">public \<return type\> <Concurrent_program_name>(param 1, param 2, …)</span></span>|  
  
 <span data-ttu-id="551b1-129">例如，下面的代码演示的方法签名，用于为生成 WCF 客户端类**MS_SAMPLE_COPY_EMP_DATA**并**Get_Status**并发程序。</span><span class="sxs-lookup"><span data-stu-id="551b1-129">As an example, the following code shows the method signatures for a WCF client class generated for the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span>  
  
```  
public partial class ConcurrentPrograms_FNDClient : System.ServiceModel.ClientBase<ConcurrentPrograms_FND>, ConcurrentPrograms_FND {      
  
    public string MS_SAMPLE_COPY_EMP_DATA(schemas.microsoft.com.OracleEBS._2008._05.Options.SetOptions SetOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetPrintOptions SetPrintOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRepeatOptions SetRepeatOptions,  
      string Description, string StartTime);  
  
    public bool GetStatusForConcurrentProgram(string RequestId, out string Phase, out string Status,  
      out string DevPhase, out string DevStatus, out string Message);  
}  
```  
  
 <span data-ttu-id="551b1-130">此代码片段**ConcurrentPrograms_FNDClient**是 WCF 中的类的生成的 OracleEBSBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="551b1-130">In this snippet, **ConcurrentPrograms_FNDClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="551b1-131">**MS_SAMPLE_COPY_EMP_DATA**是方法调用并发程序的名称。</span><span class="sxs-lookup"><span data-stu-id="551b1-131">**MS_SAMPLE_COPY_EMP_DATA** is the name of the method to invoke the concurrent program.</span></span> <span data-ttu-id="551b1-132">**GetStatusForConcurrentProgram**是要调用并发程序来获取第一个并发程序的状态的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="551b1-132">**GetStatusForConcurrentProgram** is the name of the method to invoke the concurrent program to get the status of the first concurrent program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="551b1-133">**GetStatusForConcurrentProgram**的实际名称**Get_Status**并发程序。</span><span class="sxs-lookup"><span data-stu-id="551b1-133">**GetStatusForConcurrentProgram** is the actual name of the **Get_Status** concurrent program.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-concurrent-programs"></a><span data-ttu-id="551b1-134">创建 WCF 客户端以调用并发程序</span><span class="sxs-lookup"><span data-stu-id="551b1-134">Creating a WCF Client to Invoke Concurrent Programs</span></span>  
 <span data-ttu-id="551b1-135">通用组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="551b1-135">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="551b1-136">本部分介绍如何创建 WCF 客户端以调用**MS_SAMPLE_COPY_EMP_DATA**并**Get_Status**并发程序。</span><span class="sxs-lookup"><span data-stu-id="551b1-136">This section describes how to create a WCF client to invoke the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="551b1-137">若要创建 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="551b1-137">To create a WCF client</span></span>  
  
1. <span data-ttu-id="551b1-138">在 Visual Studio 中创建一个 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="551b1-138">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="551b1-139">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="551b1-139">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="551b1-140">生成的 WCF 客户端类**MS_SAMPLE_COPY_EMP_DATA**并**Get_Status**并发程序。</span><span class="sxs-lookup"><span data-stu-id="551b1-140">Generate the WCF client class for the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span> <span data-ttu-id="551b1-141">有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="551b1-141">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="551b1-142">生成 WCF 客户端类之前，请确保设置**EnableBizTalkCompatibilityMode**属性绑定到 false。</span><span class="sxs-lookup"><span data-stu-id="551b1-142">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3. <span data-ttu-id="551b1-143">在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="551b1-143">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4. <span data-ttu-id="551b1-144">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="551b1-144">Open the Program.cs file and add the following namespaces:</span></span>  
  
   -   `Microsoft.Adapters.OracleEBS`  
  
   -   `System.ServiceModel`  
  
5. <span data-ttu-id="551b1-145">打开 Program.cs 文件，如下面的代码段中所述创建客户端。</span><span class="sxs-lookup"><span data-stu-id="551b1-145">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
   ConcurrentPrograms_FNDClient client = new ConcurrentPrograms_FNDClient(binding, address);  
   ```  
  
    <span data-ttu-id="551b1-146">在此代码段，`ConcurrentPrograms_FNDClient`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="551b1-146">In this snippet, `ConcurrentPrograms_FNDClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="551b1-147">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="551b1-147">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="551b1-148">此代码片段显式应用程序代码中指定的绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="551b1-148">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="551b1-149">此外可以从还生成的应用程序配置文件 app.config 文件中，使用这些值[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="551b1-149">You can also use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="551b1-150">指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定适用于 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="551b1-150">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6. <span data-ttu-id="551b1-151">为客户端设置的凭据。</span><span class="sxs-lookup"><span data-stu-id="551b1-151">Set the credentials for the client.</span></span>  
  
   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
7. <span data-ttu-id="551b1-152">由于正在调用并发程序 Oracle E-business Suite 应用程序中的，必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="551b1-152">Because you are invoking concurrent programs in an Oracle E-Business Suite application, you must set the application context.</span></span> <span data-ttu-id="551b1-153">在此示例中，若要设置应用程序上下文中，您指定**OracleUserName**， **OraclePassword**，并**OracleEBSResponsibilityName**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="551b1-153">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="551b1-154">有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="551b1-154">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  
  
8. <span data-ttu-id="551b1-155">打开客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="551b1-155">Open the client as described in the snippet below:</span></span>  
  
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
  
9. <span data-ttu-id="551b1-156">调用**MS_SAMPLE_COPY_EMP_DATA**并**Get_Status**并发程序。</span><span class="sxs-lookup"><span data-stu-id="551b1-156">Invoke the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span>  
  
    ```  
    string RequestID;  
    bool Result;  
    string Phase;  
    string Status;  
    string DevPhase;  
    string DevStatus;  
    string Message;  
  
    try  
    {  
        Console.WriteLine("Invoking the MS_SAMPLE_COPY_EMP_DATA concurrent program");  
        RequestID = client.MS_SAMPLE_COPY_EMP_DATA(null, null, null, null, null);  
        Console.WriteLine("The request ID generated for the concurrent program is : " + RequestID);  
        Console.WriteLine("********************************************************");  
        Console.WriteLine("\nWaiting for 60 seconds for the concurrent program to be complete");  
        System.Threading.Thread.Sleep(60000);  
        Console.WriteLine("\nInvoking the Get_Status concurrent program");  
        Result = client.GetStatusForConcurrentProgram(RequestID, out Phase, out Status, out DevPhase, out DevStatus, out Message);  
        Console.WriteLine("\nResult is  : " + Result);  
        Console.WriteLine("Phase is     : " + Phase);  
        Console.WriteLine("Status is    : " + Status);  
        Console.WriteLine("DevPhase is  : " + DevPhase);  
        Console.WriteLine("DevStatus is : " + DevStatus);  
        Console.WriteLine("Message is   : " + Message);  
        Console.WriteLine("********************************************************");  
        Console.WriteLine("\nHit <RETURN> to end");  
        Console.ReadLine();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Exception : " + ex);  
        throw;                 
    }  
    ```  
  
10. <span data-ttu-id="551b1-157">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="551b1-157">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    ```  
  
11. <span data-ttu-id="551b1-158">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="551b1-158">Build the project and then run it.</span></span> <span data-ttu-id="551b1-159">应用程序调用**MS_SAMPLE_COPY_EMP_DATA**并返回请求 id。</span><span class="sxs-lookup"><span data-stu-id="551b1-159">The application invokes the **MS_SAMPLE_COPY_EMP_DATA** and returns a request ID.</span></span> <span data-ttu-id="551b1-160">然后将该 ID 传递给**Get_Status**并发程序，它最后的状态**MS_SAMPLE_COPY_EMP_DATA**列程序。</span><span class="sxs-lookup"><span data-stu-id="551b1-160">The ID is then passed to the **Get_Status** concurrent program, which finally provides the status of the **MS_SAMPLE_COPY_EMP_DATA** column program.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="551b1-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="551b1-161">See Also</span></span>  
 [<span data-ttu-id="551b1-162">开发 Oracle E-business Suite 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="551b1-162">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)