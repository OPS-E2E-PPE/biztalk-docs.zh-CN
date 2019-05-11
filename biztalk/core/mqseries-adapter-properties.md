---
title: MQSeries 适配器属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90fa1355f17581c55645a375dcb782452cb55e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323696"
---
# <a name="mqseries-adapter-properties"></a><span data-ttu-id="27e86-102">MQSeries 适配器属性</span><span class="sxs-lookup"><span data-stu-id="27e86-102">MQSeries Adapter Properties</span></span>
<span data-ttu-id="27e86-103">若要从 BizTalk 业务流程中访问 MQSeries 标头属性，必须将对 MQSeries.dll 程序集的引用添加到你的项目中。</span><span class="sxs-lookup"><span data-stu-id="27e86-103">To access MQSeries header properties from a BizTalk orchestration, you must add a reference to the MQSeries.dll assembly to your project.</span></span> <span data-ttu-id="27e86-104">此程序集位于 MQSeries 适配器，例如，安装位置[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="27e86-104">This assembly is located where you installed the MQSeries adapter, for example, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="27e86-105">在引用 MQSeries 属性架构之后，其他上下文属性可供各种 BizTalk Server 开发工具 (例如，**消息赋值**形状在业务流程设计器中的)。</span><span class="sxs-lookup"><span data-stu-id="27e86-105">After you reference the MQSeries property schema, additional context properties are available to various BizTalk Server development tools (for example, the **Message Assignment** shape in Orchestration Designer).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27e86-106">请确保按照 IBM WebSphere MQ 文档中的准则，在使用 MQSeries 标头属性时。</span><span class="sxs-lookup"><span data-stu-id="27e86-106">Make sure that you follow the guidelines in the IBM WebSphere MQ documentation when you work with MQSeries header properties.</span></span>  
  
 <span data-ttu-id="27e86-107">适配器会自动升级一些 MQSeries 属性。</span><span class="sxs-lookup"><span data-stu-id="27e86-107">The adapter automatically promotes some MQSeries properties.</span></span> <span data-ttu-id="27e86-108">你的应用程序和自定义组件必须避免降级这些属性。</span><span class="sxs-lookup"><span data-stu-id="27e86-108">Your applications and custom components must avoid demoting these properties.</span></span> <span data-ttu-id="27e86-109">您可以通过使用自定义管道组件升级其他属性。</span><span class="sxs-lookup"><span data-stu-id="27e86-109">You can promote additional properties by using custom pipeline components.</span></span> <span data-ttu-id="27e86-110">自动升级的属性如下所示：</span><span class="sxs-lookup"><span data-stu-id="27e86-110">The automatically promoted properties are as follows:</span></span>  
  
-   <span data-ttu-id="27e86-111">**BizTalk_CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="27e86-111">**BizTalk_CorrelationID**</span></span>  
  
-   <span data-ttu-id="27e86-112">**MQMD_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="27e86-112">**MQMD_CorrelId**</span></span>  
  
-   <span data-ttu-id="27e86-113">**MQMD_MsgId**</span><span class="sxs-lookup"><span data-stu-id="27e86-113">**MQMD_MsgId**</span></span>  
  
-   <span data-ttu-id="27e86-114">**MQMD_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="27e86-114">**MQMD_ReplyToQ**</span></span>  
  
-   <span data-ttu-id="27e86-115">**MQMD_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="27e86-115">**MQMD_ReplyToQMgr**</span></span>  
  
-   <span data-ttu-id="27e86-116">**MQXQH_RemoteQMgrName**</span><span class="sxs-lookup"><span data-stu-id="27e86-116">**MQXQH_RemoteQMgrName**</span></span>  
  
-   <span data-ttu-id="27e86-117">**MQXQH_RemoteQName**</span><span class="sxs-lookup"><span data-stu-id="27e86-117">**MQXQH_RemoteQName**</span></span>  
  
-   <span data-ttu-id="27e86-118">**MQXQH_MsgDesc_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="27e86-118">**MQXQH_MsgDesc_CorrelId**</span></span>  
  
-   <span data-ttu-id="27e86-119">**MQXQH_MsgDesc_MsgId**</span><span class="sxs-lookup"><span data-stu-id="27e86-119">**MQXQH_MsgDesc_MsgId**</span></span>  
  
-   <span data-ttu-id="27e86-120">**MQXQH_MsgDesc_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="27e86-120">**MQXQH_MsgDesc_ReplyToQ**</span></span>  
  
-   <span data-ttu-id="27e86-121">**MQXQH_MsgDesc_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="27e86-121">**MQXQH_MsgDesc_ReplyToQMgr**</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27e86-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="27e86-122">In This Section</span></span>  
  
-   [<span data-ttu-id="27e86-123">属性的数据类型转换</span><span class="sxs-lookup"><span data-stu-id="27e86-123">Data Type Conversion of Properties</span></span>](../core/data-type-conversion-of-properties.md)  
  
-   [<span data-ttu-id="27e86-124">与 BizTalk Server 相关的属性</span><span class="sxs-lookup"><span data-stu-id="27e86-124">Properties Related to BizTalk Server</span></span>](../core/properties-related-to-biztalk-server.md)  
  
-   [<span data-ttu-id="27e86-125">MQSeries 上下文属性</span><span class="sxs-lookup"><span data-stu-id="27e86-125">MQSeries Context Properties</span></span>](../core/mqseries-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="27e86-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="27e86-126">See Also</span></span>  
 [<span data-ttu-id="27e86-127">配置 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="27e86-127">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)