---
title: PartyResolution （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, parties
- orchestrations, examples
- parties, examples
- parties, orchestrations
- examples, routing
- orchestrations, parties
- examples, orchestrations
- examples, messages
- routing, messages
- messages, routing
ms.assetid: 220e6bc5-6f04-4f37-b0d0-f11c2cc14422
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be8d7e33cefd2272490bd2f01243ff03b0e7009a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975419"
---
# <a name="partyresolution-biztalk-server-sample"></a><span data-ttu-id="02c7e-102">PartyResolution （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="02c7e-102">PartyResolution (BizTalk Server Sample)</span></span>
<span data-ttu-id="02c7e-103">PartyResolution 示例演示了如何配合使用 BizTalk 业务流程与参与方解析以将消息路由到两个可能的收件人中的某一个。</span><span class="sxs-lookup"><span data-stu-id="02c7e-103">The PartyResolution sample demonstrates how to use BizTalk orchestrations with party resolution to route messages to one of two possible recipients.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="02c7e-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="02c7e-104">What This Sample Does</span></span>  
 <span data-ttu-id="02c7e-105">本示例运行用于演示以下各个不同角色的多个业务流程：</span><span class="sxs-lookup"><span data-stu-id="02c7e-105">This sample runs multiple orchestrations that demonstrate the following different roles:</span></span>  
  
-   <span data-ttu-id="02c7e-106">买方业务流程：用于启动采购订单 (PO) 消息处理。</span><span class="sxs-lookup"><span data-stu-id="02c7e-106">Buyer orchestration, used to initiate the purchase order (PO) message processing.</span></span>  
  
-   <span data-ttu-id="02c7e-107">供应商业务流程：用于演示入站和出站参与方解析。</span><span class="sxs-lookup"><span data-stu-id="02c7e-107">Supplier orchestration, which demonstrates both inbound and outbound party resolution.</span></span>  
  
-   <span data-ttu-id="02c7e-108">ShipmentAgency1 和 ShipmentAgency2 业务流程：用于根据采购订单上的发货目的地响应供应商业务流程。</span><span class="sxs-lookup"><span data-stu-id="02c7e-108">ShipmentAgency1 and ShipmentAgency2 orchestrations, which respond to the supplier orchestration based on the shipment destination in the PO.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="02c7e-109">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="02c7e-109">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="02c7e-110">参与方解析是指确定发送消息的参与方的过程。</span><span class="sxs-lookup"><span data-stu-id="02c7e-110">Party resolution refers to the process of determining who (that is, what party) sends a message.</span></span> <span data-ttu-id="02c7e-111">例如，你可能希望只让已知参与方发送消息。</span><span class="sxs-lookup"><span data-stu-id="02c7e-111">For example, you may want to enable only known parties to send a message.</span></span> <span data-ttu-id="02c7e-112">出站参与方解析是指确定应将消息发送给哪些参与方的过程。</span><span class="sxs-lookup"><span data-stu-id="02c7e-112">Outbound party resolution is the process by which you determine which parties should be sent a message.</span></span>  
  
 <span data-ttu-id="02c7e-113">除参与方解析以外，本示例还将演示如何实现和使用角色。</span><span class="sxs-lookup"><span data-stu-id="02c7e-113">In addition to party resolution, this sample demonstrates how to implement and use roles.</span></span> <span data-ttu-id="02c7e-114">例如，若要进行发货，你需要创建一个向其发送文档的发送端口，此文档指示发运方发送产品。</span><span class="sxs-lookup"><span data-stu-id="02c7e-114">For example, to process the shipment of your product, you create a send port to which you send a document instructing a shipper to ship your product.</span></span> <span data-ttu-id="02c7e-115">如果有多个发运方可供选择，则可以在业务流程中创建发运方角色，而不是创建只有发运方 URL 不同的多个发送端口。</span><span class="sxs-lookup"><span data-stu-id="02c7e-115">If you have multiple shippers to choose from, you can create a shipper role in your orchestration rather than create multiple send ports whose only difference is the shipper's URL.</span></span> <span data-ttu-id="02c7e-116">然后，你可以将与产品发货有关的消息发送给该发运方角色。</span><span class="sxs-lookup"><span data-stu-id="02c7e-116">You can then send messages relating to product shipment to the shipper role.</span></span> <span data-ttu-id="02c7e-117">你需要创建各个参与方，并为每个参与方和参与方证书都关联一个发送端口。</span><span class="sxs-lookup"><span data-stu-id="02c7e-117">You create parties and associate a send port to each party and party certificate.</span></span> <span data-ttu-id="02c7e-118">最后，在发运方角色中登记每个参与方以启用该参与方。</span><span class="sxs-lookup"><span data-stu-id="02c7e-118">Finally, you enlist each party to the shipper role to enable it.</span></span> <span data-ttu-id="02c7e-119">然后，你可在业务流程中动态指定将消息发送到哪个发运方。</span><span class="sxs-lookup"><span data-stu-id="02c7e-119">In the orchestration, you can then dynamically specify which shipper you are sending the message to.</span></span>  
  
 <span data-ttu-id="02c7e-120">本示例还演示了如何使用相关将传入消息与适当的业务流程实例匹配。</span><span class="sxs-lookup"><span data-stu-id="02c7e-120">This sample also demonstrates how to use correlation to match the incoming message to the right orchestration instance.</span></span>  
  
-   <span data-ttu-id="02c7e-121">买方、供应商和发货机构的业务流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="02c7e-121">The business process flows for the buyer, supplier, and shipping agencies are as follows:</span></span>  
  
-   <span data-ttu-id="02c7e-122">买方业务流程：</span><span class="sxs-lookup"><span data-stu-id="02c7e-122">Buyer business process flow:</span></span>  
  
    1.  <span data-ttu-id="02c7e-123">以 .xml 文件的形式从内部部门接收采购订单消息。</span><span class="sxs-lookup"><span data-stu-id="02c7e-123">Receive PO message from internal department as an .xml file.</span></span>  
  
    2.  <span data-ttu-id="02c7e-124">将采购订单消息发送给供应商。</span><span class="sxs-lookup"><span data-stu-id="02c7e-124">Send PO message to supplier.</span></span>  
  
