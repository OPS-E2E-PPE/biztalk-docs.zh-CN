---
title: "安装和运行动态解析示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4359987-b18c-44f5-a2cf-e30e17ac5e9f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04d697028eb76cf922cf4bf5e5db85c561c67d00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-running-the-dynamic-resolution-sample"></a><span data-ttu-id="764a6-102">安装和运行动态解析示例</span><span class="sxs-lookup"><span data-stu-id="764a6-102">Installing and Running the Dynamic Resolution Sample</span></span>
<span data-ttu-id="764a6-103">此动态解析示例演示 ESB 调度程序和 ESB 调度程序反汇编程序管道组件的典型使用方案。</span><span class="sxs-lookup"><span data-stu-id="764a6-103">The Dynamic Resolution sample demonstrates typical usage scenarios for the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components.</span></span> <span data-ttu-id="764a6-104">它演示如何使用组件来动态解析终结点的位置、 设置路由的属性，并解决，并执行在消息级别的 Microsoft BizTalk 映射，而无需使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="764a6-104">It demonstrates how you can use the components to dynamically resolve endpoint location, set routing properties, and resolve and execute Microsoft BizTalk maps at the messaging level without using an orchestration.</span></span> <span data-ttu-id="764a6-105">它还演示了单向和双向消息模式。</span><span class="sxs-lookup"><span data-stu-id="764a6-105">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="764a6-106">为获得最佳结果时您熟悉在解决机制[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，应运行[安装和运行解析程序服务示例](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)运行动态解析示例之前。</span><span class="sxs-lookup"><span data-stu-id="764a6-106">For optimum results when familiarizing yourself with the resolution mechanism within the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], you should run the [Installing and Running the Resolver Service Sample](../esb-toolkit/installing-and-running-the-resolver-service-sample.md) before you run the Dynamic Resolution sample.</span></span>  
  
 <span data-ttu-id="764a6-107">示例应用程序包含两个接收位置和两个动态发送端口，此示例使用来演示多个用例的动态解析组件。</span><span class="sxs-lookup"><span data-stu-id="764a6-107">The sample application contains two receive locations and two dynamic send ports, which the sample uses to demonstrate multiple use cases for the dynamic resolution components.</span></span> <span data-ttu-id="764a6-108">每个用例显示了解析程序和适配器中解析的提供程序和适配器提供程序框架中，当结合使用，可以提供各种松耦合的消息传递解决方案的基础。</span><span class="sxs-lookup"><span data-stu-id="764a6-108">Each use case shows how the resolvers and adapter providers in the Resolution and Adapter Provider Framework, when used in combination, can provide the basis for a variety of loosely coupled messaging solutions.</span></span>  
  
## <a name="one-way-messaging-scenarios"></a><span data-ttu-id="764a6-109">单向消息传递方案</span><span class="sxs-lookup"><span data-stu-id="764a6-109">One-Way Messaging Scenarios</span></span>  
 <span data-ttu-id="764a6-110">所有单向消息传送 （除了使用 XPATH 解析程序的一个） 的方案使用文件 NAOrderDoc.xml，位于 \Source\Samples\DynamicResolution\Test\Data 文件夹中，作为输入接收位置名为 DynamicResolution_FILE。</span><span class="sxs-lookup"><span data-stu-id="764a6-110">All one-way messaging scenarios (except the one that uses the XPATH Resolver) use the file NAOrderDoc.xml, located in the \Source\Samples\DynamicResolution\Test\Data folder, as input to the receive location named DynamicResolution_FILE.</span></span> <span data-ttu-id="764a6-111">有七个单向消息传送示例，由唯一绑定表示所有文件，则必须导入才能执行每个示例。</span><span class="sxs-lookup"><span data-stu-id="764a6-111">There are seven one-way messaging examples, all represented by a unique binding file that you must import before you execute each example.</span></span>  
  
