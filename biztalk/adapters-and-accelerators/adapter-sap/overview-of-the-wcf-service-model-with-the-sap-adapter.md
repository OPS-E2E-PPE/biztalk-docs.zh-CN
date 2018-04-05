---
title: 与 SAP 适配器的 WCF 服务模型概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, overview of using
ms.assetid: 02a4b43e-ade0-4dba-b8f6-074bca7cbe5c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da5b2f7cc8e38eb8afd211a2008c0f740760cd4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-service-model-with-the-sap-adapter"></a><span data-ttu-id="96e6b-102">与 SAP 适配器的 WCF 服务模型概述</span><span class="sxs-lookup"><span data-stu-id="96e6b-102">Overview of the WCF service model with the SAP adapter</span></span>
<span data-ttu-id="96e6b-103">当你使用操作的[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]图面，你的代码起作用作为客户端或服务进行适配器。</span><span class="sxs-lookup"><span data-stu-id="96e6b-103">When you consume operations that the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] surfaces, your code acts either as a client or a service to the adapter.</span></span>  
  
 <span data-ttu-id="96e6b-104">你的代码充当客户端来调用以下类型的 SAP 系统上的操作：</span><span class="sxs-lookup"><span data-stu-id="96e6b-104">Your code acts as a client to invoke the following kinds of operations on the SAP system:</span></span>  
  
-   <span data-ttu-id="96e6b-105">调用远程函数调用 (RFC)。</span><span class="sxs-lookup"><span data-stu-id="96e6b-105">Invoke a Remote Function Call (RFC).</span></span>  
  
-   <span data-ttu-id="96e6b-106">调用事务远程函数调用 (tRFC)。</span><span class="sxs-lookup"><span data-stu-id="96e6b-106">Invoke a Transactional Remote Function Call (tRFC).</span></span>  
  
-   <span data-ttu-id="96e6b-107">调用业务应用程序编程接口 (BAPI)。</span><span class="sxs-lookup"><span data-stu-id="96e6b-107">Invoke a Business Application Programming Interface (BAPI).</span></span>  
  
-   <span data-ttu-id="96e6b-108">发送中间文档 (IDOC)</span><span class="sxs-lookup"><span data-stu-id="96e6b-108">Send an Intermediate Document (IDOC)</span></span>  
  
 <span data-ttu-id="96e6b-109">你的代码用作服务以接收以下类型的操作：</span><span class="sxs-lookup"><span data-stu-id="96e6b-109">Your code acts as a service to receive the following kinds of operations:</span></span>  
  
-   <span data-ttu-id="96e6b-110">接收 RFC (RFC server)</span><span class="sxs-lookup"><span data-stu-id="96e6b-110">Receive an RFC (RFC server)</span></span>  
  
-   <span data-ttu-id="96e6b-111">接收 tRFC （tRFC 服务器）</span><span class="sxs-lookup"><span data-stu-id="96e6b-111">Receive a tRFC (tRFC server)</span></span>  
  
