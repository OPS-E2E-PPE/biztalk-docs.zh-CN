---
title: HelloWorld （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, messages
ms.assetid: 4416029a-ca76-45a4-b66c-b44cb71ded58
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3d26c006c7752b5e2ef2480cff3b57457f4dbfc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387571"
---
# <a name="helloworld-biztalk-server-sample"></a><span data-ttu-id="1ccd0-102">HelloWorld （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="1ccd0-102">HelloWorld (BizTalk Server Sample)</span></span>
<span data-ttu-id="1ccd0-103">HelloWorld 示例演示如何使用 BizTalk 业务流程将 XML 消息 （采购订单） 转换为相关但不同的消息 （发票） 的类型。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-103">The HelloWorld sample demonstrates how to use BizTalk orchestrations to convert an XML message (a purchase order) into a related, but distinct, type of message (an invoice).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="1ccd0-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="1ccd0-104">What This Sample Does</span></span>  
 <span data-ttu-id="1ccd0-105">此示例配置**在**与接收位置的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-105">This sample configures the **In** folder as a receive location.</span></span> <span data-ttu-id="1ccd0-106">当将一个文件，如示例文件**SamplePOInput.xml**，到此文件夹中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]按照以下步骤处理该消息：</span><span class="sxs-lookup"><span data-stu-id="1ccd0-106">When you place a file, such as the sample file **SamplePOInput.xml**, into this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the message using the following steps:</span></span>  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1ccd0-107">从接收位置文件夹检索 XML 采购订单消息。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-107">retrieves the XML purchase order message from the receive location folder.</span></span>  
  
