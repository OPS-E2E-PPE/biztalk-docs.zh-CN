---
title: 演练 (X12)： 发送批处理的 EDI 交换 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b80ea79b-6112-49bd-90e8-9a0a0e604df8
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d5ce491b5cf9ff3d1c142599edee4e6c5f6a324
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22292029"
---
# <a name="walkthrough-x12-sending-batched-edi-interchanges"></a><span data-ttu-id="0bfb9-102">演练 (X12)：发送批处理 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="0bfb9-102">Walkthrough (X12): Sending Batched EDI Interchanges</span></span>
<span data-ttu-id="0bfb9-103">本演练提供了一组使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为在参与方间发送批处理 EDI 交换创建解决方案的分步操作过程。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-103">This walkthrough provides a set of step-by-step procedures that creates a solution for sending batched EDI interchanges from one party to another using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0bfb9-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="0bfb9-104">Prerequisites</span></span>  
 <span data-ttu-id="0bfb9-105">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="how-the-solution-sends-batched-edi-interchanges"></a><span data-ttu-id="0bfb9-106">解决方案如何发送批处理 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="0bfb9-106">How the Solution Sends Batched EDI Interchanges</span></span>  
 <span data-ttu-id="0bfb9-107">该解决方案将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0bfb9-107">The solution will do the following:</span></span>  
  
1.  <span data-ttu-id="0bfb9-108">接收位置接收从的 EDI 交换**当事方 A**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-108">The receive location receives an EDI interchange from a **Party A**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-109">此列表中的事件可能不会按所示顺序发生。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-109">The events in this list may not occur in the order shown.</span></span>  
  
2.  <span data-ttu-id="0bfb9-110">接收管道将 EDI 格式的交换转换为内部 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-110">The receive pipeline converts the EDI format of the interchange to internal XML format.</span></span> <span data-ttu-id="0bfb9-111">接收管道确定要对交换进行批处理。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-111">The receive pipeline determines that the interchange is to be batched.</span></span> <span data-ttu-id="0bfb9-112">因此，BatchMarkerReceivePipeline 组件会升级 `EDI.ToBeBatched==True` 和 `EDI.BatchId` 属性。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-112">As a result, the BatchMarkerReceivePipeline component promotes the `EDI.ToBeBatched==True` and `EDI.BatchId` properties.</span></span> <span data-ttu-id="0bfb9-113">然后，它将交换放入 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-113">It then drops the interchange into the MessageBox.</span></span>  
  
3.  <span data-ttu-id="0bfb9-114">批处理业务流程从 MessageBox 检索收到的交换，因为它基于 `EDI.ToBeBatched==True` 和 `EDI.BatchId==%BatchID%` 订阅该消息。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-114">The Batching Orchestration retrieves the received interchange from the MessageBox, because it subscribes to the message based upon `EDI.ToBeBatched==True` and `EDI.BatchId==%BatchID%`.</span></span>  
  
4.  <span data-ttu-id="0bfb9-115">接收位置接收来自发送第一个交换的同一参与方的第二个 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-115">The receive location receives a second EDI interchange from the same party that sent the first interchange.</span></span>  
  
5.  <span data-ttu-id="0bfb9-116">接收位置按照第 2 步中的说明处理交换，然后将交换放入 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-116">The receive location processes the interchange as in step 2, and then drops the interchange into the MessageBox.</span></span>  
  
6.  <span data-ttu-id="0bfb9-117">批处理业务流程按照第 3 步中的说明检索交换。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-117">The Batching Orchestration retrieves the interchange as in step 3.</span></span>  
  
7.  <span data-ttu-id="0bfb9-118">在满足释放条件之后（释放条件定义了交换是如何匹配的），批处理业务流程就会组装包含所有交换的交换，然后升级 `EDI.ToBeBatched==False`、`EDI.BatchName` 和 `EDI.DestinationPartyName` 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-118">After the release criteria is met (release criteria defines how the interchanges have to be matched), the Batching Orchestration assembles the interchange containing all the interchanges, and then promotes the `EDI.ToBeBatched==False`, `EDI.BatchName` and `EDI.DestinationPartyName` context properties.</span></span> <span data-ttu-id="0bfb9-119">它将批处理交换放入 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-119">It drops the batched interchange into the MessageBox.</span></span>  
  
8.  <span data-ttu-id="0bfb9-120">发送端口通过订阅上下文属性 `EDI.ToBeBatched`==False、`EDI.BatchName` 和 `EDI.DestinationPartyName` 来提取批处理交换。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-120">The send port picks up the batched interchange by subscribing on the context properties `EDI.ToBeBatched`==False, `EDI.BatchName` and `EDI.DestinationPartyName`.</span></span>  
  