-   <span data-ttu-id="02c7e-125">供应商业务流程：</span><span class="sxs-lookup"><span data-stu-id="02c7e-125">Supplier business process flow:</span></span>  
  
    1.  <span data-ttu-id="02c7e-126">根据签名证书解析参与方（入站参与方解析）以更新源参与方。</span><span class="sxs-lookup"><span data-stu-id="02c7e-126">Resolve the party (inbound party resolution) to update the source party based on signature certificate.</span></span>  
  
    2.  <span data-ttu-id="02c7e-127">从买方接收激活消息（采购订单）。</span><span class="sxs-lookup"><span data-stu-id="02c7e-127">Receive an activation message (PO) from buyer.</span></span>  
  
    3.  <span data-ttu-id="02c7e-128">向买方发送采购订单确认消息。</span><span class="sxs-lookup"><span data-stu-id="02c7e-128">Send a PO Acknowledgement message to buyer.</span></span>  
  
    4.  <span data-ttu-id="02c7e-129">验证要送达的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="02c7e-129">Verify the delivery country/region.</span></span>  
  
    5.  <span data-ttu-id="02c7e-130">解析出站参与方以找到要使用的发货机构。</span><span class="sxs-lookup"><span data-stu-id="02c7e-130">Resolve the outbound party to find which shipping agency to use.</span></span> <span data-ttu-id="02c7e-131">如果国家/地区是美国，则发货机构为 ShipmentAgency2。</span><span class="sxs-lookup"><span data-stu-id="02c7e-131">If the country/region is U.S., the shipping agency is ShipmentAgency2.</span></span> <span data-ttu-id="02c7e-132">如果国家/地区是加拿大，则发货机构为 ShipmentAgency1。</span><span class="sxs-lookup"><span data-stu-id="02c7e-132">If the country/region is Canada, the shipping agency is ShipmentAgency1.</span></span>  
  
    6.  <span data-ttu-id="02c7e-133">向相应的发货机构发送发货订单请求消息。</span><span class="sxs-lookup"><span data-stu-id="02c7e-133">Send a Shipment Order Request message to the appropriate shipping agency.</span></span>  
  
    7.  <span data-ttu-id="02c7e-134">从相应的发货机构接收发货订单确认消息。</span><span class="sxs-lookup"><span data-stu-id="02c7e-134">Receive the Shipment Order Acknowledgement message from the appropriate shipping agency.</span></span>  
  
    8.  <span data-ttu-id="02c7e-135">向相应的发货机构发送发货通知消息。</span><span class="sxs-lookup"><span data-stu-id="02c7e-135">Send a Shipment Advice message to the appropriate shipping agency.</span></span>  
  
    9. <span data-ttu-id="02c7e-136">从相应的发货机构接收发货通知确认消息。</span><span class="sxs-lookup"><span data-stu-id="02c7e-136">Receive a Shipment Advice Acknowledgement message from the appropriate shipping agency.</span></span>  
  
    10. <span data-ttu-id="02c7e-137">将最终的采购订单送达回执消息发送给买方。</span><span class="sxs-lookup"><span data-stu-id="02c7e-137">Send a final PO Delivery Receipt message to the buyer.</span></span>  
  
-   <span data-ttu-id="02c7e-138">发货机构业务流程（两个发货机构的业务流程相同）：</span><span class="sxs-lookup"><span data-stu-id="02c7e-138">Shipping agency business process flow (same for both shipping agencies):</span></span>  
  
    1.  <span data-ttu-id="02c7e-139">从供应商接收发货订单请求消息。</span><span class="sxs-lookup"><span data-stu-id="02c7e-139">Receive the Shipment Order Request message from the supplier.</span></span>  
  
    2.  <span data-ttu-id="02c7e-140">生成并发送发货订单请求消息的确认消息。</span><span class="sxs-lookup"><span data-stu-id="02c7e-140">Generate and send an Acknowledgement message for the Shipment Order Request message.</span></span>  
  
    3.  <span data-ttu-id="02c7e-141">从供应商接收发货通知消息。</span><span class="sxs-lookup"><span data-stu-id="02c7e-141">Receive a Shipment Advice message from the supplier.</span></span>  
  
    4.  <span data-ttu-id="02c7e-142">生成并发送发货通知消息的确认消息。</span><span class="sxs-lookup"><span data-stu-id="02c7e-142">Generate and send an Acknowledgement message for the Shipment Advice message.</span></span>  
  
 <span data-ttu-id="02c7e-143">以下说明解释了此示例是如何设计的：</span><span class="sxs-lookup"><span data-stu-id="02c7e-143">The following statements explain how this sample is designed:</span></span>  
  
-   <span data-ttu-id="02c7e-144">BuyerProcess.odx 业务流程接收消息，然后使用自定义管道 MimePartyResSendPipeline 对该消息进行编码，再将其发送给供应商。</span><span class="sxs-lookup"><span data-stu-id="02c7e-144">The BuyerProcess.odx orchestration receives a message and uses the custom pipeline MimePartyResSendPipeline to encode the message and send it to the supplier.</span></span> <span data-ttu-id="02c7e-145">这是通过使用管道设计器构建和部署自定义发送管道实现的。</span><span class="sxs-lookup"><span data-stu-id="02c7e-145">This is done by using Pipeline Designer to build and deploy a custom send pipeline.</span></span> <span data-ttu-id="02c7e-146">在将消息发送给供应商之前，系统使用在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的 BizTalk 组属性中指定的买方私钥对消息进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="02c7e-146">Before sending the message to the supplier, the message is digitally signed with buyer's private key, which is specified in BizTalk Group Properties in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
-   <span data-ttu-id="02c7e-147">然后，SupplierProcess.odx 业务流程使用自定义管道 MimePartyResReceivePipeline（其中包含 MIME/SMIME 解码器组件）对该消息进行解码，然后使用买方公钥执行入站参与方解析，以解析和验证买方标识。</span><span class="sxs-lookup"><span data-stu-id="02c7e-147">The SupplierProcess.odx orchestration uses the custom pipeline MimePartyResReceivePipeline, which includes a MIME/SMIME decoder component, to decode the message and perform inbound party resolution by using the buyer's public key to resolve and validate the buyer's identity.</span></span> <span data-ttu-id="02c7e-148">这是通过构建和部署自定义接收管道实现的。</span><span class="sxs-lookup"><span data-stu-id="02c7e-148">This is done by building and deploying a custom receive pipeline.</span></span>  
  
-   <span data-ttu-id="02c7e-149">供应商业务流程随后启动 POCorrelationSets，后者被定义为基于升级属性 PONo。</span><span class="sxs-lookup"><span data-stu-id="02c7e-149">The supplier orchestration then initiates the POCorrelationSets which is defined to base on a promoted property - PONo.</span></span> <span data-ttu-id="02c7e-150">PONo 用于在后面的阶段中将入站和出站消息与此业务流程实例匹配，因为整个业务流程中包括多个发送和接收操作。</span><span class="sxs-lookup"><span data-stu-id="02c7e-150">The PONo is used to match the inbound and outbound messages to this orchestration instance in the later stage, because there are multiple send and receive actions throughout the entire orchestration.</span></span>  
  