## <a name="two-way-messaging-scenarios"></a><span data-ttu-id="764a6-112">双向消息处理方案</span><span class="sxs-lookup"><span data-stu-id="764a6-112">Two-Way Messaging Scenarios</span></span>  
 <span data-ttu-id="764a6-113">所有的双向消息传递方案使用示例 ESB。NorthAmericanServices Web 位于 http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx 以将请求消息发布到 BizTalk 服务。</span><span class="sxs-lookup"><span data-stu-id="764a6-113">All two-way messaging scenarios use the sample ESB.NorthAmericanServices Web service located at http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx to publish the request message into BizTalk.</span></span> <span data-ttu-id="764a6-114">你可以执行此 Web 服务使用 Microsoft InfoPath 或通过从可用 Storm 之类的实用工具[CodePlex](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409))。</span><span class="sxs-lookup"><span data-stu-id="764a6-114">You can execute this Web service using Microsoft InfoPath or through a utility such as the Storm available from [CodePlex](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409)).</span></span>  
  
 <span data-ttu-id="764a6-115">每个示例动态解析要提交到示例 ESB 消息的终结点 URL。位于 http://localhost/ESB.CanadianServices/SubmitPOService.asmx CanadianServices Web 服务。</span><span class="sxs-lookup"><span data-stu-id="764a6-115">Each example dynamically resolves the endpoint URL to submit the message to the sample ESB.CanadianServices Web service located at http://localhost/ESB.CanadianServices/SubmitPOService.asmx.</span></span> <span data-ttu-id="764a6-116">该示例将执行**将订单**操作或**submitPurchase**操作，具体取决于解析过程的结果。</span><span class="sxs-lookup"><span data-stu-id="764a6-116">The example will execute either the **submitOrder** action or the **submitPurchase** action, depending on the results of the resolution process.</span></span> <span data-ttu-id="764a6-117">接收位置为双向消息传递方案是 DynamicResolutionReqResp_SOAP。</span><span class="sxs-lookup"><span data-stu-id="764a6-117">The receive location for two-way messaging scenarios is DynamicResolutionReqResp_SOAP.</span></span> <span data-ttu-id="764a6-118">有 10 双向消息传送示例，由唯一绑定表示所有文件，则必须导入才能执行每个示例。</span><span class="sxs-lookup"><span data-stu-id="764a6-118">There are 10 two-way messaging examples, all represented by a unique binding file that you must import before you execute each example.</span></span>  
  
## <a name="binding-files"></a><span data-ttu-id="764a6-119">绑定文件</span><span class="sxs-lookup"><span data-stu-id="764a6-119">Binding Files</span></span>  
 <span data-ttu-id="764a6-120">此示例的绑定文件位于名为 \Source\Samples\DynamicResolution\Samples\Release 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="764a6-120">The binding files for this sample are located in the folder named \Source\Samples\DynamicResolution\Samples\Release.</span></span>  
  
 <span data-ttu-id="764a6-121">所有绑定文件名称以 GlobalBank.ESB.DynamicResolution_SubmitOrder_To，跟相对值它们应用到的各个示例的开头。</span><span class="sxs-lookup"><span data-stu-id="764a6-121">The binding file names all start with GlobalBank.ESB.DynamicResolution_SubmitOrder_To, followed by an indication of the individual example to which they apply.</span></span> <span data-ttu-id="764a6-122">例如，"文件入站文件出站到使用静态冲突解决程序"示例的绑定文件是 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml。</span><span class="sxs-lookup"><span data-stu-id="764a6-122">For example, the binding file for the "File Inbound to File Outbound using the STATIC Resolver" example is GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml.</span></span>  
  
 <span data-ttu-id="764a6-123">每次你导入到 GlobalBank.ESB BizTalk 应用程序，基础文件接收的绑定之一时将重置示例应用程序中的位置。</span><span class="sxs-lookup"><span data-stu-id="764a6-123">Every time you import one of the binding files into the GlobalBank.ESB BizTalk application, the underlying receive location within the sample application is reset.</span></span> <span data-ttu-id="764a6-124">接收端口名称关联的动态发送端口筛选器。</span><span class="sxs-lookup"><span data-stu-id="764a6-124">The associated dynamic send port filters on the receive port name.</span></span> <span data-ttu-id="764a6-125">因此，若要执行测试，你只需将一个绑定文件，则除去适当地命名的消息导入输入文件夹 （对于单向消息传递方案） 或调用 NorthAmerican Web 服务使用 InfoPath、 在内的 Storm 实用程序或任何其他合适的客户端。</span><span class="sxs-lookup"><span data-stu-id="764a6-125">Therefore, to execute a test, you just import one of the binding files and either drop the appropriately named message into the input folder (for one-way messaging scenarios) or call the NorthAmerican Web service using InfoPath, the Storm utility, or any other suitable client.</span></span>  
  
