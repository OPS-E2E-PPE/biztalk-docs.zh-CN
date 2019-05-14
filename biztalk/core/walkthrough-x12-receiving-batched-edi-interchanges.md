---
title: 演练 (X12):接收批处理的 EDI 交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f6e6e96-39ec-469d-a845-1bfdce6cc0bf
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45aebe254b5620f6bdc5ecd2d525b6e272e9ca69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393743"
---
# <a name="walkthrough-x12-receiving-batched-edi-interchanges"></a><span data-ttu-id="9c5b1-102">演练 (X12):接收批处理的 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="9c5b1-102">Walkthrough (X12): Receiving Batched EDI Interchanges</span></span>
<span data-ttu-id="9c5b1-103">本演练提供了一的分步过程，将创建一个解决方案以接收 EDI 批使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-103">This walkthrough provides a set of step-by-step procedures that creates a solution for receiving EDI batches using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="9c5b1-104">此解决方案演示了两种接收批处理的 EDI 交换的方法：</span><span class="sxs-lookup"><span data-stu-id="9c5b1-104">This solution demonstrates two ways to receive a batched EDI interchange:</span></span>  

- <span data-ttu-id="9c5b1-105">通过将批拆分为其组成事务设置。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-105">By splitting the batch into its constituent transaction sets.</span></span>  

- <span data-ttu-id="9c5b1-106">通过保留交换的交换作为一个文档处理而不拆分事务设置。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-106">By preserving the interchange by processing the interchange as one document without splitting the transaction sets.</span></span>  

  <span data-ttu-id="9c5b1-107">本演练演示如何配置拆分和保留批。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-107">This walkthrough demonstrates how to configure both splitting and preserving batches.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="9c5b1-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="9c5b1-108">Prerequisites</span></span>  
 <span data-ttu-id="9c5b1-109">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  

## <a name="how-the-solution-splits-received-edi-batches"></a><span data-ttu-id="9c5b1-110">解决方案如何拆分接收的 EDI 批</span><span class="sxs-lookup"><span data-stu-id="9c5b1-110">How the Solution Splits Received EDI Batches</span></span>  
 <span data-ttu-id="9c5b1-111">时配置解决方案以将批处理的交换拆分为其组成事务集，解决方案将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9c5b1-111">When you configure the solution to split the batched interchange into its constituent transaction sets, the solution will do the following:</span></span>  

1. <span data-ttu-id="9c5b1-112">接收位置接收批处理的 EDI 交换，它包含从参与方的多个事务集。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-112">The receive location receives a batched EDI interchange containing multiple transaction sets from a party.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-113">显示的顺序可能不是此列表中的事件。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-113">The events in this list may not occur in the order shown.</span></span>  

2. <span data-ttu-id="9c5b1-114">接收管道将拆分为事务集转换为内部 XML 格式其组成事务集收到的交换。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-114">The receive pipeline splits the received interchange into its constituent transaction sets, converting the transaction sets into internal XML format.</span></span>  

3. <span data-ttu-id="9c5b1-115">接收管道将整个交换和组标头的每个事务的上下文从交换集拆分。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-115">The receive pipeline promotes the entire interchange and group headers into the context of each transaction set split from the interchange.</span></span> <span data-ttu-id="9c5b1-116">它还会升级某些特定交换和组标头，如 ISA6、 GS1 和 GS2，以便这些字段可用于路由。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-116">It also promotes certain specific interchange and group headers, such as ISA6, GS1, and GS2, so that these fields can be used for routing.</span></span>  

4. <span data-ttu-id="9c5b1-117">接收管道将每个事务集 XML 文件放入 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-117">The receive pipeline drops each transaction set XML file into the MessageBox.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-118">在此解决方案中，批处理包含相同的消息类型的多个实例。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-118">In this solution, the batch contains multiple instances of the same message type.</span></span>  

5. <span data-ttu-id="9c5b1-119">发送端口提取每个事务集通过订阅适当的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-119">The send port picks up each transaction set by subscribing on an appropriate context property.</span></span>  

