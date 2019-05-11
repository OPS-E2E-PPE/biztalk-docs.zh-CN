---
title: 保留批的交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 907e07f3-1f3e-485e-a82d-b28eb7658e0a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4360e4e042ee7302935d20029be2880aee9f4be2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271160"
---
# <a name="preserving-a-batched-interchange"></a><span data-ttu-id="18744-102">保留批的交换</span><span class="sxs-lookup"><span data-stu-id="18744-102">Preserving a Batched Interchange</span></span>
<span data-ttu-id="18744-103">本主题介绍如何配置批处理的 EDI 交换作为单个文档处理而不拆分事务集从交换的协议。</span><span class="sxs-lookup"><span data-stu-id="18744-103">This topic describes how to configure an agreement for processing a batched EDI interchange as a single document without splitting the transaction sets from the interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="18744-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="18744-104">Prerequisites</span></span>  
 <span data-ttu-id="18744-105">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="18744-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-receiving-and-sending-of-a-preserved-batch"></a><span data-ttu-id="18744-106">若要配置接收和发送保留批</span><span class="sxs-lookup"><span data-stu-id="18744-106">To configure the receiving and sending of a preserved batch</span></span>  
  
1. <span data-ttu-id="18744-107">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。</span><span class="sxs-lookup"><span data-stu-id="18744-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Parties** node.</span></span> <span data-ttu-id="18744-108">在中**参与方和业务配置文件**页上，单击具有将解析为传入批处理交换的协议的参与方。</span><span class="sxs-lookup"><span data-stu-id="18744-108">In the **Parties and Business Profiles** page, click the party that has the agreement that will resolve to the incoming batched interchange.</span></span> <span data-ttu-id="18744-109">在中**协议**部分中的页上，右键单击该协议，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="18744-109">In the **Agreement** section of the page, right-click the agreement and click **Properties**.</span></span> <span data-ttu-id="18744-110">在中**协议属性**对话框单向协议选项卡 （向其解析将入站批处理的交换） 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="18744-110">In the **Agreement Properties** dialog box, in the one-way agreement tab (to which the inbound batched interchange will resolve), do the following:</span></span>  
  
   1.  <span data-ttu-id="18744-111">在中**标识符**页上，输入为 ISA5、 ISA6、 ISA7 和 ISA8 的值输入值。</span><span class="sxs-lookup"><span data-stu-id="18744-111">In the **Identifiers** page, enter the values for enter values for ISA5, ISA6, ISA7, and ISA8.</span></span> <span data-ttu-id="18744-112">请确保输入正确的值，使传入批处理的交换解析为该协议。</span><span class="sxs-lookup"><span data-stu-id="18744-112">Make sure you enter the correct values so that the incoming batched interchange resolves to this agreement.</span></span>  
  
   2.  <span data-ttu-id="18744-113">在中**本地主机设置**页 (下**交换设置**)，在**接收方设置**部分中，为**入站批处理选项**，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="18744-113">In the **Local Host Settings** page (under **Interchange Settings**), under **Receiver’s Settings** section, for the **Inbound batch processing option**, select one the following options:</span></span>  
  
       -   <span data-ttu-id="18744-114">**保留交换-出错时挂起交换**– 选择此选项可指定 BizTalk Server 应原样保留交换不变，同时创建一个 XML 文档为整个批处理交换。</span><span class="sxs-lookup"><span data-stu-id="18744-114">**Preserve Interchange - suspend Interchange on Error** – Select this option to specify that BizTalk Server should leave the interchange intact, creating an XML document for the entire batched interchange.</span></span> <span data-ttu-id="18744-115">使用此选项时，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。</span><span class="sxs-lookup"><span data-stu-id="18744-115">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend the entire interchange.</span></span>  
  
       -   <span data-ttu-id="18744-116">**保留交换-出错时挂起事务集**– 选择此选项可指定 BizTalk Server 应原样保留交换不变，同时创建一个 XML 文档为整个批处理交换。</span><span class="sxs-lookup"><span data-stu-id="18744-116">**Preserve Interchange - suspend Transaction Sets on Error** – Select this option to specify that BizTalk Server should leave the interchange intact, creating an XML document for the entire batched interchange.</span></span> <span data-ttu-id="18744-117">使用此选项，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起的事务集，同时继续处理所有其他事务集。</span><span class="sxs-lookup"><span data-stu-id="18744-117">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend only those transaction sets, while continuing to process all other transaction sets.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="18744-118">如果选择上面提到的两个选项之一，则交换、 组和事务集段属性 （确定 BizTalk Server 将如何创建传出交换的 ISA、 GS 和 ST 标头） 不适。</span><span class="sxs-lookup"><span data-stu-id="18744-118">If you select either of the two options mentioned above, the interchange, group, and transaction set segment properties (which determine how BizTalk Server will create the ISA, GS, and ST headers of an outgoing interchange) do not apply.</span></span> <span data-ttu-id="18744-119">当发送管道对其进行处理用于发送保留交换、 组和要保留的交换中存在的事务集标头。</span><span class="sxs-lookup"><span data-stu-id="18744-119">The interchange, group, and transaction-set headers that exist in the interchange that is being preserved are retained when the send pipeline processes it for sending.</span></span> <span data-ttu-id="18744-120">但是，如果你确实想要使用的交换协议中指定的值，设置`EDI.PopulateInterchangeValues`上下文属性设为 true。</span><span class="sxs-lookup"><span data-stu-id="18744-120">However, if you do want to use the values specified for the interchange in the agreement, set the `EDI.PopulateInterchangeValues` context property to true.</span></span>  
  
