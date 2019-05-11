---
title: 动态解析示例的单向消息传送方案 |Microsoft Docs
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
ms.openlocfilehash: ad8fe10f3da18822e722c57159fd9707de5ced8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400066"
---
# <a name="one-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a><span data-ttu-id="eac75-102">动态解析示例的单向消息传送方案</span><span class="sxs-lookup"><span data-stu-id="eac75-102">One-Way Messaging Scenarios for the Dynamic Resolution Sample</span></span>
<span data-ttu-id="eac75-103">本主题演示如何运行的单向消息传送方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态解析示例。</span><span class="sxs-lookup"><span data-stu-id="eac75-103">This topic shows how you can run the one-way messaging scenarios for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Dynamic Resolution sample.</span></span>  

 <span data-ttu-id="eac75-104">**若要运行动态解析示例的单向消息传送方案**</span><span class="sxs-lookup"><span data-stu-id="eac75-104">**To run the one-way messaging scenarios for the Dynamic Resolution sample**</span></span>  

1. <span data-ttu-id="eac75-105">第一次运行此示例之前，请确保接收位置 URL 指向相应的目录。</span><span class="sxs-lookup"><span data-stu-id="eac75-105">Before you run this sample for the first time, make sure that the receive location URL points to the appropriate directory.</span></span> <span data-ttu-id="eac75-106">指定源的子文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\In DynamicResolution_FILE 接收位置。</span><span class="sxs-lookup"><span data-stu-id="eac75-106">Specify the source subfolder \Source\Samples\DynamicResolution\Test\Filedrop\In for the DynamicResolution_FILE receive location.</span></span> <span data-ttu-id="eac75-107">此外，请确保存在名为 DynamicResolutionOneWay 的动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="eac75-107">Additionally, make sure that the dynamic send port named DynamicResolutionOneWay exists.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="eac75-108">动态解析示例使用动态解析机制将消息发送到输出文件夹、 FTP 站点或 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="eac75-108">The Dynamic Resolution sample uses the dynamic resolution mechanism to send messages to the output folder, FTP site, or MQSeries queue.</span></span> <span data-ttu-id="eac75-109">这就是原因本示例未定义静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="eac75-109">This is why a static send port is not defined for this sample.</span></span> <span data-ttu-id="eac75-110">动态解析组件解决方法从检索输出 URL 和适配器提供程序框架时调用的 ESBReceiveXml 管道，在 DynamicResolution_FILE 中配置接收位置。</span><span class="sxs-lookup"><span data-stu-id="eac75-110">The Dynamic Resolution component retrieves the output URL from the Resolution and Adapter Provider Framework when called by the ESBReceiveXml pipeline, which is configured within the DynamicResolution_FILE receive location.</span></span>  

2. <span data-ttu-id="eac75-111">如果尚未运行 GlobalBank.ESB 应用程序，使用 Microsoft BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="eac75-111">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  

