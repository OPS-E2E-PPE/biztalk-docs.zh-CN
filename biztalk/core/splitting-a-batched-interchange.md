---
title: 拆分批处理的交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e67bef19-77fb-47a9-88f3-ee20043b3691
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1cb3c6c912985a81a2265afa11bebc636381c5a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024059"
---
# <a name="splitting-a-batched-interchange"></a><span data-ttu-id="93231-102">拆分批处理的交换</span><span class="sxs-lookup"><span data-stu-id="93231-102">Splitting a Batched Interchange</span></span>
<span data-ttu-id="93231-103">本主题介绍了如何配置协议以便通过从交换拆分事务集来处理批处理的 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="93231-103">This topic describes how to configure an agreement for processing a batched EDI interchange by splitting the transaction sets from the interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="93231-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="93231-104">Prerequisites</span></span>  
 <span data-ttu-id="93231-105">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="93231-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-receive-a-split-edi-interchange"></a><span data-ttu-id="93231-106">接收一个拆分 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="93231-106">To receive a split EDI interchange</span></span>  
  
1. <span data-ttu-id="93231-107">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。</span><span class="sxs-lookup"><span data-stu-id="93231-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Parties** node.</span></span> <span data-ttu-id="93231-108">在中**参与方和业务配置文件**页上，单击具有将解析为传入批处理交换的协议的参与方。</span><span class="sxs-lookup"><span data-stu-id="93231-108">In the **Parties and Business Profiles** page, click the party that has the agreement that will resolve to the incoming batched interchange.</span></span> <span data-ttu-id="93231-109">在中**协议**部分中的页上，右键单击该协议，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="93231-109">In the **Agreement** section of the page, right-click the agreement and click **Properties**.</span></span> <span data-ttu-id="93231-110">在中**协议属性**对话框单向协议选项卡 （向其解析将入站批处理的交换） 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="93231-110">In the **Agreement Properties** dialog box, in the one-way agreement tab (to which the inbound batched interchange will resolve), do the following:</span></span>  
  
   1.  <span data-ttu-id="93231-111">在中**标识符**页上，请确保输入正确的值，使传入批处理的交换解析为该协议。</span><span class="sxs-lookup"><span data-stu-id="93231-111">In the **Identifiers** page, make sure you enter the correct values so that the incoming batched interchange resolves to this agreement.</span></span>  
  
       -   <span data-ttu-id="93231-112">情况下**X12**： 设置 ISA5、 ISA6、 ISA7 和 ISA8。</span><span class="sxs-lookup"><span data-stu-id="93231-112">In case of **X12**: Set ISA5, ISA6, ISA7, and ISA8.</span></span>  
  
       -   <span data-ttu-id="93231-113">情况下**Edifact**： 设置 UNB2.1、 UNB2.2、 UNB3.1 和 unb3.2 一起使用。</span><span class="sxs-lookup"><span data-stu-id="93231-113">In case of **Edifact**: Set UNB2.1, UNB2.2, UNB3.1, and UNB3.2.</span></span>  
  
   2.  <span data-ttu-id="93231-114">在中**本地主机设置**页 (下**交换设置**)，在**接收方设置**部分中，为**入站批处理选项**，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="93231-114">In the **Local Host Settings** page (under **Interchange Settings**), under **Receiver’s Settings** section, for the **Inbound batch processing option**, select one the following options:</span></span>  
  
       -   <span data-ttu-id="93231-115">**将交换拆分为事务集-出错时挂起事务集**– 选择此选项以指定 BizTalk Server 应解析为单独 XML 文档将交换中设置每个事务。</span><span class="sxs-lookup"><span data-stu-id="93231-115">**Split Interchange as Transaction Sets - suspend Transaction Sets on Error** – Select this option to specify that BizTalk Server should parse each transaction set in an interchange into a separate XML document.</span></span> <span data-ttu-id="93231-116">然后，BizTalk Server 将相应的信封应用到事务集，并且将事务集文档路由至 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="93231-116">BizTalk Server will then apply the appropriate envelope to the transaction set and route the transaction set document to the MessageBox.</span></span> <span data-ttu-id="93231-117">选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将仅挂起这些交换集。</span><span class="sxs-lookup"><span data-stu-id="93231-117">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend only those transaction sets.</span></span>  
  
       -   <span data-ttu-id="93231-118">**将交换拆分为事务集-出错时挂起交换**– 选择此选项以指定 BizTalk Server 应解析为单独 XML 文档将交换中设置每个事务。</span><span class="sxs-lookup"><span data-stu-id="93231-118">**Split Interchange as Transaction Sets - suspend Interchange on Error** – Select this option to specify that BizTalk Server should parse each transaction set in an interchange into a separate XML document.</span></span> <span data-ttu-id="93231-119">然后，BizTalk Server 将相应的信封应用到事务集，并且将事务集文档路由至 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="93231-119">BizTalk Server will then apply the appropriate envelope to the transaction set and route the transaction set document to the MessageBox.</span></span> <span data-ttu-id="93231-120">选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。</span><span class="sxs-lookup"><span data-stu-id="93231-120">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend the entire interchange.</span></span>  
  
2. <span data-ttu-id="93231-121">按下列操作为保留批创建 Visual Studio 项目：</span><span class="sxs-lookup"><span data-stu-id="93231-121">Create a Visual Studio project for the preserved batch as follows:</span></span>  
  
   1. <span data-ttu-id="93231-122">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建一个 BizTalk 项目，并为批处理内的所有消息添加架构。</span><span class="sxs-lookup"><span data-stu-id="93231-122">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a BizTalk project and add the schemas for all the messages within the batch.</span></span>  
  
   2. <span data-ttu-id="93231-123">生成和部署项目。</span><span class="sxs-lookup"><span data-stu-id="93231-123">Build and deploy the project.</span></span>  
  
3. <span data-ttu-id="93231-124">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，创建发送端口以便发送拆分批处理，如下所示：</span><span class="sxs-lookup"><span data-stu-id="93231-124">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, create a send port to send split batches as follows:</span></span>  
  
   1.  <span data-ttu-id="93231-125">发送管道设置为**EdiSend**或**AS2EdiSend**。</span><span class="sxs-lookup"><span data-stu-id="93231-125">Set the send pipeline to **EdiSend** or **AS2EdiSend**.</span></span>  
  
   2.  <span data-ttu-id="93231-126">将发送端口的筛选器设置为所需值以便提取每个事务集，例如，设置为 BTS.MessageType。</span><span class="sxs-lookup"><span data-stu-id="93231-126">Set the filter of the send port to the value required to pick up each transaction set, for example, to BTS.MessageType.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93231-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="93231-127">See Also</span></span>  
 <span data-ttu-id="93231-128">[配置 EDI 批](../core/configuring-edi-batches.md) </span><span class="sxs-lookup"><span data-stu-id="93231-128">[Configuring EDI Batches](../core/configuring-edi-batches.md) </span></span>  
 [<span data-ttu-id="93231-129">如何创建发送端口</span><span class="sxs-lookup"><span data-stu-id="93231-129">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)