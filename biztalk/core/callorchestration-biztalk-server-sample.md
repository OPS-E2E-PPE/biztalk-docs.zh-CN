---
title: CallOrchestration （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, calling
- examples, orchestrations
ms.assetid: 0c4194f0-c1e2-419a-8a1a-a3c96e8d2667
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64c0481242c86038cde10a0505b5a12f039ec9bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357659"
---
# <a name="callorchestration-biztalk-server-sample"></a><span data-ttu-id="82d23-102">CallOrchestration （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="82d23-102">CallOrchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="82d23-103">CallOrchestration 示例演示如何从另一个业务流程调用一个 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="82d23-103">The CallOrchestration sample demonstrates how to call one BizTalk orchestration from another orchestration.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="82d23-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="82d23-104">What This Sample Does</span></span>  
 <span data-ttu-id="82d23-105">此示例演示一个业务流程调用另一个业务流程使用以下步骤序列：</span><span class="sxs-lookup"><span data-stu-id="82d23-105">This sample demonstrates one orchestration calling another orchestration using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="82d23-106">主业务流程接收采购订单 (PO) 消息。</span><span class="sxs-lookup"><span data-stu-id="82d23-106">The primary orchestration receives a purchase order (PO) message.</span></span>  
  
2.  <span data-ttu-id="82d23-107">主业务流程调用次业务流程来确定采购订单的发货价格。</span><span class="sxs-lookup"><span data-stu-id="82d23-107">The primary orchestration calls the secondary orchestration to determine the shipping price for the PO.</span></span>  
  
3.  <span data-ttu-id="82d23-108">次业务流程计算请求的发货价格，并将其返回给主业务流程。</span><span class="sxs-lookup"><span data-stu-id="82d23-108">The secondary orchestration calculates the requested shipping price and returns it to the primary orchestration.</span></span>  
  
4.  <span data-ttu-id="82d23-109">主业务流程使用返回的发货价格更新采购订单消息。</span><span class="sxs-lookup"><span data-stu-id="82d23-109">The primary orchestration updates the PO message with the returned shipping price.</span></span>  
  
5.  <span data-ttu-id="82d23-110">主业务流程将更新后的采购订单消息放入文件夹备查。</span><span class="sxs-lookup"><span data-stu-id="82d23-110">The primary orchestration puts the updated PO message into a folder for your inspection.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="82d23-111">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="82d23-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="82d23-112">此示例的主要目的是说明如何调用另一个业务流程内的从业务流程。</span><span class="sxs-lookup"><span data-stu-id="82d23-112">The primary purpose of this sample is to show you how to call an orchestration from within another orchestration.</span></span> <span data-ttu-id="82d23-113">调用业务流程的能力，可以将您的业务流程划分为可重用的组件。</span><span class="sxs-lookup"><span data-stu-id="82d23-113">The ability to call orchestrations gives you a way to divide your business processes into reusable components.</span></span> <span data-ttu-id="82d23-114">您可以分解到不同的其他人重复使用的业务流程将通用流程。</span><span class="sxs-lookup"><span data-stu-id="82d23-114">You can factor your common processes out into separate orchestrations for others to re-use.</span></span>  
  
 <span data-ttu-id="82d23-115">在此示例中，**调用业务流程**receivePO.odx 中的形状调用 findShippingPrice.odx，并等待嵌套的业务流程 findShippingPrice.odx 来计算并返回发货价格发送在购买前顺序。</span><span class="sxs-lookup"><span data-stu-id="82d23-115">In this sample, the **Call Orchestration** shape in receivePO.odx invokes findShippingPrice.odx and waits for the nested orchestration, findShippingPrice.odx, to calculate and return the shipping price before sending the purchase order.</span></span> <span data-ttu-id="82d23-116">业务流程 findShippingPrice.odx 使用以下逻辑来计算发货价格：</span><span class="sxs-lookup"><span data-stu-id="82d23-116">The orchestration findShippingPrice.odx uses the following logic to calculate the shipping price:</span></span>  
  
