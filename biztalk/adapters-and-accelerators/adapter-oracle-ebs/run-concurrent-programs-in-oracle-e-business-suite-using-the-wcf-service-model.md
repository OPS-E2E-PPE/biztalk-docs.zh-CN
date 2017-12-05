---
title: "调用中使用 WCF 服务模型的 Oracle E-business Suite 的并发程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e227c60f-f6fe-40bf-bf41-2784a4428ad0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c9ff6b37f2e18c03a364e3f584ea9f79b547f1e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="146b2-102">调用中使用 WCF 服务模型的 Oracle E-business Suite 的并发程序</span><span class="sxs-lookup"><span data-stu-id="146b2-102">Invoke concurrent programs in Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="146b2-103">Oracle E-business Suite 公开可以执行以执行对 Oracle 应用程序的特定操作的并发程序。</span><span class="sxs-lookup"><span data-stu-id="146b2-103">Oracle E-Business Suite exposes concurrent programs that you can execute to perform specific operations on Oracle applications.</span></span> <span data-ttu-id="146b2-104">每个 Oracle 应用程序具有一套标准的并发程序 （即在所有操作都相同） 和某些特定于 Oracle 应用程序的并发程序。</span><span class="sxs-lookup"><span data-stu-id="146b2-104">Each Oracle application has a set of standard concurrent programs (that are same across all operations) and certain concurrent programs that are specific to an Oracle application.</span></span> <span data-ttu-id="146b2-105">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开所有的并发程序作为适配器客户端可以调用的操作。</span><span class="sxs-lookup"><span data-stu-id="146b2-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes all concurrent programs as operations that adapter clients can invoke.</span></span> <span data-ttu-id="146b2-106">有关如何适配器支持并发程序的详细信息，请参阅[并发程序上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)。</span><span class="sxs-lookup"><span data-stu-id="146b2-106">For more information about how the adapter supports concurrent programs, see [Operations on Concurrent Programs](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="146b2-107">对于不公开其元数据的并发程序，Oracle E-business 适配器为每个这些并发程序公开 100 的可选参数。</span><span class="sxs-lookup"><span data-stu-id="146b2-107">For the concurrent programs that do not expose their metadata, the Oracle E-Business adapter exposes 100 optional parameters for each of these concurrent programs.</span></span> <span data-ttu-id="146b2-108">若要成功调用这些并发程序，用户必须咨询 Oracle E-business Suite 文档以找出需要一个值，并发程序的参数，然后指定它们。</span><span class="sxs-lookup"><span data-stu-id="146b2-108">To invoke these concurrent programs successfully, the user must consult the Oracle E-Business Suite documentation to figure out the parameters for a concurrent program that require a value, and then specify them.</span></span> <span data-ttu-id="146b2-109">这样的并发程序的一个示例是**日志导入**(实际名称： **GLLEZL**) 中**常规分类帐**应用程序。</span><span class="sxs-lookup"><span data-stu-id="146b2-109">An example of such a concurrent program is **Journal Import** (actual name: **GLLEZL**) in the **General Ledger** application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="146b2-110">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="146b2-110">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="146b2-111">本主题中的示例时，将调用**MS_SAMPLE_COPY_EMP_DATA**并发程序后, 跟**Get_Status**并发程序知道的第一个并发程序的状态。</span><span class="sxs-lookup"><span data-stu-id="146b2-111">The example in this topic invokes the **MS_SAMPLE_COPY_EMP_DATA** concurrent program, followed by the **Get_Status** concurrent program to know the status of the first concurrent program.</span></span> <span data-ttu-id="146b2-112">这些并发程序调用从**应用程序对象库**应用程序。</span><span class="sxs-lookup"><span data-stu-id="146b2-112">These concurrent programs are invoked from the **Application Object Library** application.</span></span> <span data-ttu-id="146b2-113">**MS_SAMPLE_COPY_EMP_DATA**通过运行这些示例使用提供的脚本。</span><span class="sxs-lookup"><span data-stu-id="146b2-113">The **MS_SAMPLE_COPY_EMP_DATA** is created by running the script provided with the samples.</span></span> <span data-ttu-id="146b2-114">有关示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="146b2-114">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="146b2-115">示例中， **ConcurrentProgram_ServiceModel**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="146b2-115">A sample, **ConcurrentProgram_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="146b2-116">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="146b2-116">The WCF Client Class</span></span>  
 <span data-ttu-id="146b2-117">为调用的并发程序生成 WCF 客户端的名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]下表中列出。</span><span class="sxs-lookup"><span data-stu-id="146b2-117">The name of the WCF client generated for invoking the concurrent programs by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="146b2-118">项目</span><span class="sxs-lookup"><span data-stu-id="146b2-118">Artifact</span></span>|<span data-ttu-id="146b2-119">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="146b2-119">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="146b2-120">并发程序</span><span class="sxs-lookup"><span data-stu-id="146b2-120">Concurrent Program</span></span>|<span data-ttu-id="146b2-121">ConcurrentPrograms_ [APP_NAME] 客户端</span><span class="sxs-lookup"><span data-stu-id="146b2-121">ConcurrentPrograms_[APP_NAME]Client</span></span>|  
  
 <span data-ttu-id="146b2-122">[APP_NAME] = Oracle E-business Suite 应用程序; 实际名称例如，查找。</span><span class="sxs-lookup"><span data-stu-id="146b2-122">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  
  
