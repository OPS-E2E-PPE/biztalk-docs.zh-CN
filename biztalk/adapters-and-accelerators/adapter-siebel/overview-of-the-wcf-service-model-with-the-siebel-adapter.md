---
title: "与 Siebel 适配器的 WCF 服务模型概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, invoke operations on the Siebel system with a WCF client
- WCF service model, overview of
ms.assetid: 0e812473-0f50-4972-8b07-ec8edc2ef000
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c638255b103a9c588f22d6ddcb2a75b81619b73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-service-model-with-the-siebel-adapter"></a><span data-ttu-id="c6106-102">与 Siebel 适配器的 WCF 服务模型概述</span><span class="sxs-lookup"><span data-stu-id="c6106-102">Overview of the WCF service model with the Siebel adapter</span></span>
<span data-ttu-id="c6106-103">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公开作为 WCF 服务的 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="c6106-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] exposes a Siebel system as a WCF service.</span></span> <span data-ttu-id="c6106-104">若要在 Siebel 系统项目，例如，若要调用的 Siebel 业务服务，方法上执行操作你调用上的适配器，这反过来会对执行 Siebel 系统操作的操作。</span><span class="sxs-lookup"><span data-stu-id="c6106-104">To perform operations on Siebel system artifacts, for example to invoke a method of a Siebel business service, you invoke an operation on the adapter, which, in turn, performs the operation on the Siebel system.</span></span> <span data-ttu-id="c6106-105">你的代码因此充当客户端提供的适配器的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="c6106-105">Your code therefore acts as a client to the WCF service presented by the adapter.</span></span>  
  
 <span data-ttu-id="c6106-106">在[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型，为.NET 接口，表示客户端和服务之间存在的服务协定和操作表示为此接口上的方法。</span><span class="sxs-lookup"><span data-stu-id="c6106-106">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="c6106-107">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]并 WCF 提供使你能够从适配器公开的元数据生成目标操作此接口的工具。</span><span class="sxs-lookup"><span data-stu-id="c6106-107">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="c6106-108">这些工具还创建一个可用于调用服务接口中公开的操作的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="c6106-108">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="c6106-109">客户端应用程序可以调用 WCF 客户端类，以调用在适配器上的操作的方法。</span><span class="sxs-lookup"><span data-stu-id="c6106-109">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span>  
  
 <span data-ttu-id="c6106-110">以下部分介绍如何使用 WCF 服务模型来调用操作与 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="c6106-110">The following section explains how to use the WCF service model to invoke operations with a WCF client.</span></span>  
  
## <a name="invoking-operations-on-the-siebel-system-with-a-wcf-client"></a><span data-ttu-id="c6106-111">调用 Siebel 系统与 WCF 客户端上的操作</span><span class="sxs-lookup"><span data-stu-id="c6106-111">Invoking Operations on the Siebel System with a WCF Client</span></span>  
 <span data-ttu-id="c6106-112">以使用 WCF 服务模型上调用操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，你必须首先生成的目标操作一个 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="c6106-112">To use the WCF service model to invoke operations on the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="c6106-113">然后，你可以创建 WCF 客户端，此类的实例并调用其方法来执行这些操作 Siebel 系统上。</span><span class="sxs-lookup"><span data-stu-id="c6106-113">You can then create an instance of this class, a WCF client, and call its methods to perform these operations on the Siebel system.</span></span>  
  
#### <a name="to-invoke-operations-on-the-siebel-adapter"></a><span data-ttu-id="c6106-114">若要在 Siebel 适配器上调用操作</span><span class="sxs-lookup"><span data-stu-id="c6106-114">To invoke operations on the Siebel adapter</span></span>  
  
1.  <span data-ttu-id="c6106-115">生成 WCF 客户端类和帮助程序代码。</span><span class="sxs-lookup"><span data-stu-id="c6106-115">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="c6106-116">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类 Siebel 系统项目针对你想要。</span><span class="sxs-lookup"><span data-stu-id="c6106-116">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class targeted at the Siebel system artifacts with which you want to work.</span></span> <span data-ttu-id="c6106-117">有关如何生成 WCF 客户端的详细信息，请参阅[为 Siebel 解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="c6106-117">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF service contract for Siebel Solution Artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="c6106-118">创建 WCF 客户端实例和配置 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="c6106-118">Create a WCF client instance and configure the WCF client.</span></span> <span data-ttu-id="c6106-119">配置 WCF 客户端涉及到指定的绑定和客户端将使用的终结点地址 （连接 URI）。</span><span class="sxs-lookup"><span data-stu-id="c6106-119">Configuring the WCF client involves specifying the binding and endpoint address (connection URI) that the client will use.</span></span> <span data-ttu-id="c6106-120">可以在代码中以强制方式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c6106-120">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="c6106-121">有关如何配置 WCF 客户端的详细信息，请参阅[为 Siebel 系统配置 WCF 客户端](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)。</span><span class="sxs-lookup"><span data-stu-id="c6106-121">For more information about how to configure the WCF client, see [Configure a WCF Client for a Siebel System](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md).</span></span> <span data-ttu-id="c6106-122">下面的代码创建面向 Siebel 时间戳业务服务的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="c6106-122">The following code creates a WCF client that targets the Siebel TimeStamp business service.</span></span> <span data-ttu-id="c6106-123">它还将设置 Siebel 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="c6106-123">It also sets the credentials for the Siebel system.</span></span> <span data-ttu-id="c6106-124">WCF 客户端从配置初始化。</span><span class="sxs-lookup"><span data-stu-id="c6106-124">The WCF client is initialized from configuration.</span></span>  
  
    ```  
    BusinessServices_TimeStamp_OperationClient client =  
        new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
    client.ClientCredentials.UserName.UserName = "YourUserName";  
    client.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  <span data-ttu-id="c6106-125">打开 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="c6106-125">Open the WCF client.</span></span>  
  
    ```  
    client.Open();  
    ```  
  
4.  <span data-ttu-id="c6106-126">调用在步骤 2 中创建的 WCF 客户端在 Siebel 系统上执行操作的方法。</span><span class="sxs-lookup"><span data-stu-id="c6106-126">Invoke methods on the WCF client created in step 2 to perform operations on the Siebel system.</span></span> <span data-ttu-id="c6106-127">下面的代码调用**执行**的 WCF 客户端以调用的方法**执行**Siebel 系统上的时间戳业务服务的方法。</span><span class="sxs-lookup"><span data-stu-id="c6106-127">The following code invokes the **Execute** method of the WCF client to invoke the **Execute** method of the TimeStamp business service on the Siebel system.</span></span>  
  
    ```  
    // Create a parameter to hold the results and then invoke the Execute method of the TimeStamp business service.  
    microsoft.lobservices.siebel._2007._03.BusinessServices.TimeStamp.ExecuteResponseRecord er;  
    er = client.Execute();  
    ```  
  
5.  <span data-ttu-id="c6106-128">关闭 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="c6106-128">Close the WCF client.</span></span>  
  
    ```  
    client.Close();  
    ```  
  
 <span data-ttu-id="c6106-129">有关调用 Siebel 业务服务方法的详细信息，请参阅[与使用 WCF 服务模型的 Siebel 适配器调用业务服务的方法](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md)</span><span class="sxs-lookup"><span data-stu-id="c6106-129">For more information about invoking Siebel business service methods, see [Invoke Business Service Methods with the Siebel adapter using the WCF Service Model](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md)</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c6106-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6106-130">See Also</span></span>  
 [<span data-ttu-id="c6106-131">开发 Siebel 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="c6106-131">Develop Siebel Applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)