2. <span data-ttu-id="18744-121">创建保留的批处理的 Visual Studio 项目，如下所示：</span><span class="sxs-lookup"><span data-stu-id="18744-121">Create a Visual Studio project for the preserved batch as follows:</span></span>  
  
   1. <span data-ttu-id="18744-122">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、 创建 BizTalk 项目并添加批中的所有消息的架构。</span><span class="sxs-lookup"><span data-stu-id="18744-122">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a BizTalk project and add the schemas for all the messages within the batch.</span></span>  
  
   2. <span data-ttu-id="18744-123">生成和部署项目。</span><span class="sxs-lookup"><span data-stu-id="18744-123">Build and deploy the project.</span></span>  
  
3. <span data-ttu-id="18744-124">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建发送端口以发送保留的批，如下所示：</span><span class="sxs-lookup"><span data-stu-id="18744-124">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, create a send port to send preserved batches as follows:</span></span>  
  
   1.  <span data-ttu-id="18744-125">发送管道设置为**EdiSend**或**AS2EdiSend**。</span><span class="sxs-lookup"><span data-stu-id="18744-125">Set the send pipeline to **EdiSend** or **AS2EdiSend**.</span></span>  
  
   2.  <span data-ttu-id="18744-126">将发送端口的筛选器设置为上下文属性`EDI.ReuseEnvelope == True`。</span><span class="sxs-lookup"><span data-stu-id="18744-126">Set the filter of the send port to the context property `EDI.ReuseEnvelope == True`.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="18744-127">设置此筛选器，可确保发送端口将订阅保留的所有批处理交换。</span><span class="sxs-lookup"><span data-stu-id="18744-127">Setting this filter ensures that the send port will subscribe to all batched interchanges that are preserved.</span></span> <span data-ttu-id="18744-128">EdiReceive 接收管道会升级上下文属性`EDI.ReuseEnvelope`以将交换标识为保留。</span><span class="sxs-lookup"><span data-stu-id="18744-128">The EdiReceive receive pipeline promotes the context property `EDI.ReuseEnvelope` to identify the interchange as preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18744-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="18744-129">See Also</span></span>  
 <span data-ttu-id="18744-130">[配置 EDI 批](../core/configuring-edi-batches.md) </span><span class="sxs-lookup"><span data-stu-id="18744-130">[Configuring EDI Batches](../core/configuring-edi-batches.md) </span></span>  
 [<span data-ttu-id="18744-131">如何创建发送端口</span><span class="sxs-lookup"><span data-stu-id="18744-131">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)