-   <span data-ttu-id="02c7e-151">供应商业务流程实现角色链接，以便处理入站和出站参与方解析。</span><span class="sxs-lookup"><span data-stu-id="02c7e-151">The supplier orchestration implements role links to deal with inbound and outbound party resolution.</span></span> <span data-ttu-id="02c7e-152">供应商业务流程使用两种角色链接类型：</span><span class="sxs-lookup"><span data-stu-id="02c7e-152">The supplier orchestration uses two role link types:</span></span>  
  
    -   <span data-ttu-id="02c7e-153">Buyer_Supplier 角色链接类型</span><span class="sxs-lookup"><span data-stu-id="02c7e-153">Buyer_Supplier role link type</span></span>  
  
    -   <span data-ttu-id="02c7e-154">Supplier_Shipment 角色链接类型</span><span class="sxs-lookup"><span data-stu-id="02c7e-154">Supplier_Shipment role link type</span></span>  
  
-   <span data-ttu-id="02c7e-155">在 Buyer_Supplier**角色链接**形状，供应商正在将提供程序角色，因为供应商购买者从接收第一条消息，买方在使用者角色中。</span><span class="sxs-lookup"><span data-stu-id="02c7e-155">In the Buyer_Supplier **Role Link** shape, the supplier is in the Provider role and the buyer is in the Consumer role because the supplier receives the first message from the buyer.</span></span> <span data-ttu-id="02c7e-156">当供应商业务流程向买方角色发送确认消息时，有一个发送端口与买方相关联，该消息通过此指定发送端口发送给买方。</span><span class="sxs-lookup"><span data-stu-id="02c7e-156">When the supplier orchestration sends the acknowledgment to the buyer role, there is a send port associated with the buyer, and the message is sent to the buyer through the specified send port.</span></span> <span data-ttu-id="02c7e-157">若要查找发送端口，右键单击**BuyerAgency**中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-157">To find the send port, right-click **BuyerAgency** in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console and then click **Properties**.</span></span> <span data-ttu-id="02c7e-158">发送端口将显示在**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-158">The send port is displayed under **Send Ports**.</span></span>  
  
-   <span data-ttu-id="02c7e-159">然后，此业务流程使用以下表达式返回合作伙伴信息，并通过调用名为 CheckPartyName 的外部程序集将一个 XML 文件写入一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="02c7e-159">The orchestration then uses the following expression to return the partner information, and writes an XML file to a folder through a call to an external assembly named CheckPartyName.</span></span>  
  
    ```  
    Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty)  
    ```  
  
-   <span data-ttu-id="02c7e-160">在 Supplier_Shipment**角色链接**形状，装运角色包含具有用于将消息从供应商发送到对相应传送一家旅行社具体取决于目标方的两个操作发送端口。</span><span class="sxs-lookup"><span data-stu-id="02c7e-160">In the Supplier_Shipment **Role Link** shape, the Shipment role contains a send port with two operations that are used to send the message from the supplier to the appropriate shipping agency depending on the destination party.</span></span> <span data-ttu-id="02c7e-161">供应商角色包含一个具有两个操作的接收端口，这两个操作用于从发货机构接收响应。</span><span class="sxs-lookup"><span data-stu-id="02c7e-161">The Supplier role contains a receive port with two operations that are used to receive the response from the shipping agency.</span></span> <span data-ttu-id="02c7e-162">在发送和接收这些消息时将使用相关，该相关基于 PONo。</span><span class="sxs-lookup"><span data-stu-id="02c7e-162">The correlation is used when sending and receiving these messages, and it is based on the PONo.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02c7e-163">在绑定供应商业务流程时，你将发现只有一个发送端口和两个接收端口需要绑定。</span><span class="sxs-lookup"><span data-stu-id="02c7e-163">When you bind the supplier orchestration, you will find that only one send port and two receive ports need to be bound.</span></span> <span data-ttu-id="02c7e-164">这是因为到目标参与方的发送端口已与目标参与方绑定。</span><span class="sxs-lookup"><span data-stu-id="02c7e-164">This is because the send ports to the destination parties are already bound with the parties.</span></span> <span data-ttu-id="02c7e-165">此外，业务流程中的接收端口之一包含两个接收操作，因此即使你看到三个**接收**形状，其中只有两个需要绑定。</span><span class="sxs-lookup"><span data-stu-id="02c7e-165">Moreover, one of the receive ports in the orchestration contains two receive operations, so even if you see three **Receive** shapes, only two of them need to be bound.</span></span>  
  
-   <span data-ttu-id="02c7e-166">供应商业务流程使用以下代码中的第一行，通过调用名为 QueryShipmentCatalogComponent 的外部程序集来获取发货机构。</span><span class="sxs-lookup"><span data-stu-id="02c7e-166">The supplier orchestration uses the first line in the following code to get the shipment agency by calling an external assembly named QueryShipmentCatalogComponent.</span></span> <span data-ttu-id="02c7e-167">然后，此业务流程使用第二行为发货角色设置目标参与方。</span><span class="sxs-lookup"><span data-stu-id="02c7e-167">It then uses the second line to set the destination party for the shipment role.</span></span>  
  
    ```  
    strShipmentName= objQueryShipmentCatalog.GetShipmentDetails(POMessage.MessagePart_1.POHeader.Address.Country);  
    Supplier_Shipment(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party(strShipmentName,"OrganizationName");  
    ```  
  