### <a name="method-signature-for-invoking-concurrent-programs"></a><span data-ttu-id="146b2-123">用于调用并发程序的方法签名</span><span class="sxs-lookup"><span data-stu-id="146b2-123">Method Signature for Invoking Concurrent Programs</span></span>  
 <span data-ttu-id="146b2-124">下表显示的并发程序的方法签名。</span><span class="sxs-lookup"><span data-stu-id="146b2-124">The following table shows the method signature for the concurrent programs.</span></span>  
  
|<span data-ttu-id="146b2-125">运算</span><span class="sxs-lookup"><span data-stu-id="146b2-125">Operation</span></span>|<span data-ttu-id="146b2-126">方法签名</span><span class="sxs-lookup"><span data-stu-id="146b2-126">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="146b2-127">并发程序</span><span class="sxs-lookup"><span data-stu-id="146b2-127">Concurrent program</span></span>|<span data-ttu-id="146b2-128">公共\<返回类型\>< Concurrent_program_name > (param 1，param 2，...)</span><span class="sxs-lookup"><span data-stu-id="146b2-128">public \<return type\> <Concurrent_program_name>(param 1, param 2, …)</span></span>|  
  
 <span data-ttu-id="146b2-129">例如，下面的代码演示方法签名，用于生成 WCF 客户端类**MS_SAMPLE_COPY_EMP_DATA**和**Get_Status**并发程序。</span><span class="sxs-lookup"><span data-stu-id="146b2-129">As an example, the following code shows the method signatures for a WCF client class generated for the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span>  
  
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
  
 <span data-ttu-id="146b2-130">在此代码段， **ConcurrentPrograms_FNDClient**是 WCF 中的类的生成的 OracleEBSBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="146b2-130">In this snippet, **ConcurrentPrograms_FNDClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="146b2-131">**MS_SAMPLE_COPY_EMP_DATA**是要调用的并发程序的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="146b2-131">**MS_SAMPLE_COPY_EMP_DATA** is the name of the method to invoke the concurrent program.</span></span> <span data-ttu-id="146b2-132">**GetStatusForConcurrentProgram**是要调用的并发程序来获取第一个并发程序状态的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="146b2-132">**GetStatusForConcurrentProgram** is the name of the method to invoke the concurrent program to get the status of the first concurrent program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="146b2-133">**GetStatusForConcurrentProgram**是实际名称**Get_Status**并发程序。</span><span class="sxs-lookup"><span data-stu-id="146b2-133">**GetStatusForConcurrentProgram** is the actual name of the **Get_Status** concurrent program.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-concurrent-programs"></a><span data-ttu-id="146b2-134">创建 WCF 客户端来调用并发程序</span><span class="sxs-lookup"><span data-stu-id="146b2-134">Creating a WCF Client to Invoke Concurrent Programs</span></span>  
 <span data-ttu-id="146b2-135">泛型组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="146b2-135">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="146b2-136">本部分介绍如何创建 WCF 客户端来调用**MS_SAMPLE_COPY_EMP_DATA**和**Get_Status**并发程序。</span><span class="sxs-lookup"><span data-stu-id="146b2-136">This section describes how to create a WCF client to invoke the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="146b2-137">若要创建 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="146b2-137">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="146b2-138">在 Visual Studio 中创建 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="146b2-138">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="146b2-139">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="146b2-139">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="146b2-140">生成的 WCF 客户端类**MS_SAMPLE_COPY_EMP_DATA**和**Get_Status**并发程序。</span><span class="sxs-lookup"><span data-stu-id="146b2-140">Generate the WCF client class for the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span> <span data-ttu-id="146b2-141">有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="146b2-141">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="146b2-142">在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。</span><span class="sxs-lookup"><span data-stu-id="146b2-142">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="146b2-143">在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="146b2-143">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="146b2-144">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="146b2-144">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  <span data-ttu-id="146b2-145">打开 Program.cs 文件并创建客户端，如下面的代码段中所述。</span><span class="sxs-lookup"><span data-stu-id="146b2-145">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
    ConcurrentPrograms_FNDClient client = new ConcurrentPrograms_FNDClient(binding, address);  
    ```  
  
     <span data-ttu-id="146b2-146">在此代码段，`ConcurrentPrograms_FNDClient`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="146b2-146">In this snippet, `ConcurrentPrograms_FNDClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="146b2-147">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="146b2-147">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="146b2-148">在此代码段，则显式应用程序代码中指定的绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="146b2-148">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="146b2-149">你还可以从还生成的应用程序配置文件 app.config，使用这些值[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="146b2-149">You can also use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="146b2-150">指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="146b2-150">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="146b2-151">为客户端设置的凭据。</span><span class="sxs-lookup"><span data-stu-id="146b2-151">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  <span data-ttu-id="146b2-152">由于正在调用 Oracle E-business Suite 应用程序中的并发程序，你必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="146b2-152">Because you are invoking concurrent programs in an Oracle E-Business Suite application, you must set the application context.</span></span> <span data-ttu-id="146b2-153">在此示例中，若要设置应用程序上下文中，你指定**OracleUserName**， **OraclePassword**，和**OracleEBSResponsibilityName**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="146b2-153">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="146b2-154">有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="146b2-154">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  <span data-ttu-id="146b2-155">下面的代码段中所述，请打开客户端：</span><span class="sxs-lookup"><span data-stu-id="146b2-155">Open the client as described in the snippet below:</span></span>  
  
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
  
9. <span data-ttu-id="146b2-156">调用**MS_SAMPLE_COPY_EMP_DATA**和**Get_Status**并发程序。</span><span class="sxs-lookup"><span data-stu-id="146b2-156">Invoke the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span>  
  
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
  
10. <span data-ttu-id="146b2-157">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="146b2-157">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    ```  
  
11. <span data-ttu-id="146b2-158">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="146b2-158">Build the project and then run it.</span></span> <span data-ttu-id="146b2-159">应用程序时，将调用**MS_SAMPLE_COPY_EMP_DATA**并返回请求 id。</span><span class="sxs-lookup"><span data-stu-id="146b2-159">The application invokes the **MS_SAMPLE_COPY_EMP_DATA** and returns a request ID.</span></span> <span data-ttu-id="146b2-160">然后将 ID 传递给**Get_Status**并发程序，最后提供的状态**MS_SAMPLE_COPY_EMP_DATA**列程序。</span><span class="sxs-lookup"><span data-stu-id="146b2-160">The ID is then passed to the **Get_Status** concurrent program, which finally provides the status of the **MS_SAMPLE_COPY_EMP_DATA** column program.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="146b2-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="146b2-161">See Also</span></span>  
 [<span data-ttu-id="146b2-162">开发 Oracle E-business Suite 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="146b2-162">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)