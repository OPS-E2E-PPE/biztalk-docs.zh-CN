---
title: BizTalk Server 消息上下文属性 （发送处理程序） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a065ba89-9fdb-47dc-9021-fb95cf347cdc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfd3dca7c807ef48c82d46743e749e19a40001bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016296"
---
# <a name="biztalk-server-message-context-properties-send-handlers"></a><span data-ttu-id="f12ec-102">BizTalk Server 消息上下文属性 （发送处理程序）</span><span class="sxs-lookup"><span data-stu-id="f12ec-102">BizTalk Server Message Context Properties (Send Handlers)</span></span>
<span data-ttu-id="f12ec-103">除了消息负载之外，消息包含的补充信息必须在运行时从 BizTalk Server 业务流程访问。</span><span class="sxs-lookup"><span data-stu-id="f12ec-103">In addition to the message payload, the supplementary information that a message contains must be accessible from the BizTalk Server orchestration at run time.</span></span>  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a><span data-ttu-id="f12ec-104">TIBCO RV 消息信息升级为消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="f12ec-104">TIBCO RV Message Information Promoted as Message Context Properties</span></span>  
  
|<span data-ttu-id="f12ec-105">数据标识</span><span class="sxs-lookup"><span data-stu-id="f12ec-105">Data Identification</span></span>|<span data-ttu-id="f12ec-106">类型</span><span class="sxs-lookup"><span data-stu-id="f12ec-106">Type</span></span>|<span data-ttu-id="f12ec-107">可路由</span><span class="sxs-lookup"><span data-stu-id="f12ec-107">Routable</span></span>|<span data-ttu-id="f12ec-108">发送位置</span><span class="sxs-lookup"><span data-stu-id="f12ec-108">Send Location</span></span>|  
|-------------------------|----------|--------------|-------------------|  
|<span data-ttu-id="f12ec-109">发送主题</span><span class="sxs-lookup"><span data-stu-id="f12ec-109">Send Subject</span></span>|<span data-ttu-id="f12ec-110">string</span><span class="sxs-lookup"><span data-stu-id="f12ec-110">string</span></span>|<span data-ttu-id="f12ec-111">是</span><span class="sxs-lookup"><span data-stu-id="f12ec-111">Yes</span></span>|<span data-ttu-id="f12ec-112">指定 TIBCO Rendezvous 发送主题的业务流程。</span><span class="sxs-lookup"><span data-stu-id="f12ec-112">Orchestration specifies the TIBCO Rendezvous send subject.</span></span> <span data-ttu-id="f12ec-113">默认值为 Null。</span><span class="sxs-lookup"><span data-stu-id="f12ec-113">Default value is Null.</span></span> <span data-ttu-id="f12ec-114">必填字段，除非在端口配置中指定了默认主题。</span><span class="sxs-lookup"><span data-stu-id="f12ec-114">Mandatory unless a default subject is specified in the port configuration.</span></span>|  
|<span data-ttu-id="f12ec-115">答复主题</span><span class="sxs-lookup"><span data-stu-id="f12ec-115">Reply Subject</span></span>|<span data-ttu-id="f12ec-116">string</span><span class="sxs-lookup"><span data-stu-id="f12ec-116">string</span></span>|<span data-ttu-id="f12ec-117">是</span><span class="sxs-lookup"><span data-stu-id="f12ec-117">Yes</span></span>|<span data-ttu-id="f12ec-118">提供答复消息的主题的业务流程（相关时）。</span><span class="sxs-lookup"><span data-stu-id="f12ec-118">Orchestration provides a subject for reply messages, when pertinent.</span></span> <span data-ttu-id="f12ec-119">默认值为 Null。</span><span class="sxs-lookup"><span data-stu-id="f12ec-119">Default value is Null.</span></span>|  
  
