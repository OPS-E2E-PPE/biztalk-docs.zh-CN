---
title: "保留批处理的交换 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 907e07f3-1f3e-485e-a82d-b28eb7658e0a
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e7ea2bdef1fe2b2c3db92421d610b0b889e0460
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="preserving-a-batched-interchange"></a><span data-ttu-id="4eb29-102">保留批处理交换</span><span class="sxs-lookup"><span data-stu-id="4eb29-102">Preserving a Batched Interchange</span></span>
<span data-ttu-id="4eb29-103">本主题介绍了如何配置协议以便将批处理 EDI 交换作为单个文档处理而不是从交换拆分事务集。</span><span class="sxs-lookup"><span data-stu-id="4eb29-103">This topic describes how to configure an agreement for processing a batched EDI interchange as a single document without splitting the transaction sets from the interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4eb29-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="4eb29-104">Prerequisites</span></span>  
 <span data-ttu-id="4eb29-105">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="4eb29-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-receiving-and-sending-of-a-preserved-batch"></a><span data-ttu-id="4eb29-106">配置保留的批的接收和发送</span><span class="sxs-lookup"><span data-stu-id="4eb29-106">To configure the receiving and sending of a preserved batch</span></span>  
  
1.  <span data-ttu-id="4eb29-107">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。</span><span class="sxs-lookup"><span data-stu-id="4eb29-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Parties** node.</span></span> <span data-ttu-id="4eb29-108">在**方和业务配置文件**页上，单击具有协议，将解析为传入批处理的交换的当事方。</span><span class="sxs-lookup"><span data-stu-id="4eb29-108">In the **Parties and Business Profiles** page, click the party that has the agreement that will resolve to the incoming batched interchange.</span></span> <span data-ttu-id="4eb29-109">在**协议**部分的页上，右键单击该协议，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4eb29-109">In the **Agreement** section of the page, right-click the agreement and click **Properties**.</span></span> <span data-ttu-id="4eb29-110">在**协议属性**对话框中，在 （向其解决将入站批处理的交换） 的单向协议选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4eb29-110">In the **Agreement Properties** dialog box, in the one-way agreement tab (to which the inbound batched interchange will resolve), do the following:</span></span>  
  
    1.  <span data-ttu-id="4eb29-111">在**标识符**页上，为 ISA5、 ISA6、 ISA7 和 ISA8 输入 enter 值的值。</span><span class="sxs-lookup"><span data-stu-id="4eb29-111">In the **Identifiers** page, enter the values for enter values for ISA5, ISA6, ISA7, and ISA8.</span></span> <span data-ttu-id="4eb29-112">确保您输入了正确的值，以便传入的批处理交换解析为该协议。</span><span class="sxs-lookup"><span data-stu-id="4eb29-112">Make sure you enter the correct values so that the incoming batched interchange resolves to this agreement.</span></span>  
  
    2.  <span data-ttu-id="4eb29-113">在**本地主机设置**页 (下**交换设置**) 下**接收方设置**部分中，为**入站批处理选项**，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="4eb29-113">In the **Local Host Settings** page (under **Interchange Settings**), under **Receiver’s Settings** section, for the **Inbound batch processing option**, select one the following options:</span></span>  
  
        -   <span data-ttu-id="4eb29-114">**保留交换-出错时暂停交换**– 选择此选项以指定 BizTalk Server，应保留交换不变，以创建 XML 文档是否为整个批处理的交换。</span><span class="sxs-lookup"><span data-stu-id="4eb29-114">**Preserve Interchange - suspend Interchange on Error** – Select this option to specify that BizTalk Server should leave the interchange intact, creating an XML document for the entire batched interchange.</span></span> <span data-ttu-id="4eb29-115">选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。</span><span class="sxs-lookup"><span data-stu-id="4eb29-115">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend the entire interchange.</span></span>  
  
        -   <span data-ttu-id="4eb29-116">**保留交换-出错时暂停事务集**– 选择此选项以指定 BizTalk Server，应保留交换不变，以创建 XML 文档是否为整个批处理的交换。</span><span class="sxs-lookup"><span data-stu-id="4eb29-116">**Preserve Interchange - suspend Transaction Sets on Error** – Select this option to specify that BizTalk Server should leave the interchange intact, creating an XML document for the entire batched interchange.</span></span> <span data-ttu-id="4eb29-117">使用此选项时，如果交换中的一个或多个事务集未通过验证，BizTalk Server 将会挂起仅这些事务集，同时继续处理所有其他事务集。</span><span class="sxs-lookup"><span data-stu-id="4eb29-117">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend only those transaction sets, while continuing to process all other transaction sets.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4eb29-118">如果您选择以上两个选项之一，则交换、组和事务集段属性（确定 BizTalk Server 将如何创建传出交换的 ISA、GS 和 ST 标头）将不适用。</span><span class="sxs-lookup"><span data-stu-id="4eb29-118">If you select either of the two options mentioned above, the interchange, group, and transaction set segment properties (which determine how BizTalk Server will create the ISA, GS, and ST headers of an outgoing interchange) do not apply.</span></span> <span data-ttu-id="4eb29-119">被保留的交换中存在的交换、组和事务集标头将在发送管道对其执行发送前的相关处理时予以保留。</span><span class="sxs-lookup"><span data-stu-id="4eb29-119">The interchange, group, and transaction-set headers that exist in the interchange that is being preserved are retained when the send pipeline processes it for sending.</span></span> <span data-ttu-id="4eb29-120">但是，如果您要使用在协议中为交换指定的值，请将 `EDI.PopulateInterchangeValues` 上下文属性设置为“true”。</span><span class="sxs-lookup"><span data-stu-id="4eb29-120">However, if you do want to use the values specified for the interchange in the agreement, set the `EDI.PopulateInterchangeValues` context property to true.</span></span>  
  