6. <span data-ttu-id="9c5b1-120">发送管道生成每个事务集成 EDI 交换，并随后将交换发送到目标。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-120">The send pipeline builds each transaction set into an EDI interchange, and then sends the interchange to the destination.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-121">详细了解如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]拆分事务集在一个批处理中，请参阅[拆分批处理的 EDI 交换](../core/splitting-a-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-121">For more information on how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] splits the transaction sets in a batch, see [Splitting a Batched EDI Interchange](../core/splitting-a-batched-edi-interchange.md).</span></span>  

   <span data-ttu-id="9c5b1-122">下图显示了体系结构和批处理交换中的消息流的解决方案是配置为拆分事务集。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-122">The following figure shows the architecture and message flow of the solution when it is configured to split the transaction sets in the batched interchange.</span></span>  

   <span data-ttu-id="9c5b1-123">![拆分成批的 EDI 交换](../core/media/ef386df6-e195-45d9-abff-4d0bd3a82a4f.gif "ef386df6-e195-45d9-abff-4d0bd3a82a4f")</span><span class="sxs-lookup"><span data-stu-id="9c5b1-123">![Splitting batched EDI interchanges](../core/media/ef386df6-e195-45d9-abff-4d0bd3a82a4f.gif "ef386df6-e195-45d9-abff-4d0bd3a82a4f")</span></span>  

## <a name="how-the-solution-preserves-received-edi-batches"></a><span data-ttu-id="9c5b1-124">解决方案如何保留接收的 EDI 批</span><span class="sxs-lookup"><span data-stu-id="9c5b1-124">How the Solution Preserves Received EDI Batches</span></span>  
 <span data-ttu-id="9c5b1-125">在配置解决方案以保留批处理的交换时，解决方案将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9c5b1-125">When you configure the solution to preserve the batched interchange, the solution will do the following:</span></span>  

1. <span data-ttu-id="9c5b1-126">接收位置接收批处理的 EDI 交换包含来自参与方的多个事务集。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-126">The receive location receives a batched EDI interchange containing multiple transaction sets from the party.</span></span>  

2. <span data-ttu-id="9c5b1-127">接收管道处理交换而不拆分事务集，并将两个事务集作为一个单元为内部 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-127">The receive pipeline process the interchange without splitting the transaction sets, converting the two transaction sets as a unit into internal XML format.</span></span>  

3. <span data-ttu-id="9c5b1-128">如果如交换不是批处理中，使用它将保留的标记应用到的 XML，它将生成的异常，则接收管道将升级相同的属性。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-128">The receive pipeline promotes the same properties as if the interchange were not a batch, with the exception that it will applied a reserved tag to the XML that it generates.</span></span> <span data-ttu-id="9c5b1-129">此标记\<X12InterchangeXml\>对于 X12 编码的 EDI 交换或\<EdifactInterchangeXml\>对于 EDIFACT 编码的 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-129">This tag is \<X12InterchangeXml\> for an X12-encoded EDI interchange or \<EdifactInterchangeXml\> for an EDIFACT-encoded EDI interchange.</span></span> <span data-ttu-id="9c5b1-130">EDI 接收管道还应用上下文属性`ReuseEnvelope`以将交换标识为保留。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-130">The EDI receive pipeline also applies the context property `ReuseEnvelope` to identify the interchange as preserved.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-131">EDI 发送管道使用\<X12InterchangeXml\>或\<EdifactInterchangeXml\>标记来标识为保留批的消息。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-131">The EDI send pipeline uses the \<X12InterchangeXml\> or \<EdifactInterchangeXml\> tag to identify the message as a preserved batch.</span></span> <span data-ttu-id="9c5b1-132">`ReuseEnvelope`上下文属性，可创建用于订阅保留的所有批处理交换的发送端口。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-132">The `ReuseEnvelope` context property enables you to create a send port that subscribes to all batched interchanges that are preserved.</span></span>  

4. <span data-ttu-id="9c5b1-133">接收管道将消息 XML 文件放入 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-133">The receive pipeline drops the message XML file into the MessageBox.</span></span>  

5. <span data-ttu-id="9c5b1-134">发送端口通过订阅适当的上下文属性来提取交换。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-134">The send port picks up the interchange by subscribing on an appropriate context property.</span></span>  

6. <span data-ttu-id="9c5b1-135">发送管道生成的两个事务批处理的 EDI 交换，在 XML 文件中设置，然后将交换发送到目标。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-135">The send pipeline builds the two transaction sets in the XML file into a batched EDI interchange, and then sends the interchange to the destination.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-136">详细了解如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理保留的批，请参阅[保留接收批处理 EDI 交换](../core/preserving-a-received-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-136">For more information on how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes a preserved batch, see [Preserving a Received Batched EDI Interchange](../core/preserving-a-received-batched-edi-interchange.md).</span></span>  

## <a name="functionality-in-this-solution"></a><span data-ttu-id="9c5b1-137">在此解决方案中的功能</span><span class="sxs-lookup"><span data-stu-id="9c5b1-137">Functionality in this Solution</span></span>  
 <span data-ttu-id="9c5b1-138">对于本演练的目的，将启用以下功能：</span><span class="sxs-lookup"><span data-stu-id="9c5b1-138">For the purposes of this walkthrough, the following functionality will be enabled:</span></span>  

-   <span data-ttu-id="9c5b1-139">该解决方案专用于使用 X12 编码而不是 EDIFACT 交换编码。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-139">The solution is designed for interchanges using X12 encoding, not EDIFACT encoding.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="9c5b1-140">用于 HIPAA 和 EDIFACT 编码的配置是近与用于 X12 编码。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-140">The configuration used for HIPAA and for EDIFACT encoding is closely parallel to that used for X12 encoding.</span></span>  

-   <span data-ttu-id="9c5b1-141">不会返回确认技术或功能确认以响应最初接收的交换或发送任何批处理的交换。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-141">Technical or functional acknowledgments will not be returned in response to the interchange originally received or any batched interchange that is sent.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="9c5b1-142">有关生成 EDI 确认的信息，请参阅[演练 (X12):接收 EDI 交换并发送回确认](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-142">For information about generating EDI acknowledgments, see [Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md).</span></span>  

-   <span data-ttu-id="9c5b1-143">此解决方案使用一个单向接收端口和一个静态单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-143">This solution uses a one-way receive port and a static one-way send port.</span></span> <span data-ttu-id="9c5b1-144">将使用 FILE 传输类型配置这些端口。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-144">These ports will be configured with the FILE transport type.</span></span>  

-   <span data-ttu-id="9c5b1-145">将启用 EDI 报告。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-145">EDI reporting will be enabled.</span></span>  

-   <span data-ttu-id="9c5b1-146">事务集将保存以从交换状态报告进行查看。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-146">Transaction sets will be saved for viewing from the interchange status report.</span></span>  

-   <span data-ttu-id="9c5b1-147">出于测试目的，该解决方案到本地文件夹使用发送端口以发送拆分的交换或保留的批。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-147">For testing purposes, the solution uses a send ports to send the split interchanges or the preserved batch to a local folder.</span></span>  

## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="9c5b1-148">配置和测试演练</span><span class="sxs-lookup"><span data-stu-id="9c5b1-148">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="9c5b1-149">此解决方案所需的过程包括：</span><span class="sxs-lookup"><span data-stu-id="9c5b1-149">The procedures required for this solution include the following:</span></span>  

- <span data-ttu-id="9c5b1-150">将必需的消息架构添加到 BizTalk 项目，然后生成并部署该项目，使架构可供使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在处理消息。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-150">Add the required message schema(s) to a BizTalk project, and then build and deploy the project, making the schema(s) available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the messages.</span></span>  

- <span data-ttu-id="9c5b1-151">创建接收端口的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以接收 EDI X12 编码的.txt 批处理输入的消息从参与方。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-151">Create a receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the EDI X12-encoded .txt batched input message from a party.</span></span>  

- <span data-ttu-id="9c5b1-152">创建发送端口的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成每个事务交换设置收到批处理 （如果拆分批） 中或以生成单个交换中接收的批中的事务集 （如果保留批）。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-152">Create a send port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to build an interchange out of each transaction sets received in the batch (if splitting the batch), or to build a single interchange from the transaction sets in the received batch (if preserving the batch).</span></span> <span data-ttu-id="9c5b1-153">然后，发送端口将交换发送，或到目标参与方的交换。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-153">The send port then sends the interchange or interchanges to the destination party.</span></span> <span data-ttu-id="9c5b1-154">此发送端口将是一个静态单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-154">This send port will be a static one-way send port.</span></span>  

- <span data-ttu-id="9c5b1-155">为参与方 A 和参与方 B 创建参与方 （贸易合作伙伴）</span><span class="sxs-lookup"><span data-stu-id="9c5b1-155">Create a party (trading partner) for both Party A and Party B.</span></span>  

- <span data-ttu-id="9c5b1-156">为这两个贸易合作伙伴创建业务配置文件每个。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-156">Create a business profile each for both the trading partners.</span></span>  

- <span data-ttu-id="9c5b1-157">创建通过配置要接收的消息通过拆分或保留交换的 EDI 属性的两个配置文件之间的协议。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-157">Create an agreement between the two profiles by configuring the EDI properties to receive the message by splitting or preserving the interchange.</span></span>  

- <span data-ttu-id="9c5b1-158">一个批处理的 EDI 交换放入与接收位置关联的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-158">Drop one batched EDI interchange into the local folder associated with the receive location.</span></span> <span data-ttu-id="9c5b1-159">然后，您可以验证的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是否已从接收的批 （如果拆分批） 或单个保留的批处理的交换 （如果保留批） 放入与发送端口关联的文件夹将单独的交换。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-159">You can then verify that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has dropped the separate interchanges from the received batch (if splitting the batch) or the single preserved batched interchange (if preserving the batch) into the folder associated with the send port.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="9c5b1-160">如果您已执行中的步骤发送批处理交换演练中，您可以使用该解决方案的输出作为输入此解决方案。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-160">If you have performed the steps in the sending batched interchanges walkthrough, you can use the output from that solution as the input for this solution.</span></span> <span data-ttu-id="9c5b1-161">该解决方案的输出是两个 850 消息批。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-161">The output from that solution is a batch of two 850 messages.</span></span> <span data-ttu-id="9c5b1-162">有关详细信息，请参阅[演练 (X12):发送批处理 EDI 交换](../core/walkthrough-x12-sending-batched-edi-interchanges.md)。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-162">For more information, see [Walkthrough (X12): Sending Batched EDI Interchanges](../core/walkthrough-x12-sending-batched-edi-interchanges.md).</span></span>  

  <span data-ttu-id="9c5b1-163">本部分介绍配置本演练的步骤。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-163">This section describes the procedures to configure the walkthrough.</span></span>  

##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="9c5b1-164">若要部署的消息架构</span><span class="sxs-lookup"><span data-stu-id="9c5b1-164">To deploy the message schema</span></span>  

1. <span data-ttu-id="9c5b1-165">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，创建或打开 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-165">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-166">本主题假定你已从对 BizTalk EDI 应用程序，其中包含 EDI 架构、 管道和业务流程应用程序中添加了一个引用。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-166">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="9c5b1-167">如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-167">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  

2. <span data-ttu-id="9c5b1-168">右键单击你的项目，指向**外**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-168">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="9c5b1-169">将移动到**\<驱动器\>: \Program Files\Microsoft BizTalk Server 2009\XSD_Schema\EDI\X12\00401**，然后双击与测试消息对应的架构。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-169">Move to **\<drive\>:\Program Files\Microsoft BizTalk Server 2009\XSD_Schema\EDI\X12\00401**, and then double-click the schema corresponding to your test message.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-170">如果 EDI 架构尚未解压缩到 XSD_SchemaEDI 文件夹，则执行**MicrosoftEdiXSDTemplates.exe** XSD_SchemaEDI 文件夹将架构解压缩到默认文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-170">If the EDI schemas have not been unzipped into the XSD_SchemaEDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the XSD_SchemaEDI folder to unzip the schemas into the default folder.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="9c5b1-171">对于测试消息，可以使用由发送批处理的交换演练中的解决方案生成的批处理的交换。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-171">For a test message, you can use the batched interchange generated by the solution in the sending batched interchanges walkthrough.</span></span> <span data-ttu-id="9c5b1-172">该解决方案的输出是用于 EDI 接口开发人员教程的 850 示例消息的两个实例一个批。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-172">The output from that solution is a batch of two instances of the 850 sample message used for the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="9c5b1-173">如果这样做，则必须使用 x12_00401_850.xsd 架构位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDKEDI 接口开发人员 TutorialInbound_EDI。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-173">If you do so, you must use the schema x12_00401_850.xsd located in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDKEDI Interface Developer TutorialInbound_EDI.</span></span>  

3. <span data-ttu-id="9c5b1-174">设置程序集密钥文件，然后生成并部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-174">Set the assembly key file, and then build and deploy the assembly.</span></span>  

##### <a name="to-create-a-one-way-receive-port-to-receive-the-batched-edi-messages"></a><span data-ttu-id="9c5b1-175">若要创建一个单向接收端口以接收批处理的 EDI 消息</span><span class="sxs-lookup"><span data-stu-id="9c5b1-175">To create a one-way receive port to receive the batched EDI messages</span></span>  

1. <span data-ttu-id="9c5b1-176">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-176">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port.**</span></span>  

2. <span data-ttu-id="9c5b1-177">接收端口的名称，然后单击**接收位置**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-177">Name the receive port, and then click **Receive Locations** in the console tree.</span></span>  

3. <span data-ttu-id="9c5b1-178">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-178">Click **New**.</span></span>  

4. <span data-ttu-id="9c5b1-179">名称的接收位置，选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-179">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  

5. <span data-ttu-id="9c5b1-180">输入一个文件夹**接收文件夹**，和一个掩码**文件掩码**，如 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-180">Enter a folder for **Receive folder**, and a mask for **File Mask**, such as **\*.txt**.</span></span>  

6. <span data-ttu-id="9c5b1-181">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-181">Click **OK**.</span></span>  

7. <span data-ttu-id="9c5b1-182">有关**接收管道**，选择**EdiReceive**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-182">For **Receive pipeline**, select **EdiReceive**.</span></span>  

8. <span data-ttu-id="9c5b1-183">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-183">Click **OK**.</span></span>  

9. <span data-ttu-id="9c5b1-184">在控制台树中，单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-184">In the console tree, click **Receive Locations**.</span></span> <span data-ttu-id="9c5b1-185">在中**接收位置**窗格中，右键单击将接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-185">In the **Receive Locations** pane, right-click your receive location, and then click **Enable**.</span></span>  

##### <a name="to-create-a-static-one-way-send-port-to-send-the-batched-edi-interchange"></a><span data-ttu-id="9c5b1-186">若要创建静态单向发送端口以发送批处理的 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="9c5b1-186">To create a static one-way send port to send the batched EDI interchange</span></span>  

1. <span data-ttu-id="9c5b1-187">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-187">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port.**</span></span>  

2. <span data-ttu-id="9c5b1-188">在中**发送端口属性**对话框中，发送端口名称。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-188">In the **Send Port Properties** dialog box, name the send port.</span></span>  

3. <span data-ttu-id="9c5b1-189">在中**传输**部分中，选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-189">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  

4. <span data-ttu-id="9c5b1-190">输入一个文件夹**目标文件夹**，和一个掩码**文件掩码**，如 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-190">Enter a folder for **Destination folder**, and a mask for **File Mask**, such as **\*.txt**.</span></span>  

5. <span data-ttu-id="9c5b1-191">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-191">Click **OK**.</span></span>  

6. <span data-ttu-id="9c5b1-192">在中**发送管道**，选择**EdiSend**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-192">In **Send pipeline**, select **EdiSend**.</span></span>  

7. <span data-ttu-id="9c5b1-193">在控制台树中，选择**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-193">In the console tree, select **Filters**.</span></span> <span data-ttu-id="9c5b1-194">上**筛选器**页上，输入将订阅批中消息的筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-194">On the **Filters** page, enter a filter expression that will subscribe to the messages in the batch.</span></span> <span data-ttu-id="9c5b1-195">例如，选择**BTS。ReceivePortName**有关**属性**， **==** 有关**运算符**，和刚创建的用于的接收端口的名称**值**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-195">For example, select **BTS.ReceivePortName** for **Property**, **==** for **Operator**, and the name of the receive port that you just created for **Value**.</span></span>  

8. <span data-ttu-id="9c5b1-196">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-196">Click **OK**.</span></span>  

9. <span data-ttu-id="9c5b1-197">在控制台树中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-197">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="9c5b1-198">在中**发送端口**窗格中，右键单击您的发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-198">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  

##### <a name="to-create-a-party-and-a-business-profile-for-party-a"></a><span data-ttu-id="9c5b1-199">若要为参与方 A 创建一个参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="9c5b1-199">To create a party and a business profile for Party A</span></span>  

1. <span data-ttu-id="9c5b1-200">右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-200">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="9c5b1-201">输入中的参与方的名称**名称**文本框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-201">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-202">通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c5b1-202">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="9c5b1-203">此基础，某些属性将启用，或禁用在创建协议时。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-203">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="9c5b1-204">但是，对于此演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-204">However, for this walkthrough, you can leave this check box selected.</span></span>  

3. <span data-ttu-id="9c5b1-205">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-205">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  

4. <span data-ttu-id="9c5b1-206">在中**配置文件属性**对话框中，在**常规**页上，输入**PartyA_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-206">In the **Profile Properties** dialog box, on the **General** page, enter **PartyA_Profile** in the **Name** text box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-207">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-207">When you create a party, a profile is also created.</span></span> <span data-ttu-id="9c5b1-208">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-208">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="9c5b1-209">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-209">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="9c5b1-210">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-210">In the **General** page, specify a name for the profile.</span></span>  

##### <a name="to-create-a-party-and-a-business-profile-for-party-b"></a><span data-ttu-id="9c5b1-211">若要为参与方 B 创建一个参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="9c5b1-211">To create a party and a business profile for Party B</span></span>  

1. <span data-ttu-id="9c5b1-212">右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-212">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="9c5b1-213">输入中的参与方的名称**名称**文本框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-213">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-214">通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c5b1-214">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="9c5b1-215">此基础，某些属性将启用，或禁用在创建协议时。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-215">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="9c5b1-216">但是，对于此演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-216">However, for this walkthrough, you can leave this check box selected.</span></span>  

3. <span data-ttu-id="9c5b1-217">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-217">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  

4. <span data-ttu-id="9c5b1-218">在中**配置文件属性**对话框中，在**常规**页上，输入**PartyB_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-218">In the **Profile Properties** dialog box, on the **General** page, enter **PartyB_Profile** in the **Name** text box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-219">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-219">When you create a party, a profile is also created.</span></span> <span data-ttu-id="9c5b1-220">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-220">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="9c5b1-221">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-221">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="9c5b1-222">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-222">In the **General** page, specify a name for the profile.</span></span>  

##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a><span data-ttu-id="9c5b1-223">若要创建的两个业务配置文件之间的协议</span><span class="sxs-lookup"><span data-stu-id="9c5b1-223">To create an agreement between the two business profiles</span></span>  

1. <span data-ttu-id="9c5b1-224">右键单击**PartyA_Profile**，依次指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-224">Right-click **PartyA_Profile**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="9c5b1-225">在**常规属性**页上，对于**名称**文字框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-225">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  

3. <span data-ttu-id="9c5b1-226">从**协议**下拉列表中，选择**X12**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-226">From the **Protocol** drop-down list, select **X12**.</span></span>  

4. <span data-ttu-id="9c5b1-227">在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**参与**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-227">In the **Second Partner** section, from the **Name** drop-down list, select **PartyB**.</span></span>  

5. <span data-ttu-id="9c5b1-228">在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**PartyB_Profile**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-228">In the **Second Partner** section, from the **Profile** drop-down list, select **PartyB_Profile**.</span></span>  

    <span data-ttu-id="9c5b1-229">你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡用于配置一个单向协议，每个单向协议代表消息 （包括消息传输和确认传输） 的一次完整事务。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-229">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way agreement and each one-way agreement represents one complete transaction of message (including message transfer and acknowledgement transfer).</span></span>  

6. <span data-ttu-id="9c5b1-230">在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**，，然后选择**存储消息负载以用于报告**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-230">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  

7. <span data-ttu-id="9c5b1-231">在执行以下任务**PartyA-> 参与**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-231">Perform the following tasks on the **PartyA->PartyB** tab.</span></span>  

   1. <span data-ttu-id="9c5b1-232">上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-232">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9c5b1-233">需要发送方和接收方限定符和标识符字段才能执行协议解析。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-233">requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="9c5b1-234">它将匹配的值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**与协议属性中的交换标头中。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-234">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9c5b1-235">此外将通过匹配发送方限定符和标识符 （不接收方限定符和标识符） 来解析协议。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-235">will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="9c5b1-236">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不能解析协议，它将使用后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-236">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="9c5b1-237">如果将"EDI 接口开发人员教程"中的 SamplePO.txt 文件用作测试消息，设置**ISA5**到**ZZ**， **ISA6**到**THEM**， **ISA7**到**ZZ**，并**ISA8**到**美国**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-237">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **THEM**, **ISA7** to **ZZ**, and **ISA8** to **US**.</span></span>  

   2. <span data-ttu-id="9c5b1-238">上**验证**页**交换设置**部分中，请确保**检查重复的 isa13**选项处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-238">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="9c5b1-239">清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-239">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  

   3. <span data-ttu-id="9c5b1-240">上**字符集和分隔符**页**交换设置**部分中，选择**CR LF**选项。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-240">On the **Charset and Separators** page under the **Interchange Settings** section, select the **CR LF** option.</span></span>  

   4. <span data-ttu-id="9c5b1-241">上**本地主机设置**页**交换设置**部分的**入站消息处理选项**框中，选择**拆分交换为事务集-出错时挂起事务集**选项。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-241">On the **Local Host Settings** page under the **Interchange Settings** section, in the **Inbound Message Processing Option** box, select the **Split Interchange as Transaction Sets - suspend Transaction Sets on Error** option.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="9c5b1-242">开始时，在此解决方案中，我们会将交换拆分通过选择此选项。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-242">To start with, in this solution, we will split the interchange by selecting this option.</span></span> <span data-ttu-id="9c5b1-243">更高版本，作为的一部分[测试演练](../core/walkthrough-x12-receiving-batched-edi-interchanges.md#BKMK_Proc)下面的过程，我们将配置解决方案以保留该交换。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-243">Later, as part of [To test the walkthrough](../core/walkthrough-x12-receiving-batched-edi-interchanges.md#BKMK_Proc) procedure below, we will configure the solution to preserve the interchange.</span></span>  

   5. <span data-ttu-id="9c5b1-244">上**发送端口**页**交换设置**部分中，将前面创建的发送端口相关联。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-244">On the **Send Ports** page under the **Interchange Settings** section, associate the send port that you created earlier.</span></span> <span data-ttu-id="9c5b1-245">在中**发送端口**网格下**名称**列，再单击某个空单元格，并从下拉列表中，选择发送端口。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-245">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port.</span></span>  

   6. <span data-ttu-id="9c5b1-246">上**信封**页**事务集设置**部分中，输入在网格的第一行中的所有列的值。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-246">On the **Envelopes** page under the **Transaction Set Settings** section, enter values for all columns in the first line of the grid.</span></span>  


      |       <span data-ttu-id="9c5b1-247">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9c5b1-247">Use this</span></span>       |                                                                                                                                    <span data-ttu-id="9c5b1-248">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9c5b1-248">To do this</span></span>                                                                                                                                    |
      |----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     <span data-ttu-id="9c5b1-249">**默认**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-249">**Default**</span></span>      |   <span data-ttu-id="9c5b1-250">选择**默认**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-250">Select **Default**.</span></span> <span data-ttu-id="9c5b1-251">**注意：** 选择此行作为默认值的值**GS1**， **GS2**， **GS3**， **GS7**，并**GS8**是即使使用的值**事务类型**，**版本/发行版**，并**目标命名空间**不是消息的匹配项。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-251">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and **Target namespace** are not a match for the message.</span></span>    |
      | <span data-ttu-id="9c5b1-252">**事务类型**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-252">**Transaction Type**</span></span> |                                                                                                     <span data-ttu-id="9c5b1-253">选择你的测试消息的消息类型**850 – 采购订单**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-253">Select the message type of your test message, **850 - Purchase Order**.</span></span>                                                                                                      |
      | <span data-ttu-id="9c5b1-254">**版本/发行版**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-254">**Version/Release**</span></span>  |                                                                                                                        <span data-ttu-id="9c5b1-255">输入 EDI 版本， **00401**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-255">Enter the EDI version, **00401**.</span></span>                                                                                                                         |
      | <span data-ttu-id="9c5b1-256">**目标命名空间**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-256">**Target namespace**</span></span> |                                                                                                                <span data-ttu-id="9c5b1-257">选择 <http://schemas.microsoft.com/Edi/X12>。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-257">Select **<http://schemas.microsoft.com/Edi/X12>**.</span></span>                                                                                                                |
      |       <span data-ttu-id="9c5b1-258">**GS1**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-258">**GS1**</span></span>        |                                                                                           <span data-ttu-id="9c5b1-259">验证是否已选中的测试消息的消息类型， **PO-采购订单 (850)**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-259">Verify that the message type of the test message is selected, **PO - Purchase Order (850)**.</span></span>                                                                                           |
      |       <span data-ttu-id="9c5b1-260">**GS2**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-260">**GS2**</span></span>        |                                                                                                      <span data-ttu-id="9c5b1-261">例如，应用程序发送方输入的值**Purchasing**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-261">Enter a value for the Application sender, for example, **Purchasing**.</span></span>                                                                                                      |
      |       <span data-ttu-id="9c5b1-262">**GS3**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-262">**GS3**</span></span>        |                                                                                                    <span data-ttu-id="9c5b1-263">例如，应用程序接收方输入的值**OrderControl**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-263">Enter a value for the Application receiver, for example, **OrderControl**.</span></span>                                                                                                    |
      |       <span data-ttu-id="9c5b1-264">**GS4**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-264">**GS4**</span></span>        | <span data-ttu-id="9c5b1-265">选择所需的日期格式。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-265">Select the date format that you want.</span></span> <span data-ttu-id="9c5b1-266">**注意：** 您必须下拉列表中选择一个值，而不仅仅是单击该字段以显示默认值。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-266">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="9c5b1-267">如果您单击字段而无需从下拉列表中选择值，该值将不实际选择。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-267">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span> |
      |       <span data-ttu-id="9c5b1-268">**GS5**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-268">**GS5**</span></span>        |                                                                                                                      <span data-ttu-id="9c5b1-269">选择所需的时间格式。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-269">Select the time format that you want.</span></span>                                                                                                                       |
      |       <span data-ttu-id="9c5b1-270">**GS7**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-270">**GS7**</span></span>        |                                                                                                                <span data-ttu-id="9c5b1-271">选择**X-公认的标准委员会 X12**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-271">Select **X - Accredited Standards Committee X12**.</span></span>                                                                                                                |
      |       <span data-ttu-id="9c5b1-272">**GS8**</span><span class="sxs-lookup"><span data-stu-id="9c5b1-272">**GS8**</span></span>        |                                                                                                             <span data-ttu-id="9c5b1-273">验证已输入 EDI 版本， **00401**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-273">Verify that the EDI version has been entered, **00401**.</span></span>                                                                                                             |

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9c5b1-274">将设置 GS01、 GS02、 GS03、 GS04、 GS05、 GS07 和基于为输入的值对出站确认的 GS08**事务类型**，**版本/发行版**，和**目标命名空间**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-274">will set the values for GS01, GS02, GS03, GS04, GS05, GS07, and GS08 of the outbound acknowledgments based on the values entered for **Transaction Type**, **Version/Release**, and **Target namespace**.</span></span> <span data-ttu-id="9c5b1-275">发送管道将尝试匹配事务集类型、 X12 版本和消息的标头中的相应值的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-275">The send pipeline attempts to match the transaction set type, the X12 version, and the target namespace with the corresponding values in the header of the message.</span></span> <span data-ttu-id="9c5b1-276">如果成功，它将使用与关联的 GS 值**事务类型**，**版本/发行版**，并**目标命名空间**值。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-276">If successful, it uses the GS values associated with the **Transaction Type**, **Version/Release**, and **Target namespace** values.</span></span>  

8. <span data-ttu-id="9c5b1-277">在执行以下任务**参与-> PartyA**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-277">Perform the following tasks on the **PartyB->PartyA** tab.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-278">在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-278">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="9c5b1-279">若要成功创建协议，两个单向协议选项卡必须具有定义为值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-279">To successfully create an agreement, both one-way agreement tabs must have values defined for **ISA5**, **ISA6**, **ISA7**, and **ISA8**.</span></span>  

   1.  <span data-ttu-id="9c5b1-280">上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-280">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="9c5b1-281">如果将"EDI 接口开发人员教程"中的 SamplePO.txt 文件用作测试消息，设置**ISA5**到**ZZ**， **ISA6**到**美国**， **ISA7**到**ZZ**，并**ISA8**到**THEM**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-281">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **US**, **ISA7** to **ZZ**, and **ISA8** to **THEM**.</span></span>  

9. <span data-ttu-id="9c5b1-282">单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-282">Click **Apply**.</span></span>  

10. <span data-ttu-id="9c5b1-283">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-283">Click **OK**.</span></span> <span data-ttu-id="9c5b1-284">中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-284">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="9c5b1-285">默认情况下启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-285">The newly added agreement is enabled by default.</span></span>  

### <a name="testing-the-walkthrough"></a><span data-ttu-id="9c5b1-286">测试演练</span><span class="sxs-lookup"><span data-stu-id="9c5b1-286">Testing the Walkthrough</span></span>  
 <span data-ttu-id="9c5b1-287">本部分提供有关如何测试演练的信息。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-287">This section provides information on how to test the walkthrough.</span></span>  

####  <a name="BKMK_Proc"></a> <span data-ttu-id="9c5b1-288">若要测试演练</span><span class="sxs-lookup"><span data-stu-id="9c5b1-288">To test the walkthrough</span></span>  

1. <span data-ttu-id="9c5b1-289">在 Windows 资源管理器，打开与接收位置关联的本地文件夹并测试批处理 EDI 交换放入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-289">In Windows Explorer, open the local folder associated with the receive location, and drop a test batched EDI interchange into the folder.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c5b1-290">对于测试消息，可以使用由发送批处理的交换演练中的解决方案生成的批处理的交换输出。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-290">For a test message, you can use the batched interchange output generated by the solution in the sending batched interchanges walkthrough.</span></span> <span data-ttu-id="9c5b1-291">此示例消息将包含两个事务集。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-291">This sample message would contain two transaction sets.</span></span>  

2. <span data-ttu-id="9c5b1-292">打开与上面创建的发送端口关联的文件夹。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-292">Open the folder that you associated with the send port that you created above.</span></span> <span data-ttu-id="9c5b1-293">验证该文件夹包含两个新文件，以及每个文件包含一个事务的测试批处理消息中设置的 850 交换。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-293">Verify that the folder contains two new files, and that each file is an 850 interchange containing one of the transaction sets in the test batched message.</span></span>  

3. <span data-ttu-id="9c5b1-294">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，单击任何先前创建的协议的一部分的两个业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-294">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Parties** node, click any of the two business profiles that are part of the agreement created earlier.</span></span> <span data-ttu-id="9c5b1-295">在中**协议**部分中，右键单击协议，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-295">In the **Agreements** section, right-click the agreement, and click **Properties**.</span></span>  

4. <span data-ttu-id="9c5b1-296">在中**协议属性**对话框中，在**本地主机设置**页**交换设置**部分的**入站消息处理选项**框中，选择**保留交换-出错时挂起交换**或**保留交换-出错时挂起事务集**单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-296">In the **Agreement Properties** dialog box, on the **Local Host Settings** page under the **Interchange Settings** section, in the **Inbound Message Processing Option** box, select either **Preserve Interchange - suspend Interchange on Error** or **Preserve Interchange - suspend Transaction Sets on Error** and click **OK**.</span></span>  

5. <span data-ttu-id="9c5b1-297">单击**主机实例**下**平台设置**节点，右键单击**BizTalkServerApplication**，然后单击**重启**。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-297">Click **Host Instances** under the **Platform Settings** node, right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  

6. <span data-ttu-id="9c5b1-298">在 Windows 资源管理器，打开与接收位置关联的本地文件夹，再一次相同的测试批处理 EDI 交换放入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-298">In Windows Explorer, open the local folder associated with the receive location, and once again drop the same test batched EDI interchange into the folder.</span></span>  

7. <span data-ttu-id="9c5b1-299">在 Windows 资源管理器中，打开与上面创建的发送端口关联的文件夹。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-299">In Windows Explorer, open the folder that you associated with the send port that you created above.</span></span> <span data-ttu-id="9c5b1-300">验证该文件夹现在包含一个新文件，并且该文件是包含测试批处理消息中的两个 850 事务集的交换。</span><span class="sxs-lookup"><span data-stu-id="9c5b1-300">Verify that the folder now contains only one new file, and that the file is an interchange containing the two 850 transaction sets that were in the test batched message.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9c5b1-301">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c5b1-301">See Also</span></span>  
 <span data-ttu-id="9c5b1-302">[开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="9c5b1-302">[Developing and Configuring BizTalk Server EDI Solutions](../core/developing-and-configuring-biztalk-server-edi-solutions.md) </span></span>  
 <span data-ttu-id="9c5b1-303">[拆分批处理的 EDI 交换](../core/splitting-a-batched-edi-interchange.md) </span><span class="sxs-lookup"><span data-stu-id="9c5b1-303">[Splitting a Batched EDI Interchange](../core/splitting-a-batched-edi-interchange.md) </span></span>  
 <span data-ttu-id="9c5b1-304">[拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md) </span><span class="sxs-lookup"><span data-stu-id="9c5b1-304">[Splitting HIPAA Subdocuments](../core/splitting-hipaa-subdocuments.md) </span></span>  
 <span data-ttu-id="9c5b1-305">[保留收到的批处理 EDI 交换](../core/preserving-a-received-batched-edi-interchange.md) </span><span class="sxs-lookup"><span data-stu-id="9c5b1-305">[Preserving a Received Batched EDI Interchange](../core/preserving-a-received-batched-edi-interchange.md) </span></span>  
 <span data-ttu-id="9c5b1-306">[演练 (X12):发送批处理 EDI 交换](../core/walkthrough-x12-sending-batched-edi-interchanges.md) </span><span class="sxs-lookup"><span data-stu-id="9c5b1-306">[Walkthrough (X12): Sending Batched EDI Interchanges](../core/walkthrough-x12-sending-batched-edi-interchanges.md) </span></span>  
 <span data-ttu-id="9c5b1-307">[演练 (X12):接收 EDI 交换并发送回确认](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md) </span><span class="sxs-lookup"><span data-stu-id="9c5b1-307">[Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md) </span></span>  
 [<span data-ttu-id="9c5b1-308">演练 (X12):发送 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="9c5b1-308">Walkthrough (X12): Sending EDI Interchanges</span></span>](../core/walkthrough-x12-sending-edi-interchanges.md)