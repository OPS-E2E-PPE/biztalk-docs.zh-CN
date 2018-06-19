---
title: 动态解析示例的单向消息传递方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38237840-e957-4298-84c9-700ec72f2bc5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8296c46561a8afa928033ae6002e3de621170234
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296669"
---
# <a name="one-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a><span data-ttu-id="c291f-102">动态解析示例的单向消息传递方案</span><span class="sxs-lookup"><span data-stu-id="c291f-102">One-Way Messaging Scenarios for the Dynamic Resolution Sample</span></span>
<span data-ttu-id="c291f-103">本主题演示如何能够运行的单向消息传递方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态解析示例。</span><span class="sxs-lookup"><span data-stu-id="c291f-103">This topic shows how you can run the one-way messaging scenarios for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Dynamic Resolution sample.</span></span>  
  
 <span data-ttu-id="c291f-104">**若要运行动态解析示例的单向消息传递方案**</span><span class="sxs-lookup"><span data-stu-id="c291f-104">**To run the one-way messaging scenarios for the Dynamic Resolution sample**</span></span>  
  
1.  <span data-ttu-id="c291f-105">首次运行此示例之前，请确保接收位置 URL 指向相应的目录。</span><span class="sxs-lookup"><span data-stu-id="c291f-105">Before you run this sample for the first time, make sure that the receive location URL points to the appropriate directory.</span></span> <span data-ttu-id="c291f-106">指定源子文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\In DynamicResolution_FILE 接收位置。</span><span class="sxs-lookup"><span data-stu-id="c291f-106">Specify the source subfolder \Source\Samples\DynamicResolution\Test\Filedrop\In for the DynamicResolution_FILE receive location.</span></span> <span data-ttu-id="c291f-107">此外，请确保存在名为 DynamicResolutionOneWay 动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="c291f-107">Additionally, make sure that the dynamic send port named DynamicResolutionOneWay exists.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c291f-108">动态解析示例使用动态解决机制将消息发送到输出文件夹，FTP 站点或 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="c291f-108">The Dynamic Resolution sample uses the dynamic resolution mechanism to send messages to the output folder, FTP site, or MQSeries queue.</span></span> <span data-ttu-id="c291f-109">这是此示例未定义静态发送端口的原因。</span><span class="sxs-lookup"><span data-stu-id="c291f-109">This is why a static send port is not defined for this sample.</span></span> <span data-ttu-id="c291f-110">动态解析组件解析检索的输出 URL 和适配器提供程序框架调用 ESBReceiveXml 管道中，在 DynamicResolution_FILE 配置时接收位置。</span><span class="sxs-lookup"><span data-stu-id="c291f-110">The Dynamic Resolution component retrieves the output URL from the Resolution and Adapter Provider Framework when called by the ESBReceiveXml pipeline, which is configured within the DynamicResolution_FILE receive location.</span></span>  
  
