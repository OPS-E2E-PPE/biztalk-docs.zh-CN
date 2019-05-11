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
ms.openlocfilehash: 4396f3404b885d4b2069eae2b6e9be882401e664
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358149"
---
# <a name="biztalk-server-message-context-properties-send-handlers"></a><span data-ttu-id="1273d-102">BizTalk Server 消息上下文属性 （发送处理程序）</span><span class="sxs-lookup"><span data-stu-id="1273d-102">BizTalk Server Message Context Properties (Send Handlers)</span></span>
<span data-ttu-id="1273d-103">除了消息负载中，一条消息包含的补充信息必须可从 BizTalk Server 业务流程在运行时访问。</span><span class="sxs-lookup"><span data-stu-id="1273d-103">In addition to the message payload, the supplementary information that a message contains must be accessible from the BizTalk Server orchestration at run time.</span></span>  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a><span data-ttu-id="1273d-104">TIBCO RV 消息信息升级为消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="1273d-104">TIBCO RV Message Information Promoted as Message Context Properties</span></span>  
  
|<span data-ttu-id="1273d-105">数据标识</span><span class="sxs-lookup"><span data-stu-id="1273d-105">Data Identification</span></span>|<span data-ttu-id="1273d-106">类型</span><span class="sxs-lookup"><span data-stu-id="1273d-106">Type</span></span>|<span data-ttu-id="1273d-107">路由</span><span class="sxs-lookup"><span data-stu-id="1273d-107">Routable</span></span>|<span data-ttu-id="1273d-108">发送位置</span><span class="sxs-lookup"><span data-stu-id="1273d-108">Send Location</span></span>|  
|-------------------------|----------|--------------|-------------------|  
|<span data-ttu-id="1273d-109">发送主题</span><span class="sxs-lookup"><span data-stu-id="1273d-109">Send Subject</span></span>|<span data-ttu-id="1273d-110">string</span><span class="sxs-lookup"><span data-stu-id="1273d-110">string</span></span>|<span data-ttu-id="1273d-111">是</span><span class="sxs-lookup"><span data-stu-id="1273d-111">Yes</span></span>|<span data-ttu-id="1273d-112">业务流程指定 TIBCO Rendezvous 发送主题。</span><span class="sxs-lookup"><span data-stu-id="1273d-112">Orchestration specifies the TIBCO Rendezvous send subject.</span></span> <span data-ttu-id="1273d-113">默认值为 Null。</span><span class="sxs-lookup"><span data-stu-id="1273d-113">Default value is Null.</span></span> <span data-ttu-id="1273d-114">必需，除非在端口配置中指定了默认主题。</span><span class="sxs-lookup"><span data-stu-id="1273d-114">Mandatory unless a default subject is specified in the port configuration.</span></span>|  
|<span data-ttu-id="1273d-115">答复主题</span><span class="sxs-lookup"><span data-stu-id="1273d-115">Reply Subject</span></span>|<span data-ttu-id="1273d-116">string</span><span class="sxs-lookup"><span data-stu-id="1273d-116">string</span></span>|<span data-ttu-id="1273d-117">是</span><span class="sxs-lookup"><span data-stu-id="1273d-117">Yes</span></span>|<span data-ttu-id="1273d-118">业务流程提供使用者的答复消息，相关时。</span><span class="sxs-lookup"><span data-stu-id="1273d-118">Orchestration provides a subject for reply messages, when pertinent.</span></span> <span data-ttu-id="1273d-119">默认值为 Null。</span><span class="sxs-lookup"><span data-stu-id="1273d-119">Default value is Null.</span></span>|  
  
