---
title: 调用中使用 WCF 服务模型的 SAP Rfc |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- invoking RFCs, using the WCF service model
- WCF service model, invoking RFCs
ms.assetid: 06a373e2-5d16-4480-81ec-611bd0b9749c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a741ac41c86258567a22bb3a8a8d9ec699064dd0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373321"
---
# <a name="invoke-rfcs-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="77310-102">调用中使用 WCF 服务模型的 SAP Rfc</span><span class="sxs-lookup"><span data-stu-id="77310-102">Invoke RFCs in SAP using the WCF Service Model</span></span>
<span data-ttu-id="77310-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] SAP 系统上的 Rfc 显示为可由客户端程序调用的操作。</span><span class="sxs-lookup"><span data-stu-id="77310-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] surfaces RFCs on the SAP system as operations that can be invoked by a client program.</span></span> <span data-ttu-id="77310-104">在 WCF 服务模型中，为生成的 WCF 客户端类的方法调用这些操作。</span><span class="sxs-lookup"><span data-stu-id="77310-104">In the WCF service model, these operations are invoked as methods of a generated WCF client class.</span></span> <span data-ttu-id="77310-105">可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]来生成 WCF 客户端类，它包含你要在代码中调用每个 RFC 的方法。</span><span class="sxs-lookup"><span data-stu-id="77310-105">You can use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class that contains methods for each RFC that you want to invoke in your code.</span></span> <span data-ttu-id="77310-106">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成.NET 类型来封装由每个 RFC 的参数和数据类型。</span><span class="sxs-lookup"><span data-stu-id="77310-106">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates .NET types to encapsulate the parameters and data types that are used by each RFC.</span></span> <span data-ttu-id="77310-107">然后，您可以创建此 WCF 客户端类的实例并调用其方法来调用目标 Rfc。</span><span class="sxs-lookup"><span data-stu-id="77310-107">You can then create an instance of this WCF client class and call its methods to invoke the target RFCs.</span></span>  
  
 <span data-ttu-id="77310-108">以下部分说明如何使用 SAP 系统上调用 Rfc [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="77310-108">The following sections show you how to invoke RFCs on the SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="77310-109">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="77310-109">The WCF Client Class</span></span>  
 <span data-ttu-id="77310-110">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]单一的服务合同，"Rfc"下的所有 RFC 操作的图都面。</span><span class="sxs-lookup"><span data-stu-id="77310-110">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces all RFC operations under a single service contract, "Rfc".</span></span> <span data-ttu-id="77310-111">这意味着，单一的 WCF 客户端类， **RfcClient**，为所有你想要调用的 RFC 操作的创建。</span><span class="sxs-lookup"><span data-stu-id="77310-111">This means that a single WCF client class, **RfcClient**, is created for all of the RFC operations that you want to invoke.</span></span> <span data-ttu-id="77310-112">每个目标 RFC 表示为此类的方法。</span><span class="sxs-lookup"><span data-stu-id="77310-112">Each target RFC is represented as a method of this class.</span></span> <span data-ttu-id="77310-113">在每个方法中：</span><span class="sxs-lookup"><span data-stu-id="77310-113">In each method:</span></span>  
  
- <span data-ttu-id="77310-114">SAP 导出参数显示为**出**参数</span><span class="sxs-lookup"><span data-stu-id="77310-114">SAP export parameters are surfaced as **out** parameters</span></span>  
  
- <span data-ttu-id="77310-115">SAP 更改参数显示为**ref**参数。</span><span class="sxs-lookup"><span data-stu-id="77310-115">SAP changing parameters are surfaced as **ref** parameters.</span></span>  
  
- <span data-ttu-id="77310-116">如结构复杂 SAP 类型为.NET 类相对应的属性与提供给 SAP 类型的字段。</span><span class="sxs-lookup"><span data-stu-id="77310-116">Complex SAP types such as structures are surfaced as .NET classes with properties that correspond to the fields of the SAP type.</span></span> <span data-ttu-id="77310-117">在以下命名空间中定义这些类： microsoft.lobservices.sap._2007._03.Types.Rfc。</span><span class="sxs-lookup"><span data-stu-id="77310-117">These classes are defined in the following namespace: microsoft.lobservices.sap._2007._03.Types.Rfc.</span></span>  
  
  <span data-ttu-id="77310-118">下面的代码显示了一部分**RfcClient**类和方法调用 SD_RFC_CUSTOMER_GET SAP 系统上。</span><span class="sxs-lookup"><span data-stu-id="77310-118">The following code shows part of the **RfcClient** class and the method that invokes SD_RFC_CUSTOMER_GET on the SAP system.</span></span>  
  
```  
 [System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class RfcClient : System.ServiceModel.ClientBase<Rfc>, Rfc {  
  
    ...  
  
    /// <summary>The metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="KUNNR">Customer number</param>  
    /// <param name="NAME1">Name of the customer</param>  
    /// <param name="CUSTOMER_T">Table of the selected customers</param>  
    /// <returns></returns>  
    public void SD_RFC_CUSTOMER_GET(string KUNNR, string NAME1, ref microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] CUSTOMER_T) {...}  
}  
```  
  