```  
If ( weight * shippingRate ) < minShippingPrice Then  
    shippingPrice = minShippingPrice  
Else  
    shippingPrice = weight * shippingRate  
End If  
```  
  
 <span data-ttu-id="82d23-117">示例输入采购订单文件 InputPO.xml 指定权重为 20，从而导致输出采购订单消息将其发货价格由 10 更改为 20。</span><span class="sxs-lookup"><span data-stu-id="82d23-117">The sample input PO file, InputPO.xml, specifies a weight of 20, resulting in the output PO message having its shipping price changed from 10 to 20.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82d23-118">不能从原子业务流程调用长期事务。</span><span class="sxs-lookup"><span data-stu-id="82d23-118">You cannot call a long-running transaction from an atomic orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82d23-119">使用不同之处**调用业务流程**形状和**启动业务流程**形状是，在调用业务流程时，调用方等到嵌套的业务流程返回之前继续操作。</span><span class="sxs-lookup"><span data-stu-id="82d23-119">The difference between using the **Call Orchestration** shape and the **Start Orchestration** shape is that when calling an orchestration, the caller waits for the nested orchestration to return before continuing.</span></span> <span data-ttu-id="82d23-120">当从业务流程中，启动业务流程，调用方启动该操作后，调用方将向前移动到处理流程的下一步。</span><span class="sxs-lookup"><span data-stu-id="82d23-120">When starting an orchestration from an orchestration, after the caller initiates the action, the caller moves forward to the next step in the process flow.</span></span> <span data-ttu-id="82d23-121">调用方已调用的业务流程独立运行，直到它完成处理流程。</span><span class="sxs-lookup"><span data-stu-id="82d23-121">The orchestration that was invoked by the caller runs independently until it finishes the process flow.</span></span> <span data-ttu-id="82d23-122">有关详细信息，请参阅[如何配置调用业务流程形状](../core/how-to-configure-the-call-orchestration-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="82d23-122">For more information, see [How to Configure the Call Orchestration Shape](../core/how-to-configure-the-call-orchestration-shape.md).</span></span> <span data-ttu-id="82d23-123">另请参阅[如何配置启动业务流程形状](../core/how-to-configure-the-start-orchestration-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="82d23-123">Also see [How to Configure the Start Orchestration Shape](../core/how-to-configure-the-start-orchestration-shape.md).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="82d23-124">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="82d23-124">Where to Find This Sample</span></span>  
 <span data-ttu-id="82d23-125">\<*Samples Path*\>\Orchestrations\CallOrchestration</span><span class="sxs-lookup"><span data-stu-id="82d23-125">\<*Samples Path*\>\Orchestrations\CallOrchestration</span></span>\  
  
 <span data-ttu-id="82d23-126">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="82d23-126">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="82d23-127">文件</span><span class="sxs-lookup"><span data-stu-id="82d23-127">File(s)</span></span>|<span data-ttu-id="82d23-128">Description</span><span class="sxs-lookup"><span data-stu-id="82d23-128">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82d23-129">CallOrchestration.btproj, CallOrchestration.sln</span><span class="sxs-lookup"><span data-stu-id="82d23-129">CallOrchestration.btproj, CallOrchestration.sln</span></span>|<span data-ttu-id="82d23-130">本示例的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="82d23-130">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="82d23-131">CallOrchestrationBinding.xml</span><span class="sxs-lookup"><span data-stu-id="82d23-131">CallOrchestrationBinding.xml</span></span>|<span data-ttu-id="82d23-132">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="82d23-132">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="82d23-133">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="82d23-133">Cleanup.bat</span></span>|<span data-ttu-id="82d23-134">用于取消部署程序集并从全局程序集缓存中删除。</span><span class="sxs-lookup"><span data-stu-id="82d23-134">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="82d23-135">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="82d23-135">Removes send and receive ports.</span></span> <span data-ttu-id="82d23-136">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="82d23-136">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="82d23-137">findShippingPrice.odx</span><span class="sxs-lookup"><span data-stu-id="82d23-137">findShippingPrice.odx</span></span>|<span data-ttu-id="82d23-138">从主业务流程调用可作为次业务流程的 BizTalk 业务流程 receivepo.odx 进行。</span><span class="sxs-lookup"><span data-stu-id="82d23-138">BizTalk orchestration that serves as a secondary orchestration, called from the primary orchestration, receivePO.odx.</span></span>|  
|<span data-ttu-id="82d23-139">InputPO.xml</span><span class="sxs-lookup"><span data-stu-id="82d23-139">InputPO.xml</span></span>|<span data-ttu-id="82d23-140">示例输入采购订单消息符合 PO.xsd 文件中定义的架构。</span><span class="sxs-lookup"><span data-stu-id="82d23-140">Sample input PO message that conforms to the schema defined in the file PO.xsd.</span></span>|  
|<span data-ttu-id="82d23-141">PO.xsd</span><span class="sxs-lookup"><span data-stu-id="82d23-141">PO.xsd</span></span>|<span data-ttu-id="82d23-142">定义如示例输入文件 InputPO.xml 的入站采购订单消息的结构并在架构中定义的属性升级的所有三个元素的架构。</span><span class="sxs-lookup"><span data-stu-id="82d23-142">Schema that defines the structure of inbound PO messages such as the sample input file InputPO.xml, and defines property promotion for all three elements in the schema.</span></span>|  
|<span data-ttu-id="82d23-143">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="82d23-143">PropertySchema.xsd</span></span>|<span data-ttu-id="82d23-144">参与架构 PO.xsd 中所有三个元素的属性升级的属性架构文件。</span><span class="sxs-lookup"><span data-stu-id="82d23-144">Property schema file that participates in property promotion for all three elements in the schema PO.xsd.</span></span>|  
|<span data-ttu-id="82d23-145">receivePO.odx</span><span class="sxs-lookup"><span data-stu-id="82d23-145">receivePO.odx</span></span>|<span data-ttu-id="82d23-146">充当主业务流程，在此示例中的 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="82d23-146">BizTalk orchestration that serves as the primary orchestration in this sample.</span></span> <span data-ttu-id="82d23-147">它从接收文件夹检索采购订单消息，然后调用其他业务流程 findShippingPrice.odx 来计算和更新发货价格。</span><span class="sxs-lookup"><span data-stu-id="82d23-147">It retrieves PO messages from the receive folder and then calls the other orchestration, findShippingPrice.odx, to calculate and update the shipping price.</span></span>|  
|<span data-ttu-id="82d23-148">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="82d23-148">Setup.bat</span></span>|<span data-ttu-id="82d23-149">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="82d23-149">Used to build and initialize this sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="82d23-150">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="82d23-150">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-callorchestration-sample"></a><span data-ttu-id="82d23-151">若要生成并初始化 CallOrchestration 示例</span><span class="sxs-lookup"><span data-stu-id="82d23-151">To build and initialize the CallOrchestration sample</span></span>  
  
1. <span data-ttu-id="82d23-152">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="82d23-152">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="82d23-153">\<*Samples Path*\>\Orchestrations\CallOrchestration</span><span class="sxs-lookup"><span data-stu-id="82d23-153">\<*Samples Path*\>\Orchestrations\CallOrchestration</span></span>\  
  
2. <span data-ttu-id="82d23-154">运行文件 Setup.bat，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="82d23-154">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="82d23-155">创建输入 (In) 和输出 (Out) 文件夹中，为此示例在 CallOrchestration 文件夹。</span><span class="sxs-lookup"><span data-stu-id="82d23-155">Creates the input (In) and output (Out) folders for this sample in the CallOrchestration folder.</span></span>  
  
   - <span data-ttu-id="82d23-156">编译并部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]包含两个业务流程，此示例的项目。</span><span class="sxs-lookup"><span data-stu-id="82d23-156">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project, containing both orchestrations, for this sample.</span></span>  
  
   - <span data-ttu-id="82d23-157">创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="82d23-157">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
   - <span data-ttu-id="82d23-158">启用该接收位置，并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="82d23-158">Enables the receive location, and starts the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82d23-159">您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。</span><span class="sxs-lookup"><span data-stu-id="82d23-159">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="82d23-160">运行本示例</span><span class="sxs-lookup"><span data-stu-id="82d23-160">Running This Sample</span></span>  
  
#### <a name="to-run-the-callorchestration-sample"></a><span data-ttu-id="82d23-161">若要运行 CallOrchestration 示例</span><span class="sxs-lookup"><span data-stu-id="82d23-161">To run the CallOrchestration sample</span></span>  
  
1.  <span data-ttu-id="82d23-162">将 InputPO.xml 文件的副本放到 In 文件夹。</span><span class="sxs-lookup"><span data-stu-id="82d23-162">Put a copy of the file InputPO.xml into the In folder.</span></span>  
  
2.  <span data-ttu-id="82d23-163">查看在 Out 文件夹中创建的已更新的 XML 采购订单文件。</span><span class="sxs-lookup"><span data-stu-id="82d23-163">Observe the updated XML PO file created in the Out folder.</span></span> <span data-ttu-id="82d23-164">它包含原始采购订单消息，修改为包含计算如前面所述的发货费用。</span><span class="sxs-lookup"><span data-stu-id="82d23-164">It contains the original PO message, modified to include a shipping cost calculated as explained earlier.</span></span> <span data-ttu-id="82d23-165">此文件的名称的格式\< *MessageID*\>.xml，其中 *\<MessageID\>* 生成的 GUID 来唯一标识消息.</span><span class="sxs-lookup"><span data-stu-id="82d23-165">The format of the name of this file is \<*MessageID*\>.xml, where *\<MessageID\>* is the GUID generated to uniquely identify the message.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="82d23-166">卸载本示例</span><span class="sxs-lookup"><span data-stu-id="82d23-166">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-callorchestration-sample"></a><span data-ttu-id="82d23-167">若要卸载 CallOrchestration 示例</span><span class="sxs-lookup"><span data-stu-id="82d23-167">To uninstall the CallOrchestration sample</span></span>  
  
1. <span data-ttu-id="82d23-168">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="82d23-168">In a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="82d23-169">\<*Samples Path*\>\Orchestrations\CallOrchestration</span><span class="sxs-lookup"><span data-stu-id="82d23-169">\<*Samples Path*\>\Orchestrations\CallOrchestration</span></span>\  
  
2. <span data-ttu-id="82d23-170">运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="82d23-170">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82d23-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="82d23-171">See Also</span></span>  
 [<span data-ttu-id="82d23-172">业务流程（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="82d23-172">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)