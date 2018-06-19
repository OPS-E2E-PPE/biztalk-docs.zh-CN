---
title: 无法将消息路由到批处理业务流程，因为无法确定编码类型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d2ee38d-22c0-4fcf-bb68-b2ef00088c4c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe5054f53f779274c9b25f2751fdcb9d85545560
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241941"
---
# <a name="the-message-cannot-be-routed-to-the-batching-orchestration-as-the-encoding-type-could-not-be-determined"></a><span data-ttu-id="076c4-102">无法将消息路由到批处理业务流程，因为无法确定编码类型</span><span class="sxs-lookup"><span data-stu-id="076c4-102">The message cannot be routed to the batching orchestration as the Encoding type could not be determined</span></span>
## <a name="details"></a><span data-ttu-id="076c4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="076c4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="076c4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="076c4-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="076c4-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="076c4-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="076c4-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="076c4-106">Event ID</span></span>|-|  
|<span data-ttu-id="076c4-107">事件源</span><span class="sxs-lookup"><span data-stu-id="076c4-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="076c4-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="076c4-108"> EDI</span></span>|  
|<span data-ttu-id="076c4-109">组件</span><span class="sxs-lookup"><span data-stu-id="076c4-109">Component</span></span>|<span data-ttu-id="076c4-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="076c4-110">Batching Engine</span></span>|  
|<span data-ttu-id="076c4-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="076c4-111">Symbolic Name</span></span>|<span data-ttu-id="076c4-112">UnknownEncodingType</span><span class="sxs-lookup"><span data-stu-id="076c4-112">UnknownEncodingType</span></span>|  
|<span data-ttu-id="076c4-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="076c4-113">Message Text</span></span>|<span data-ttu-id="076c4-114">消息不能路由到批处理业务流程，因为无法确定编码类型。</span><span class="sxs-lookup"><span data-stu-id="076c4-114">The message cannot be routed to the batching orchestration as the Encoding type could not be determined.</span></span> <span data-ttu-id="076c4-115">对于要批处理的消息，编码类型应为 X12 或 EDIFACT。</span><span class="sxs-lookup"><span data-stu-id="076c4-115">The encoding type needs to be either X12 or EDIFACT for the message to be batched.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="076c4-116">解释</span><span class="sxs-lookup"><span data-stu-id="076c4-116">Explanation</span></span>  
 <span data-ttu-id="076c4-117">此错误/警告/信息事件表明未将非 EDI 批处理元素路由到批处理业务流程实例，即使事务集符合批处理的筛选条件也是如此。</span><span class="sxs-lookup"><span data-stu-id="076c4-117">This Error/Warning/Information event indicates that a non-EDI batch element was not routed to the batching orchestration instance, even though the transaction set meets the filter criteria for batching.</span></span> <span data-ttu-id="076c4-118">无法将事务集路由到批处理业务流程实例，因为 EDI.EncodingType 上下文属性未使用 X12 的值 0 或 EDIFACT 的值 1 升级。</span><span class="sxs-lookup"><span data-stu-id="076c4-118">The transaction set could not be routed to the batching orchestration instance because the EDI.EncodingType context property was not promoted with a value of 0 for X12 or 1 for EDIFACT.</span></span> <span data-ttu-id="076c4-119">当 BatchMarker 管道组件将批处理元素路由到路由业务流程，但非 EDI 批处理元素未通过映射转换为 EDI 消息时会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="076c4-119">This error occurred when the batch element was routed by the BatchMarker pipeline component to the routing orchestration, but the non-EDI batch element was not converted by a map into an EDI message.</span></span> <span data-ttu-id="076c4-120">因此，路由业务流程无法从 EDI 标头确定编码类型。</span><span class="sxs-lookup"><span data-stu-id="076c4-120">As a result, the routing orchestration could not determine the encoding type from the EDI headers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="076c4-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="076c4-121">User Action</span></span>  
 <span data-ttu-id="076c4-122">若要解决此错误，请确保先将非 EDI 消息通过映射转换为 EDI 消息，然后再将该消息路由到路由业务流程。</span><span class="sxs-lookup"><span data-stu-id="076c4-122">To resolve this error, make sure that the non-EDI message is converted by a map into an EDI message before it is routed to the routing orchestration.</span></span> <span data-ttu-id="076c4-123">还必须包含自定义的管道组件（具有 BatchMarker 组件）或自定义的业务流程才能处理非 EDI 批处理元素。</span><span class="sxs-lookup"><span data-stu-id="076c4-123">You must also include a custom pipeline component (with the BatchMarker component) or custom orchestration to process the non-EDI batch element.</span></span> <span data-ttu-id="076c4-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的“装配批处理的 EDI 交换”。</span><span class="sxs-lookup"><span data-stu-id="076c4-124">For more information, see "Assembling a Batched EDI Interchange" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>