3. <span data-ttu-id="eac75-112">决定你想要执行的示例。</span><span class="sxs-lookup"><span data-stu-id="eac75-112">Decide which example you want to execute.</span></span> <span data-ttu-id="eac75-113">所有单向消息传送 （只使用 XPATH 解析程序） 的示例使用 NAOrderDoc.xml \Source\Samples\DynamicResolution\Test\Data 的文件夹中的文件输入到名为 DynamicResolution_FILE 接收位置。</span><span class="sxs-lookup"><span data-stu-id="eac75-113">All one-way messaging examples (except the one that uses the XPATH Resolver) use the file NAOrderDoc.xml located in the \Source\Samples\DynamicResolution\Test\Data folder as input to the receive location named DynamicResolution_FILE.</span></span> <span data-ttu-id="eac75-114">有七个单向消息传送示例，每个唯一绑定文件表示。</span><span class="sxs-lookup"><span data-stu-id="eac75-114">There are seven one-way messaging examples, each represented by a unique binding file.</span></span> <span data-ttu-id="eac75-115">下表列出了这些示例中，使用其关联的绑定文件和说明。</span><span class="sxs-lookup"><span data-stu-id="eac75-115">The following tables list these examples, with their associated binding files and descriptions.</span></span>  

   |<span data-ttu-id="eac75-116">文件的入站到出站使用静态的冲突解决程序的文件</span><span class="sxs-lookup"><span data-stu-id="eac75-116">File Inbound to File Outbound Using the STATIC Resolver</span></span>|  
   |-------------------------------------------------------------|  
   |<span data-ttu-id="eac75-117">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="eac75-117">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="eac75-118">在接收端口以静态方式设置这些映射。</span><span class="sxs-lookup"><span data-stu-id="eac75-118">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="eac75-119">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="eac75-119">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   |<span data-ttu-id="eac75-120">文件的入站到出站使用 UDDI 解析程序的文件</span><span class="sxs-lookup"><span data-stu-id="eac75-120">File Inbound to File Outbound Using the UDDI Resolver</span></span>|  
   |-----------------------------------------------------------|  
   |<span data-ttu-id="eac75-121">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="eac75-121">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="eac75-122">在接收端口以静态方式设置这些映射。</span><span class="sxs-lookup"><span data-stu-id="eac75-122">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="eac75-123">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="eac75-123">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   |<span data-ttu-id="eac75-124">文件的入站到出站使用 UDDI 服务密钥通过 UDDI 解析程序的文件</span><span class="sxs-lookup"><span data-stu-id="eac75-124">File Inbound to File Outbound Using UDDI Resolver via UDDI Service Key</span></span>|  
   |----------------------------------------------------------------------------|  
   |<span data-ttu-id="eac75-125">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="eac75-125">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="eac75-126">在接收端口以静态方式设置这些映射。</span><span class="sxs-lookup"><span data-stu-id="eac75-126">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="eac75-127">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="eac75-127">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   > [!NOTE]
   >  <span data-ttu-id="eac75-128">对于上述示例中，必须更改绑定文件中的服务密钥为其中一个目标 UDDI 服务器上存在。</span><span class="sxs-lookup"><span data-stu-id="eac75-128">For the preceding example, you must change the service key in the binding file to one that exists on the target UDDI server.</span></span>  

   |<span data-ttu-id="eac75-129">文件的入站到 FTP 出站使用静态的冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="eac75-129">File Inbound to FTP Outbound Using the STATIC Resolver</span></span>|  
   |------------------------------------------------------------|  
   |<span data-ttu-id="eac75-130">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="eac75-130">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="eac75-131">在接收端口以静态方式设置这些映射。</span><span class="sxs-lookup"><span data-stu-id="eac75-131">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="eac75-132">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="eac75-132">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   |<span data-ttu-id="eac75-133">文件的入站到 FTP 出站使用静态解析程序和 ENDPOINTCONFIG 参数</span><span class="sxs-lookup"><span data-stu-id="eac75-133">File Inbound to FTP Outbound Using the STATIC Resolver and ENDPOINTCONFIG Parameter</span></span>|  
   |-----------------------------------------------------------------------------------------|  
   |<span data-ttu-id="eac75-134">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="eac75-134">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="eac75-135">在接收端口以静态方式设置这些映射。</span><span class="sxs-lookup"><span data-stu-id="eac75-135">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="eac75-136">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="eac75-136">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
   |<span data-ttu-id="eac75-137">将传递的其他名称/值对的适配器提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="eac75-137">Passes additional name/values pairs for the adapter provider to set.</span></span>|  

   |<span data-ttu-id="eac75-138">文件的入站到 MQS 出站使用静态的冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="eac75-138">File Inbound to MQS Outbound Using the STATIC Resolver</span></span>|  
   |------------------------------------------------------------|  
   |<span data-ttu-id="eac75-139">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="eac75-139">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="eac75-140">在接收端口以静态方式设置这些映射。</span><span class="sxs-lookup"><span data-stu-id="eac75-140">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="eac75-141">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="eac75-141">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   |                                                                             <span data-ttu-id="eac75-142">文件的入站到出站使用 XPATH 冲突解决程序的文件</span><span class="sxs-lookup"><span data-stu-id="eac75-142">File Inbound to FILE Outbound Using the XPATH Resolver</span></span>                                                                             |
   |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                        <span data-ttu-id="eac75-143">使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。</span><span class="sxs-lookup"><span data-stu-id="eac75-143">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>                        |
   |                                                                                 <span data-ttu-id="eac75-144">在接收端口以静态方式设置这些映射。</span><span class="sxs-lookup"><span data-stu-id="eac75-144">Sets the maps statically at the receive port.</span></span>                                                                                  |
   |                                                                    <span data-ttu-id="eac75-145">使用 ESB 调度程序在接收位置的终结点解析。</span><span class="sxs-lookup"><span data-stu-id="eac75-145">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>                                                                    |
   | <span data-ttu-id="eac75-146">使用消息中的信息来确定适当的终结点。</span><span class="sxs-lookup"><span data-stu-id="eac75-146">Uses information within the message to determine the appropriate endpoint.</span></span> <span data-ttu-id="eac75-147">可以使用此示例中使用的测试文件是 NAOrderDoc_XPATH_FILE.xml、 NAOrderDoc_XPATH_FTP.xml 和 NAOrderDoc_XPATH_MQS.xml。</span><span class="sxs-lookup"><span data-stu-id="eac75-147">The test files you can use with this example are NAOrderDoc_XPATH_FILE.xml, NAOrderDoc_XPATH_FTP.xml, and NAOrderDoc_XPATH_MQS.xml.</span></span> |