-   <span data-ttu-id="02c7e-168">生成 Shipper1Process.odx 和 Shipper2Process.odx 以从 SupplierProcess.odx 接收发货订单和发货通知，并将响应发送回 SupplierProcess.odx。</span><span class="sxs-lookup"><span data-stu-id="02c7e-168">Shipper1Process.odx and Shipper2Process.odx are built to receive the shipping order and the shipping advice from SupplierProcess.odx and to send the response back to SupplierProcess.odx.</span></span> <span data-ttu-id="02c7e-169">在这两个发运方业务流程中都将使用相关，且相关类型基于已升级的属性 PONo。</span><span class="sxs-lookup"><span data-stu-id="02c7e-169">In both of the shipper orchestrations, correlation is used, and the correlation type is based on the promoted property PONo.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="02c7e-170">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="02c7e-170">Where to Find This Sample</span></span>  
 <span data-ttu-id="02c7e-171">*\<示例路径\>* \Orchestrations\PartyResolution\\</span><span class="sxs-lookup"><span data-stu-id="02c7e-171">*\<Samples Path\>* \Orchestrations\PartyResolution\\</span></span>  
  
 <span data-ttu-id="02c7e-172">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="02c7e-172">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="02c7e-173">文件</span><span class="sxs-lookup"><span data-stu-id="02c7e-173">File(s)</span></span>|<span data-ttu-id="02c7e-174">Description</span><span class="sxs-lookup"><span data-stu-id="02c7e-174">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02c7e-175">BuyerBinding.xml、ShippingAgency1Binding.xml、ShippingAgency2Binding.xml 和 SupplierBinding.xml</span><span class="sxs-lookup"><span data-stu-id="02c7e-175">BuyerBinding.xml, ShippingAgency1Binding.xml, ShippingAgency2Binding.xml, SupplierBinding.xml</span></span>|<span data-ttu-id="02c7e-176">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="02c7e-176">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="02c7e-177">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="02c7e-177">Cleanup.bat</span></span>|<span data-ttu-id="02c7e-178">用于取消部署程序集并从全局程序集缓存中删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="02c7e-178">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="02c7e-179">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="02c7e-179">Removes send and receive ports.</span></span> <span data-ttu-id="02c7e-180">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="02c7e-180">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="02c7e-181">PartyResolution.sln</span><span class="sxs-lookup"><span data-stu-id="02c7e-181">PartyResolution.sln</span></span>|<span data-ttu-id="02c7e-182">包含各种子文件夹中的所有项目的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="02c7e-182">Solution file that contains all of the projects in the various subfolders.</span></span>|  