## <a name="getting-a-tibco-reply"></a><span data-ttu-id="1273d-120">获取 TIBCO 答复</span><span class="sxs-lookup"><span data-stu-id="1273d-120">Getting a TIBCO Reply</span></span>  
 <span data-ttu-id="1273d-121">**问：** 如何用于 TIBCO Rendezvous 的 BizTalk 适配器读取和处理业务流程中的答复主题，您可以将其用作发送主题响应？</span><span class="sxs-lookup"><span data-stu-id="1273d-121">**Question:** How does BizTalk Adapter for TIBCO Rendezvous read and manipulate the reply subject inside an orchestration so that you can use it as the send subject for the response?</span></span> <span data-ttu-id="1273d-122">适配器如何作用到传入消息的消息上下文来自 Rendezvous？</span><span class="sxs-lookup"><span data-stu-id="1273d-122">How does the adapter get to the message context of an incoming message from Rendezvous?</span></span>  
  
 <span data-ttu-id="1273d-123">**答案：** 答复主题在传入消息的上下文中填充和业务流程可以读取它。</span><span class="sxs-lookup"><span data-stu-id="1273d-123">**Answer:** The reply subject is populated in the context of the incoming message, and the orchestration can read it.</span></span> <span data-ttu-id="1273d-124">如果业务流程最终可以生成答复，它可以使用该值来设置答复消息的发送主题。</span><span class="sxs-lookup"><span data-stu-id="1273d-124">If the orchestration ultimately produces a reply, it can use that value to set the send subject of the reply message.</span></span>  
  
1. <span data-ttu-id="1273d-125">在 BizTalk Server 项目中，将添加到 < 请 > \TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="1273d-125">In a BizTalk Server project, add a reference to <install_directory>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span>  
  
2. <span data-ttu-id="1273d-126">在业务流程 （某处之间分发传入 Rendezvous 消息的接收形状和发送答复的发送形状），添加消息构造/赋值形状 （或表达式形状） 来执行一些操作如下例所示为您构造的答复：</span><span class="sxs-lookup"><span data-stu-id="1273d-126">In the orchestration (somewhere between the Receive shape that is handed the incoming Rendezvous message and the Send shape that is sending the reply), add a message construction/assignment shape (or an expression shape) to do something like the following example to the reply you constructed:</span></span>  
  
   ```  
   OutgoingMsg(Rendezvous.SendSubject) = IncomingMsg  
   (Rendezvous.ReplySubject);  
   ```  
   ## <a name="management-assembly"></a><span data-ttu-id="1273d-127">管理程序集</span><span class="sxs-lookup"><span data-stu-id="1273d-127">Management assembly</span></span>
   <span data-ttu-id="1273d-128">TIBCO Rendezvous 未提供元数据存储库，用于 TIBCO Rendezvous 管理程序集的 Microsoft BizTalk 适配器不提供浏览功能或架构生成。</span><span class="sxs-lookup"><span data-stu-id="1273d-128">TIBCO Rendezvous does not provide metadata repositories, and Microsoft BizTalk Adapter for TIBCO Rendezvous management assembly does not provide browsing capabilities or schema generation.</span></span> <span data-ttu-id="1273d-129">因此，必须向 BizTalk Server 提供架构。</span><span class="sxs-lookup"><span data-stu-id="1273d-129">Therefore, you must provide a schema to BizTalk Server.</span></span> <span data-ttu-id="1273d-130">有关详细信息，请参阅[安装、 架构和限制](../core/installing-biztalk-adapter-for-tibco-rendezvous.md)。</span><span class="sxs-lookup"><span data-stu-id="1273d-130">For more information, see [Install, schemas, & limitations](../core/installing-biztalk-adapter-for-tibco-rendezvous.md).</span></span>
  
   <span data-ttu-id="1273d-131">用于 TIBCO Rendezvous 的 BizTalk 适配器包括具有预定义的类型的架构。</span><span class="sxs-lookup"><span data-stu-id="1273d-131">BizTalk Adapter for TIBCO Rendezvous includes a schema with predefined types.</span></span> <span data-ttu-id="1273d-132">生成一些特定的数据类型 （数组） 的消息时，适配器将使用这些类型。</span><span class="sxs-lookup"><span data-stu-id="1273d-132">The adapter uses these types when generating messages for some specific data types (arrays).</span></span>

  
## <a name="see-also"></a><span data-ttu-id="1273d-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="1273d-133">See Also</span></span>  
 <span data-ttu-id="1273d-134">[用于 TIBCO Rendezvous 中的发送处理程序的数据类型映射](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="1273d-134">[Data Type Mapping for Send Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="1273d-135">创建 TIBCO Rendezvous 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="1273d-135">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)