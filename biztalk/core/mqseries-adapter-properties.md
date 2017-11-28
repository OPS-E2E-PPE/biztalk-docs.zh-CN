---
title: "MQSeries 适配器属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQXQH_RemoteQName property [MQSeries adapters]
- MQMD_ReplyToQ property [MQSeries adapters]
- configuring [MQSeries adapters], properties
- MQXQH_MsgDesc_ReplyToQMgr property [MQSeries adapters]
- UserHttpHeaders property [MQSeries adapters]
- MQMD_CorrelId property [MQSeries adapters]
- MQXQH_MsgDesc_MsgId property [MQSeries adapters]
- MQXQH_MsgDesc_ReplyToQ property [MQSeries adapters]
- SubmissionHandle property [MQSeries adapters]
- BizTalk_CorrelationID property [MQSeries adapters]
- MQMD_ReplyToQMgr property [MQSeries adapters]
- EnableChunkedEncoding property [MQSeries adapters]
- MQSeries adapters, properties
- MQXQH_MsgDesc_CorrelId property [MQSeries adapters]
- MQXQH_RemoteQMgrName property [MQSeries adapters]
- MQMD_MsgId property [MQSeries adapters]
ms.assetid: c3cfbc8c-4c9b-431e-b0b6-4c065a69ce6b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fae8cc1ed67f077b6ae12945da10c58cf0f147da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-properties"></a><span data-ttu-id="d15b3-102">MQSeries 适配器属性</span><span class="sxs-lookup"><span data-stu-id="d15b3-102">MQSeries Adapter Properties</span></span>
<span data-ttu-id="d15b3-103">若要在 BizTalk 业务流程中访问 MQSeries 标头属性，必须向项目添加对 MQSeries.dll 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d15b3-103">To access MQSeries header properties from a BizTalk orchestration, you must add a reference to the MQSeries.dll assembly to your project.</span></span> <span data-ttu-id="d15b3-104">此程序集位于 MQSeries 适配器的安装位置，例如 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d15b3-104">This assembly is located where you installed the MQSeries adapter, for example, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="d15b3-105">引用 MQSeries 属性架构后，其他上下文属性可供各种 BizTalk Server 开发工具 (例如，**消息分配**形状中业务流程设计器)。</span><span class="sxs-lookup"><span data-stu-id="d15b3-105">After you reference the MQSeries property schema, additional context properties are available to various BizTalk Server development tools (for example, the **Message Assignment** shape in Orchestration Designer).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d15b3-106">在使用 MQSeries 标头属性时，请确保按照 IBM WebSphere MQ 文档中的指南操作。</span><span class="sxs-lookup"><span data-stu-id="d15b3-106">Make sure that you follow the guidelines in the IBM WebSphere MQ documentation when you work with MQSeries header properties.</span></span>  
  
 <span data-ttu-id="d15b3-107">适配器会自动升级一些 MQSeries 属性。</span><span class="sxs-lookup"><span data-stu-id="d15b3-107">The adapter automatically promotes some MQSeries properties.</span></span> <span data-ttu-id="d15b3-108">应用程序和自定义组件必须避免对这些属性进行降级。</span><span class="sxs-lookup"><span data-stu-id="d15b3-108">Your applications and custom components must avoid demoting these properties.</span></span> <span data-ttu-id="d15b3-109">您可以通过使用自定义管道组件来升级其他属性。</span><span class="sxs-lookup"><span data-stu-id="d15b3-109">You can promote additional properties by using custom pipeline components.</span></span> <span data-ttu-id="d15b3-110">自动升级的属性如下所示：</span><span class="sxs-lookup"><span data-stu-id="d15b3-110">The automatically promoted properties are as follows:</span></span>  
  
-   <span data-ttu-id="d15b3-111">**BizTalk_CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="d15b3-111">**BizTalk_CorrelationID**</span></span>  
  
-   <span data-ttu-id="d15b3-112">**MQMD_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="d15b3-112">**MQMD_CorrelId**</span></span>  
  
-   <span data-ttu-id="d15b3-113">**MQMD_MsgId**</span><span class="sxs-lookup"><span data-stu-id="d15b3-113">**MQMD_MsgId**</span></span>  
  
-   <span data-ttu-id="d15b3-114">**MQMD_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="d15b3-114">**MQMD_ReplyToQ**</span></span>  
  
-   <span data-ttu-id="d15b3-115">**MQMD_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="d15b3-115">**MQMD_ReplyToQMgr**</span></span>  
  
-   <span data-ttu-id="d15b3-116">**MQXQH_RemoteQMgrName**</span><span class="sxs-lookup"><span data-stu-id="d15b3-116">**MQXQH_RemoteQMgrName**</span></span>  
  
-   <span data-ttu-id="d15b3-117">**MQXQH_RemoteQName**</span><span class="sxs-lookup"><span data-stu-id="d15b3-117">**MQXQH_RemoteQName**</span></span>  
  
-   <span data-ttu-id="d15b3-118">**MQXQH_MsgDesc_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="d15b3-118">**MQXQH_MsgDesc_CorrelId**</span></span>  
  
-   <span data-ttu-id="d15b3-119">**MQXQH_MsgDesc_MsgId**</span><span class="sxs-lookup"><span data-stu-id="d15b3-119">**MQXQH_MsgDesc_MsgId**</span></span>  
  
-   <span data-ttu-id="d15b3-120">**MQXQH_MsgDesc_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="d15b3-120">**MQXQH_MsgDesc_ReplyToQ**</span></span>  
  
-   <span data-ttu-id="d15b3-121">**MQXQH_MsgDesc_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="d15b3-121">**MQXQH_MsgDesc_ReplyToQMgr**</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d15b3-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="d15b3-122">In This Section</span></span>  
  
-   [<span data-ttu-id="d15b3-123">数据类型转换的属性</span><span class="sxs-lookup"><span data-stu-id="d15b3-123">Data Type Conversion of Properties</span></span>](../core/data-type-conversion-of-properties.md)  
  
-   [<span data-ttu-id="d15b3-124">与 BizTalk Server 相关的属性</span><span class="sxs-lookup"><span data-stu-id="d15b3-124">Properties Related to BizTalk Server</span></span>](../core/properties-related-to-biztalk-server.md)  
  
-   [<span data-ttu-id="d15b3-125">MQSeries 上下文属性</span><span class="sxs-lookup"><span data-stu-id="d15b3-125">MQSeries Context Properties</span></span>](../core/mqseries-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="d15b3-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d15b3-126">See Also</span></span>  
 [<span data-ttu-id="d15b3-127">配置 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="d15b3-127">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)