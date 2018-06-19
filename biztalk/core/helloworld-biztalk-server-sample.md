---
title: HelloWorld （BizTalk Server 示例） |Microsoft 文档
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
ms.openlocfilehash: e70271967086f530ce5421348c118a74019dd366
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969307"
---
# <a name="helloworld-biztalk-server-sample"></a><span data-ttu-id="1e836-102">HelloWorld （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="1e836-102">HelloWorld (BizTalk Server Sample)</span></span>
<span data-ttu-id="1e836-103">HelloWorld 示例演示如何使用 BizTalk 业务流程将 XML 消息（采购订单）转换为相关但不同类型的消息（发票）。</span><span class="sxs-lookup"><span data-stu-id="1e836-103">The HelloWorld sample demonstrates how to use BizTalk orchestrations to convert an XML message (a purchase order) into a related, but distinct, type of message (an invoice).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="1e836-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="1e836-104">What This Sample Does</span></span>  
 <span data-ttu-id="1e836-105">本示例配置**中**接收位置的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e836-105">This sample configures the **In** folder as a receive location.</span></span> <span data-ttu-id="1e836-106">当您放置文件，如示例文件**SamplePOInput.xml**，到此文件夹中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理消息使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1e836-106">When you place a file, such as the sample file **SamplePOInput.xml**, into this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the message using the following steps:</span></span>  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1e836-107"> 从接收位置文件夹检索 XML 采购订单消息。</span><span class="sxs-lookup"><span data-stu-id="1e836-107"> retrieves the XML purchase order message from the receive location folder.</span></span>  
  