2.  <span data-ttu-id="c291f-111">如果 GlobalBank.ESB 应用程序尚未运行，使用 Microsoft BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="c291f-111">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
3.  <span data-ttu-id="c291f-112">决定你想要执行的示例。</span><span class="sxs-lookup"><span data-stu-id="c291f-112">Decide which example you want to execute.</span></span> <span data-ttu-id="c291f-113">所有单向消息传送 （除了使用 XPATH 解析程序的一个） 的示例使用 NAOrderDoc.xml 位于 \Source\Samples\DynamicResolution\Test\Data 的文件夹中的文件输入到名为 DynamicResolution_FILE 接收位置。</span><span class="sxs-lookup"><span data-stu-id="c291f-113">All one-way messaging examples (except the one that uses the XPATH Resolver) use the file NAOrderDoc.xml located in the \Source\Samples\DynamicResolution\Test\Data folder as input to the receive location named DynamicResolution_FILE.</span></span> <span data-ttu-id="c291f-114">有七个单向消息传送示例，每个由唯一绑定文件。</span><span class="sxs-lookup"><span data-stu-id="c291f-114">There are seven one-way messaging examples, each represented by a unique binding file.</span></span> <span data-ttu-id="c291f-115">下表列出了这些示例中，与其关联的绑定文件和说明。</span><span class="sxs-lookup"><span data-stu-id="c291f-115">The following tables list these examples, with their associated binding files and descriptions.</span></span>  
  
    |<span data-ttu-id="c291f-116">文件入站到出站使用静态冲突解决程序的文件</span><span class="sxs-lookup"><span data-stu-id="c291f-116">File Inbound to File Outbound Using the STATIC Resolver</span></span>|  
    |-------------------------------------------------------------|  
    |<span data-ttu-id="c291f-117">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="c291f-117">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="c291f-118">将地图静态处接收端口设置。</span><span class="sxs-lookup"><span data-stu-id="c291f-118">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="c291f-119">终结点解析时，在接收位置使用 ESB 调度程序。</span><span class="sxs-lookup"><span data-stu-id="c291f-119">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    |<span data-ttu-id="c291f-120">文件入站到出站使用 UDDI 冲突解决程序的文件</span><span class="sxs-lookup"><span data-stu-id="c291f-120">File Inbound to File Outbound Using the UDDI Resolver</span></span>|  
    |-----------------------------------------------------------|  
    |<span data-ttu-id="c291f-121">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="c291f-121">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="c291f-122">将地图静态处接收端口设置。</span><span class="sxs-lookup"><span data-stu-id="c291f-122">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="c291f-123">终结点解析时，在接收位置使用 ESB 调度程序。</span><span class="sxs-lookup"><span data-stu-id="c291f-123">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    |<span data-ttu-id="c291f-124">文件入站到出站使用 UDDI 冲突解决程序通过 UDDI 服务密钥的文件</span><span class="sxs-lookup"><span data-stu-id="c291f-124">File Inbound to File Outbound Using UDDI Resolver via UDDI Service Key</span></span>|  
    |----------------------------------------------------------------------------|  
    |<span data-ttu-id="c291f-125">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="c291f-125">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="c291f-126">将地图静态处接收端口设置。</span><span class="sxs-lookup"><span data-stu-id="c291f-126">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="c291f-127">终结点解析时，在接收位置使用 ESB 调度程序。</span><span class="sxs-lookup"><span data-stu-id="c291f-127">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="c291f-128">对于前面的示例中，你必须将绑定文件中的服务密钥更改为一个目标 UDDI 服务器上存在。</span><span class="sxs-lookup"><span data-stu-id="c291f-128">For the preceding example, you must change the service key in the binding file to one that exists on the target UDDI server.</span></span>  
  
    |<span data-ttu-id="c291f-129">文件的入站到 FTP 出站使用静态冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="c291f-129">File Inbound to FTP Outbound Using the STATIC Resolver</span></span>|  
    |------------------------------------------------------------|  
    |<span data-ttu-id="c291f-130">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="c291f-130">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="c291f-131">将地图静态处接收端口设置。</span><span class="sxs-lookup"><span data-stu-id="c291f-131">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="c291f-132">终结点解析时，在接收位置使用 ESB 调度程序。</span><span class="sxs-lookup"><span data-stu-id="c291f-132">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    |<span data-ttu-id="c291f-133">文件的入站到 FTP 出站使用静态解析程序和 ENDPOINTCONFIG 参数</span><span class="sxs-lookup"><span data-stu-id="c291f-133">File Inbound to FTP Outbound Using the STATIC Resolver and ENDPOINTCONFIG Parameter</span></span>|  
    |-----------------------------------------------------------------------------------------|  
    |<span data-ttu-id="c291f-134">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="c291f-134">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="c291f-135">将地图静态处接收端口设置。</span><span class="sxs-lookup"><span data-stu-id="c291f-135">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="c291f-136">终结点解析时，在接收位置使用 ESB 调度程序。</span><span class="sxs-lookup"><span data-stu-id="c291f-136">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
    |<span data-ttu-id="c291f-137">将传递要设置的适配器提供程序的其他名称/值对。</span><span class="sxs-lookup"><span data-stu-id="c291f-137">Passes additional name/values pairs for the adapter provider to set.</span></span>|  
  
    |<span data-ttu-id="c291f-138">文件的入站到 MQS 出站使用静态冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="c291f-138">File Inbound to MQS Outbound Using the STATIC Resolver</span></span>|  
    |------------------------------------------------------------|  
    |<span data-ttu-id="c291f-139">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="c291f-139">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="c291f-140">将地图静态处接收端口设置。</span><span class="sxs-lookup"><span data-stu-id="c291f-140">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="c291f-141">终结点解析时，在接收位置使用 ESB 调度程序。</span><span class="sxs-lookup"><span data-stu-id="c291f-141">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    |<span data-ttu-id="c291f-142">文件入站到出站使用 XPATH 冲突解决程序的文件</span><span class="sxs-lookup"><span data-stu-id="c291f-142">File Inbound to FILE Outbound Using the XPATH Resolver</span></span>|  
    |------------------------------------------------------------|  
    |<span data-ttu-id="c291f-143">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="c291f-143">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="c291f-144">将地图静态处接收端口设置。</span><span class="sxs-lookup"><span data-stu-id="c291f-144">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="c291f-145">终结点解析时，在接收位置使用 ESB 调度程序。</span><span class="sxs-lookup"><span data-stu-id="c291f-145">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
    |<span data-ttu-id="c291f-146">使用消息中的信息来确定相应的终结点。</span><span class="sxs-lookup"><span data-stu-id="c291f-146">Uses information within the message to determine the appropriate endpoint.</span></span> <span data-ttu-id="c291f-147">你可以使用此示例中的测试文件是 NAOrderDoc_XPATH_FILE.xml、 NAOrderDoc_XPATH_FTP.xml 和 NAOrderDoc_XPATH_MQS.xml。</span><span class="sxs-lookup"><span data-stu-id="c291f-147">The test files you can use with this example are NAOrderDoc_XPATH_FILE.xml, NAOrderDoc_XPATH_FTP.xml, and NAOrderDoc_XPATH_MQS.xml.</span></span>|  
  