## <a name="sample-dependencies"></a><span data-ttu-id="764a6-126">示例依赖关系</span><span class="sxs-lookup"><span data-stu-id="764a6-126">Sample Dependencies</span></span>  
 <span data-ttu-id="764a6-127">动态解析示例有大量的作为核心 ESB 安装的一部分的程序集依赖项。</span><span class="sxs-lookup"><span data-stu-id="764a6-127">The Dynamic Resolution sample has dependencies on a number of assemblies that are part of the core ESB installation.</span></span> <span data-ttu-id="764a6-128">这些程序集如下所示：</span><span class="sxs-lookup"><span data-stu-id="764a6-128">These assemblies are the following:</span></span>  
  
-   <span data-ttu-id="764a6-129">**Microsoft.Practices.ESB.PipelineComponents.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-129">**Microsoft.Practices.ESB.PipelineComponents.dll**.</span></span> <span data-ttu-id="764a6-130">这包含 ESB 调度程序管道组件。</span><span class="sxs-lookup"><span data-stu-id="764a6-130">This contains the ESB Dispatcher Pipeline component.</span></span>  
  
-   <span data-ttu-id="764a6-131">**Microsoft.Practices.ESB.Resolver.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-131">**Microsoft.Practices.ESB.Resolver.dll**.</span></span> <span data-ttu-id="764a6-132">这将实现由管道调用冲突解决程序管理器。</span><span class="sxs-lookup"><span data-stu-id="764a6-132">This implements the Resolver Manager called by the pipeline.</span></span>  
  
-   <span data-ttu-id="764a6-133">**Microsoft.Practices.ESB.Resolver.BRE.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-133">**Microsoft.Practices.ESB.Resolver.BRE.dll**.</span></span> <span data-ttu-id="764a6-134">这将会实现此业务规则引擎冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="764a6-134">This implements the Business Rules Engine Resolver.</span></span>  
  
-   <span data-ttu-id="764a6-135">**Microsoft.Practices.ESB.Resolver.STATIC.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-135">**Microsoft.Practices.ESB.Resolver.STATIC.dll**.</span></span> <span data-ttu-id="764a6-136">这将实现静态解析程序。</span><span class="sxs-lookup"><span data-stu-id="764a6-136">This implements the STATIC Resolver.</span></span>  
  
-   <span data-ttu-id="764a6-137">**Microsoft.Practices.ESB.Resolver.UDDI.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-137">**Microsoft.Practices.ESB.Resolver.UDDI.dll**.</span></span> <span data-ttu-id="764a6-138">这将实现 UDDI 解析程序。</span><span class="sxs-lookup"><span data-stu-id="764a6-138">This implements the UDDI Resolver.</span></span>  
  
-   <span data-ttu-id="764a6-139">**Microsoft.Practices.ESB.Resolver.UDDI3.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-139">**Microsoft.Practices.ESB.Resolver.UDDI3.dll**.</span></span> <span data-ttu-id="764a6-140">这将实现 UDDI3 解析程序。</span><span class="sxs-lookup"><span data-stu-id="764a6-140">This implements the UDDI3 Resolver.</span></span>  
  
-   <span data-ttu-id="764a6-141">**Microsoft.Practices.ESB.Resolver.XPATH.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-141">**Microsoft.Practices.ESB.Resolver.XPATH.dll**.</span></span> <span data-ttu-id="764a6-142">这将实现由 XPATH 冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="764a6-142">This implements the XPATH Resolver.</span></span>  
  