2. <span data-ttu-id="1ccd0-108">业务流程使用映射文件从 XML 采购订单创建 XML 发票。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-108">The orchestration uses the map file to create an XML invoice from the XML purchase order.</span></span>  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1ccd0-109">将生成的 XML 发票消息放入发送适配器**出**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-109">places the resulting XML invoice message into the send adapter **Out** folder.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="1ccd0-110">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="1ccd0-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="1ccd0-111">在公司间的消息交换方案中，通常很有必要，将从为内部应用程序可以识别的格式贸易合作伙伴接收的入站的消息。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-111">In an intercompany message-exchange scenario, it is often necessary to convert inbound messages received from trading partners into a format that internal applications can recognize.</span></span> <span data-ttu-id="1ccd0-112">此示例使用**接收**形状**转换**形状，和一个**发送**形状来实现此目标。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-112">This sample uses a **Receive** shape, a **Transform** shape, and a **Send** shape to achieve this result.</span></span> <span data-ttu-id="1ccd0-113">**转换**形状在此示例中扮演重要角色，因为它是消息格式转换发生的地方。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-113">The **Transform** shape plays the important role in this sample because it is where the message format conversion occurs.</span></span> <span data-ttu-id="1ccd0-114">您拖动**转换**形状在业务流程，然后为其配置源消息、 映射名称和目标消息。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-114">You drag a **Transform** shape into your orchestration and configure the source message, map name, and destination message for it.</span></span> <span data-ttu-id="1ccd0-115">在运行时，将源消息通过使用指定的映射映射到目标消息。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-115">During run time, the source message is mapped to the destination message by using the map you designated.</span></span>  
  
 <span data-ttu-id="1ccd0-116">有关详细信息**转换**形状中，请参阅[如何配置转换形状](../core/how-to-configure-the-transform-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-116">For more information about the **Transform** shape, see [How to Configure the Transform Shape](../core/how-to-configure-the-transform-shape.md).</span></span> <span data-ttu-id="1ccd0-117">有关构建映射的详细信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-117">For more information about building a map, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="1ccd0-118">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="1ccd0-118">Where to Find This Sample</span></span>  
 <span data-ttu-id="1ccd0-119">\<*Samples Path*\>\Orchestrations\HelloWorld\\</span><span class="sxs-lookup"><span data-stu-id="1ccd0-119">\<*Samples Path*\>\Orchestrations\HelloWorld\\</span></span>  
  
 <span data-ttu-id="1ccd0-120">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="1ccd0-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="1ccd0-121">文件</span><span class="sxs-lookup"><span data-stu-id="1ccd0-121">File(s)</span></span>|<span data-ttu-id="1ccd0-122">Description</span><span class="sxs-lookup"><span data-stu-id="1ccd0-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ccd0-123">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="1ccd0-123">Cleanup.bat</span></span>|<span data-ttu-id="1ccd0-124">用于取消部署程序集并从全局程序集缓存中删除。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-124">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="1ccd0-125">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-125">Removes send and receive ports.</span></span> <span data-ttu-id="1ccd0-126">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-126">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="1ccd0-127">HelloOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="1ccd0-127">HelloOrchestration.odx</span></span>|<span data-ttu-id="1ccd0-128">业务流程的采购订单转换为发票进行协调。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-128">Orchestration that coordinates the conversion of the purchase order into an invoice.</span></span>|  
|<span data-ttu-id="1ccd0-129">HelloWorld.btproj, HelloWorld.sln</span><span class="sxs-lookup"><span data-stu-id="1ccd0-129">HelloWorld.btproj, HelloWorld.sln</span></span>|<span data-ttu-id="1ccd0-130">本示例的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-130">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="1ccd0-131">HelloWorldBinding.xml</span><span class="sxs-lookup"><span data-stu-id="1ccd0-131">HelloWorldBinding.xml</span></span>|<span data-ttu-id="1ccd0-132">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-132">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="1ccd0-133">InvoiceSchema.xsd, POSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="1ccd0-133">InvoiceSchema.xsd, POSchema.xsd</span></span>|<span data-ttu-id="1ccd0-134">有关发票和采购订单消息的架构，分别。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-134">Schemas for the invoice and purchase order messages, respectively.</span></span>|  
|<span data-ttu-id="1ccd0-135">POToInvoice.btm</span><span class="sxs-lookup"><span data-stu-id="1ccd0-135">POToInvoice.btm</span></span>|<span data-ttu-id="1ccd0-136">用于将采购订单转换为发票的映射。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-136">Map for converting the purchase order to an invoice.</span></span>|  
|<span data-ttu-id="1ccd0-137">SamplePOInput.xml</span><span class="sxs-lookup"><span data-stu-id="1ccd0-137">SamplePOInput.xml</span></span>|<span data-ttu-id="1ccd0-138">示例输入的文件。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-138">Sample input file.</span></span>|  
|<span data-ttu-id="1ccd0-139">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="1ccd0-139">Setup.bat</span></span>|<span data-ttu-id="1ccd0-140">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-140">Used to build and initialize this sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="1ccd0-141">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="1ccd0-141">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-helloworld-sample"></a><span data-ttu-id="1ccd0-142">若要生成并初始化 HelloWorld 示例</span><span class="sxs-lookup"><span data-stu-id="1ccd0-142">To build and initialize the HelloWorld sample</span></span>  
  
1. <span data-ttu-id="1ccd0-143">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="1ccd0-143">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="1ccd0-144">\<*Samples Path*\>\Orchestrations\HelloWorld</span><span class="sxs-lookup"><span data-stu-id="1ccd0-144">\<*Samples Path*\>\Orchestrations\HelloWorld</span></span>  
  
2. <span data-ttu-id="1ccd0-145">运行文件 Setup.bat，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1ccd0-145">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="1ccd0-146">创建输入 (In) 和输出 (Out) 文件夹中，为此示例的以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="1ccd0-146">Creates the input (In) and output (Out) folders for this sample in the following folder:</span></span>  
  
      <span data-ttu-id="1ccd0-147">\<*Samples Path*\>\Orchestrations\HelloWorld</span><span class="sxs-lookup"><span data-stu-id="1ccd0-147">\<*Samples Path*\>\Orchestrations\HelloWorld</span></span>  
  
   - <span data-ttu-id="1ccd0-148">编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例项目。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-148">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  
  
   - <span data-ttu-id="1ccd0-149">创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收到业务流程的端口。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-149">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports to the orchestration.</span></span>  
  
   - <span data-ttu-id="1ccd0-150">启用该接收位置，并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-150">Enables the receive location, and starts the send port.</span></span> <span data-ttu-id="1ccd0-151">登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-151">Enlists and starts orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ccd0-152">您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-152">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span> <span data-ttu-id="1ccd0-153">你可以通过查看事件日志来确认这一点。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-153">You can confirm this by viewing your event logs.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="1ccd0-154">运行本示例</span><span class="sxs-lookup"><span data-stu-id="1ccd0-154">Running This Sample</span></span>  
  
#### <a name="to-run-the-helloworld-sample"></a><span data-ttu-id="1ccd0-155">若要运行 HelloWorld 示例</span><span class="sxs-lookup"><span data-stu-id="1ccd0-155">To run the HelloWorld sample</span></span>  
  
1.  <span data-ttu-id="1ccd0-156">将文件 SamplePOInput.xml 的副本粘贴到**在**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-156">Paste a copy of the file SamplePOInput.xml into the **In** folder.</span></span>  
  
2.  <span data-ttu-id="1ccd0-157">查看在中创建的.xml 文件**出**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-157">Observe the .xml file created in the **Out** folder.</span></span> <span data-ttu-id="1ccd0-158">此文件包含从输入文件 SamplePOInput.xml 构造的 XML 发票。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-158">This file contains the XML invoice constructed from the input file SamplePOInput.xml.</span></span> <span data-ttu-id="1ccd0-159">此文件的名称的格式\< *MessageID*\>.xml，其中*\<MessageID\>* 生成的 GUID 来唯一标识消息.</span><span class="sxs-lookup"><span data-stu-id="1ccd0-159">The format of the name of this file is \<*MessageID*\>.xml, where *\<MessageID\>* is the GUID generated to uniquely identify the message.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="1ccd0-160">卸载本示例</span><span class="sxs-lookup"><span data-stu-id="1ccd0-160">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-helloworld-sample"></a><span data-ttu-id="1ccd0-161">卸载 HelloWorld 示例</span><span class="sxs-lookup"><span data-stu-id="1ccd0-161">To uninstall the HelloWorld sample</span></span>  
  
1.  <span data-ttu-id="1ccd0-162">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="1ccd0-162">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="1ccd0-163">\<*Samples Path*\>\Orchestrations\HelloWorld\\</span><span class="sxs-lookup"><span data-stu-id="1ccd0-163">\<*Samples Path*\>\Orchestrations\HelloWorld\\</span></span>  
  
2.  <span data-ttu-id="1ccd0-164">运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="1ccd0-164">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ccd0-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ccd0-165">See Also</span></span>  
 [<span data-ttu-id="1ccd0-166">业务流程（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="1ccd0-166">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)