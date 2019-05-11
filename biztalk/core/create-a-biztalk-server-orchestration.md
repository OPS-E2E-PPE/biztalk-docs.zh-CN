---
title: 创建 BizTalk Server 业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c637ae-f94f-40f8-8ce7-73a7b7df9f8f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ae4a8b8f2c70143d1b9969bdcd7537911a99cc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390155"
---
# <a name="create-a-biztalk-server-orchestration"></a><span data-ttu-id="0a3c9-102">创建 BizTalk Server 业务流程</span><span class="sxs-lookup"><span data-stu-id="0a3c9-102">Create a BizTalk Server orchestration</span></span>
> [!NOTE]
>  <span data-ttu-id="0a3c9-103">本教程仅适用于 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="0a3c9-104">创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程，在部署时，接收 JSON 采购订单消息、 将其转换为 XML 发票，然后发送 JSON 发票。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-104">Create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that, when deployed, receives a JSON purchase order message, transforms it to an XML invoice, and then sends out a JSON invoice.</span></span>  
  
## <a name="define-message-and-message-types"></a><span data-ttu-id="0a3c9-105">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="0a3c9-105">Define message and message types</span></span>  
 <span data-ttu-id="0a3c9-106">此解决方案结合使用两个基本消息 – 采购订单和发票。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-106">This solution works with two basic messages – purchase order and invoice.</span></span> <span data-ttu-id="0a3c9-107">我们已从使用 JSON 架构向导的 JSON 消息生成采购订单的架构。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-107">We already generated the schema of the purchase order from a JSON message using the JSON schema wizard.</span></span> <span data-ttu-id="0a3c9-108">提供有关本教程中已具有发票消息的架构的示例。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-108">The sample provided for this tutorial already has the schema for the invoice message.</span></span> <span data-ttu-id="0a3c9-109">我们使用这些架构来创建中的消息类型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-109">We use these schemas to create the message types in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
1.  <span data-ttu-id="0a3c9-110">将业务流程添加到 BizTalk 项目并打开业务流程视图。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-110">Add an orchestration to the BizTalk project and open the Orchestration view.</span></span>  
  
2.  <span data-ttu-id="0a3c9-111">在业务流程视图中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-111">In the Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="0a3c9-112">右键单击新创建的消息，然后依次**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-112">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="0a3c9-113">在中**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0a3c9-113">In the **Properties** pane for the **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="0a3c9-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0a3c9-114">Use this</span></span>|<span data-ttu-id="0a3c9-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0a3c9-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0a3c9-116">Identifier</span><span class="sxs-lookup"><span data-stu-id="0a3c9-116">Identifier</span></span>|<span data-ttu-id="0a3c9-117">类型 `PurchaseOrder`</span><span class="sxs-lookup"><span data-stu-id="0a3c9-117">Type `PurchaseOrder`</span></span>|  
    |<span data-ttu-id="0a3c9-118">消息类型</span><span class="sxs-lookup"><span data-stu-id="0a3c9-118">Message Type</span></span>|<span data-ttu-id="0a3c9-119">从下拉列表中，展开**架构**，然后选择*BTSJSON。采购订单*，其中*BTSJSON*是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-119">From the drop-down list, expand **Schemas**, and then select *BTSJSON.PO*, where *BTSJSON* is the name of your BizTalk project.</span></span>|  
  
5.  <span data-ttu-id="0a3c9-120">重复上述步骤创建新的发票消息的消息类型。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-120">Repeat the previous step to create a new message type for the invoice message.</span></span> <span data-ttu-id="0a3c9-121">在中**属性**窗格中的新消息，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0a3c9-121">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="0a3c9-122">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0a3c9-122">Use this</span></span>|<span data-ttu-id="0a3c9-123">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0a3c9-123">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0a3c9-124">Identifier</span><span class="sxs-lookup"><span data-stu-id="0a3c9-124">Identifier</span></span>|<span data-ttu-id="0a3c9-125">类型 `InvoiceMsg`</span><span class="sxs-lookup"><span data-stu-id="0a3c9-125">Type `InvoiceMsg`</span></span>|  
    |<span data-ttu-id="0a3c9-126">消息类型</span><span class="sxs-lookup"><span data-stu-id="0a3c9-126">Message Type</span></span>|<span data-ttu-id="0a3c9-127">从下拉列表中，展开**架构**，然后选择*BTSJSON。发票*。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-127">From the drop-down list, expand **Schemas**, and then select *BTSJSON.Invoice*.</span></span>|  
  
## <a name="set-up-the-orchestration"></a><span data-ttu-id="0a3c9-128">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="0a3c9-128">Set up the orchestration</span></span>  
 <span data-ttu-id="0a3c9-129">在此步骤中，添加消息形状和端口，创建一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-129">In this step, you add message shapes and ports to create an orchestration.</span></span>  
  