|<span data-ttu-id="02c7e-183">PurchaseOrder.xml</span><span class="sxs-lookup"><span data-stu-id="02c7e-183">PurchaseOrder.xml</span></span>|<span data-ttu-id="02c7e-184">示例输入采购订单。</span><span class="sxs-lookup"><span data-stu-id="02c7e-184">Sample input PO.</span></span>|  
|<span data-ttu-id="02c7e-185">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="02c7e-185">Setup.bat</span></span>|<span data-ttu-id="02c7e-186">用于生成和初始化本示例的各个部分。</span><span class="sxs-lookup"><span data-stu-id="02c7e-186">Used to build and initialize portions of this sample.</span></span>|  
|<span data-ttu-id="02c7e-187">在 \Buyer 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="02c7e-187">In the \Buyer folder:</span></span><br /><br /> <span data-ttu-id="02c7e-188">Buyer.btproj、BuyerProcess.odx</span><span class="sxs-lookup"><span data-stu-id="02c7e-188">Buyer.btproj, BuyerProcess.odx</span></span>|<span data-ttu-id="02c7e-189">用于实现本示例中的买方的 BizTalk 项目和业务流程。</span><span class="sxs-lookup"><span data-stu-id="02c7e-189">BizTalk project and orchestration used to implement the buyer in this sample.</span></span>|  
|<span data-ttu-id="02c7e-190">在 \Catalog 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="02c7e-190">In the \Catalog folder:</span></span><br /><br /> <span data-ttu-id="02c7e-191">Catalog.xml</span><span class="sxs-lookup"><span data-stu-id="02c7e-191">Catalog.xml</span></span>|<span data-ttu-id="02c7e-192">用于根据采购订单中指定的发货目的地确定发货机构。</span><span class="sxs-lookup"><span data-stu-id="02c7e-192">Used to determine shipment agency based on shipping destination specified in the PO.</span></span>|  
|<span data-ttu-id="02c7e-193">在 \CheckPartyName 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="02c7e-193">In the \CheckPartyName folder:</span></span><br /><br /> <span data-ttu-id="02c7e-194">AssemblyInfo.cs、CheckPartyName.csproj 和 Class1.cs</span><span class="sxs-lookup"><span data-stu-id="02c7e-194">AssemblyInfo.cs, CheckPartyName.csproj, Class1.cs</span></span>|<span data-ttu-id="02c7e-195">用于访问源参与方属性的 CheckPartyName 应用程序的 Microsoft Visual C# 项目和源文件。</span><span class="sxs-lookup"><span data-stu-id="02c7e-195">Microsoft Visual C# project and source files for the CheckPartyName application used to access the properties of the source party.</span></span>|  
|<span data-ttu-id="02c7e-196">在 \FilePolling 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="02c7e-196">In the \FilePolling folder:</span></span><br /><br /> <span data-ttu-id="02c7e-197">App.ico、AssemblyInfo.cs、FilePolling.cs、FilePolling.csproj、FilePolling.resx 和 FilePolling.sln</span><span class="sxs-lookup"><span data-stu-id="02c7e-197">App.ico, AssemblyInfo.cs, FilePolling.cs, FilePolling.csproj, FilePolling.resx, FilePolling.sln,</span></span>|<span data-ttu-id="02c7e-198">FilePolling 应用程序的 Visual C# 解决方案、项目、源文件以及相关文件。</span><span class="sxs-lookup"><span data-stu-id="02c7e-198">Visual C# solution, project, source, and associated files for the FilePolling application.</span></span><br /><br /> <span data-ttu-id="02c7e-199">使用此应用程序可了解此自动化方案的进展情况。</span><span class="sxs-lookup"><span data-stu-id="02c7e-199">Use this application to keep informed about the progressing state of this automated scenario.</span></span>|  
|<span data-ttu-id="02c7e-200">在 \Pipeline\projectschema 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="02c7e-200">In the \Pipeline\projectschema folder:</span></span><br /><br /> <span data-ttu-id="02c7e-201">MimePartyResReceivePipeline.btp、MimePartyResSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="02c7e-201">MimePartyResReceivePipeline.btp, MimePartyResSendPipeline.btp</span></span>|<span data-ttu-id="02c7e-202">本示例中的各个不同角色使用的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管道文件。</span><span class="sxs-lookup"><span data-stu-id="02c7e-202">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline files used by the different roles in this sample.</span></span>|  
|<span data-ttu-id="02c7e-203">在 \QueryShipmentCatalogComponent 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="02c7e-203">In the \QueryShipmentCatalogComponent folder:</span></span><br /><br /> <span data-ttu-id="02c7e-204">AssemblyInfo.cs、QueryShipmentCatalog.cs 和 QueryShipmentCatalogComponent.csproj</span><span class="sxs-lookup"><span data-stu-id="02c7e-204">AssemblyInfo.cs, QueryShipmentCatalog.cs, QueryShipmentCatalogComponent.csproj</span></span>|<span data-ttu-id="02c7e-205">QueryShipmentCatalog 组件的 Visual C# 项目和源文件，该组件用于访问在 Catalog.xml 文件中定义的发货目录。</span><span class="sxs-lookup"><span data-stu-id="02c7e-205">Visual C# project and source files for the QueryShipmentCatalog component used to access the shipment catalog defined in the file Catalog.xml.</span></span><br /><br /> <span data-ttu-id="02c7e-206">QueryShipmentCatalog 组件确定供应商要使用的发货机构。</span><span class="sxs-lookup"><span data-stu-id="02c7e-206">The QueryShipmentCatalog component determines which shipment agency the supplier will use.</span></span> <span data-ttu-id="02c7e-207">它使用 Catalog.xml 中的数据，根据地理位置确定最佳发运方。</span><span class="sxs-lookup"><span data-stu-id="02c7e-207">It uses data from Catalog.xml to determine the best shipper based on geography.</span></span>|  
|<span data-ttu-id="02c7e-208">在 \Schemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="02c7e-208">In the \Schemas folder:</span></span><br /><br /> <span data-ttu-id="02c7e-209">PODeliveryReceipt.xsd、POPropertySchema.xsd、PurchaseOrder.xsd、PurchaseOrderAcknowledgement.xsd、Schemas.btproj、ShipmentAdvice.xsd、ShipmentAdviceAcknowledgement.xsd、ShipmentOrderAcknowledgement.xsd 和 ShipmentOrderRequest.xsd</span><span class="sxs-lookup"><span data-stu-id="02c7e-209">PODeliveryReceipt.xsd, POPropertySchema.xsd, PurchaseOrder.xsd, PurchaseOrderAcknowledgement.xsd, Schemas.btproj, ShipmentAdvice.xsd, ShipmentAdviceAcknowledgement.xsd, ShipmentOrderAcknowledgement.xsd, ShipmentOrderRequest.xsd</span></span>|<span data-ttu-id="02c7e-210">本示例中的各种角色使用的架构。</span><span class="sxs-lookup"><span data-stu-id="02c7e-210">Schemas used by the various roles in this sample.</span></span>|  
|<span data-ttu-id="02c7e-211">在 \ShipmentAgency1 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="02c7e-211">In the \ShipmentAgency1 folder:</span></span><br /><br /> <span data-ttu-id="02c7e-212">ShipmentAdviceAck.btm、ShipmentAgency1.btproj、ShipmentOrderAck.btm 和 Shipper1Process.odx</span><span class="sxs-lookup"><span data-stu-id="02c7e-212">ShipmentAdviceAck.btm, ShipmentAgency1.btproj, ShipmentOrderAck.btm, Shipper1Process.odx</span></span>|<span data-ttu-id="02c7e-213">用于实现本示例中的 ShipmentAgency1 的 BizTalk 项目、业务流程和映射。</span><span class="sxs-lookup"><span data-stu-id="02c7e-213">BizTalk project, orchestration, and maps used to implement ShipmentAgency1 in this sample.</span></span>|  
|<span data-ttu-id="02c7e-214">在 \ShipmentAgency2 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="02c7e-214">In the \ShipmentAgency2 folder:</span></span><br /><br /> <span data-ttu-id="02c7e-215">ShipmentAdviceAck.btm、ShipmentAgency2.btproj、ShipmentOrderAck.btm 和 Shipper2Process.odx</span><span class="sxs-lookup"><span data-stu-id="02c7e-215">ShipmentAdviceAck.btm, ShipmentAgency2.btproj, ShipmentOrderAck.btm, Shipper2Process.odx</span></span>|<span data-ttu-id="02c7e-216">用于实现本示例中的 ShipmentAgency2 的 BizTalk 项目、业务流程和映射。</span><span class="sxs-lookup"><span data-stu-id="02c7e-216">BizTalk project, orchestration, and maps used to implement ShipmentAgency2 in this sample.</span></span>|  
|<span data-ttu-id="02c7e-217">在 \Supplier 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="02c7e-217">In the \Supplier folder:</span></span><br /><br /> <span data-ttu-id="02c7e-218">PO_POAck.btm、PO_ShipmentOrderRequest.btm、ShipmentAdviceAck_PODeliveryReceipt.btm、ShipmentOrder_ShipmentAdvice.btm、Supplier.btproj 和 SupplierProcess.odx</span><span class="sxs-lookup"><span data-stu-id="02c7e-218">PO_POAck.btm, PO_ShipmentOrderRequest.btm, ShipmentAdviceAck_PODeliveryReceipt.btm, ShipmentOrder_ShipmentAdvice.btm, Supplier.btproj, SupplierProcess.odx</span></span>|<span data-ttu-id="02c7e-219">用于实现本示例中的供应商的 BizTalk 项目、业务流程和映射。</span><span class="sxs-lookup"><span data-stu-id="02c7e-219">BizTalk project, orchestration, and maps used to implement the supplier in this sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="02c7e-220">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="02c7e-220">Building and Initializing This Sample</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02c7e-221">在生成并初始化本示例之前，需要确保将默认 BizTalk 进程内主机配置为“受信任验证”。</span><span class="sxs-lookup"><span data-stu-id="02c7e-221">Before you build and initialize this sample, you need to make sure that the default BizTalk In-Process Host is configured as Authentication Trusted.</span></span> <span data-ttu-id="02c7e-222">有关详细信息，请参阅[BizTalk Server 运行时安全建议](../core/biztalk-server-runtime-security-recommendations.md)。</span><span class="sxs-lookup"><span data-stu-id="02c7e-222">For more information, see [BizTalk Server Runtime Security Recommendations](../core/biztalk-server-runtime-security-recommendations.md).</span></span>  
  
 <span data-ttu-id="02c7e-223">64 位主机实例不支持 MIME 管道组件。</span><span class="sxs-lookup"><span data-stu-id="02c7e-223">The MIME pipeline component is not supported in a 64-bit host instance.</span></span> <span data-ttu-id="02c7e-224">与文件适配器的发送和接收处理程序相关联的主机必须配置为仅 32 位主机。</span><span class="sxs-lookup"><span data-stu-id="02c7e-224">The host associated with the send and receive handler for the file adapter must be configured as a 32-bit only host.</span></span> <span data-ttu-id="02c7e-225">有关详细信息此，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="02c7e-225">For more information on this see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span> <span data-ttu-id="02c7e-226">如果你已具有 32 位唯一的一个主机配置在系统上，并想要使用它，请参阅[配置文件适配器](../core/configure-the-file-adapter.md)配置与文件适配器相关联的主机的说明发送和接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="02c7e-226">If you already have a 32-bit only host configured on the system, and want to use it, see [Configuring the File Adapter](../core/configure-the-file-adapter.md) for instructions on configuring the host(s) associated to the file adapter’s send and receive handler.</span></span>  
  
 <span data-ttu-id="02c7e-227">本部分中提及的证书必须添加到为默认 BizTalk 进程内主机实例（将对消息进行签名）配置的登录帐户的“个人”存储中。</span><span class="sxs-lookup"><span data-stu-id="02c7e-227">The certificate mentioned in this section must to be added to the Personal store of the Logon account configured for the default BizTalk In-Process host instance which will be signing messages.</span></span>  
  
 <span data-ttu-id="02c7e-228">默认情况下，下面提到的 setup.bat 文件会将参与方解析示例添安装到默认 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="02c7e-228">By default the setup.bat file mentioned below will install the Party Resolution sample into the default [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="02c7e-229">你可以修改 setup.bat 文件以将该示例部署到新的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中，方法是打开 setup.bat 文件，并将本部分前面的语句 `@ECHO Deploy Assemblies...` 替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="02c7e-229">You can modify the setup.bat file to deploy the sample into a new [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application by opening the setup.bat file and replacing the section preceded by the statement `@ECHO Deploy Assemblies...` with the following:</span></span>  
  
```  
@ECHO Deploy Assemblies...  
  
btstask AddApp -ApplicationName:PartyResolutionSample -Description:"Party Resolution Orchestration sample from the SDK"  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Schemas\bin\Release\Schemas.dll -Options:GacOnAdd  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Pipeline\projectschema\bin\Release\ProjectSchema.dll -Options:GacOnAdd   
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Buyer\bin\Release\Buyer.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%BuyerBindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:ShipmentAgency1\bin\Release\ShipmentAgency1.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%ShipmentAgency1BindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:ShipmentAgency2\bin\Release\ShipmentAgency2.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%ShipmentAgency2BindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Supplier\bin\Release\Supplier.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%SupplierBindingFileName%  
```  
  
#### <a name="to-build-and-initialize-the-partyresolution-sample"></a><span data-ttu-id="02c7e-230">生成并初始化 PartyResolution 示例</span><span class="sxs-lookup"><span data-stu-id="02c7e-230">To build and initialize the PartyResolution sample</span></span>  
  
1.  <span data-ttu-id="02c7e-231">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="02c7e-231">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="02c7e-232">\<*示例路径*> \Orchestrations\PartyResolution</span><span class="sxs-lookup"><span data-stu-id="02c7e-232">\<*Samples Path*>\Orchestrations\PartyResolution</span></span>  
  
2.  <span data-ttu-id="02c7e-233">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="02c7e-233">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="02c7e-234">编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目对于此示例，并部署生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="02c7e-234">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, and deploys the resulting assemblies.</span></span>  
  
    -   <span data-ttu-id="02c7e-235">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="02c7e-235">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports.</span></span>  
  
         <span data-ttu-id="02c7e-236">在设置过程中，你可能会接收到以下警告或类似警告。</span><span class="sxs-lookup"><span data-stu-id="02c7e-236">You may receive the following or similar warnings during the setup process.</span></span> <span data-ttu-id="02c7e-237">你可以放心地忽略它们。</span><span class="sxs-lookup"><span data-stu-id="02c7e-237">You can safely ignore them.</span></span>  
  
        ```  
        "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\PartyResolution.sln" (Buildtarget) (1) ->  
        "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj" (default target) (5) ->  
        "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj" (default target) (5:2) ->  
        (CompileODX target) ->  
          C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\SupplierProcess.odx(831,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it [C:\ProgramFiles\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj]  
          C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\SupplierProcess.odx(841,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it [C:\ProgramFiles\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj]  
  
        ```  
  
3.  <span data-ttu-id="02c7e-238">启动**Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-238">Start **Visual Studio Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="02c7e-239">键入下述命令将这些程序集安装到全局程序集缓存中：</span><span class="sxs-lookup"><span data-stu-id="02c7e-239">Type the following commands to install the assemblies to the global assembly cache:</span></span>  
  
    -   <span data-ttu-id="02c7e-240">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Schemas\bin\Release\schemas.dll</span><span class="sxs-lookup"><span data-stu-id="02c7e-240">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Schemas\bin\Release\schemas.dll</span></span>  
  
    -   <span data-ttu-id="02c7e-241">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Pipeline\projectschema\bin\Release\ProjectSchema.dll</span><span class="sxs-lookup"><span data-stu-id="02c7e-241">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Pipeline\projectschema\bin\Release\ProjectSchema.dll</span></span>  
  
    -   <span data-ttu-id="02c7e-242">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Buyer\bin\Release\Buyer.dll</span><span class="sxs-lookup"><span data-stu-id="02c7e-242">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Buyer\bin\Release\Buyer.dll</span></span>  
  
    -   <span data-ttu-id="02c7e-243">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency1\bin\Release\ShipmentAgency1.dll</span><span class="sxs-lookup"><span data-stu-id="02c7e-243">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency1\bin\Release\ShipmentAgency1.dll</span></span>  
  
    -   <span data-ttu-id="02c7e-244">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency2\bin\Release\ShipmentAgency2.dll</span><span class="sxs-lookup"><span data-stu-id="02c7e-244">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency2\bin\Release\ShipmentAgency2.dll</span></span>  
  
    -   <span data-ttu-id="02c7e-245">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Supplier\bin\Release\Supplier.dll</span><span class="sxs-lookup"><span data-stu-id="02c7e-245">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Supplier\bin\Release\Supplier.dll</span></span>  
  
5.  <span data-ttu-id="02c7e-246">从证书颁发机构 (CA) 获得安全的电子邮件证书。</span><span class="sxs-lookup"><span data-stu-id="02c7e-246">Obtain a secured e-mail certificate from a certificate authority (CA).</span></span> <span data-ttu-id="02c7e-247">CA 可以是第三方颁发机构，也可以是你所在组织的颁发机构。</span><span class="sxs-lookup"><span data-stu-id="02c7e-247">The CA could be a third-party authority or the authority within your organization.</span></span> <span data-ttu-id="02c7e-248">获得证书后，导出公钥和私钥。</span><span class="sxs-lookup"><span data-stu-id="02c7e-248">After you obtain the certificate, export the public key and private key.</span></span>  
  
6.  <span data-ttu-id="02c7e-249">若要将私钥导入主机实例登录帐户的“个人”存储区中，并将公钥导入本地计算机的“其他人”存储区中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="02c7e-249">To import the private key to the Personal store of the Host instance logon account and the public key to the Local Computer Other People store, do the following:</span></span>  
  
    1.  <span data-ttu-id="02c7e-250">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开 BizTalk 组，然后展开**平台设置**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-250">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand the BizTalk Group, and then expand **Platform Settings**.</span></span>  
  
    2.  <span data-ttu-id="02c7e-251">单击**主机实例**并查找显示默认进程内主机实例的登录帐户。</span><span class="sxs-lookup"><span data-stu-id="02c7e-251">Click on **Host Instances** and find the Logon account shown for the default In-Process host instance.</span></span> <span data-ttu-id="02c7e-252">在默认安装中，默认的进程内主机的名称应为 BizTalkServerApplication。</span><span class="sxs-lookup"><span data-stu-id="02c7e-252">In a default installation the default In-Process host should be named BizTalkServerApplication.</span></span>  
  
    3.  <span data-ttu-id="02c7e-253">单击 **“启动”**，再单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-253">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="02c7e-254">在**运行**框中，键入**mmc.exe**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-254">In the **Run** box, type **mmc.exe**, and then click **OK**.</span></span> <span data-ttu-id="02c7e-255">为主机实例登录帐户输入正确的密码以打开该帐户下的 Microsoft 管理控制台 (MMC)。</span><span class="sxs-lookup"><span data-stu-id="02c7e-255">Enter the correct password for the host instance logon account to open the Microsoft Management Console (MMC) under that account.</span></span>  
  
    4.  <span data-ttu-id="02c7e-256">在“文件”  菜单上，单击“添加/删除管理单元” 。</span><span class="sxs-lookup"><span data-stu-id="02c7e-256">On the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
    5.  <span data-ttu-id="02c7e-257">在**添加或删除管理单元**对话框中，选择**证书**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-257">In the **Add or Remove Snap-ins** dialog box, select **Certificates**, and then click **Add**.</span></span>  
  
    6.  <span data-ttu-id="02c7e-258">在**证书管理单元**对话框中，选择**我的用户帐户**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-258">In the **Certificates snap-in** dialog box, select **My user account**, and then click **Finish**.</span></span>  
  
    7.  <span data-ttu-id="02c7e-259">在**添加或删除管理单元**对话框中，选择**证书**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-259">In the **Add or Remove Snap-ins** dialog box, select **Certificates**, and then click **Add**.</span></span>  
  
    8.  <span data-ttu-id="02c7e-260">在**证书管理单元**对话框中，选择**计算机帐户**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-260">In the **Certificates snap-in** dialog box, select **Computer account**, and then click **Next**.</span></span>  
  
    9. <span data-ttu-id="02c7e-261">在**选择计算机**对话框中，选择**本地计算机**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-261">In the **Select Computer** dialog box, select **Local computer**, and then click **Finish**.</span></span>  
  
    10. <span data-ttu-id="02c7e-262">在**添加或删除管理单元**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-262">In the **Add or Remove Snap-ins** dialog box, click **OK**.</span></span>  
  
    11. <span data-ttu-id="02c7e-263">展开**证书-当前用户**节点，然后展开**个人**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-263">Expand the **Certificates - Current User** node and then expand **Personal**.</span></span> <span data-ttu-id="02c7e-264">右键单击**证书**，单击**所有任务**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-264">Right-click **Certificates**, click **All Tasks**, and then click **Import**.</span></span>  
  
    12. <span data-ttu-id="02c7e-265">导入私钥，并在向导中提供密码。</span><span class="sxs-lookup"><span data-stu-id="02c7e-265">Import the private key and provide a password in the wizard.</span></span>  
  
    13. <span data-ttu-id="02c7e-266">展开**证书 （本地计算机）** 节点，然后展开**其他人**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-266">Expand the **Certificates (Local Computer)** node and then expand **Other People**.</span></span> <span data-ttu-id="02c7e-267">右键单击**证书**，单击**所有任务**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-267">Right-click **Certificates**, click **All Tasks**, and then click **Import**.</span></span>  
  
    14. <span data-ttu-id="02c7e-268">导入公钥。</span><span class="sxs-lookup"><span data-stu-id="02c7e-268">Import the public key.</span></span>  
  
7.  <span data-ttu-id="02c7e-269">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**BizTalk 组**节点，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-269">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **BizTalk Group** node and then click **Properties**.</span></span> <span data-ttu-id="02c7e-270">在**BizTalk 组-组属性**对话框中，选择**证书**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-270">In the **BizTalk Group - Group Properties** dialog box, select **Certificate**.</span></span>  
  
8.  <span data-ttu-id="02c7e-271">在**证书**对话框中，单击**浏览**和选择你刚导入的私钥。</span><span class="sxs-lookup"><span data-stu-id="02c7e-271">In the **Certificate** dialog box, click **Browse** and select the private key you just imported.</span></span> <span data-ttu-id="02c7e-272">此处指定的证书用于对出站消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="02c7e-272">The certificate specified here is used to sign the outbound message.</span></span> <span data-ttu-id="02c7e-273">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-273">Click **OK**.</span></span>  
  
9. <span data-ttu-id="02c7e-274">若要更新本示例中的 BuyerAgency 参与方，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="02c7e-274">To update the BuyerAgency party in this sample do the following:</span></span>  
  
    1.  <span data-ttu-id="02c7e-275">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，选择**方**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-275">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, select **Parties**.</span></span>  
  
    2.  <span data-ttu-id="02c7e-276">右键单击**BuyerAgency** ，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-276">Right-click **BuyerAgency** and then click **Properties**.</span></span> <span data-ttu-id="02c7e-277">在**BuyerAgency 的参与方属性**对话框中，选择**常规**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-277">In the **BuyerAgency - Party Properties** dialog box, select **General**.</span></span>  
  
    3.  <span data-ttu-id="02c7e-278">下**别名**部分的对话框中，添加具有名称和限定符设置为新的别名**WindowsUser**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-278">Under the **Aliases** section of the dialog, add a new alias with the name and qualifier set to **WindowsUser**.</span></span> <span data-ttu-id="02c7e-279">将值设置为用户名称的格式\<域 \ 用户名 > (例如 SOMEDOMAIN\someuser)。</span><span class="sxs-lookup"><span data-stu-id="02c7e-279">Set the Value to a user name in format of \<domain\user name> (e.g. SOMEDOMAIN\someuser).</span></span>  
  
    4.  <span data-ttu-id="02c7e-280">选择**证书**，然后单击**浏览**，然后选择你刚导入的公钥。</span><span class="sxs-lookup"><span data-stu-id="02c7e-280">Select **Certificate** and then click **Browse** and select the public key you just imported.</span></span> <span data-ttu-id="02c7e-281">此处指定的证书将用于验证入站消息的发送方标识。</span><span class="sxs-lookup"><span data-stu-id="02c7e-281">The certificate specified here is used to validate the sender identity of the inbound message.</span></span> <span data-ttu-id="02c7e-282">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-282">Click **OK**.</span></span>  
  
10. <span data-ttu-id="02c7e-283">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，然后选择**主机**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-283">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Platform Settings**, and then select **Hosts**.</span></span>  
  
11. <span data-ttu-id="02c7e-284">右键单击**BizTalkServerApplication** ，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-284">Right-click **BizTalkServerApplication** and then click **Properties**.</span></span> <span data-ttu-id="02c7e-285">在**BizTalkServerApplication-主机属性**对话框中，选择**证书**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-285">In the **BizTalkServerApplication - Host Properties** dialog box, select **Certificates**.</span></span>  
  
12. <span data-ttu-id="02c7e-286">单击**浏览**和选择你刚导入的私钥。</span><span class="sxs-lookup"><span data-stu-id="02c7e-286">Click **Browse** and select the private key you just imported.</span></span> <span data-ttu-id="02c7e-287">此处指定的证书用于对入站消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="02c7e-287">The certificate specified here is used to decrypt the inbound messages.</span></span> <span data-ttu-id="02c7e-288">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-288">Click **OK**.</span></span>  
  
13. <span data-ttu-id="02c7e-289">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，然后选择**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-289">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Platform Settings**, and then select **Host Instances**.</span></span>  
  
14. <span data-ttu-id="02c7e-290">右键单击**BizTalkServerApplication** ，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-290">Right-click **BizTalkServerApplication** and then click **Restart**.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="02c7e-291">运行本示例</span><span class="sxs-lookup"><span data-stu-id="02c7e-291">Running This Sample</span></span>  
  
#### <a name="to-run-the-partyresolution-sample"></a><span data-ttu-id="02c7e-292">运行 PartyResolution 示例</span><span class="sxs-lookup"><span data-stu-id="02c7e-292">To run the PartyResolution sample</span></span>  
  
1.  <span data-ttu-id="02c7e-293">从以下文件夹中运行 FilePolling.exe：</span><span class="sxs-lookup"><span data-stu-id="02c7e-293">Run FilePolling.exe from the following folder:</span></span>  
  
     <span data-ttu-id="02c7e-294">*\<示例路径 >* \Orchestrations\PartyResolution\FilePolling\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="02c7e-294">*\<Samples Path>* \Orchestrations\PartyResolution\FilePolling\bin\Debug</span></span>  
  
2.  <span data-ttu-id="02c7e-295">单击**开始轮询**。</span><span class="sxs-lookup"><span data-stu-id="02c7e-295">Click **Start polling**.</span></span>  
  
3.  <span data-ttu-id="02c7e-296">将所提供的采购订单实例文件 PurchaseOrder.xml 的副本复制到以下文件夹中：</span><span class="sxs-lookup"><span data-stu-id="02c7e-296">Paste a copy of the provided PO instance file, PurchaseOrder.xml, in the following folder:</span></span>  
  
     <span data-ttu-id="02c7e-297">*\<示例路径 >* \Orchestrations\PartyResolution\FileDrop\PurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="02c7e-297">*\<Samples Path>* \Orchestrations\PartyResolution\FileDrop\PurchaseOrder</span></span>  
  
4.  <span data-ttu-id="02c7e-298">观察以消息框形式提供的通知你本示例进度的消息序列：</span><span class="sxs-lookup"><span data-stu-id="02c7e-298">Observe the sequence of messages that are provided in the form of message boxes that keep you informed about the progress of the sample:</span></span>  
  
    1.  <span data-ttu-id="02c7e-299">供应商从买方接收采购订单的时间。</span><span class="sxs-lookup"><span data-stu-id="02c7e-299">When the supplier receives the PO from the buyer.</span></span>  
  
    2.  <span data-ttu-id="02c7e-300">从发货机构 1 或 2 接收到发货订单请求的时间。</span><span class="sxs-lookup"><span data-stu-id="02c7e-300">When a shipment order request is received from shipment agency 1 or 2.</span></span>  
  
    3.  <span data-ttu-id="02c7e-301">发货机构 1 或 2 接收到发货通知的时间。</span><span class="sxs-lookup"><span data-stu-id="02c7e-301">When a shipment advice is received by shipment agency 1 or 2.</span></span>  
  
    4.  <span data-ttu-id="02c7e-302">供应商向买方发送采购订单送达回执的时间。</span><span class="sxs-lookup"><span data-stu-id="02c7e-302">When the supplier sends the PO delivery receipt to the buyer.</span></span>  
  
5.  <span data-ttu-id="02c7e-303">单击**退出**关闭文件轮询程序。</span><span class="sxs-lookup"><span data-stu-id="02c7e-303">Click **Exit** to close the File Polling program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02c7e-304">你可以编辑的国家/地区标记为"美国"的 PurchaseOrder.xml 中，然后重复步骤 2 和步骤 3。</span><span class="sxs-lookup"><span data-stu-id="02c7e-304">You can edit the Country tag in PurchaseOrder.xml to "US" and then repeat step 2 and step 3.</span></span> <span data-ttu-id="02c7e-305">观察装运顺序现在发送到装运机构 2。</span><span class="sxs-lookup"><span data-stu-id="02c7e-305">Observe that the shipment order is now sent to shipment agency 2.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="02c7e-306">卸载本示例</span><span class="sxs-lookup"><span data-stu-id="02c7e-306">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-partyresolution-sample"></a><span data-ttu-id="02c7e-307">卸载 PartyResolution 示例</span><span class="sxs-lookup"><span data-stu-id="02c7e-307">To uninstall the PartyResolution sample</span></span>  
  
1.  <span data-ttu-id="02c7e-308">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 到\<*示例路径*> \Orchestrations\ PartyResolution\\。</span><span class="sxs-lookup"><span data-stu-id="02c7e-308">At a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to \<*Samples Path*>\Orchestrations\ PartyResolution\\.</span></span>  
  
2.  <span data-ttu-id="02c7e-309">运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="02c7e-309">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c7e-310">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02c7e-310">See Also</span></span>  
 <span data-ttu-id="02c7e-311">[参与方解析管道组件](../core/party-resolution-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="02c7e-311">[Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md) </span></span>  
 <span data-ttu-id="02c7e-312">[如何配置 MIME SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="02c7e-312">[How to Configure the MIME-SMIME Encoder Pipeline Component](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md) </span></span>  
 <span data-ttu-id="02c7e-313">[如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="02c7e-313">[How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md) </span></span>  
 [<span data-ttu-id="02c7e-314">业务流程（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="02c7e-314">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)