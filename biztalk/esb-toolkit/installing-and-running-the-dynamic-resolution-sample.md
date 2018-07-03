---
title: 安装和运行动态解析示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4359987-b18c-44f5-a2cf-e30e17ac5e9f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0939111bc0a62ecf31286045f412ed160a97c3f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967726"
---
# <a name="installing-and-running-the-dynamic-resolution-sample"></a><span data-ttu-id="d9bef-102">安装和运行动态解析示例</span><span class="sxs-lookup"><span data-stu-id="d9bef-102">Installing and Running the Dynamic Resolution Sample</span></span>
<span data-ttu-id="d9bef-103">动态解析示例演示了用于 ESB 调度程序和 ESB 调度程序反汇编程序管道组件的典型使用方案。</span><span class="sxs-lookup"><span data-stu-id="d9bef-103">The Dynamic Resolution sample demonstrates typical usage scenarios for the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components.</span></span> <span data-ttu-id="d9bef-104">它演示了如何使用组件动态解析终结点位置、 设置路由属性和解析和执行而无需使用业务流程在消息级别的 Microsoft BizTalk 映射。</span><span class="sxs-lookup"><span data-stu-id="d9bef-104">It demonstrates how you can use the components to dynamically resolve endpoint location, set routing properties, and resolve and execute Microsoft BizTalk maps at the messaging level without using an orchestration.</span></span> <span data-ttu-id="d9bef-105">它还演示了单向和双向消息传送模式。</span><span class="sxs-lookup"><span data-stu-id="d9bef-105">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9bef-106">获得最佳结果，在您熟悉内解决机制[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，则应运行[安装和运行解析程序服务示例](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)运行动态解析示例之前。</span><span class="sxs-lookup"><span data-stu-id="d9bef-106">For optimum results when familiarizing yourself with the resolution mechanism within the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], you should run the [Installing and Running the Resolver Service Sample](../esb-toolkit/installing-and-running-the-resolver-service-sample.md) before you run the Dynamic Resolution sample.</span></span>  
  
 <span data-ttu-id="d9bef-107">示例应用程序包含两个接收位置和两个动态发送端口，该示例使用演示多个用例的动态解析组件。</span><span class="sxs-lookup"><span data-stu-id="d9bef-107">The sample application contains two receive locations and two dynamic send ports, which the sample uses to demonstrate multiple use cases for the dynamic resolution components.</span></span> <span data-ttu-id="d9bef-108">每个用例显示了冲突解决程序和适配器提供程序中解析和适配器提供程序框架，在组合中，使用时如何提供各种松散耦合的消息传送解决方案的基础。</span><span class="sxs-lookup"><span data-stu-id="d9bef-108">Each use case shows how the resolvers and adapter providers in the Resolution and Adapter Provider Framework, when used in combination, can provide the basis for a variety of loosely coupled messaging solutions.</span></span>  
  
## <a name="one-way-messaging-scenarios"></a><span data-ttu-id="d9bef-109">单向消息传送方案</span><span class="sxs-lookup"><span data-stu-id="d9bef-109">One-Way Messaging Scenarios</span></span>  
 <span data-ttu-id="d9bef-110">所有单向消息传送方案 （只使用 XPATH 解析程序） 使用 \Source\Samples\DynamicResolution\Test\Data 文件夹中的文件 NAOrderDoc.xml，作为输入接收位置名为 DynamicResolution_FILE。</span><span class="sxs-lookup"><span data-stu-id="d9bef-110">All one-way messaging scenarios (except the one that uses the XPATH Resolver) use the file NAOrderDoc.xml, located in the \Source\Samples\DynamicResolution\Test\Data folder, as input to the receive location named DynamicResolution_FILE.</span></span> <span data-ttu-id="d9bef-111">有七个单向消息传送示例中，所有由唯一绑定文件，您必须导入之前执行的每个示例。</span><span class="sxs-lookup"><span data-stu-id="d9bef-111">There are seven one-way messaging examples, all represented by a unique binding file that you must import before you execute each example.</span></span>  
  