-   <span data-ttu-id="764a6-143">**Microsoft.Practices.ESB.Resolver.Schemas.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-143">**Microsoft.Practices.ESB.Resolver.Schemas.dll**.</span></span> <span data-ttu-id="764a6-144">这包含的冲突解决程序架构。</span><span class="sxs-lookup"><span data-stu-id="764a6-144">This contains the resolver schemas.</span></span>  
  
-   <span data-ttu-id="764a6-145">**Microsoft.Practices.ESB.Adapter.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-145">**Microsoft.Practices.ESB.Adapter.dll**.</span></span> <span data-ttu-id="764a6-146">这将实现的适配器管理器。</span><span class="sxs-lookup"><span data-stu-id="764a6-146">This implements the adapter manager.</span></span>  
  
-   <span data-ttu-id="764a6-147">**Microsoft.Practices.ESB.Adapter.FTP.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-147">**Microsoft.Practices.ESB.Adapter.FTP.dll**.</span></span> <span data-ttu-id="764a6-148">这将实现 FTP 适配器提供程序。</span><span class="sxs-lookup"><span data-stu-id="764a6-148">This implements the FTP adapter provider.</span></span>  
  
-   <span data-ttu-id="764a6-149">**Microsoft.Practices.ESB.Adapter.FILE.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-149">**Microsoft.Practices.ESB.Adapter.FILE.dll**.</span></span> <span data-ttu-id="764a6-150">这将实现文件适配器提供程序。</span><span class="sxs-lookup"><span data-stu-id="764a6-150">This implements the FILE adapter provider.</span></span>  
  
-   <span data-ttu-id="764a6-151">**Microsoft.Practices.ESB.Adapter.MQSeries.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-151">**Microsoft.Practices.ESB.Adapter.MQSeries.dll**.</span></span> <span data-ttu-id="764a6-152">这将实现 MQSeries 适配器提供程序。</span><span class="sxs-lookup"><span data-stu-id="764a6-152">This implements the MQSeries adapter provider.</span></span>  
  
-   <span data-ttu-id="764a6-153">**Microsoft.Practices.ESB.Adapter.WcfBasicHttp.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-153">**Microsoft.Practices.ESB.Adapter.WcfBasicHttp.dll**.</span></span> <span data-ttu-id="764a6-154">这将实现 WCF BasicHttp 适配器提供程序。</span><span class="sxs-lookup"><span data-stu-id="764a6-154">This implements the WCF-BasicHttp adapter provider.</span></span>  
  
-   <span data-ttu-id="764a6-155">**Microsoft.Practices.ESB.Adapter.WcfWSHttp.dll**。</span><span class="sxs-lookup"><span data-stu-id="764a6-155">**Microsoft.Practices.ESB.Adapter.WcfWSHttp.dll**.</span></span> <span data-ttu-id="764a6-156">这将实现 WCF WSHttp 适配器提供程序。</span><span class="sxs-lookup"><span data-stu-id="764a6-156">This implements the WCF-WSHttp adapter provider.</span></span>  
  
 <span data-ttu-id="764a6-157">动态解析示例也是依赖于前面的解析程序和适配器的正确配置的。</span><span class="sxs-lookup"><span data-stu-id="764a6-157">The Dynamic Resolution sample is also dependent on correct configuration of the preceding resolvers and adapters.</span></span> <span data-ttu-id="764a6-158">请确保你完成配置这些过程，安装中所述[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="764a6-158">Make sure that you complete the process for configuring these, as described in Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="764a6-159">本节包含下列主题：</span><span class="sxs-lookup"><span data-stu-id="764a6-159">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="764a6-160">安装动态解析示例</span><span class="sxs-lookup"><span data-stu-id="764a6-160">Installing the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="764a6-161">运行动态解析示例</span><span class="sxs-lookup"><span data-stu-id="764a6-161">Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/running-the-dynamic-resolution-sample.md)