### <a name="add-message-shapes"></a><span data-ttu-id="0a3c9-130">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="0a3c9-130">Add message shapes</span></span>  
 <span data-ttu-id="0a3c9-131">从解决方案资源管理器中打开业务流程文件并添加以下消息形状。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-131">Open the orchestration file from Solution Explorer, and add the following message shapes.</span></span>  
  
-   <span data-ttu-id="0a3c9-132">添加接收形状，将其名称设置为**ReceivePO**，和消息类型设置为**PurchaseOrder**。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-132">Add a Receive shape, set its name to **ReceivePO**, and message type to **PurchaseOrder**.</span></span>  
  
-   <span data-ttu-id="0a3c9-133">添加发送形状，将其名称设置为**SendInvoice**，和消息类型设置为**InvoiceMsg**。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-133">Add a Send shape, set its name to **SendInvoice**, and message type to **InvoiceMsg**.</span></span>  
  
-   <span data-ttu-id="0a3c9-134">添加构造消息形状，并设置**构造的消息**向构造消息形状的属性**InvoiceMsg**。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-134">Add a Construct Message shape and set the **Messages Constructed** property of the Construct Message shape to **InvoiceMsg**.</span></span>  
  
-   <span data-ttu-id="0a3c9-135">添加转换形状中构造消息形状。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-135">Add a Transform shape within the Construct Message shape.</span></span> <span data-ttu-id="0a3c9-136">双击转换形状并在**转换配置**对话框中，选择**现有映射**选项，并选择**BTSJSON。POToInvoice**映射。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-136">Double-click the Transform shape and in the **Transform Configuration** dialog box, select the **Existing Map** option, and then select **BTSJSON.POToInvoice** map.</span></span> <span data-ttu-id="0a3c9-137">此映射作为示例的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-137">This map is provided as part of the sample.</span></span> <span data-ttu-id="0a3c9-138">在对话框中，将**源**到**PurchaseOrder**并设置**目标**到**InvoiceMsg**。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-138">In the dialog box, set **Source** to **PurchaseOrder** and set **Destination** to **InvoiceMsg**.</span></span> <span data-ttu-id="0a3c9-139">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-139">Click **OK**.</span></span>  
  
### <a name="add-ports"></a><span data-ttu-id="0a3c9-140">添加端口</span><span class="sxs-lookup"><span data-stu-id="0a3c9-140">Add ports</span></span>  
 <span data-ttu-id="0a3c9-141">将两个端口添加到业务流程 – 一个用于接收消息，一个用于发送消息。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-141">Add two ports to the orchestration – one for receiving messages and one for sending messages.</span></span> <span data-ttu-id="0a3c9-142">使用以下属性的端口。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-142">Use the following properties for the ports.</span></span>  
  
|<span data-ttu-id="0a3c9-143">Port</span><span class="sxs-lookup"><span data-stu-id="0a3c9-143">Port</span></span>|<span data-ttu-id="0a3c9-144">属性</span><span class="sxs-lookup"><span data-stu-id="0a3c9-144">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="0a3c9-145">MessageIn</span><span class="sxs-lookup"><span data-stu-id="0a3c9-145">MessageIn</span></span>|<span data-ttu-id="0a3c9-146">-设置**标识符**到*ReceiveJSONPO*</span><span class="sxs-lookup"><span data-stu-id="0a3c9-146">-   Set **Identifier** to *ReceiveJSONPO*</span></span><br /><span data-ttu-id="0a3c9-147">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="0a3c9-147">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="0a3c9-148">-设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="0a3c9-148">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="0a3c9-149">ResponseOut</span><span class="sxs-lookup"><span data-stu-id="0a3c9-149">ResponseOut</span></span>|<span data-ttu-id="0a3c9-150">-设置**标识符**到*SendJSONInvoice*</span><span class="sxs-lookup"><span data-stu-id="0a3c9-150">-   Set **Identifier** to *SendJSONInvoice*</span></span><br /><span data-ttu-id="0a3c9-151">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="0a3c9-151">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="0a3c9-152">-设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="0a3c9-152">-   Set **Communication Direction** to *Send*</span></span>|  
  
 <span data-ttu-id="0a3c9-153">下面的屏幕截图中所示连接端口和消息形状，并将更改保存到项目。</span><span class="sxs-lookup"><span data-stu-id="0a3c9-153">Connect the ports and message shape, as shown in the screenshot below, and save changes to the project.</span></span>  
  
 <span data-ttu-id="0a3c9-154">![处理 JSON 消息的业务流程](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")</span><span class="sxs-lookup"><span data-stu-id="0a3c9-154">![Orchestration to process JSON messages](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a3c9-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a3c9-155">See Also</span></span>  
 [<span data-ttu-id="0a3c9-156">使用 BizTalk Server 处理 JSON 消息</span><span class="sxs-lookup"><span data-stu-id="0a3c9-156">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)