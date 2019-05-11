---
title: 调用请求集 Oracle E-business Suite 使用 WCF 服务模型中的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb6ec551-c069-4133-add5-2ba83d20405d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09eb5e16e45d97e4035f2f16639773f9fbaaa39f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375448"
---
# <a name="invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="049dc-102">调用请求集 Oracle E-business Suite 使用 WCF 服务模型中</span><span class="sxs-lookup"><span data-stu-id="049dc-102">Invoke request sets in Oracle E-Business Suite using the WCF service model</span></span>
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] <span data-ttu-id="049dc-103">可以在 Oracle E-business Suite 中执行请求集。</span><span class="sxs-lookup"><span data-stu-id="049dc-103">enables you to execute request sets in Oracle E-Business Suite.</span></span> <span data-ttu-id="049dc-104">请求集划分为一个或多个阶段，并且每个阶段包含了一组报表和并发程序。</span><span class="sxs-lookup"><span data-stu-id="049dc-104">Request sets are divided into one or more stages, and each stage contains a set of reports and concurrent programs.</span></span> <span data-ttu-id="049dc-105">有关如何在适配器支持请求集的详细信息，请参阅[对请求设置操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="049dc-105">For more information about how the adapter supports request sets, see [Operations on Request Sets](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="049dc-106">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="049dc-106">The WCF Client Class</span></span>  
 <span data-ttu-id="049dc-107">WCF 客户端生成有关调用请求集的名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]下表中列出。</span><span class="sxs-lookup"><span data-stu-id="049dc-107">The name of the WCF client generated for invoking the request sets by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="049dc-108">项目</span><span class="sxs-lookup"><span data-stu-id="049dc-108">Artifact</span></span>|<span data-ttu-id="049dc-109">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="049dc-109">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="049dc-110">请求组</span><span class="sxs-lookup"><span data-stu-id="049dc-110">Request Set</span></span>|<span data-ttu-id="049dc-111">RequestSets_[APP_NAME]Client</span><span class="sxs-lookup"><span data-stu-id="049dc-111">RequestSets_[APP_NAME]Client</span></span>|  
  
 <span data-ttu-id="049dc-112">[A p p _] = Oracle E-business Suite 应用程序; 的实际名称例如，SQLAP。</span><span class="sxs-lookup"><span data-stu-id="049dc-112">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, SQLAP.</span></span>  
  
### <a name="method-signature-for-invoking-request-sets"></a><span data-ttu-id="049dc-113">用于调用请求集的方法签名</span><span class="sxs-lookup"><span data-stu-id="049dc-113">Method Signature for Invoking Request Sets</span></span>  
 <span data-ttu-id="049dc-114">下表显示了请求集的方法签名。</span><span class="sxs-lookup"><span data-stu-id="049dc-114">The following table shows the method signature for request sets.</span></span>  
  
|<span data-ttu-id="049dc-115">操作</span><span class="sxs-lookup"><span data-stu-id="049dc-115">Operation</span></span>|<span data-ttu-id="049dc-116">方法签名</span><span class="sxs-lookup"><span data-stu-id="049dc-116">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="049dc-117">请求组</span><span class="sxs-lookup"><span data-stu-id="049dc-117">Request Set</span></span>|<span data-ttu-id="049dc-118">公共\<返回类型\>\<请求设置名称\>（参数 1，参数 2，...）</span><span class="sxs-lookup"><span data-stu-id="049dc-118">public \<return type\> \<request set name\>(param 1, param 2, …)</span></span>|  
  
 <span data-ttu-id="049dc-119">例如，下面的代码演示的方法签名，用于为生成 WCF 客户端类**reqset_singlestage**请求组。</span><span class="sxs-lookup"><span data-stu-id="049dc-119">As an example, the following code shows the method signatures for a WCF client class generated for the **reqset_singlestage** request set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="049dc-120">这是自定义请求组，可能不是 Oracle 电子商务解决方案实例上可用。</span><span class="sxs-lookup"><span data-stu-id="049dc-120">This is a custom request set and might not be available on your Oracle E-Business Solution instance.</span></span>  
  
```  
public partial class RequestSets_SQLAPClient : System.ServiceModel.ClientBase<RequestSets_SQLAP>, RequestSets_SQLAP{      
  
    public string REQSTG(  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRelClassOptions SetRelClassOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetPrintOptions SetPrintOptions,   
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRepeatOptions SetRepeatOptions,   
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetNlsOptions SetNlsOptions,  
      string StartTime,  
      schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1 set1_set1);  
}  
```  
  
 <span data-ttu-id="049dc-121">此代码片段**RequestSets_SQLAPClient**是 WCF 中的类的生成的 OracleEBSBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="049dc-121">In this snippet, **RequestSets_SQLAPClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="049dc-122">**REQSTG**是要调用请求集的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="049dc-122">**REQSTG** is the name of the method to invoke the request set.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-request-sets"></a><span data-ttu-id="049dc-123">创建 WCF 客户端以调用请求集</span><span class="sxs-lookup"><span data-stu-id="049dc-123">Creating a WCF Client to Invoke Request Sets</span></span>  
 <span data-ttu-id="049dc-124">通用组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="049dc-124">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="049dc-125">本部分介绍如何创建 WCF 客户端以调用**reqset_singlestage**请求组。</span><span class="sxs-lookup"><span data-stu-id="049dc-125">This section describes how to create a WCF client to invoke the **reqset_singlestage** request set.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="049dc-126">若要创建 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="049dc-126">To create a WCF client</span></span>  
  
1. <span data-ttu-id="049dc-127">在 Visual Studio 中创建一个 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="049dc-127">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="049dc-128">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="049dc-128">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="049dc-129">生成的 WCF 客户端类**reqset_singlestage**请求组。</span><span class="sxs-lookup"><span data-stu-id="049dc-129">Generate the WCF client class for the **reqset_singlestage** request set.</span></span> <span data-ttu-id="049dc-130">有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="049dc-130">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="049dc-131">生成 WCF 客户端类之前，请确保设置**EnableBizTalkCompatibilityMode**属性绑定到 false。</span><span class="sxs-lookup"><span data-stu-id="049dc-131">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3. <span data-ttu-id="049dc-132">在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="049dc-132">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4. <span data-ttu-id="049dc-133">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="049dc-133">Open the Program.cs file and add the following namespaces:</span></span>  
  
   -   `Microsoft.Adapters.OracleEBS`  
  
   -   `System.ServiceModel`  
  
5. <span data-ttu-id="049dc-134">打开 Program.cs 文件，如下面的代码段中所述创建客户端。</span><span class="sxs-lookup"><span data-stu-id="049dc-134">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
   RequestSets_SQLAPClient client = new RequestSets_SQLAPClient(binding, address);  
   ```  
  
    <span data-ttu-id="049dc-135">在此代码段，`RequestSets_SQLAPClient`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="049dc-135">In this snippet, `RequestSets_SQLAPClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="049dc-136">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="049dc-136">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="049dc-137">此代码片段显式应用程序代码中指定的绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="049dc-137">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="049dc-138">此外可以从还生成的应用程序配置文件 app.config 文件中，使用这些值[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="049dc-138">You can also use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="049dc-139">有关指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定适用于 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="049dc-139">For more information about the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6. <span data-ttu-id="049dc-140">为客户端设置的凭据。</span><span class="sxs-lookup"><span data-stu-id="049dc-140">Set the credentials for the client.</span></span>  
  
   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
7. <span data-ttu-id="049dc-141">因为调用请求集 Oracle E-business Suite 应用程序中的，必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="049dc-141">Because you are invoking request sets in an Oracle E-Business Suite application, you must set the application context.</span></span> <span data-ttu-id="049dc-142">在此示例中，若要设置应用程序上下文中，您指定**OracleUserName**， **OraclePassword**，并**OracleEBSResponsibilityName**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="049dc-142">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="049dc-143">有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="049dc-143">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  
  
8. <span data-ttu-id="049dc-144">打开客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="049dc-144">Open the client as described in the snippet below:</span></span>  
  
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
  
9. <span data-ttu-id="049dc-145">调用**reqset_singlestage**请求组。</span><span class="sxs-lookup"><span data-stu-id="049dc-145">Invoke the **reqset_singlestage** request set.</span></span>  
  
    ```  
    string RequestID;  
  
    schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1 param =  
        new schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1();  
  
    param.INSPARAMPROG = new schemas.microsoft.com.OracleEBS._2008._05.RequestSetConcurrentProgram.SQLAP.REQSTG.set1.SQLAP1.INSPARAMPROG();  
    param.INSPARAMPROG.p_id = "123";  
    param.INSPARAMPROG.p_name = "MyName";  
  
    try  
    {  
        Console.WriteLine("Invoking the reqset_singlestage request set");  
        RequestID = client.REQSTG(null, null, null, null, null, param);  
        Console.WriteLine("The request ID generated for the request set is : " + RequestID);  
        Console.WriteLine("*****************************************************************");  
        Console.WriteLine("\nHit <RETURN> to end");  
        Console.ReadLine();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Exception : " + ex);  
        throw;  
    }  
    ```  
  
10. <span data-ttu-id="049dc-146">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="049dc-146">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    ```  
  
11. <span data-ttu-id="049dc-147">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="049dc-147">Build the project and then run it.</span></span> <span data-ttu-id="049dc-148">应用程序调用**reqset_singlestage**请求设置，并返回一个请求 ID，写入到控制台。</span><span class="sxs-lookup"><span data-stu-id="049dc-148">The application invokes the **reqset_singlestage** request set and returns a request ID, which is written to the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="049dc-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="049dc-149">See Also</span></span>  
 [<span data-ttu-id="049dc-150">开发 Oracle E-business Suite 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="049dc-150">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)