## <a name="getting-a-tibco-reply"></a><span data-ttu-id="f12ec-120">获取 TIBCO 答复</span><span class="sxs-lookup"><span data-stu-id="f12ec-120">Getting a TIBCO Reply</span></span>  
 <span data-ttu-id="f12ec-121">**问：** 原理的 BizTalk 适配器的 TIBCO Rendezvous 读取和处理业务流程中的答复主题，您可以将其用作发送主题响应？</span><span class="sxs-lookup"><span data-stu-id="f12ec-121">**Question:** How does BizTalk Adapter for TIBCO Rendezvous read and manipulate the reply subject inside an orchestration so that you can use it as the send subject for the response?</span></span> <span data-ttu-id="f12ec-122">适配器如何获得来自 Rendezvous 的传入消息的消息上下文？</span><span class="sxs-lookup"><span data-stu-id="f12ec-122">How does the adapter get to the message context of an incoming message from Rendezvous?</span></span>  
  
 <span data-ttu-id="f12ec-123">**答案是：** 答复主题在传入消息的上下文中填充和业务流程可以读取它。</span><span class="sxs-lookup"><span data-stu-id="f12ec-123">**Answer:** The reply subject is populated in the context of the incoming message, and the orchestration can read it.</span></span> <span data-ttu-id="f12ec-124">如果业务流程最终可以生成答复，则可以使用该值来设置答复消息的发送主题。</span><span class="sxs-lookup"><span data-stu-id="f12ec-124">If the orchestration ultimately produces a reply, it can use that value to set the send subject of the reply message.</span></span>  
  
1. <span data-ttu-id="f12ec-125">在 BizTalk Server 项目中，请向 <install_directory>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll 中添加引用。</span><span class="sxs-lookup"><span data-stu-id="f12ec-125">In a BizTalk Server project, add a reference to <install_directory>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span>  
  
2. <span data-ttu-id="f12ec-126">在业务流程中（传输传入 Rendezvous 消息的“接收”形状和发送答复的“发送”形状之间的某个位置），添加消息构造/赋值形状（或表达式形状）以进行某些类似于下面您构造答复示例的操作。</span><span class="sxs-lookup"><span data-stu-id="f12ec-126">In the orchestration (somewhere between the Receive shape that is handed the incoming Rendezvous message and the Send shape that is sending the reply), add a message construction/assignment shape (or an expression shape) to do something like the following example to the reply you constructed:</span></span>  
  
   ```  
   OutgoingMsg(Rendezvous.SendSubject) = IncomingMsg  
   (Rendezvous.ReplySubject);  
   ```  
   ## <a name="management-assembly"></a><span data-ttu-id="f12ec-127">管理程序集</span><span class="sxs-lookup"><span data-stu-id="f12ec-127">Management assembly</span></span>
   <span data-ttu-id="f12ec-128">TIBCO Rendezvous 未提供元数据储存库，并且用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器管理程序集未提供浏览功能或架构生成。</span><span class="sxs-lookup"><span data-stu-id="f12ec-128">TIBCO Rendezvous does not provide metadata repositories, and Microsoft BizTalk Adapter for TIBCO Rendezvous management assembly does not provide browsing capabilities or schema generation.</span></span> <span data-ttu-id="f12ec-129">因此，您必须向 BizTalk Server 提供架构。</span><span class="sxs-lookup"><span data-stu-id="f12ec-129">Therefore, you must provide a schema to BizTalk Server.</span></span> <span data-ttu-id="f12ec-130">有关详细信息，请参阅[安装、 架构和限制](../core/installing-biztalk-adapter-for-tibco-rendezvous.md)。</span><span class="sxs-lookup"><span data-stu-id="f12ec-130">For more information, see [Install, schemas, & limitations](../core/installing-biztalk-adapter-for-tibco-rendezvous.md).</span></span>
  
   <span data-ttu-id="f12ec-131">用于 TIBCO Rendezvous 的 BizTalk 适配器包括具有预定义类型的架构。</span><span class="sxs-lookup"><span data-stu-id="f12ec-131">BizTalk Adapter for TIBCO Rendezvous includes a schema with predefined types.</span></span> <span data-ttu-id="f12ec-132">为某些特定数据类型（数组）生成消息时，该适配器将使用这些类型。</span><span class="sxs-lookup"><span data-stu-id="f12ec-132">The adapter uses these types when generating messages for some specific data types (arrays).</span></span>

  
## <a name="see-also"></a><span data-ttu-id="f12ec-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="f12ec-133">See Also</span></span>  
 <span data-ttu-id="f12ec-134">[用于 TIBCO Rendezvous 中的发送处理程序的数据类型映射](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="f12ec-134">[Data Type Mapping for Send Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="f12ec-135">创建 TIBCO Rendezvous 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="f12ec-135">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)