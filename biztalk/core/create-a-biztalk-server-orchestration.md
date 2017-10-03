---
title: "创建 BizTalk Server 业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16c637ae-f94f-40f8-8ce7-73a7b7df9f8f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb9c2347a989dd59b97125e119ea79a9996c53ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-biztalk-server-orchestration"></a><span data-ttu-id="72c16-102">创建 BizTalk Server 业务流程</span><span class="sxs-lookup"><span data-stu-id="72c16-102">Create a BizTalk Server orchestration</span></span>
> [!NOTE]
>  <span data-ttu-id="72c16-103">本教程仅适用于 [!INCLUDE[prague](../includes/prague-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="72c16-103">This tutorial applies to [!INCLUDE[prague](../includes/prague-md.md)] only.</span></span>  
  
 <span data-ttu-id="72c16-104">部署时创建一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程，以接收 JSON 采购订单消息、将其转换成 XML 发票，然后向外发送 JSON 发票。</span><span class="sxs-lookup"><span data-stu-id="72c16-104">Create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that, when deployed, receives a JSON purchase order message, transforms it to an XML invoice, and then sends out a JSON invoice.</span></span>  
  
## <a name="define-message-and-message-types"></a><span data-ttu-id="72c16-105">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="72c16-105">Define message and message types</span></span>  
 <span data-ttu-id="72c16-106">此解决方案结合使用两个基本消息 – 采购订单和发票。</span><span class="sxs-lookup"><span data-stu-id="72c16-106">This solution works with two basic messages – purchase order and invoice.</span></span> <span data-ttu-id="72c16-107">我们已经使用 JSON 架构向导从 JSON 消息生成采购订单的架构。</span><span class="sxs-lookup"><span data-stu-id="72c16-107">We already generated the schema of the purchase order from a JSON message using the JSON schema wizard.</span></span> <span data-ttu-id="72c16-108">为本教程提供的示例已具有发票消息的架构。</span><span class="sxs-lookup"><span data-stu-id="72c16-108">The sample provided for this tutorial already has the schema for the invoice message.</span></span> <span data-ttu-id="72c16-109">我们使用这些架构在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中创建消息类型。</span><span class="sxs-lookup"><span data-stu-id="72c16-109">We use these schemas to create the message types in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
1.  <span data-ttu-id="72c16-110">将业务流程添加到 BizTalk 项目中，然后打开业务流程视图。</span><span class="sxs-lookup"><span data-stu-id="72c16-110">Add an orchestration to the BizTalk project and open the Orchestration view.</span></span>  
  
2.  <span data-ttu-id="72c16-111">在业务流程视图中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="72c16-111">In the Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="72c16-112">右键单击新创建的消息中，，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="72c16-112">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="72c16-113">在**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="72c16-113">In the **Properties** pane for the **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="72c16-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="72c16-114">Use this</span></span>|<span data-ttu-id="72c16-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="72c16-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="72c16-116">Identifier</span><span class="sxs-lookup"><span data-stu-id="72c16-116">Identifier</span></span>|<span data-ttu-id="72c16-117">类型`PurchaseOrder`</span><span class="sxs-lookup"><span data-stu-id="72c16-117">Type `PurchaseOrder`</span></span>|  
    |<span data-ttu-id="72c16-118">消息类型</span><span class="sxs-lookup"><span data-stu-id="72c16-118">Message Type</span></span>|<span data-ttu-id="72c16-119">从下拉列表中，展开**架构**，然后选择*BTSJSON。PO*，其中*BTSJSON*是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="72c16-119">From the drop-down list, expand **Schemas**, and then select *BTSJSON.PO*, where *BTSJSON* is the name of your BizTalk project.</span></span>|  
  
5.  <span data-ttu-id="72c16-120">重复上一步骤，为发票消息创建一个新消息类型。</span><span class="sxs-lookup"><span data-stu-id="72c16-120">Repeat the previous step to create a new message type for the invoice message.</span></span> <span data-ttu-id="72c16-121">在**属性**窗格中，为新的消息中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="72c16-121">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="72c16-122">使用此选项</span><span class="sxs-lookup"><span data-stu-id="72c16-122">Use this</span></span>|<span data-ttu-id="72c16-123">执行的操作</span><span class="sxs-lookup"><span data-stu-id="72c16-123">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="72c16-124">Identifier</span><span class="sxs-lookup"><span data-stu-id="72c16-124">Identifier</span></span>|<span data-ttu-id="72c16-125">类型`InvoiceMsg`</span><span class="sxs-lookup"><span data-stu-id="72c16-125">Type `InvoiceMsg`</span></span>|  
    |<span data-ttu-id="72c16-126">消息类型</span><span class="sxs-lookup"><span data-stu-id="72c16-126">Message Type</span></span>|<span data-ttu-id="72c16-127">从下拉列表中，展开**架构**，然后选择*BTSJSON。发票*。</span><span class="sxs-lookup"><span data-stu-id="72c16-127">From the drop-down list, expand **Schemas**, and then select *BTSJSON.Invoice*.</span></span>|  
  
## <a name="set-up-the-orchestration"></a><span data-ttu-id="72c16-128">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="72c16-128">Set up the orchestration</span></span>  
 <span data-ttu-id="72c16-129">在此步骤中，您将添加消息形状和端口，创建一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="72c16-129">In this step, you add message shapes and ports to create an orchestration.</span></span>  
  
### <a name="add-message-shapes"></a><span data-ttu-id="72c16-130">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="72c16-130">Add message shapes</span></span>  
 <span data-ttu-id="72c16-131">从解决方案资源管理器打开业务流程文件，然后添加以下消息形状。</span><span class="sxs-lookup"><span data-stu-id="72c16-131">Open the orchestration file from Solution Explorer, and add the following message shapes.</span></span>  
  
-   <span data-ttu-id="72c16-132">添加接收图形，请将其名称设置为**ReceivePO**，和消息类型设置为**PurchaseOrder**。</span><span class="sxs-lookup"><span data-stu-id="72c16-132">Add a Receive shape, set its name to **ReceivePO**, and message type to **PurchaseOrder**.</span></span>  
  
-   <span data-ttu-id="72c16-133">添加发送图形，请将其名称设置为**SendInvoice**，和消息类型设置为**InvoiceMsg**。</span><span class="sxs-lookup"><span data-stu-id="72c16-133">Add a Send shape, set its name to **SendInvoice**, and message type to **InvoiceMsg**.</span></span>  
  
-   <span data-ttu-id="72c16-134">添加构造消息形状，并设置**消息构造**属性构造消息形状上与**InvoiceMsg**。</span><span class="sxs-lookup"><span data-stu-id="72c16-134">Add a Construct Message shape and set the **Messages Constructed** property of the Construct Message shape to **InvoiceMsg**.</span></span>  
  
-   <span data-ttu-id="72c16-135">在“构造消息”形状内添加“转换”形状。</span><span class="sxs-lookup"><span data-stu-id="72c16-135">Add a Transform shape within the Construct Message shape.</span></span> <span data-ttu-id="72c16-136">双击转换形状并在**转换配置**对话框中，选择**现有映射**选项，然后再选中**BTSJSON。POToInvoice**映射。</span><span class="sxs-lookup"><span data-stu-id="72c16-136">Double-click the Transform shape and in the **Transform Configuration** dialog box, select the **Existing Map** option, and then select **BTSJSON.POToInvoice** map.</span></span> <span data-ttu-id="72c16-137">此映射是作为示例的一部分提供的。</span><span class="sxs-lookup"><span data-stu-id="72c16-137">This map is provided as part of the sample.</span></span> <span data-ttu-id="72c16-138">在对话框中，设置**源**到**PurchaseOrder**并设置**目标**到**InvoiceMsg**。</span><span class="sxs-lookup"><span data-stu-id="72c16-138">In the dialog box, set **Source** to **PurchaseOrder** and set **Destination** to **InvoiceMsg**.</span></span> <span data-ttu-id="72c16-139">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="72c16-139">Click **OK**.</span></span>  
  
### <a name="add-ports"></a><span data-ttu-id="72c16-140">添加端口</span><span class="sxs-lookup"><span data-stu-id="72c16-140">Add ports</span></span>  
 <span data-ttu-id="72c16-141">向业务流程添加两个端口 – 一个用于接收消息，一个用于发送消息。</span><span class="sxs-lookup"><span data-stu-id="72c16-141">Add two ports to the orchestration – one for receiving messages and one for sending messages.</span></span> <span data-ttu-id="72c16-142">针对端口使用以下属性。</span><span class="sxs-lookup"><span data-stu-id="72c16-142">Use the following properties for the ports.</span></span>  
  
|<span data-ttu-id="72c16-143">端口</span><span class="sxs-lookup"><span data-stu-id="72c16-143">Port</span></span>|<span data-ttu-id="72c16-144">属性</span><span class="sxs-lookup"><span data-stu-id="72c16-144">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="72c16-145">MessageIn</span><span class="sxs-lookup"><span data-stu-id="72c16-145">MessageIn</span></span>|<span data-ttu-id="72c16-146">-将设置**标识符**到*ReceiveJSONPO*</span><span class="sxs-lookup"><span data-stu-id="72c16-146">-   Set **Identifier** to *ReceiveJSONPO*</span></span><br /><span data-ttu-id="72c16-147">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="72c16-147">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="72c16-148">-将设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="72c16-148">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="72c16-149">ResponseOut</span><span class="sxs-lookup"><span data-stu-id="72c16-149">ResponseOut</span></span>|<span data-ttu-id="72c16-150">-将设置**标识符**到*SendJSONInvoice*</span><span class="sxs-lookup"><span data-stu-id="72c16-150">-   Set **Identifier** to *SendJSONInvoice*</span></span><br /><span data-ttu-id="72c16-151">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="72c16-151">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="72c16-152">-将设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="72c16-152">-   Set **Communication Direction** to *Send*</span></span>|  
  
 <span data-ttu-id="72c16-153">按照下面的屏幕快照所示连接端口和消息形状，然后将更改保存至项目。</span><span class="sxs-lookup"><span data-stu-id="72c16-153">Connect the ports and message shape, as shown in the screenshot below, and save changes to the project.</span></span>  
  
 <span data-ttu-id="72c16-154">![业务流程来处理 JSON 消息](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")</span><span class="sxs-lookup"><span data-stu-id="72c16-154">![Orchestration to process JSON messages](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72c16-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72c16-155">See Also</span></span>  
 [<span data-ttu-id="72c16-156">使用 BizTalk Server 处理 JSON 消息</span><span class="sxs-lookup"><span data-stu-id="72c16-156">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)