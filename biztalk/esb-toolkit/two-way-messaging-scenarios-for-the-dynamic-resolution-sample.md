---
title: 动态解析示例的双向消息传送方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e89792f1-c725-46c4-946c-23211e2f892a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6787edc22c06d6935518be9d223f5968a595d6cf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997014"
---
# <a name="two-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a><span data-ttu-id="3da75-102">动态解析示例的双向消息传送方案</span><span class="sxs-lookup"><span data-stu-id="3da75-102">Two-Way Messaging Scenarios for the Dynamic Resolution Sample</span></span>
<span data-ttu-id="3da75-103">本主题演示如何运行的双向消息传送方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态解析示例。</span><span class="sxs-lookup"><span data-stu-id="3da75-103">This topic shows how you can run the two-way messaging scenarios for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Dynamic Resolution sample.</span></span>  

 <span data-ttu-id="3da75-104">**若要运行动态解析示例的双向消息传送方案**</span><span class="sxs-lookup"><span data-stu-id="3da75-104">**To run the two-way messaging scenarios for the Dynamic Resolution sample**</span></span>  

1. <span data-ttu-id="3da75-105">第一次运行此示例之前，请确保接收位置 URL 指向适当的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="3da75-105">Before you run this sample for the first time, make sure that the receive location URL points to the appropriate Web service.</span></span> <span data-ttu-id="3da75-106">指定 Web 服务 URL /ESB。有关 DynamicResolutionReqResp_SOAP NorthAmericanServices/CustomerOrder.asmx 接收位置。</span><span class="sxs-lookup"><span data-stu-id="3da75-106">Specify the Web service URL /ESB.NorthAmericanServices/CustomerOrder.asmx for the DynamicResolutionReqResp_SOAP receive location.</span></span> <span data-ttu-id="3da75-107">此外，请确保存在名为 DynamicResolutionSolicitResp 的动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="3da75-107">Also, make sure that the dynamic send port named DynamicResolutionSolicitResp exists.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3da75-108">动态解析示例使用动态解析发送邮件，并接收来自加拿大的 Web 服务响应 (http://localhost/ESB.CanadianServices/SubmitPOService.asmx)。</span><span class="sxs-lookup"><span data-stu-id="3da75-108">The Dynamic Resolution sample uses dynamic resolution to send messages to, and receive responses from, the Canadian Web service (http://localhost/ESB.CanadianServices/SubmitPOService.asmx).</span></span> <span data-ttu-id="3da75-109">这就是原因本示例未定义静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="3da75-109">This is why a static send port is not defined for this sample.</span></span> <span data-ttu-id="3da75-110">动态解析组件解决方法从检索的出站 URL 和适配器提供程序框架调用 ESBReceiveXml 管道，在 DynamicResolutionReqResp_SOAP 中配置的接收位置。</span><span class="sxs-lookup"><span data-stu-id="3da75-110">The dynamic resolution component retrieves the outbound URL from the Resolution and Adapter Provider Framework called by the ESBReceiveXml pipeline, which is configured within the DynamicResolutionReqResp_SOAP receive location.</span></span> <span data-ttu-id="3da75-111">在某些双向消息传送示例中，ESBMapSend 管道解析和执行 Microsoft BizTalk 映射。</span><span class="sxs-lookup"><span data-stu-id="3da75-111">In some of the two-way messaging examples, the ESBMapSend pipeline resolves and executes Microsoft BizTalk maps.</span></span>  

2. <span data-ttu-id="3da75-112">如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="3da75-112">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  