2.  <span data-ttu-id="1e836-108">业务流程使用映射文件从 XML 采购订单创建 XML 发票。</span><span class="sxs-lookup"><span data-stu-id="1e836-108">The orchestration uses the map file to create an XML invoice from the XML purchase order.</span></span>  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1e836-109">将生成的 XML 发票消息放入发送适配器**出**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e836-109"> places the resulting XML invoice message into the send adapter **Out** folder.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="1e836-110">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="1e836-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="1e836-111">在公司间消息交换方案中，经常需要将从贸易合作伙伴接收的入站消息转换为内部应用程序可以识别的格式。</span><span class="sxs-lookup"><span data-stu-id="1e836-111">In an intercompany message-exchange scenario, it is often necessary to convert inbound messages received from trading partners into a format that internal applications can recognize.</span></span> <span data-ttu-id="1e836-112">此示例使用**接收**形状，**转换**形状，和一个**发送**形状以获得此结果。</span><span class="sxs-lookup"><span data-stu-id="1e836-112">This sample uses a **Receive** shape, a **Transform** shape, and a **Send** shape to achieve this result.</span></span> <span data-ttu-id="1e836-113">**转换**形状在此示例中扮演重要角色，因为它是消息格式转换的出现位置。</span><span class="sxs-lookup"><span data-stu-id="1e836-113">The **Transform** shape plays the important role in this sample because it is where the message format conversion occurs.</span></span> <span data-ttu-id="1e836-114">拖动**转换**调整到您的业务流程和为其配置的源消息、 映射名称和目标消息。</span><span class="sxs-lookup"><span data-stu-id="1e836-114">You drag a **Transform** shape into your orchestration and configure the source message, map name, and destination message for it.</span></span> <span data-ttu-id="1e836-115">在运行期间，使用您指定的映射将源消息映射到目标消息。</span><span class="sxs-lookup"><span data-stu-id="1e836-115">During run time, the source message is mapped to the destination message by using the map you designated.</span></span>  
  
 <span data-ttu-id="1e836-116">有关详细信息**转换**形状，请参阅[如何配置转换形状](../core/how-to-configure-the-transform-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="1e836-116">For more information about the **Transform** shape, see [How to Configure the Transform Shape](../core/how-to-configure-the-transform-shape.md).</span></span> <span data-ttu-id="1e836-117">有关生成地图的详细信息，请参阅[创建地图使用 BizTalk 映射程序](../core/creating-maps-using-biztalk-mapper.md)。</span><span class="sxs-lookup"><span data-stu-id="1e836-117">For more information about building a map, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="1e836-118">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="1e836-118">Where to Find This Sample</span></span>  
 <span data-ttu-id="1e836-119">\<*示例路径*\>\Orchestrations\HelloWorld\\</span><span class="sxs-lookup"><span data-stu-id="1e836-119">\<*Samples Path*\>\Orchestrations\HelloWorld\\</span></span>  
  
 <span data-ttu-id="1e836-120">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="1e836-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="1e836-121">文件</span><span class="sxs-lookup"><span data-stu-id="1e836-121">File(s)</span></span>|<span data-ttu-id="1e836-122">Description</span><span class="sxs-lookup"><span data-stu-id="1e836-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e836-123">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="1e836-123">Cleanup.bat</span></span>|<span data-ttu-id="1e836-124">用于取消部署程序集并从全局程序集缓存中删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="1e836-124">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="1e836-125">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="1e836-125">Removes send and receive ports.</span></span> <span data-ttu-id="1e836-126">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="1e836-126">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="1e836-127">HelloOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="1e836-127">HelloOrchestration.odx</span></span>|<span data-ttu-id="1e836-128">对采购订单转换为发票进行协调的业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e836-128">Orchestration that coordinates the conversion of the purchase order into an invoice.</span></span>|  
|<span data-ttu-id="1e836-129">HelloWorld.btproj、HelloWorld.sln</span><span class="sxs-lookup"><span data-stu-id="1e836-129">HelloWorld.btproj, HelloWorld.sln</span></span>|<span data-ttu-id="1e836-130">本示例的项目文件和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="1e836-130">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="1e836-131">HelloWorldBinding.xml</span><span class="sxs-lookup"><span data-stu-id="1e836-131">HelloWorldBinding.xml</span></span>|<span data-ttu-id="1e836-132">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="1e836-132">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="1e836-133">InvoiceSchema.xsd、POSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="1e836-133">InvoiceSchema.xsd, POSchema.xsd</span></span>|<span data-ttu-id="1e836-134">分别用于发票和采购订单消息的架构。</span><span class="sxs-lookup"><span data-stu-id="1e836-134">Schemas for the invoice and purchase order messages, respectively.</span></span>|  
|<span data-ttu-id="1e836-135">POToInvoice.btm</span><span class="sxs-lookup"><span data-stu-id="1e836-135">POToInvoice.btm</span></span>|<span data-ttu-id="1e836-136">将采购订单转换为发票的映射。</span><span class="sxs-lookup"><span data-stu-id="1e836-136">Map for converting the purchase order to an invoice.</span></span>|  
|<span data-ttu-id="1e836-137">SamplePOInput.xml</span><span class="sxs-lookup"><span data-stu-id="1e836-137">SamplePOInput.xml</span></span>|<span data-ttu-id="1e836-138">示例输入文件。</span><span class="sxs-lookup"><span data-stu-id="1e836-138">Sample input file.</span></span>|  
|<span data-ttu-id="1e836-139">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="1e836-139">Setup.bat</span></span>|<span data-ttu-id="1e836-140">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="1e836-140">Used to build and initialize this sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="1e836-141">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="1e836-141">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-helloworld-sample"></a><span data-ttu-id="1e836-142">生成并初始化 HelloWorld 示例</span><span class="sxs-lookup"><span data-stu-id="1e836-142">To build and initialize the HelloWorld sample</span></span>  
  
1.  <span data-ttu-id="1e836-143">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="1e836-143">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="1e836-144">\<*示例路径*\>\Orchestrations\HelloWorld</span><span class="sxs-lookup"><span data-stu-id="1e836-144">\<*Samples Path*\>\Orchestrations\HelloWorld</span></span>  
  
2.  <span data-ttu-id="1e836-145">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1e836-145">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="1e836-146">在下面的文件夹中，为本示例创建输入 (In) 和输出 (Out) 文件夹：</span><span class="sxs-lookup"><span data-stu-id="1e836-146">Creates the input (In) and output (Out) folders for this sample in the following folder:</span></span>  
  
         <span data-ttu-id="1e836-147">\<*示例路径*\>\Orchestrations\HelloWorld</span><span class="sxs-lookup"><span data-stu-id="1e836-147">\<*Samples Path*\>\Orchestrations\HelloWorld</span></span>  
  
    -   <span data-ttu-id="1e836-148">编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例项目。</span><span class="sxs-lookup"><span data-stu-id="1e836-148">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  
  
    -   <span data-ttu-id="1e836-149">创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口，并将它们绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e836-149">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports to the orchestration.</span></span>  
  
    -   <span data-ttu-id="1e836-150">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="1e836-150">Enables the receive location, and starts the send port.</span></span> <span data-ttu-id="1e836-151">登记，并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e836-151">Enlists and starts orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e836-152">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="1e836-152">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span> <span data-ttu-id="1e836-153">通过查看事件日志可以确认这一点。</span><span class="sxs-lookup"><span data-stu-id="1e836-153">You can confirm this by viewing your event logs.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="1e836-154">运行本示例</span><span class="sxs-lookup"><span data-stu-id="1e836-154">Running This Sample</span></span>  
  
#### <a name="to-run-the-helloworld-sample"></a><span data-ttu-id="1e836-155">运行 HelloWorld 示例</span><span class="sxs-lookup"><span data-stu-id="1e836-155">To run the HelloWorld sample</span></span>  
  
1.  <span data-ttu-id="1e836-156">将文件 SamplePOInput.xml 的副本粘贴到**中**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e836-156">Paste a copy of the file SamplePOInput.xml into the **In** folder.</span></span>  
  
2.  <span data-ttu-id="1e836-157">观察在中创建的.xml 文件**出**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e836-157">Observe the .xml file created in the **Out** folder.</span></span> <span data-ttu-id="1e836-158">此文件包含从输入文件 SamplePOInput.xml 构造 XML 发票。</span><span class="sxs-lookup"><span data-stu-id="1e836-158">This file contains the XML invoice constructed from the input file SamplePOInput.xml.</span></span> <span data-ttu-id="1e836-159">此文件的名称的格式是\< *MessageID*\>.xml，其中 *\<MessageID\>*  GUID 生成以唯一标识消息.</span><span class="sxs-lookup"><span data-stu-id="1e836-159">The format of the name of this file is \<*MessageID*\>.xml, where *\<MessageID\>* is the GUID generated to uniquely identify the message.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="1e836-160">卸载本示例</span><span class="sxs-lookup"><span data-stu-id="1e836-160">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-helloworld-sample"></a><span data-ttu-id="1e836-161">卸载 HelloWorld 示例</span><span class="sxs-lookup"><span data-stu-id="1e836-161">To uninstall the HelloWorld sample</span></span>  
  
1.  <span data-ttu-id="1e836-162">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="1e836-162">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="1e836-163">\<*示例路径*\>\Orchestrations\HelloWorld\\</span><span class="sxs-lookup"><span data-stu-id="1e836-163">\<*Samples Path*\>\Orchestrations\HelloWorld\\</span></span>  
  
2.  <span data-ttu-id="1e836-164">运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="1e836-164">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e836-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e836-165">See Also</span></span>  
 [<span data-ttu-id="1e836-166">业务流程（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="1e836-166">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)