4. <span data-ttu-id="eac75-148">导入绑定文件对于您要执行到 GlobalBank.ESB 应用程序的消息传送示例。</span><span class="sxs-lookup"><span data-stu-id="eac75-148">Import the binding file for the messaging example you want to execute into the GlobalBank.ESB application.</span></span>  

5. <span data-ttu-id="eac75-149">在 Windows 资源管理器，打开文件夹 \Source\Samples\DynamicResolution\Test\Data 并将相应的输入的文件复制到文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\In。</span><span class="sxs-lookup"><span data-stu-id="eac75-149">In Windows Explorer, open the folder \Source\Samples\DynamicResolution\Test\Data and copy the appropriate input file into the folder \Source\Samples\DynamicResolution\Test\Filedrop\In.</span></span> <span data-ttu-id="eac75-150">使用的文件取决于您决定要执行的示例：</span><span class="sxs-lookup"><span data-stu-id="eac75-150">The file you use depends on the example you decided to execute:</span></span>  

   -   <span data-ttu-id="eac75-151">有关 XPATH 的示例中，使用以下文件之一：NAOrderDoc_XPATH_FILE.xml、 NAOrderDoc_XPATH_FTP.xml 或 NAOrderDoc_XPATH_MQS.xml。</span><span class="sxs-lookup"><span data-stu-id="eac75-151">For the XPATH example, use one of the following files: NAOrderDoc_XPATH_FILE.xml, NAOrderDoc_XPATH_FTP.xml, or NAOrderDoc_XPATH_MQS.xml.</span></span>  

   -   <span data-ttu-id="eac75-152">对于所有其他示例，请使用文件 NAOrderDoc.xml。</span><span class="sxs-lookup"><span data-stu-id="eac75-152">For all other examples, use the file NAOrderDoc.xml.</span></span>  

6. <span data-ttu-id="eac75-153">查看已发送邮件的适当位置。</span><span class="sxs-lookup"><span data-stu-id="eac75-153">Look in the appropriate location for the delivered message.</span></span> <span data-ttu-id="eac75-154">位置取决于您使用的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="eac75-154">The location depends on the binding file you used.</span></span> <span data-ttu-id="eac75-155">示例如下：</span><span class="sxs-lookup"><span data-stu-id="eac75-155">The following are examples:</span></span>  

   -   <span data-ttu-id="eac75-156">文件的入站与出站 FTP 示例的消息传递到名为 Out 的 FTP 虚拟目录创建时安装示例。</span><span class="sxs-lookup"><span data-stu-id="eac75-156">The File Inbound to FTP Outbound example delivers the message to the FTP virtual directory named Out that you created when you installed the sample.</span></span>  

   -   <span data-ttu-id="eac75-157">文件的入站与出站文件示例的消息传递到 \DynamicResolution\Test\Filedrop\Out 子文件夹。</span><span class="sxs-lookup"><span data-stu-id="eac75-157">The File Inbound to FILE Outbound example delivers the message to the \DynamicResolution\Test\Filedrop\Out subfolder.</span></span>  

   -   <span data-ttu-id="eac75-158">文件的入站与出站 MQS 示例的消息传递到测试。队列时创建出安装示例。</span><span class="sxs-lookup"><span data-stu-id="eac75-158">The File Inbound to MQS Outbound example delivers the message to the TEST.OUT queue that you created when you installed the sample.</span></span>  

   -   <span data-ttu-id="eac75-159">对文件出使用 XPATH 冲突解决程序示例的文件入站的消息传递到消息中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="eac75-159">The File Inbound to FILE Outbound using the XPATH Resolver example delivers the message to the location specified in the message.</span></span> <span data-ttu-id="eac75-160">示例文档包含目标位置和传输类型 （传输类型附加到消息文件名称; 例如，NAOrderDoc_XPATH_FTP.xml 消息包含 FTP 传输类型规范）。</span><span class="sxs-lookup"><span data-stu-id="eac75-160">The sample documents contain the destination location and transport type (the transport type is appended to the message file name; for example, the NAOrderDoc_XPATH_FTP.xml message contains the FTP transport type specification).</span></span>  

   <span data-ttu-id="eac75-161">若要了解此示例如何使用 ESB 调度程序和 ESB 调度程序反汇编程序管道组件，请参阅[动态解析示例的工作原理](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)。</span><span class="sxs-lookup"><span data-stu-id="eac75-161">To understand how the sample uses the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components, see [How the Dynamic Resolution Sample Works](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span></span>