3. <span data-ttu-id="3da75-113">决定你想要执行的示例。</span><span class="sxs-lookup"><span data-stu-id="3da75-113">Decide which example you want to execute.</span></span> <span data-ttu-id="3da75-114">所有的双向消息传送方案使用 ESB。NorthAmericanServices Web 服务位于http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx将请求消息发布到 BizTalk，使用名为 DynamicResolutionReqResp_SOAP 的接收位置。</span><span class="sxs-lookup"><span data-stu-id="3da75-114">All two-way messaging scenarios use the ESB.NorthAmericanServices Web service located at http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx to publish the request message to BizTalk, which uses the receive location named DynamicResolutionReqResp_SOAP.</span></span> <span data-ttu-id="3da75-115">有 10 个双向消息传送示例，每个唯一绑定文件表示。</span><span class="sxs-lookup"><span data-stu-id="3da75-115">There are 10 two-way messaging examples, each represented by a unique binding file.</span></span> <span data-ttu-id="3da75-116">下表列出了这些示例中，使用其关联的绑定文件和说明。</span><span class="sxs-lookup"><span data-stu-id="3da75-116">The following tables list these examples, with their associated binding files and descriptions.</span></span>  

   |<span data-ttu-id="3da75-117">SOAP 到 SOAP 出站 (submitOrder 操作) 的入站使用 BRE 冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="3da75-117">SOAP Inbound to SOAP Outbound (submitOrder Action) Using the BRE Resolver</span></span>|  
   |---------------------------------------------------------------------------------|  
   |<span data-ttu-id="3da75-118">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="3da75-118">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="3da75-119">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="3da75-119">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   |<span data-ttu-id="3da75-120">SOAP 到 SOAP 出站 (submitOrder 操作) 的入站终结点和转换解析使用 BRE 冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="3da75-120">SOAP Inbound to SOAP Outbound (submitOrder Action) Using the BRE Resolver for Endpoint and Transformation Resolution</span></span>|  
   |----------------------------------------------------------------------------------------------------------------------------|  
   |<span data-ttu-id="3da75-121">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Routing_AND_ Transform_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="3da75-121">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Routing_AND_ Transform_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="3da75-122">使用出站发送端口上的 ESB 调度程序组件的管道和出站接收位置管道动态解析和执行映射。</span><span class="sxs-lookup"><span data-stu-id="3da75-122">Uses the ESB Dispatcher component on the outbound send port pipeline and the outbound receive location pipeline to dynamically resolve and execute the map.</span></span>|  
   |<span data-ttu-id="3da75-123">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="3da75-123">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   |<span data-ttu-id="3da75-124">SOAP 到 SOAP 出站 (submitOrder 操作) 的入站使用静态的冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="3da75-124">SOAP Inbound to SOAP Outbound (submitOrder Action) Using the STATIC Resolver</span></span>|  
   |------------------------------------------------------------------------------------|  
   |<span data-ttu-id="3da75-125">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="3da75-125">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="3da75-126">在接收端口以静态方式设置这些映射。</span><span class="sxs-lookup"><span data-stu-id="3da75-126">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="3da75-127">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="3da75-127">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   |<span data-ttu-id="3da75-128">SOAP 到 SOAP 出站 (submitOrder 操作) 的入站使用 UDDI 解析程序对 Microsoft UDDI 服务器</span><span class="sxs-lookup"><span data-stu-id="3da75-128">SOAP Inbound to SOAP Outbound (submitOrder Action) Using the UDDI Resolver Against the Microsoft UDDI Server</span></span>|  
   |--------------------------------------------------------------------------------------------------------------------|  
   |<span data-ttu-id="3da75-129">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_MSFTREGISTRY_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="3da75-129">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_MSFTREGISTRY_ Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="3da75-130">在接收端口以静态方式设置这些映射。</span><span class="sxs-lookup"><span data-stu-id="3da75-130">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="3da75-131">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="3da75-131">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   > [!NOTE]
   >  <span data-ttu-id="3da75-132">对于上述示例中，必须更改绑定文件中的服务密钥为其中一个目标 UDDI 服务器上存在。</span><span class="sxs-lookup"><span data-stu-id="3da75-132">For the preceding example, you must change the service key in the binding file to one that exists on the target UDDI server.</span></span>  

   |<span data-ttu-id="3da75-133">SOAP 到 SOAP 出站 (submitOrder 操作) 的入站使用 UDDI 解析程序针对 SOA 软件 UDDI 服务器</span><span class="sxs-lookup"><span data-stu-id="3da75-133">SOAP Inbound to SOAP Outbound (submitOrder Action) Using the UDDI Resolver Against the SOA Software UDDI Server</span></span>|  
   |-----------------------------------------------------------------------------------------------------------------------|  
   |<span data-ttu-id="3da75-134">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_SOAREGISTRY_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="3da75-134">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_SOAREGISTRY_ Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="3da75-135">在接收端口以静态方式设置这些映射。</span><span class="sxs-lookup"><span data-stu-id="3da75-135">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="3da75-136">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="3da75-136">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   |                                                            <span data-ttu-id="3da75-137">SOAP 到 SOAP 出站 (submitOrder 操作) 的入站使用 XPATH 冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="3da75-137">SOAP Inbound to SOAP Outbound (submitOrder Action) Using the XPATH Resolver</span></span>                                                            |
   |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                 <span data-ttu-id="3da75-138">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_XPATH_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="3da75-138">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_XPATH_Bindings.xml to set the receive location and send port properties.</span></span>                  |
   |                                                                           <span data-ttu-id="3da75-139">在接收端口以静态方式设置这些映射。</span><span class="sxs-lookup"><span data-stu-id="3da75-139">Sets the maps statically at the receive port.</span></span>                                                                           |
   |                                                             <span data-ttu-id="3da75-140">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="3da75-140">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>                                                              |
   | <span data-ttu-id="3da75-141">该消息包含的终结点配置 ID =<http://localhost/ESB.CanadianServices/SubmitPOService.asmx>和 customerName =<http://globalbank.esb.dynamicresolution.com/canadianservices/>。</span><span class="sxs-lookup"><span data-stu-id="3da75-141">The message contains the endpoint configuration ID=<http://localhost/ESB.CanadianServices/SubmitPOService.asmx> and customerName=<http://globalbank.esb.dynamicresolution.com/canadianservices/>.</span></span> |

   |<span data-ttu-id="3da75-142">SOAP 到 SOAP 出站 (submitPurchase 操作) 的入站使用 BRE 冲突解决程序终结点和转换解析</span><span class="sxs-lookup"><span data-stu-id="3da75-142">SOAP Inbound to SOAP Outbound (submitPurchase Action) Using the BRE Resolver Endpoint and Transformation Resolution</span></span>|  
   |---------------------------------------------------------------------------------------------------------------------------|  
   |<span data-ttu-id="3da75-143">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_BRE_Routing_ AND_Transform_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="3da75-143">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_BRE_Routing_ AND_Transform_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="3da75-144">使用出站发送端口上的 ESB 调度程序组件的管道和出站接收位置管道动态解析和执行映射。</span><span class="sxs-lookup"><span data-stu-id="3da75-144">Uses the ESB Dispatcher component on the outbound send port pipeline and the outbound receive location pipeline to dynamically resolve and execute the map.</span></span>|  
   |<span data-ttu-id="3da75-145">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="3da75-145">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
   |<span data-ttu-id="3da75-146">BRE 冲突解决程序更改**操作**从**submitOrder**到**submitPurchase**。</span><span class="sxs-lookup"><span data-stu-id="3da75-146">The BRE Resolver changes the **Action** from **submitOrder** to **submitPurchase**.</span></span>|  

   |                                              <span data-ttu-id="3da75-147">SOAP 到 SOAP 出站 (submitPurchase 操作) 的入站使用静态的冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="3da75-147">SOAP Inbound to SOAP Outbound (submitPurchase Action) Using the STATIC Resolver</span></span>                                               |
   |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="3da75-148">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_STATIC_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="3da75-148">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_STATIC_ Bindings.xml to set the receive location and send port properties.</span></span> |
   |                                                               <span data-ttu-id="3da75-149">在接收端口以静态方式设置这些映射。</span><span class="sxs-lookup"><span data-stu-id="3da75-149">Sets the maps statically at the receive port.</span></span>                                                                |
   |                                                  <span data-ttu-id="3da75-150">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="3da75-150">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>                                                  |
   |                                           <span data-ttu-id="3da75-151">静态解析程序更改**操作**从**submitOrder**到**submitPurchase**。</span><span class="sxs-lookup"><span data-stu-id="3da75-151">The STATIC Resolver changes the **Action** from **submitOrder** to **submitPurchase**.</span></span>                                           |