## <a name="how-to-create-an-rfc-client-application"></a><span data-ttu-id="77310-119">如何创建 RFC 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="77310-119">How to Create an RFC Client Application</span></span>  
 <span data-ttu-id="77310-120">若要创建的 RFC 客户端应用程序，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="77310-120">To create an RFC client application, perform the following steps.</span></span>  
  
#### <a name="to-create-an-rfc-client-application"></a><span data-ttu-id="77310-121">若要创建的 RFC 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="77310-121">To create an RFC client application</span></span>  
  
1. <span data-ttu-id="77310-122">生成**RfcClient**类。</span><span class="sxs-lookup"><span data-stu-id="77310-122">Generate an **RfcClient** class.</span></span> <span data-ttu-id="77310-123">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 生成**RfcClient**以你想要的 Rfc 目标的类。</span><span class="sxs-lookup"><span data-stu-id="77310-123">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate an **RfcClient** class that targets the RFCs with which you want to work.</span></span> <span data-ttu-id="77310-124">有关如何生成 WCF 客户端的详细信息，请参阅[的 SAP 解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="77310-124">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF Service Contract for SAP Solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2. <span data-ttu-id="77310-125">创建的实例**RfcClient**类中生成的步骤 1，并指定客户端绑定。</span><span class="sxs-lookup"><span data-stu-id="77310-125">Create an instance of the **RfcClient** class generated in step 1, and specify a client binding.</span></span> <span data-ttu-id="77310-126">指定客户端绑定涉及到指定的绑定和终结点地址**RfcClient**将使用。</span><span class="sxs-lookup"><span data-stu-id="77310-126">Specifying a client binding involves specifying the binding and endpoint address that the **RfcClient** will use.</span></span> <span data-ttu-id="77310-127">可以在代码中以强制方式或在配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="77310-127">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="77310-128">有关如何指定客户端绑定的详细信息，请参阅[SAP 系统的配置客户端绑定](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="77310-128">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="77310-129">下面的代码初始化**RfcClient**从配置和 SAP 系统的凭据集。</span><span class="sxs-lookup"><span data-stu-id="77310-129">The following code initializes the **RfcClient** from configuration and sets the credentials for the SAP system.</span></span>  
  
   ```  
   RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
   rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
   rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. <span data-ttu-id="77310-130">打开 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="77310-130">Open the WCF client.</span></span>  
  
   ```  
   rfcClient.Open();  
   ```  
  
4. <span data-ttu-id="77310-131">调用方法**RfcClient**在步骤 2 来执行 SAP 系统的操作中创建。</span><span class="sxs-lookup"><span data-stu-id="77310-131">Invoke methods on the **RfcClient** created in step 2 to perform operations on the SAP system.</span></span> <span data-ttu-id="77310-132">下面的代码调用**SD_RFC_CUSTOMER_GET**方法**RfcClient**调用 SAP 系统上的 RFC。</span><span class="sxs-lookup"><span data-stu-id="77310-132">The following code invokes the **SD_RFC_CUSTOMER_GET** method of the **RfcClient** to invoke the RFC on the SAP system.</span></span>  
  
   ```  
   microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
       new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
   rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
   ```  
  
5. <span data-ttu-id="77310-133">关闭 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="77310-133">Close the WCF client.</span></span>  
  
   ```  
   rfcClient.Close();   
   ```  
  
### <a name="example"></a><span data-ttu-id="77310-134">示例</span><span class="sxs-lookup"><span data-stu-id="77310-134">Example</span></span>  
 <span data-ttu-id="77310-135">下面是完整的代码示例调用 SD_RFC_CUSTOMER_GET 返回名称以"AB"开头的客户的列表，然后将名称和 ID 为每个客户写入控制台。</span><span class="sxs-lookup"><span data-stu-id="77310-135">The following is a complete code example that invokes SD_RFC_CUSTOMER_GET to return a list of customers with names that begin with "AB" and then writes the name and ID for each customer to the console.</span></span> <span data-ttu-id="77310-136">此示例将创建**RfcClient**内**使用**语句。</span><span class="sxs-lookup"><span data-stu-id="77310-136">This example creates the **RfcClient** inside a **using** statement.</span></span> <span data-ttu-id="77310-137">无需显式关闭**RfcClient**; 的执行路径退出上下文时将关闭。</span><span class="sxs-lookup"><span data-stu-id="77310-137">There is no need to explicitly close the **RfcClient**; it will be closed when the execution path exits the context.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.SAP;  
  
namespace SapRfcClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                // Create client from configuration  
                using (RfcClient rfcClient = new RfcClient("SAPBinding_Rfc"))  
                {  
  
                    rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
                    rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                    // Open client  
                    rfcClient.Open();  
  
                    microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers = new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
                    // Invoke SD_RFC_CUSTOMER_GET  
                    rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
  
                    // Write the results to the console  
                    foreach (microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST customer in customers)  
                    {  
                        Console.WriteLine("Customer Name = " + customer.NAME1);  
                        Console.WriteLine("         Id   = " + customer.KUNNR);  
                        Console.WriteLine();  
                    }  
                }  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
                if (ex.InnerException != null)  
                    Console.WriteLine("Inner exception is :" + ex.InnerException);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="77310-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="77310-138">See Also</span></span>  
<span data-ttu-id="77310-139">[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="77310-139">[Develop applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 [<span data-ttu-id="77310-140">RFC 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="77310-140">Message Schemas for RFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)