## <a name="two-way-messaging-scenarios"></a><span data-ttu-id="d9bef-112">双向消息传送方案</span><span class="sxs-lookup"><span data-stu-id="d9bef-112">Two-Way Messaging Scenarios</span></span>  
 <span data-ttu-id="d9bef-113">所有的双向消息传送方案使用 ESB 的示例。NorthAmericanServices Web 服务位于http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx以将请求消息发布到 BizTalk。</span><span class="sxs-lookup"><span data-stu-id="d9bef-113">All two-way messaging scenarios use the sample ESB.NorthAmericanServices Web service located at http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx to publish the request message into BizTalk.</span></span> <span data-ttu-id="d9bef-114">您可以使用 Microsoft InfoPath 此 Web 服务或通过可从 Storm 之类的实用工具[CodePlex](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="d9bef-114">You can execute this Web service using Microsoft InfoPath or through a utility such as the Storm available from [CodePlex](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409).</span></span>  
  
 <span data-ttu-id="d9bef-115">每个示例动态解析终结点 URL，以便提交到 ESB 的示例消息。CanadianServices Web 服务位于http://localhost/ESB.CanadianServices/SubmitPOService.asmx。</span><span class="sxs-lookup"><span data-stu-id="d9bef-115">Each example dynamically resolves the endpoint URL to submit the message to the sample ESB.CanadianServices Web service located at http://localhost/ESB.CanadianServices/SubmitPOService.asmx.</span></span> <span data-ttu-id="d9bef-116">该示例将执行**submitOrder**操作或**submitPurchase**操作，具体取决于解析过程的结果。</span><span class="sxs-lookup"><span data-stu-id="d9bef-116">The example will execute either the **submitOrder** action or the **submitPurchase** action, depending on the results of the resolution process.</span></span> <span data-ttu-id="d9bef-117">双向消息传送方案的接收位置是 DynamicResolutionReqResp_SOAP。</span><span class="sxs-lookup"><span data-stu-id="d9bef-117">The receive location for two-way messaging scenarios is DynamicResolutionReqResp_SOAP.</span></span> <span data-ttu-id="d9bef-118">有 10 个双向消息传送示例中，所有由唯一绑定文件，您必须导入之前执行的每个示例。</span><span class="sxs-lookup"><span data-stu-id="d9bef-118">There are 10 two-way messaging examples, all represented by a unique binding file that you must import before you execute each example.</span></span>  
  
## <a name="binding-files"></a><span data-ttu-id="d9bef-119">绑定文件</span><span class="sxs-lookup"><span data-stu-id="d9bef-119">Binding Files</span></span>  
 <span data-ttu-id="d9bef-120">此示例的绑定文件位于名为 \Source\Samples\DynamicResolution\Samples\Release 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d9bef-120">The binding files for this sample are located in the folder named \Source\Samples\DynamicResolution\Samples\Release.</span></span>  
  
 <span data-ttu-id="d9bef-121">所有启动 GlobalBank.ESB.DynamicResolution_SubmitOrder_To，跟相对值的指示它们适用于各个示例使用绑定文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d9bef-121">The binding file names all start with GlobalBank.ESB.DynamicResolution_SubmitOrder_To, followed by an indication of the individual example to which they apply.</span></span> <span data-ttu-id="d9bef-122">例如，"文件入站文件的出站到使用静态的冲突解决程序"示例的绑定文件是 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml。</span><span class="sxs-lookup"><span data-stu-id="d9bef-122">For example, the binding file for the "File Inbound to File Outbound using the STATIC Resolver" example is GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml.</span></span>  
  
 <span data-ttu-id="d9bef-123">每次导入一个绑定接收到 GlobalBank.ESB BizTalk 应用程序，基础文件中的示例应用程序的位置重置。</span><span class="sxs-lookup"><span data-stu-id="d9bef-123">Every time you import one of the binding files into the GlobalBank.ESB BizTalk application, the underlying receive location within the sample application is reset.</span></span> <span data-ttu-id="d9bef-124">接收端口名称相关的动态发送端口筛选器。</span><span class="sxs-lookup"><span data-stu-id="d9bef-124">The associated dynamic send port filters on the receive port name.</span></span> <span data-ttu-id="d9bef-125">因此，若要执行测试，您只需导入一个绑定文件，则除去适当命名的消息到输入文件夹 （适用于单向消息传送方案） 或调用使用 InfoPath、 Storm 实用程序，或任何其他的 NorthAmerican Web 服务合适的客户端。</span><span class="sxs-lookup"><span data-stu-id="d9bef-125">Therefore, to execute a test, you just import one of the binding files and either drop the appropriately named message into the input folder (for one-way messaging scenarios) or call the NorthAmerican Web service using InfoPath, the Storm utility, or any other suitable client.</span></span>  
  
## <a name="sample-dependencies"></a><span data-ttu-id="d9bef-126">示例依赖关系</span><span class="sxs-lookup"><span data-stu-id="d9bef-126">Sample Dependencies</span></span>  
 <span data-ttu-id="d9bef-127">动态解析示例数是核心 ESB 安装的一部分的程序集具有依赖关系。</span><span class="sxs-lookup"><span data-stu-id="d9bef-127">The Dynamic Resolution sample has dependencies on a number of assemblies that are part of the core ESB installation.</span></span> <span data-ttu-id="d9bef-128">这些程序集如下所示：</span><span class="sxs-lookup"><span data-stu-id="d9bef-128">These assemblies are the following:</span></span>  
  
- <span data-ttu-id="d9bef-129">**Microsoft.Practices.ESB.PipelineComponents.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-129">**Microsoft.Practices.ESB.PipelineComponents.dll**.</span></span> <span data-ttu-id="d9bef-130">这包含 ESB 调度程序管道组件。</span><span class="sxs-lookup"><span data-stu-id="d9bef-130">This contains the ESB Dispatcher Pipeline component.</span></span>  
  
- <span data-ttu-id="d9bef-131">**Microsoft.Practices.ESB.Resolver.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-131">**Microsoft.Practices.ESB.Resolver.dll**.</span></span> <span data-ttu-id="d9bef-132">这会实现调用管道的解析程序管理器。</span><span class="sxs-lookup"><span data-stu-id="d9bef-132">This implements the Resolver Manager called by the pipeline.</span></span>  
  
- <span data-ttu-id="d9bef-133">**Microsoft.Practices.ESB.Resolver.BRE.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-133">**Microsoft.Practices.ESB.Resolver.BRE.dll**.</span></span> <span data-ttu-id="d9bef-134">这会实现业务规则引擎冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="d9bef-134">This implements the Business Rules Engine Resolver.</span></span>  
  
- <span data-ttu-id="d9bef-135">**Microsoft.Practices.ESB.Resolver.STATIC.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-135">**Microsoft.Practices.ESB.Resolver.STATIC.dll**.</span></span> <span data-ttu-id="d9bef-136">这会实现静态冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="d9bef-136">This implements the STATIC Resolver.</span></span>  
  
- <span data-ttu-id="d9bef-137">**Microsoft.Practices.ESB.Resolver.UDDI.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-137">**Microsoft.Practices.ESB.Resolver.UDDI.dll**.</span></span> <span data-ttu-id="d9bef-138">这会实现 UDDI 解析程序。</span><span class="sxs-lookup"><span data-stu-id="d9bef-138">This implements the UDDI Resolver.</span></span>  
  
- <span data-ttu-id="d9bef-139">**Microsoft.Practices.ESB.Resolver.UDDI3.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-139">**Microsoft.Practices.ESB.Resolver.UDDI3.dll**.</span></span> <span data-ttu-id="d9bef-140">这会实现 UDDI3 冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="d9bef-140">This implements the UDDI3 Resolver.</span></span>  
  
- <span data-ttu-id="d9bef-141">**Microsoft.Practices.ESB.Resolver.XPATH.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-141">**Microsoft.Practices.ESB.Resolver.XPATH.dll**.</span></span> <span data-ttu-id="d9bef-142">这会实现 XPATH 冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="d9bef-142">This implements the XPATH Resolver.</span></span>  
  
- <span data-ttu-id="d9bef-143">**Microsoft.Practices.ESB.Resolver.Schemas.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-143">**Microsoft.Practices.ESB.Resolver.Schemas.dll**.</span></span> <span data-ttu-id="d9bef-144">这包含冲突解决程序架构。</span><span class="sxs-lookup"><span data-stu-id="d9bef-144">This contains the resolver schemas.</span></span>  
  
- <span data-ttu-id="d9bef-145">**Microsoft.Practices.ESB.Adapter.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-145">**Microsoft.Practices.ESB.Adapter.dll**.</span></span> <span data-ttu-id="d9bef-146">这会实现适配器管理器。</span><span class="sxs-lookup"><span data-stu-id="d9bef-146">This implements the adapter manager.</span></span>  
  
- <span data-ttu-id="d9bef-147">**Microsoft.Practices.ESB.Adapter.FTP.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-147">**Microsoft.Practices.ESB.Adapter.FTP.dll**.</span></span> <span data-ttu-id="d9bef-148">这会实现 FTP 适配器提供程序。</span><span class="sxs-lookup"><span data-stu-id="d9bef-148">This implements the FTP adapter provider.</span></span>  
  
- <span data-ttu-id="d9bef-149">**Microsoft.Practices.ESB.Adapter.FILE.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-149">**Microsoft.Practices.ESB.Adapter.FILE.dll**.</span></span> <span data-ttu-id="d9bef-150">这会实现文件适配器提供程序。</span><span class="sxs-lookup"><span data-stu-id="d9bef-150">This implements the FILE adapter provider.</span></span>  
  
- <span data-ttu-id="d9bef-151">**Microsoft.Practices.ESB.Adapter.MQSeries.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-151">**Microsoft.Practices.ESB.Adapter.MQSeries.dll**.</span></span> <span data-ttu-id="d9bef-152">这会实现 MQSeries 适配器提供程序。</span><span class="sxs-lookup"><span data-stu-id="d9bef-152">This implements the MQSeries adapter provider.</span></span>  
  
- <span data-ttu-id="d9bef-153">**Microsoft.Practices.ESB.Adapter.WcfBasicHttp.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-153">**Microsoft.Practices.ESB.Adapter.WcfBasicHttp.dll**.</span></span> <span data-ttu-id="d9bef-154">这将实现 WCF BasicHttp 适配器提供程序。</span><span class="sxs-lookup"><span data-stu-id="d9bef-154">This implements the WCF-BasicHttp adapter provider.</span></span>  
  
- <span data-ttu-id="d9bef-155">**Microsoft.Practices.ESB.Adapter.WcfWSHttp.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9bef-155">**Microsoft.Practices.ESB.Adapter.WcfWSHttp.dll**.</span></span> <span data-ttu-id="d9bef-156">这会实现 Wcf-wshttp 适配器提供程序。</span><span class="sxs-lookup"><span data-stu-id="d9bef-156">This implements the WCF-WSHttp adapter provider.</span></span>  
  
  <span data-ttu-id="d9bef-157">动态解析示例也是依赖于前面的冲突解决程序和适配器的正确配置。</span><span class="sxs-lookup"><span data-stu-id="d9bef-157">The Dynamic Resolution sample is also dependent on correct configuration of the preceding resolvers and adapters.</span></span> <span data-ttu-id="d9bef-158">请确保安装中所述完成配置，这些过程[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d9bef-158">Make sure that you complete the process for configuring these, as described in Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
  <span data-ttu-id="d9bef-159">本节包含下列主题：</span><span class="sxs-lookup"><span data-stu-id="d9bef-159">This section contains the following topics:</span></span>  
  
- [<span data-ttu-id="d9bef-160">安装动态解析示例</span><span class="sxs-lookup"><span data-stu-id="d9bef-160">Installing the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-the-dynamic-resolution-sample.md)  
  
- [<span data-ttu-id="d9bef-161">运行动态解析示例</span><span class="sxs-lookup"><span data-stu-id="d9bef-161">Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/running-the-dynamic-resolution-sample.md)