2.  <span data-ttu-id="4eb29-121">按下列操作为保留批创建 Visual Studio 项目：</span><span class="sxs-lookup"><span data-stu-id="4eb29-121">Create a Visual Studio project for the preserved batch as follows:</span></span>  
  
    1.  <span data-ttu-id="4eb29-122">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建一个 BizTalk 项目，并为批处理内的所有消息添加架构。</span><span class="sxs-lookup"><span data-stu-id="4eb29-122">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a BizTalk project and add the schemas for all the messages within the batch.</span></span>  
  
    2.  <span data-ttu-id="4eb29-123">生成和部署项目。</span><span class="sxs-lookup"><span data-stu-id="4eb29-123">Build and deploy the project.</span></span>  
  
3.  <span data-ttu-id="4eb29-124">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台，创建一个发送端口按照以下步骤发送保留批。</span><span class="sxs-lookup"><span data-stu-id="4eb29-124">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, create a send port to send preserved batches as follows:</span></span>  
  
    1.  <span data-ttu-id="4eb29-125">发送管道设置为**EdiSend**或**AS2EdiSend**。</span><span class="sxs-lookup"><span data-stu-id="4eb29-125">Set the send pipeline to **EdiSend** or **AS2EdiSend**.</span></span>  
  
    2.  <span data-ttu-id="4eb29-126">将发送端口的筛选器设置为上下文属性 `EDI.ReuseEnvelope == True`。</span><span class="sxs-lookup"><span data-stu-id="4eb29-126">Set the filter of the send port to the context property `EDI.ReuseEnvelope == True`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4eb29-127">设置此筛选器以确保发送端口将订阅所有保留的批处理交换。</span><span class="sxs-lookup"><span data-stu-id="4eb29-127">Setting this filter ensures that the send port will subscribe to all batched interchanges that are preserved.</span></span> <span data-ttu-id="4eb29-128">EdiReceive 接收管道会升级上下文属性 `EDI.ReuseEnvelope` 以便将交换标识为已保留。</span><span class="sxs-lookup"><span data-stu-id="4eb29-128">The EdiReceive receive pipeline promotes the context property `EDI.ReuseEnvelope` to identify the interchange as preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eb29-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4eb29-129">See Also</span></span>  
 <span data-ttu-id="4eb29-130">[配置 EDI 批处理](../core/configuring-edi-batches.md) </span><span class="sxs-lookup"><span data-stu-id="4eb29-130">[Configuring EDI Batches](../core/configuring-edi-batches.md) </span></span>  
 [<span data-ttu-id="4eb29-131">如何创建发送端口</span><span class="sxs-lookup"><span data-stu-id="4eb29-131">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)