-   <span data-ttu-id="96e6b-112">收到的 IDOC。</span><span class="sxs-lookup"><span data-stu-id="96e6b-112">Receive an IDOC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96e6b-113">由于 BAPIs 是由位于业务对象存储库 (BOR) 中的业务对象上的 SAP 系统公开方法，无法接收 BAPIs。</span><span class="sxs-lookup"><span data-stu-id="96e6b-113">Because BAPIs are methods exposed by the SAP system on business objects located in the Business Object Repository (BOR), you cannot receive BAPIs.</span></span>  
  
 <span data-ttu-id="96e6b-114">在[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型，为.NET 接口，表示客户端和服务之间存在的服务协定和操作表示为此接口上的方法。</span><span class="sxs-lookup"><span data-stu-id="96e6b-114">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="96e6b-115">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]并 WCF 提供使你能够从适配器公开的元数据生成目标操作此接口的工具。</span><span class="sxs-lookup"><span data-stu-id="96e6b-115">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="96e6b-116">这些工具还创建一个可用于调用服务接口中公开的操作的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="96e6b-116">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="96e6b-117">客户端应用程序可以调用 WCF 客户端类，以调用在适配器上的操作的方法。</span><span class="sxs-lookup"><span data-stu-id="96e6b-117">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span> <span data-ttu-id="96e6b-118">若要实现服务以接收从操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，实现为目标操作生成的接口。</span><span class="sxs-lookup"><span data-stu-id="96e6b-118">To implement a service to receive operations from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you implement the interface generated for the target operation.</span></span>  
  
 <span data-ttu-id="96e6b-119">以下各节说明如何使用 WCF 服务模型来创建客户端和服务代码[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="96e6b-119">The following sections explain how to use the WCF service model to create client and service code for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="creating-a-wcf-client-and-invoking-operations-on-sap"></a><span data-ttu-id="96e6b-120">创建 WCF 客户端和调用上 SAP 的操作</span><span class="sxs-lookup"><span data-stu-id="96e6b-120">Creating a WCF Client and Invoking Operations on SAP</span></span>  
 <span data-ttu-id="96e6b-121">以使用 WCF 服务模型上调用操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，你必须首先生成的目标操作一个 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="96e6b-121">To use the WCF service model to invoke operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="96e6b-122">然后，你可以创建 WCF 客户端，此类的实例并调用其方法来执行 SAP 系统上的操作。</span><span class="sxs-lookup"><span data-stu-id="96e6b-122">You can then create an instance of this class, a WCF client, and call its methods to perform operations on the SAP system.</span></span>  
  
#### <a name="to-invoke-operations-on-the-sap-adapter"></a><span data-ttu-id="96e6b-123">若要调用的 SAP 适配器上的操作</span><span class="sxs-lookup"><span data-stu-id="96e6b-123">To invoke operations on the SAP adapter</span></span>  
  
1.  <span data-ttu-id="96e6b-124">生成 WCF 客户端类和帮助程序代码。</span><span class="sxs-lookup"><span data-stu-id="96e6b-124">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="96e6b-125">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类的 SAP 系统项目针对你想要。</span><span class="sxs-lookup"><span data-stu-id="96e6b-125">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class targeted at the SAP system artifacts with which you want to work.</span></span> <span data-ttu-id="96e6b-126">有关如何生成 WCF 客户端的详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="96e6b-126">For more information about how to generate a WCF client, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="96e6b-127">通过指定客户端绑定中创建的 WCF 客户端实例。</span><span class="sxs-lookup"><span data-stu-id="96e6b-127">Create a WCF client instance by specifying a client binding.</span></span> <span data-ttu-id="96e6b-128">指定客户端绑定涉及到指定的绑定和 WCF 客户端将使用的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="96e6b-128">Specifying a client binding involves specifying the binding and endpoint address that the WCF client will use.</span></span> <span data-ttu-id="96e6b-129">可以在代码中以强制方式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="96e6b-129">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="96e6b-130">有关如何指定客户端绑定的详细信息，请参阅[配置客户端绑定 SAP 系统](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="96e6b-130">For more information about how to specify a client binding, see [Configure a client binding for the SAP system](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="96e6b-131">下面的代码创建可用于调用 RFC SAP 系统上的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="96e6b-131">The following code creates a WCF client that can be used to invoke an RFC on the SAP system.</span></span> <span data-ttu-id="96e6b-132">它还将设置为 SAP 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="96e6b-132">It also sets the credentials for the SAP system.</span></span> <span data-ttu-id="96e6b-133">WCF 客户端从配置初始化。</span><span class="sxs-lookup"><span data-stu-id="96e6b-133">The WCF client is initialized from configuration.</span></span>  
  
    ```  
    RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
    rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
    rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  <span data-ttu-id="96e6b-134">打开 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="96e6b-134">Open the WCF client.</span></span>  
  
    ```  
    rfcClient.Open();  
    ```  
  
4.  <span data-ttu-id="96e6b-135">调用在步骤 2 中创建的 WCF 客户端在 SAP 系统上执行操作的方法。</span><span class="sxs-lookup"><span data-stu-id="96e6b-135">Invoke methods on the WCF client created in step 2 to perform operations on the SAP system.</span></span> <span data-ttu-id="96e6b-136">下面的代码调用**SD_RFC_CUSTOMER_GET**的 WCF 客户端以调用 SAP 系统上的 RFC 的方法。</span><span class="sxs-lookup"><span data-stu-id="96e6b-136">The following code invokes the **SD_RFC_CUSTOMER_GET** method of the WCF client to invoke the RFC on the SAP system.</span></span>  
  
    ```  
    microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
        new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
    rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
    ```  
  
5.  <span data-ttu-id="96e6b-137">关闭 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="96e6b-137">Close the WCF client.</span></span>  
  
    ```  
    rfcClient.Close();  
  
    ```  
  
## <a name="creating-and-implementing-a-wcf-service-by-using-the-sap-adapter"></a><span data-ttu-id="96e6b-138">创建和使用 SAP 适配器实现的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="96e6b-138">Creating and Implementing a WCF Service by Using the SAP Adapter</span></span>  
 <span data-ttu-id="96e6b-139">使用 WCF 服务模型来接收从操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，你必须首先生成表示公开的服务协定的.NET 接口 （也称为 WCF 服务协定）[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作。</span><span class="sxs-lookup"><span data-stu-id="96e6b-139">To use the WCF service model to receive operations from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must first generate the .NET interface (also called the WCF service contract) that represents the service contract exposed by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for the operation.</span></span> <span data-ttu-id="96e6b-140">有关如何执行此操作的详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="96e6b-140">For more information about how to do this, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
 <span data-ttu-id="96e6b-141">然后情况下，通过实现生成的接口需要实现 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="96e6b-141">You then implement a WCF service by implementing the generated interface.</span></span> <span data-ttu-id="96e6b-142">此类包含业务逻辑来处理该操作并返回对该适配器的响应。</span><span class="sxs-lookup"><span data-stu-id="96e6b-142">This class contains the business logic to process the operation and return a response to the adapter.</span></span> <span data-ttu-id="96e6b-143">然后使用服务主机 (**System.ServiceModel.ServiceHost**) 来承载此服务的实例。</span><span class="sxs-lookup"><span data-stu-id="96e6b-143">Then you use a service host (**System.ServiceModel.ServiceHost**) to host an instance of this service.</span></span>  
  
#### <a name="to-create-and-implement-a-wcf-service"></a><span data-ttu-id="96e6b-144">若要创建和实现 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="96e6b-144">To create and implement a WCF service</span></span>  
  
1.  <span data-ttu-id="96e6b-145">生成 WCF 服务协定和帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="96e6b-145">Generate a WCF service contract and helper classes.</span></span> <span data-ttu-id="96e6b-146">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或 svcutil.exe 生成针对你想要的 SAP 系统项目的 WCF 服务协定 （接口）。</span><span class="sxs-lookup"><span data-stu-id="96e6b-146">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or svcutil.exe to generate a WCF service contract (interface) targeted at the SAP system artifacts with which you want to work.</span></span> <span data-ttu-id="96e6b-147">有关如何生成 WCF 客户端的详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="96e6b-147">For more information about how to generate a WCF client, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="96e6b-148">实现 WCF 服务从步骤 1 中生成的接口和帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="96e6b-148">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="96e6b-149">如果遇到错误则处理该操作的数据，处理该操作的方法可以引发异常返回到 SAP 系统，则为错误否则该方法必须返回为该操作的适当 （生成） 的响应类的实例。</span><span class="sxs-lookup"><span data-stu-id="96e6b-149">If an error is encountered processing the data for the operation, the method that handles that operation can throw an exception to return a fault to the SAP system; otherwise the method must return an instance of the appropriate (generated) response class for the operation.</span></span> <span data-ttu-id="96e6b-150">必须属性 WCF 服务类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="96e6b-150">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
    1.  <span data-ttu-id="96e6b-151">如果你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要生成界面，可以实现你的逻辑直接在相应的方法在生成中**SAPBindingService**类。</span><span class="sxs-lookup"><span data-stu-id="96e6b-151">If you used the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate the interface, you can implement your logic directly in the appropriate method in the generated **SAPBindingService** class.</span></span> <span data-ttu-id="96e6b-152">SAPBindingService.cs 中找不到此类。</span><span class="sxs-lookup"><span data-stu-id="96e6b-152">This class can be found in SAPBindingService.cs.</span></span> <span data-ttu-id="96e6b-153">下面的代码子类**SAPBindingService**类。</span><span class="sxs-lookup"><span data-stu-id="96e6b-153">The following code sub-classes the **SAPBindingService** class.</span></span>  
  
        ```  
        [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single,UseSynchronizationContext = false)]  
        class RfcServerClass : SAPBindingNamespace.SAPBindingService  
        {  
            public override Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request)  
            {  
                // If either parameter is null throw an exception   
                if (request.X == null || request.Y == null)  
                    throw new System.ArgumentNullException();  
  
                // Add the two operands  
                int result = (int) (request.X + request.Y);  
  
                return new Z_RFC_MKD_ADDResponse(result);  
            }  
        }  
        ```  
  
    2.  <span data-ttu-id="96e6b-154">如果使用 svcutil.exe 来生成界面，必须创建实现接口的类，并在此类的 appropriatemethod 中实现你的逻辑。</span><span class="sxs-lookup"><span data-stu-id="96e6b-154">If you used svcutil.exe to generate the interface, you must create a class that implements the interface and implement your logic in the appropriatemethod of this class.</span></span>  
  
3.  <span data-ttu-id="96e6b-155">创建在步骤 2 中创建的 WCF 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="96e6b-155">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    RfcServerClass rfcServerInstance = new RfcServerClass();  
    ```  
  
4.  <span data-ttu-id="96e6b-156">创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和数据库连接 URI。</span><span class="sxs-lookup"><span data-stu-id="96e6b-156">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="96e6b-157">Userinfoparams 或 query_string，不能包含基连接 URI。</span><span class="sxs-lookup"><span data-stu-id="96e6b-157">The base connection URI cannot contain userinfoparams or a query_string.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("sap://a/YourSAPHost/00") };  
    ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
    ```  
  
5.  <span data-ttu-id="96e6b-158">创建**SAPBinding**并将其配置的操作，通过设置其绑定属性。</span><span class="sxs-lookup"><span data-stu-id="96e6b-158">Create an **SAPBinding** and configure it for the operation by setting its binding properties.</span></span> <span data-ttu-id="96e6b-159">可以在代码中显式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="96e6b-159">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="96e6b-160">至少，你必须将设置**AcceptCredentialsInUri**到**true**。</span><span class="sxs-lookup"><span data-stu-id="96e6b-160">At a minimum, you must set **AcceptCredentialsInUri** to **true**.</span></span>  
  
    ```  
    // Create and configure a binding for the service endpoint. NOTE: binding  
    // parameters are set here for clarity, but these are already set in the  
    // the generated configuration file  
    SAPBinding binding = new SAPBinding();  
  
    // The credentials are included in the connection URI, so set this property to true  
    binding.AcceptCredentialsInUri = true;  
    ```  
  
6.  <span data-ttu-id="96e6b-161">将服务终结点添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="96e6b-161">Add a service endpoint to the service host.</span></span> <span data-ttu-id="96e6b-162">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="96e6b-162">To do this:</span></span>  
  
    -   <span data-ttu-id="96e6b-163">使用在步骤 5 中创建的绑定。</span><span class="sxs-lookup"><span data-stu-id="96e6b-163">Use the binding created in step 5.</span></span>  
  
    -   <span data-ttu-id="96e6b-164">指定连接 URI，它包含的凭据，并且指定的侦听器连接 （SAP 网关，网关服务和程序 ID） query_string 中。</span><span class="sxs-lookup"><span data-stu-id="96e6b-164">Specify a connection URI that contains credentials and specifies a listener connection (SAP gateway, gateway service and program ID) in the query_string.</span></span> <span data-ttu-id="96e6b-165">有关 SAP 连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="96e6b-165">For more information about the SAP connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
    -   <span data-ttu-id="96e6b-166">指定服务协定。</span><span class="sxs-lookup"><span data-stu-id="96e6b-166">Specify the service contract.</span></span> <span data-ttu-id="96e6b-167">这是表示 WCF 服务协定的接口的名称。</span><span class="sxs-lookup"><span data-stu-id="96e6b-167">This is the name of the interface that represents the WCF service contract.</span></span> <span data-ttu-id="96e6b-168">对于 Rfc，它是"Rfc"。</span><span class="sxs-lookup"><span data-stu-id="96e6b-168">For RFCs, it is "Rfc".</span></span>  
  
    ```  
    // Add service endpoint   
    // NOTE: The contract for the service endpoint is "Rfc".  
    //       This is the generated WCF service contract (interface) -- see SAPBindingInterface.cs.  
    Uri serviceUri = new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGW00&ListenerGwHost=YourSapHost&ListenerProgramId=SAPAdapter");  
    srvHost.AddServiceEndpoint("Rfc", binding, serviceUri);  
    ```  
  
7.  <span data-ttu-id="96e6b-169">若要从 SAP 系统接收操作，打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="96e6b-169">To receive the operation from the SAP system, open the service host.</span></span> <span data-ttu-id="96e6b-170">每当 SAP 系统时，将调用的程序 ID 和步骤 6 中的服务 URI 中指定的系统上的操作时，将激活您的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="96e6b-170">Your WCF service will be invoked whenever the SAP system invokes the operation on the program ID and system specified in the service URI in step 6.</span></span>  
  
    ```  
    // Open the service host to begin receiving the operation.  
    srvHost.Open();  
    ```  
  
8.  <span data-ttu-id="96e6b-171">若要停止接收该操作，关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="96e6b-171">To stop receiving the operation, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="96e6b-172">适配器将继续在关闭服务主机之前接收该操作。</span><span class="sxs-lookup"><span data-stu-id="96e6b-172">The adapter will continue to receive the operation until the service host is closed.</span></span> <span data-ttu-id="96e6b-173">当你不再想要接收操作时，你始终应关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="96e6b-173">You should always close the service host when you no longer want to receive the operation.</span></span>  
  
    ```  
    srvHost.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="96e6b-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96e6b-174">See Also</span></span>  
[<span data-ttu-id="96e6b-175">开发使用 WCF 服务模型的 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="96e6b-175">Develop SAP applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)