---
title: "与 Oracle E-business Suite 适配器的 WCF 服务模型概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aeeac8a4-a4bc-4963-951c-0c806e232f1e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f40b22865ca45cbd10823f6c514f75e5965f1df5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="36144-102">与 Oracle E-business Suite 适配器的 WCF 服务模型概述</span><span class="sxs-lookup"><span data-stu-id="36144-102">Overview of the WCF service model with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="36144-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开作为 WCF 服务的 Oracle E-business Suite 系统。</span><span class="sxs-lookup"><span data-stu-id="36144-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes an Oracle E-Business Suite system as a WCF service.</span></span> <span data-ttu-id="36144-104">若要对 Oracle E-business Suite 项目，例如来调用存储的过程中，执行操作你调用上的适配器，这反过来会对执行 Oracle E-business Suite 操作的操作。</span><span class="sxs-lookup"><span data-stu-id="36144-104">To perform operations on Oracle E-Business Suite artifacts, for example to invoke a stored procedure, you invoke an operation on the adapter, which, in turn, performs the operation on the Oracle E-Business Suite.</span></span> <span data-ttu-id="36144-105">你的代码充当客户端提供的适配器的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="36144-105">Your code acts as a client to the WCF service presented by the adapter.</span></span>  
  
 <span data-ttu-id="36144-106">在[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型，为.NET 接口，表示客户端和服务之间存在的服务协定和操作表示为此接口上的方法。</span><span class="sxs-lookup"><span data-stu-id="36144-106">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="36144-107">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]并 WCF 提供使你能够从适配器公开的元数据生成目标操作此接口的工具。</span><span class="sxs-lookup"><span data-stu-id="36144-107">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="36144-108">这些工具还创建一个可用于调用服务接口中公开的操作的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="36144-108">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="36144-109">客户端应用程序可以调用 WCF 客户端类，以调用在适配器上的操作的方法。</span><span class="sxs-lookup"><span data-stu-id="36144-109">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span>  
  
 <span data-ttu-id="36144-110">以下部分介绍如何使用 WCF 服务模型来调用操作与 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="36144-110">The following section explains how to use the WCF service model to invoke operations with a WCF client.</span></span>  
  
## <a name="invoking-operations-on-the-oracle-e-business-suite-with-a-wcf-client"></a><span data-ttu-id="36144-111">调用 Oracle E-business Suite 使用 WCF 客户端上的操作</span><span class="sxs-lookup"><span data-stu-id="36144-111">Invoking Operations on the Oracle E-Business Suite with a WCF Client</span></span>  
 <span data-ttu-id="36144-112">以使用 WCF 服务模型上调用操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，你必须首先生成的目标操作一个 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="36144-112">To use the WCF service model to invoke operations on the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="36144-113">然后，你可以创建 WCF 客户端，此类的实例并调用其方法来对 Oracle E-business Suite 执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="36144-113">You can then create an instance of this class, a WCF client, and call its methods to perform these operations on the Oracle E-Business Suite.</span></span>  
  
#### <a name="to-invoke-operations-on-the-oracle-e-business-adapter"></a><span data-ttu-id="36144-114">若要调用 Oracle E-business 适配器上的操作</span><span class="sxs-lookup"><span data-stu-id="36144-114">To invoke operations on the Oracle E-Business adapter</span></span>  
  
1.  <span data-ttu-id="36144-115">生成 WCF 客户端类和帮助程序代码。</span><span class="sxs-lookup"><span data-stu-id="36144-115">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="36144-116">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类针对 Oracle E-business Suite 项目需与之进行工作。</span><span class="sxs-lookup"><span data-stu-id="36144-116">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class targeted at Oracle E-Business Suite artifacts with which you want to work.</span></span> <span data-ttu-id="36144-117">有关如何生成 WCF 客户端的详细信息，请参阅[为 Oracle 电子商务解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="36144-117">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF Service Contract for Oracle E-Business Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="36144-118">创建 WCF 客户端实例和配置 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="36144-118">Create a WCF client instance and configure the WCF client.</span></span> <span data-ttu-id="36144-119">配置 WCF 客户端涉及到指定的绑定和客户端将使用的终结点地址 （连接 URI）。</span><span class="sxs-lookup"><span data-stu-id="36144-119">Configuring the WCF client involves specifying the binding and endpoint address (connection URI) that the client will use.</span></span> <span data-ttu-id="36144-120">可以在代码中以强制方式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="36144-120">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="36144-121">下面的代码创建一个 WCF 客户端针对**客户接口**中的并发程序**应收帐款**中 Oracle E-business Suite 应用程序。</span><span class="sxs-lookup"><span data-stu-id="36144-121">The following code creates a WCF client that targets the **Customer Interface** concurrent program in the **Receivables** application in the Oracle E-Business Suite.</span></span> <span data-ttu-id="36144-122">它还将设置为 Oracle E-business Suite 的凭据。</span><span class="sxs-lookup"><span data-stu-id="36144-122">It also sets the credentials for the Oracle E-Business Suite.</span></span> <span data-ttu-id="36144-123">WCF 客户端从配置初始化。</span><span class="sxs-lookup"><span data-stu-id="36144-123">The WCF client is initialized from configuration.</span></span>  
  
    ```  
    ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR"); //picking the binding and address from app.config  
  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="36144-124">可以在代码中指定的客户端绑定和终结点地址，也可以将其声明 app.config 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="36144-124">You can either specify the client binding and endpoint address in the code or declare it in the app.config configuration file.</span></span> <span data-ttu-id="36144-125">前面的代码段使用后者。</span><span class="sxs-lookup"><span data-stu-id="36144-125">The preceding code snippet uses the latter.</span></span> <span data-ttu-id="36144-126">有关如何使用任一方法的详细信息，请参阅[为 Oracle E-business Suite 配置客户端绑定](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="36144-126">For more information on how to use either approaches, see [Configure a Client Binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
3.  <span data-ttu-id="36144-127">打开 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="36144-127">Open the WCF client.</span></span>  
  
    ```  
    client.Open();  
    ```  
  
4.  <span data-ttu-id="36144-128">调用在步骤 2 中创建的 WCF 客户端来执行对 Oracle E-business Suite 操作的方法。</span><span class="sxs-lookup"><span data-stu-id="36144-128">Invoke methods on the WCF client created in step 2 to perform operations on the Oracle E-Business Suite.</span></span> <span data-ttu-id="36144-129">下面的代码调用**客户接口**中的并发程序**应收帐款**中 Oracle E-business Suite 应用程序。</span><span class="sxs-lookup"><span data-stu-id="36144-129">The following code invokes the **Customer Interface** concurrent program in the **Receivables** application in the Oracle E-Business Suite.</span></span>  
  
    ```  
    string Result = client.RACUST(null, null, null, description, null, recipro_cust, org_id);  
    ```  
  
     <span data-ttu-id="36144-130">**RACUST**是客户接口并发程序的实际名称。</span><span class="sxs-lookup"><span data-stu-id="36144-130">**RACUST** is the actual name of the Customer Interface concurrent program.</span></span> <span data-ttu-id="36144-131">**客户接口**是并发的程序的友好名称。</span><span class="sxs-lookup"><span data-stu-id="36144-131">**Customer Interface** is the friendly name of the concurrent program.</span></span>  
  
5.  <span data-ttu-id="36144-132">关闭 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="36144-132">Close the WCF client.</span></span>  
  
    ```  
    client.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="36144-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36144-133">See Also</span></span>  
 [<span data-ttu-id="36144-134">开发 Oracle E-business Suite 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="36144-134">Develop Oracle E-Business Suite Applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)