4.  <span data-ttu-id="c291f-148">导入你想要执行到 GlobalBank.ESB 应用程序的消息传送示例的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="c291f-148">Import the binding file for the messaging example you want to execute into the GlobalBank.ESB application.</span></span>  
  
5.  <span data-ttu-id="c291f-149">在 Windows 资源管理器，打开文件夹 \Source\Samples\DynamicResolution\Test\Data，并将相应的输入的文件复制到文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\In。</span><span class="sxs-lookup"><span data-stu-id="c291f-149">In Windows Explorer, open the folder \Source\Samples\DynamicResolution\Test\Data and copy the appropriate input file into the folder \Source\Samples\DynamicResolution\Test\Filedrop\In.</span></span> <span data-ttu-id="c291f-150">你使用的文件取决于您决定要执行的示例：</span><span class="sxs-lookup"><span data-stu-id="c291f-150">The file you use depends on the example you decided to execute:</span></span>  
  
    -   <span data-ttu-id="c291f-151">对于 XPATH 示例中，使用以下文件之一： NAOrderDoc_XPATH_FILE.xml、 NAOrderDoc_XPATH_FTP.xml 或 NAOrderDoc_XPATH_MQS.xml。</span><span class="sxs-lookup"><span data-stu-id="c291f-151">For the XPATH example, use one of the following files: NAOrderDoc_XPATH_FILE.xml, NAOrderDoc_XPATH_FTP.xml, or NAOrderDoc_XPATH_MQS.xml.</span></span>  
  
    -   <span data-ttu-id="c291f-152">对于所有其他示例，请使用文件 NAOrderDoc.xml。</span><span class="sxs-lookup"><span data-stu-id="c291f-152">For all other examples, use the file NAOrderDoc.xml.</span></span>  
  
6.  <span data-ttu-id="c291f-153">查看已发送邮件的适当位置。</span><span class="sxs-lookup"><span data-stu-id="c291f-153">Look in the appropriate location for the delivered message.</span></span> <span data-ttu-id="c291f-154">位置取决于你使用的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="c291f-154">The location depends on the binding file you used.</span></span> <span data-ttu-id="c291f-155">示例如下：</span><span class="sxs-lookup"><span data-stu-id="c291f-155">The following are examples:</span></span>  
  
    -   <span data-ttu-id="c291f-156">与 FTP 出站示例的文件入站消息传送到名为 Out 的 FTP 虚拟目录创建时安装示例。</span><span class="sxs-lookup"><span data-stu-id="c291f-156">The File Inbound to FTP Outbound example delivers the message to the FTP virtual directory named Out that you created when you installed the sample.</span></span>  
  
    -   <span data-ttu-id="c291f-157">与出站文件示例的文件入站消息传送至 \DynamicResolution\Test\Filedrop\Out 子文件夹。</span><span class="sxs-lookup"><span data-stu-id="c291f-157">The File Inbound to FILE Outbound example delivers the message to the \DynamicResolution\Test\Filedrop\Out subfolder.</span></span>  
  
    -   <span data-ttu-id="c291f-158">与出站 MQS 示例的文件入站消息传送到测试。OUT 时创建的队列安装示例。</span><span class="sxs-lookup"><span data-stu-id="c291f-158">The File Inbound to MQS Outbound example delivers the message to the TEST.OUT queue that you created when you installed the sample.</span></span>  
  
    -   <span data-ttu-id="c291f-159">为文件出站使用 XPATH Resolver 示例的文件入站将邮件传递到消息中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="c291f-159">The File Inbound to FILE Outbound using the XPATH Resolver example delivers the message to the location specified in the message.</span></span> <span data-ttu-id="c291f-160">示例文档包含的目标位置和传输类型 （传输类型追加到消息文件的扩展名; 例如，NAOrderDoc_XPATH_FTP.xml 消息包含 FTP 传输类型规范）。</span><span class="sxs-lookup"><span data-stu-id="c291f-160">The sample documents contain the destination location and transport type (the transport type is appended to the message file name; for example, the NAOrderDoc_XPATH_FTP.xml message contains the FTP transport type specification).</span></span>  
  
 <span data-ttu-id="c291f-161">若要了解该示例的 ESB 调度程序和 ESB 调度程序反汇编程序管道组件的使用，请参阅[动态解析示例的工作原理](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)。</span><span class="sxs-lookup"><span data-stu-id="c291f-161">To understand how the sample uses the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components, see [How the Dynamic Resolution Sample Works](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span></span>