4. <span data-ttu-id="3da75-152">导入绑定文件对于您要执行到 GlobalBank.ESB 应用程序的消息传送示例。</span><span class="sxs-lookup"><span data-stu-id="3da75-152">Import the binding file for the messaging example you want to execute into the GlobalBank.ESB application.</span></span>  

5. <span data-ttu-id="3da75-153">调用 NorthAmerican Web 服务使用 Microsoft InfoPath、.NET Web 服务 Studio 或任何其他适当的机制。</span><span class="sxs-lookup"><span data-stu-id="3da75-153">Call the NorthAmerican Web service using Microsoft InfoPath, the .NET Web Service Studio, or any other appropriate mechanism.</span></span> <span data-ttu-id="3da75-154">请确保包含该操作所需的所有参数。</span><span class="sxs-lookup"><span data-stu-id="3da75-154">Make sure that you include all parameters required by the operation.</span></span>  

6. <span data-ttu-id="3da75-155">查找返回的消息响应。</span><span class="sxs-lookup"><span data-stu-id="3da75-155">Look for the returned message response.</span></span> <span data-ttu-id="3da75-156">如果指定了**submitOrder**操作，"提交订单"的文本将在之前的值**ID**字段中返回的消息。</span><span class="sxs-lookup"><span data-stu-id="3da75-156">If you specified the **submitOrder** action, the text "Submit Order" will precede the value of the **ID** field in the returned message.</span></span> <span data-ttu-id="3da75-157">如果指定了**submitPurchase**操作，"提交购买"的文本将在之前的值**ID**字段中返回的消息。</span><span class="sxs-lookup"><span data-stu-id="3da75-157">If you specified the **submitPurchase** action, the text "Submit Purchase" will precede the value of the **ID** field in the returned message.</span></span>  

   <span data-ttu-id="3da75-158">若要了解此示例如何使用 ESB 调度程序和 ESB 调度程序反汇编程序管道组件，请参阅[动态解析示例的工作原理](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)。</span><span class="sxs-lookup"><span data-stu-id="3da75-158">To understand how the sample uses the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components, see [How the Dynamic Resolution Sample Works](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span></span>