9. <span data-ttu-id="0bfb9-121">发送管道适用于批处理的交换的信封的其他属性，然后将该交换发送到目标方**方 B**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-121">The send pipeline applies additional properties to the envelope of the batched interchange, and then sends the interchange to destination party, **Party B**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-122">有关详细信息，请参阅[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-122">For more information, see [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
 <span data-ttu-id="0bfb9-123">下图显示出此解决方案的结构。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-123">The following figure shows the architecture for this solution.</span></span>  
  
 <span data-ttu-id="0bfb9-124">![发送批处理的 EDI 交换](../core/media/93a09e3c-476d-4bd2-a0e3-b5b219858791.gif "93a09e3c-476d-4bd2-a0e3-b5b219858791")</span><span class="sxs-lookup"><span data-stu-id="0bfb9-124">![Sending batched EDI interchanges](../core/media/93a09e3c-476d-4bd2-a0e3-b5b219858791.gif "93a09e3c-476d-4bd2-a0e3-b5b219858791")</span></span>  
  
## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="0bfb9-125">此解决方案中的功能</span><span class="sxs-lookup"><span data-stu-id="0bfb9-125">The Functionality in this Solution</span></span>  
 <span data-ttu-id="0bfb9-126">为进行此演练，将启用以下功能：</span><span class="sxs-lookup"><span data-stu-id="0bfb9-126">For the purposes of this walkthrough, the following functionality will be enabled:</span></span>  
  
-   <span data-ttu-id="0bfb9-127">该解决方案专用于使用 X12 编码而不是 EDIFACT 编码的交换。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-127">The solution is designed for interchanges using X12 encoding, not EDIFACT encoding.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-128">用于 HIPAA 和 EDIFACT 编码的配置与用于 X12 编码的配置几近相同。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-128">The configuration used for HIPAA and for EDIFACT encoding is closely parallel to that used for X12 encoding.</span></span>  
  
-   <span data-ttu-id="0bfb9-129">将不会返回技术确认或功能确认来响应最初接收的交换或发送的任何批处理交换。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-129">Technical or functional acknowledgments will not be returned in response to the interchange originally received or any batched interchange that is sent.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-130">有关生成 EDI 确认信息，请参阅[演练 (X12)： 接收 EDI 交换和发送回确认](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-130">For information about generating EDI acknowledgments, see [Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md).</span></span>  
  
-   <span data-ttu-id="0bfb9-131">该解决方案使用一个单向接收端口和一个静态单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-131">This solution uses a one-way receive port and a static one-way send port.</span></span> <span data-ttu-id="0bfb9-132">将使用 FILE 传输类型配置这些端口。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-132">These ports will be configured with the FILE transport type.</span></span>  
  
-   <span data-ttu-id="0bfb9-133">将启用 EDI 报告。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-133">EDI reporting will be enabled.</span></span>  
  
-   <span data-ttu-id="0bfb9-134">将保存事务集以从交换状态报告进行查看。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-134">Transaction sets will be saved for viewing from the interchange status report.</span></span>  
  
## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="0bfb9-135">配置和测试演练</span><span class="sxs-lookup"><span data-stu-id="0bfb9-135">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="0bfb9-136">该解决方案所需的过程包括：</span><span class="sxs-lookup"><span data-stu-id="0bfb9-136">The procedures required for this solution include the following:</span></span>  
  
-   <span data-ttu-id="0bfb9-137">将必需的消息架构添加到 BizTalk 项目，然后生成并部署该项目，以使架构可供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在处理消息时使用。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-137">Add the required message schema(s) to a BizTalk project, and then build and deploy the project, making the schema(s) available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the messages.</span></span>  
  
-   <span data-ttu-id="0bfb9-138">更新中的 SQL 适配器的轮询间隔**BatchControlMessageReccvLoc**接收位置，以便在你单击时，批处理业务流程将被立即激活**启动**按钮发送将激活的批处理的业务流程实例控制消息。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-138">Update the polling interval for the SQL adapter in the **BatchControlMessageReccvLoc** receive location, so that the batching orchestration will be promptly activated when you click the **Start** button to send the control message that will activate a batching orchestration instance.</span></span>  
  
-   <span data-ttu-id="0bfb9-139">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个接收端口，以从参与方接收 EDI X12 编码的 .txt 输入消息。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-139">Create a receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the EDI X12-encoded .txt input messages from a party.</span></span>  
  
-   <span data-ttu-id="0bfb9-140">为参与方 A 和参与方 B 创建一个参与方（贸易合作伙伴）。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-140">Create a party (trading partner) for both Party A and Party B.</span></span>  
  
-   <span data-ttu-id="0bfb9-141">为两个贸易合作伙伴分别创建一个业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-141">Create a business profile each for both the trading partners.</span></span>  
  
-   <span data-ttu-id="0bfb9-142">通过配置要接收的消息的 EDI 属性，在两个配置文件之间创建一个协议。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-142">Create an agreement between the two profiles by configuring the EDI properties for the message to be received.</span></span> <span data-ttu-id="0bfb9-143">为要发送的批处理消息配置 EDI 属性。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-143">Configure the EDI properties for the batched message to be sent.</span></span> <span data-ttu-id="0bfb9-144">对于此解决方案，只要收到两个 850 交换，就会配置这些协议，以便 BizTalk Server 向参与方 B 发送批。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-144">For this solution, configure the agreements such that BizTalk Server will send a batch to Party B whenever two 850 interchanges are received.</span></span>  
  
-   <span data-ttu-id="0bfb9-145">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个发送端口来将批处理 EDI 交换发送到贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-145">Create a send port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send the batched EDI interchange to the trading partner.</span></span> <span data-ttu-id="0bfb9-146">此发送端口将是一个静态单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-146">This send port will be a static one-way send port.</span></span>  
  
-   <span data-ttu-id="0bfb9-147">将发送端口与处理交换并对其进行批量处理的协议相关联。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-147">Associate the send port with the agreement that processes the interchanges and batches them.</span></span>  
  
-   <span data-ttu-id="0bfb9-148">将两个测试 EDI 交换放入与接收位置关联的本地文件夹，并验证 BizTalk Server 是否已将批处理交换放入与发送端口关联的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-148">Drop two test EDI interchanges into the local folder associated with the receive location, and verifying that BizTalk Server has dropped a batched interchange into the folder associated with the send port.</span></span>  
  
### <a name="configuring-the-walkthrough"></a><span data-ttu-id="0bfb9-149">配置演练</span><span class="sxs-lookup"><span data-stu-id="0bfb9-149">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="0bfb9-150">本部分介绍配置演练的步骤。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-150">This section describes the procedures to configure the walkthrough.</span></span>  
  
##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="0bfb9-151">部署消息架构</span><span class="sxs-lookup"><span data-stu-id="0bfb9-151">To deploy the message schema</span></span>  
  
1.  <span data-ttu-id="0bfb9-152">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建或打开 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-152">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-153">本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-153">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="0bfb9-154">如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-154">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2.  <span data-ttu-id="0bfb9-155">右键单击你的项目，指向**添加**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-155">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="0bfb9-156">移动到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\X12\00401，然后双击与测试消息对应的架构。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-156">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\X12\00401, and then double-click the schema corresponding to your test message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-157">如果不具有已 EDI 架构解压缩到 \XSD_Schema\EDI 文件夹中，执行**MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI 文件夹来解压缩到默认文件夹的架构中的文件。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-157">If the EDI schemas have not been unzipped into the \XSD_Schema\EDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the \XSD_Schema\EDI folder to unzip the schemas into the default folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-158">对于测试消息，您可以使用在 EDI 接口开发人员教程中使用的 850 示例消息。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-158">For a test message, you can use the 850 sample message used for the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="0bfb9-159">此文件是在 SamplePO.txt [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 接口开发人员教程\\。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-159">This file is SamplePO.txt in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\\.</span></span> <span data-ttu-id="0bfb9-160">如果要这样做，您必须使用位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 的架构 x12_00401_850.xsd。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-160">If you do so, you must use the schema x12_00401_850.xsd located in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI.</span></span>  
  
3.  <span data-ttu-id="0bfb9-161">设置程序集密钥文件，然后生成并部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-161">Set the assembly key file, and then build and deploy the assembly.</span></span>  
  
##### <a name="to-update-the-polling-interval"></a><span data-ttu-id="0bfb9-162">更新轮询间隔</span><span class="sxs-lookup"><span data-stu-id="0bfb9-162">To update the polling interval</span></span>  
  
1.  <span data-ttu-id="0bfb9-163">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，打开**BizTalk 组**，**应用程序**， **BizTalk EDI 应用程序**节点，和**接收位置**节点。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-163">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, open the **BizTalk Group**, **Applications**, **BizTalk EDI Application** nodes, and **Receive Locations** nodes.</span></span> <span data-ttu-id="0bfb9-164">下**接收位置**节点，右键单击**BatchControlMessageRecvLoc**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-164">Under the **Receive Locations** node, right-click **BatchControlMessageRecvLoc**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0bfb9-165">对于 SQL 传输类型，请单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-165">For the SQL transport type, click **Configure**.</span></span>  
  
3.  <span data-ttu-id="0bfb9-166">在**SQL 传输属性**对话框框中，将轮询间隔设置为较小的值。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-166">In the **SQL Transport Properties** dialog box, set the polling interval to a smaller value.</span></span> <span data-ttu-id="0bfb9-167">例如，您可以更改**轮询度量单位**到**秒**，而不是分钟，才能将轮询间隔更改为 5 秒。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-167">For example, you can change **Polling Unit of Measure** to **Seconds**, instead of minutes, to change the polling interval to 5 seconds.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-168">更改轮询间隔可确保将立即激活批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-168">Changing the polling interval ensures that the batching orchestration will be promptly activated.</span></span>  
  
4.  <span data-ttu-id="0bfb9-169">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-169">Click **OK**, and then click **OK** again.</span></span>  
  
##### <a name="to-create-a-one-way-receive-port-to-receive-the-edi-messages-to-be-batched"></a><span data-ttu-id="0bfb9-170">创建接收要进行批处理的 EDI 消息的单向接收端口</span><span class="sxs-lookup"><span data-stu-id="0bfb9-170">To create a one-way receive port to receive the EDI messages to be batched</span></span>  
  
1.  <span data-ttu-id="0bfb9-171">创建用于接收要进行批处理的 EDI 消息的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-171">Create a local folder to receive the EDI messages to be batched.</span></span>  
  
2.  <span data-ttu-id="0bfb9-172">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-172">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
3.  <span data-ttu-id="0bfb9-173">将接收端口，然后单击**接收位置**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-173">Name the receive port, and then click **Receive Locations** in the console tree.</span></span>  
  
4.  <span data-ttu-id="0bfb9-174">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-174">Click **New**.</span></span>  
  
5.  <span data-ttu-id="0bfb9-175">名称的接收位置中，选择**文件**为**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-175">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="0bfb9-176">输入的文件夹**接收文件夹**，和的掩码**文件掩码**，如 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-176">Enter a folder for **Receive folder**, and a mask for **File Mask**, such as **\*.txt**.</span></span>  
  
7.  <span data-ttu-id="0bfb9-177">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-177">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="0bfb9-178">有关**接收管道**，选择**EdiReceive**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-178">For **Receive pipeline**, select **EdiReceive**.</span></span>  
  
9. <span data-ttu-id="0bfb9-179">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-179">Click **OK**, and then click **OK** again.</span></span>  
  
10. <span data-ttu-id="0bfb9-180">在控制台树中，单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-180">In the console tree, click **Receive Locations**.</span></span> <span data-ttu-id="0bfb9-181">在**接收位置**窗格中，右键单击你接收位置，并依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-181">In the **Receive Locations** pane, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-party-a"></a><span data-ttu-id="0bfb9-182">为参与方 A 创建团队和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="0bfb9-182">To create a party and a business profile for Party A</span></span>  
  
1.  <span data-ttu-id="0bfb9-183">右键单击**方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-183">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="0bfb9-184">输入的名称在方**名称**文本中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-184">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-185">通过选择**本地 BizTalk 处理接收的消息从该参与方发送方或支持消息**复选框，你可以指定当事方正在创建将为同一个组织还承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bfb9-185">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0bfb9-186">此基础，某些属性将启用，或当您创建了协议时，禁用。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-186">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="0bfb9-187">但是，对于本演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-187">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="0bfb9-188">右键单击方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-188">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="0bfb9-189">在**配置文件属性**对话框中，在**常规**页上，输入**PartyA_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-189">In the **Profile Properties** dialog box, on the **General** page, enter **PartyA_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-190">在创建参与方时，也将创建一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-190">When you create a party, a profile is also created.</span></span> <span data-ttu-id="0bfb9-191">你可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-191">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="0bfb9-192">若要重命名配置文件，右键单击配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-192">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="0bfb9-193">在**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-193">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-party-b"></a><span data-ttu-id="0bfb9-194">为参与方 B 创建团队和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="0bfb9-194">To create a party and a business profile for Party B</span></span>  
  
1.  <span data-ttu-id="0bfb9-195">右键单击**方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-195">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="0bfb9-196">输入的名称在方**名称**文本中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-196">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-197">通过选择**本地 BizTalk 处理接收的消息从该参与方发送方或支持消息**复选框，你可以指定当事方正在创建将为同一个组织还承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bfb9-197">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0bfb9-198">此基础，某些属性将启用，或当您创建了协议时，禁用。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-198">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="0bfb9-199">但是，对于本演练中，可以选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-199">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="0bfb9-200">右键单击方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-200">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="0bfb9-201">在**配置文件属性**对话框中，在**常规**页上，输入**PartyB_Profile**中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-201">In the **Profile Properties** dialog box, on the **General** page, enter **PartyB_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-202">在创建参与方时，也将创建一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-202">When you create a party, a profile is also created.</span></span> <span data-ttu-id="0bfb9-203">你可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-203">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="0bfb9-204">若要重命名配置文件，右键单击配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-204">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="0bfb9-205">在**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-205">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a><span data-ttu-id="0bfb9-206">在两个业务配置文件之间创建协议</span><span class="sxs-lookup"><span data-stu-id="0bfb9-206">To create an agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="0bfb9-207">右键单击**PartyA_Profile**，指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-207">Right-click **PartyA_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="0bfb9-208">在**常规属性**页上，为**名称**文本框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-208">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="0bfb9-209">从**协议**下拉列表中，选择**X12**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-209">From the **Protocol** drop-down list, select **X12**.</span></span>  
  
4.  <span data-ttu-id="0bfb9-210">在**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**PartyB**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-210">In the **Second Partner** section, from the **Name** drop-down list, select **PartyB**.</span></span>  
  
5.  <span data-ttu-id="0bfb9-211">在**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**PartyB_Profile**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-211">In the **Second Partner** section, from the **Profile** drop-down list, select **PartyB_Profile**.</span></span>  
  
     <span data-ttu-id="0bfb9-212">你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡配置一个单向协议，每个单向协议代表消息的一次完整事务（包括消息传输和确认传输）。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-212">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way agreement and each one-way agreement represents one complete transaction of message (including message transfer and acknowledgement transfer).</span></span>  
  
6.  <span data-ttu-id="0bfb9-213">在**常规**选项卡上，在**常规属性**页上，在**常见主机设置**部分中，选择**打开 reporting**，，然后选择**用于报告的应用商店消息负载**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-213">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  
  
7.  <span data-ttu-id="0bfb9-214">在上执行以下任务**PartyA-> PartyB**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-214">Perform the following tasks on the **PartyA->PartyB** tab.</span></span>  
  
    1.  <span data-ttu-id="0bfb9-215">上**标识符**下页上**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，和**ISA8**) 对应于测试消息中这些标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-215">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0bfb9-216"> 要求为发送方和接收方的限定符和标识符字段输入值才能执行协议解析。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-216"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="0bfb9-217">它将与匹配的值**ISA5**， **ISA6**， **ISA7**，和**ISA8**与协议的属性中的交换标头中。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-217">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0bfb9-218">此外将匹配的发件人限定符和 （而不是收件人限定符和标识符） 的标识符来解析协议。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-218"> will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="0bfb9-219">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法解析协议，则将使用后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-219">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0bfb9-220">如果你使用"EDI 接口开发人员教程"中的 SamplePO.txt 文件作为测试消息，设置**ISA5**到**ZZ**， **ISA6**到**THEM**， **ISA7**到**ZZ**，和**ISA8**到**美国**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-220">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **THEM**, **ISA7** to **ZZ**, and **ISA8** to **US**.</span></span>  
  
    2.  <span data-ttu-id="0bfb9-221">上**验证**下页上**交换设置**部分中，请确保**检查重复的 isa13**选项处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-221">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0bfb9-222">清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-222">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  
  
    3.  <span data-ttu-id="0bfb9-223">上**字符集和分隔符**下页上**交换设置**部分中，选择**CR LF**选项。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-223">On the **Charset and Separators** page under the **Interchange Settings** section, select the **CR LF** option.</span></span>  
  
    4.  <span data-ttu-id="0bfb9-224">上**批配置**下页上**交换设置**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0bfb9-224">On the **Batch Configuration** page under the **Interchange Settings** section, do the following:</span></span>  
  
        1.  <span data-ttu-id="0bfb9-225">单击**新的批处理**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-225">Click **New Batch**.</span></span>  
  
        2.  <span data-ttu-id="0bfb9-226">下**标识**部分中，为**批名称**文本，输入`Batch1`。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-226">Under the **Identification** section, for **Batch Name** text, enter `Batch1`.</span></span>  
  
        3.  <span data-ttu-id="0bfb9-227">下**筛选器**部分中，单击**筛选器**按钮，然后在**批处理筛选器**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0bfb9-227">Under the **Filter** section, click the **Filter** button, and in the **Batch Filter** dialog box, do the following:</span></span>  
  
            1.  <span data-ttu-id="0bfb9-228">单击下面的空单元格中**属性**列并选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-228">Click the empty cell under the **Property** column and select **BTS.ReceivePortName**.</span></span>  
  
            2.  <span data-ttu-id="0bfb9-229">单击下面的空单元格中**运算符**列并选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-229">Click the empty cell under the **Operator** column and select **==**.</span></span>  
  
            3.  <span data-ttu-id="0bfb9-230">单击下面的空单元格中**值**列，然后输入先前创建的接收端口名称。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-230">Click the empty cell under the **Value** column and enter the name of the receive port you created earlier.</span></span>  
  
            4.  <span data-ttu-id="0bfb9-231">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-231">Click **OK**.</span></span>  
  
        4.  <span data-ttu-id="0bfb9-232">下**版本**部分中，选择**事务的最大数量设置中**选项，请从下拉列表中选择**交换**，并在文本框中输入的数将批处理的交换。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-232">Under the **Release** section, select the **Maximum number of transaction sets in** option, from the drop-down select **Interchange**, and in the text box enter the number of interchanges that will be batched.</span></span> <span data-ttu-id="0bfb9-233">在此解决方案中，批处理两个的交换，因此在文本框中，输入`2`。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-233">In this solution, you will be batching two interchanges, so in the text box, enter `2`.</span></span>  
  
        5.  <span data-ttu-id="0bfb9-234">下**激活**部分中，选择**立即开始**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-234">Under the **Activation** section, select **Start immediately**.</span></span>  
  
    5.  <span data-ttu-id="0bfb9-235">上**包络线**下页上**事务设置设置**部分中，输入网格的第一行中的所有列的值。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-235">On the **Envelopes** page under the **Transaction Set Settings** section, enter values for all columns in the first line of the grid.</span></span>  
  
        |<span data-ttu-id="0bfb9-236">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0bfb9-236">Use this</span></span>|<span data-ttu-id="0bfb9-237">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0bfb9-237">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0bfb9-238">**Default**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-238">**Default**</span></span>|<span data-ttu-id="0bfb9-239">选择**默认**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-239">Select **Default**.</span></span> <span data-ttu-id="0bfb9-240">**注意：** 当作为默认值的值选择此行**GS1**， **GS2**， **GS3**， **GS7**，和**GS8**使用即使的值**事务类型**，**版本/发行版**，和**目标命名空间**不的匹配项消息。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-240">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and **Target namespace** are not a match for the message.</span></span>|  
        |<span data-ttu-id="0bfb9-241">**事务类型**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-241">**Transaction Type**</span></span>|<span data-ttu-id="0bfb9-242">选择你的测试消息的消息类型**850-采购订单**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-242">Select the message type of your test message, **850 - Purchase Order**.</span></span>|  
        |<span data-ttu-id="0bfb9-243">**版本/发行版**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-243">**Version/Release**</span></span>|<span data-ttu-id="0bfb9-244">输入的 EDI 版本中， **00401**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-244">Enter the EDI version, **00401**.</span></span>|  
        |<span data-ttu-id="0bfb9-245">**目标命名空间**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-245">**Target namespace**</span></span>|<span data-ttu-id="0bfb9-246">选择**http://schemas.microsoft.com/BizTalk/Edi/X12/2006**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-246">Select **http://schemas.microsoft.com/BizTalk/Edi/X12/2006**.</span></span>|  
        |<span data-ttu-id="0bfb9-247">**GS1**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-247">**GS1**</span></span>|<span data-ttu-id="0bfb9-248">验证是否已选中测试消息的消息类型， **PO-采购订单 (850)**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-248">Verify that the message type of the test message is selected, **PO - Purchase Order (850)**.</span></span>|  
        |<span data-ttu-id="0bfb9-249">**GS2**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-249">**GS2**</span></span>|<span data-ttu-id="0bfb9-250">例如，应用程序发件人，输入一个值**购买**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-250">Enter a value for the Application sender, for example, **Purchasing**.</span></span>|  
        |<span data-ttu-id="0bfb9-251">**GS3**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-251">**GS3**</span></span>|<span data-ttu-id="0bfb9-252">例如，为应用程序收件人输入一个值**OrderControl**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-252">Enter a value for the Application receiver, for example, **OrderControl**.</span></span>|  
        |<span data-ttu-id="0bfb9-253">**GS4**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-253">**GS4**</span></span>|<span data-ttu-id="0bfb9-254">选择所需的日期格式。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-254">Select the date format that you want.</span></span> <span data-ttu-id="0bfb9-255">**注意：** 你需要在下拉列表中选择值，而不仅仅是在要显示默认值的字段中单击。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-255">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="0bfb9-256">如果你仅单击字段，而没有从下拉列表中选择值，则实际上并未选择值。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-256">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span>|  
        |<span data-ttu-id="0bfb9-257">**GS5**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-257">**GS5**</span></span>|<span data-ttu-id="0bfb9-258">选择所需的时间格式。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-258">Select the time format that you want.</span></span>|  
        |<span data-ttu-id="0bfb9-259">**GS7**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-259">**GS7**</span></span>|<span data-ttu-id="0bfb9-260">选择**X 的公认的标准委员会 X12**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-260">Select **X - Accredited Standards Committee X12**.</span></span>|  
        |<span data-ttu-id="0bfb9-261">**GS8**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-261">**GS8**</span></span>|<span data-ttu-id="0bfb9-262">验证 EDI 版本具有输入**00401**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-262">Verify that the EDI version has been entered, **00401**.</span></span>|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0bfb9-263">将为 GS01、 GS02、 GS03、 GS04、 GS05、 GS07 和基于为输入的值的出站确认 GS08 设置值**事务类型**，**版本/发行版**，和**目标命名空间**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-263"> will set the values for GS01, GS02, GS03, GS04, GS05, GS07, and GS08 of the outbound acknowledgments based on the values entered for **Transaction Type**, **Version/Release**, and **Target namespace**.</span></span> <span data-ttu-id="0bfb9-264">发送管道尝试将事务集类型、X12 版本和目标命名空间与消息标头中的对应值相匹配。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-264">The send pipeline attempts to match the transaction set type, the X12 version, and the target namespace with the corresponding values in the header of the message.</span></span> <span data-ttu-id="0bfb9-265">如果成功，它将使用与关联的 GS 值**事务类型**，**版本/发行版**，和**目标命名空间**值。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-265">If successful, it uses the GS values associated with the **Transaction Type**, **Version/Release**, and **Target namespace** values.</span></span>  
  
8.  <span data-ttu-id="0bfb9-266">在上执行以下任务**PartyB-> PartyA**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-266">Perform the following tasks on the **PartyB->PartyA** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-267">在此演练中，我们将指定的选项卡中所需的值，以便可以成功创建协议。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-267">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="0bfb9-268">若要成功创建了协议，这两个单向协议选项必须为定义的值**ISA5**， **ISA6**， **ISA7**，和**ISA8**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-268">To successfully create an agreement, both one-way agreement tabs must have values defined for **ISA5**, **ISA6**, **ISA7**, and **ISA8**.</span></span>  
  
    1.  <span data-ttu-id="0bfb9-269">上**标识符**下页上**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，和**ISA8**) 对应于测试消息中这些标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-269">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0bfb9-270">如果你使用"EDI 接口开发人员教程"中的 SamplePO.txt 文件作为测试消息，设置**ISA5**到**ZZ**， **ISA6**到**美国**， **ISA7**到**ZZ**，和**ISA8**到**THEM**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-270">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **US**, **ISA7** to **ZZ**, and **ISA8** to **THEM**.</span></span>  
  
9. <span data-ttu-id="0bfb9-271">单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-271">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="0bfb9-272">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-272">Click **OK**.</span></span> <span data-ttu-id="0bfb9-273">新添加的协议被列入**协议**部分**方和业务配置文件**窗格。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-273">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="0bfb9-274">默认情况下，启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-274">The newly added agreement is enabled by default.</span></span>  
  
##### <a name="to-create-a-static-one-way-send-port-to-send-the-batched-edi-interchange"></a><span data-ttu-id="0bfb9-275">创建静态单向发送端口以发送批处理 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="0bfb9-275">To create a static one-way send port to send the batched EDI interchange</span></span>  
  
1.  <span data-ttu-id="0bfb9-276">创建要将批处理 EDI 消息发送到的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-276">Create a local folder to send the batched EDI message to.</span></span>  
  
2.  <span data-ttu-id="0bfb9-277">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="0bfb9-277">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
3.  <span data-ttu-id="0bfb9-278">在**发送端口属性**对话框中，名称发送端口。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-278">In the **Send Port Properties** dialog box, name the send port.</span></span>  
  
4.  <span data-ttu-id="0bfb9-279">在**传输**部分中，选择**文件**为**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-279">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="0bfb9-280">输入的文件夹**目标文件夹**，和一个**文件名**，如 **%MessageID%.txt**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-280">Enter a folder for **Destination folder**, and a **File name**, such as **%MessageID%.txt**.</span></span>  
  
6.  <span data-ttu-id="0bfb9-281">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-281">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="0bfb9-282">在**发送管道**，选择**EdiSend**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-282">In **Send pipeline**, select **EdiSend**.</span></span>  
  
8.  <span data-ttu-id="0bfb9-283">在控制台树中，选择**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-283">In the console tree, select **Filters**.</span></span> <span data-ttu-id="0bfb9-284">上**筛选器**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0bfb9-284">On the **Filters** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="0bfb9-285">在网格的第一行，选择**EDI。DestinationPartyName**为**属性**，  **==** 为**运算符**，为发送到用于的批处理的参与方选择的名称**值**，和**和**为**分组依据**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-285">On the first line of the grid, select **EDI.DestinationPartyName** for **Property**, **==** for **Operator**, the name you selected for the party to send the batch to for **Value**, and **And** for **Group by**.</span></span>  
  
    2.  <span data-ttu-id="0bfb9-286">在第二行中，选择**EDI。ToBeBatched**为**属性**，  **==** 为**运算符**，和**False**为**值**，和**和**为**分组依据**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-286">On the second line, select **EDI.ToBeBatched** for **Property**, **==** for **Operator**, and **False** for **Value**, and **And** for **Group by**.</span></span>  
  
    3.  <span data-ttu-id="0bfb9-287">在第三行中，选择**EDI。BatchName**为**属性**，  **==** 为**运算符**，和用于批处理的名称**值**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-287">On the third line, select **EDI.BatchName** for **Property**, **==** for **Operator**, and the name of the batch for **Value**.</span></span>  
  
9. <span data-ttu-id="0bfb9-288">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-288">Click **OK**.</span></span>  
  
10. <span data-ttu-id="0bfb9-289">在控制台树中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-289">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="0bfb9-290">在**发送端口**窗格中，右键单击你发送端口，并依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-290">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-associate-the-send-port-with-the-agreement-created-for-batching"></a><span data-ttu-id="0bfb9-291">将发送端口与为进行批处理创建的协议相关联</span><span class="sxs-lookup"><span data-stu-id="0bfb9-291">To associate the send port with the agreement created for batching</span></span>  
  
1.  <span data-ttu-id="0bfb9-292">右键单击你在前面创建的协议，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-292">Right-click the agreement you created earlier and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0bfb9-293">在**协议属性**对话框中，在**PartyA-> PartyB**选项卡上，单击**发送端口**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-293">In the **Agreement Properties** dialog box, on the **PartyA->PartyB** tab, click **Send Ports** in the left pane.</span></span>  
  
3.  <span data-ttu-id="0bfb9-294">上**发送端口**下页上**交换设置**部分中，将之前创建发送端口相关联。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-294">On the **Send Ports** page under the **Interchange Settings** section, associate the send port that you created earlier.</span></span> <span data-ttu-id="0bfb9-295">在**发送端口**网格下**名称**列中，单击空单元格，然后从下拉列表列表中，选择发送端口。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-295">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port.</span></span>  
  
4.  <span data-ttu-id="0bfb9-296">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-296">Click **OK**.</span></span>  
  
### <a name="testing-the-walkthrough"></a><span data-ttu-id="0bfb9-297">测试演练</span><span class="sxs-lookup"><span data-stu-id="0bfb9-297">Testing the Walkthrough</span></span>  
 <span data-ttu-id="0bfb9-298">本部分提供有关如何测试演练的信息。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-298">This section provides information on how to test the walkthrough.</span></span>  
  
##### <a name="to-test-the-walkthrough"></a><span data-ttu-id="0bfb9-299">若要测试演练</span><span class="sxs-lookup"><span data-stu-id="0bfb9-299">To test the walkthrough</span></span>  
  
1.  <span data-ttu-id="0bfb9-300">在 Windows 资源管理器中，打开与接收位置关联的本地文件夹，然后将测试 EDI 交换放入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-300">In Windows Explorer, open the local folder associated with the receive location, and drop a test EDI interchange into the folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bfb9-301">对于测试消息，您可以使用在 EDI 接口开发人员教程中使用的 850 示例消息。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-301">For a test message, you can use the 850 sample message used for the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="0bfb9-302">此文件是在 SamplePO.txt [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 接口开发人员教程\\。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-302">This file is SamplePO.txt in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\\.</span></span> <span data-ttu-id="0bfb9-303">如果要这样做，您必须使用位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 的架构 x12_00401_850.xsd。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-303">If you do so, you must use the schema x12_00401_850.xsd located in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI.</span></span>  
  
2.  <span data-ttu-id="0bfb9-304">测试 EDI 交换的另一个副本放在该文件夹。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-304">Drop a second copy of the test EDI interchange into the folder.</span></span>  
  
3.  <span data-ttu-id="0bfb9-305">打开与交换的发送端口关联的文件夹，并打开批处理交换。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-305">Open the folder that you associated with the send port for interchanges, and open the batched interchange.</span></span> <span data-ttu-id="0bfb9-306">验证交换是否包含一组 ISA 和 GS 标头以及两个事务集。</span><span class="sxs-lookup"><span data-stu-id="0bfb9-306">Verify that the interchange contains one set of ISA and GS headers, and two transaction sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bfb9-307">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bfb9-307">See Also</span></span>  
 <span data-ttu-id="0bfb9-308">[开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="0bfb9-308">[Developing and Configuring BizTalk Server EDI Solutions](../core/developing-and-configuring-biztalk-server-edi-solutions.md) </span></span>  
 <span data-ttu-id="0bfb9-309">[配置传出批处理](../core/configuring-an-outgoing-batch.md) </span><span class="sxs-lookup"><span data-stu-id="0bfb9-309">[Configuring an Outgoing Batch](../core/configuring-an-outgoing-batch.md) </span></span>  
 <span data-ttu-id="0bfb9-310">[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md) </span><span class="sxs-lookup"><span data-stu-id="0bfb9-310">[Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md) </span></span>  
 <span data-ttu-id="0bfb9-311">[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md) </span><span class="sxs-lookup"><span data-stu-id="0bfb9-311">[Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md) </span></span>  
 <span data-ttu-id="0bfb9-312">[演练 (X12)： 接收 EDI 交换和发送回确认](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md) </span><span class="sxs-lookup"><span data-stu-id="0bfb9-312">[Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md) </span></span>  
 [<span data-ttu-id="0bfb9-313">演练 (X12)： 发送 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="0bfb9-313">Walkthrough (X12): Sending EDI Interchanges</span></span>](../core/walkthrough-x12-sending-edi-interchanges.md)