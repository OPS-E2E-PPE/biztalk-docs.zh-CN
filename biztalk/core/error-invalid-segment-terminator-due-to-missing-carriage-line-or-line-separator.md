---
title: 交换发生了结构错误。 可能的原因是无效的段终止符由于缺少回车换行符和-或换行分隔符 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 035e37d5-d4a8-49d0-8d75-3bcf2426cac7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e983e44b1284bf16e06dbfc90159afc0ed5608c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241741"
---
# <a name="the-interchange-had-structural-error-a-likely-cause-is-invalid-segment-terminator-due-to-missing-carriage-line-and-or-line-feed-seperators"></a><span data-ttu-id="2f0df-103">交换发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="2f0df-103">The interchange had structural error.</span></span> <span data-ttu-id="2f0df-104">可能的原因是无效的段终止符由于缺少回车换行符和-或换行分隔符</span><span class="sxs-lookup"><span data-stu-id="2f0df-104">A likely cause is invalid segment terminator due to missing Carriage Line and-or Line Feed seperators</span></span>
## <a name="details"></a><span data-ttu-id="2f0df-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="2f0df-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f0df-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="2f0df-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2f0df-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="2f0df-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2f0df-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2f0df-108">Event ID</span></span>|-|  
|<span data-ttu-id="2f0df-109">事件源</span><span class="sxs-lookup"><span data-stu-id="2f0df-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2f0df-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="2f0df-110"> EDI</span></span>|  
|<span data-ttu-id="2f0df-111">组件</span><span class="sxs-lookup"><span data-stu-id="2f0df-111">Component</span></span>|<span data-ttu-id="2f0df-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="2f0df-112">EDI Engine</span></span>|  
|<span data-ttu-id="2f0df-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="2f0df-113">Symbolic Name</span></span>|<span data-ttu-id="2f0df-114">EfactInterchangeStructuralErrorAfterUnb</span><span class="sxs-lookup"><span data-stu-id="2f0df-114">EfactInterchangeStructuralErrorAfterUnb</span></span>|  
|<span data-ttu-id="2f0df-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="2f0df-115">Message Text</span></span>|<span data-ttu-id="2f0df-116">Id 为"{0}"，发件人 id {1} 交换，接收方 id {2} 在结构化错误。</span><span class="sxs-lookup"><span data-stu-id="2f0df-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="2f0df-117">可能的原因是段终止符由于缺少回车符和/或换行符而无效。</span><span class="sxs-lookup"><span data-stu-id="2f0df-117">A likely cause is invalid segment terminator due to missing Carriage Line and/or Line Feed seperators.</span></span> <span data-ttu-id="2f0df-118">错误之后的部分已被挂起，请参阅“挂起队列”以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="2f0df-118">The part after the error is being suspended, refer to Suspended Queue for details</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2f0df-119">解释</span><span class="sxs-lookup"><span data-stu-id="2f0df-119">Explanation</span></span>  
 <span data-ttu-id="2f0df-120">此错误/警告/信息事件表明接收管道、发送管道或批处理业务流程无法处理 EDIFACT 交换，因为交换中的某个段没有所需的段终止符。</span><span class="sxs-lookup"><span data-stu-id="2f0df-120">This Error/Warning/Information event indicates that the receive pipeline, send pipeline, or batching orchestration could not process the EDIFACT interchange, because a segment in the interchange did not have the required segment terminator.</span></span> <span data-ttu-id="2f0df-121">对于传入的交换，是在“UNA 段”中标识分隔符的，如果“UNA 段”不存在，则为 EfactDelimiters 管道属性。</span><span class="sxs-lookup"><span data-stu-id="2f0df-121">For an incoming interchange, the separators are identified in the UNA Segment, or if the UNA segment is not present, the EfactDelimiters pipeline property.</span></span> <span data-ttu-id="2f0df-122">对于传出的交换，是在“EDI 属性”对话框的“UNA 段定义”页中标识的。</span><span class="sxs-lookup"><span data-stu-id="2f0df-122">For an outgoing interchange, the separators are identified in the UNA Segment Definition page of the EDI Properties dialog box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2f0df-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="2f0df-123">User Action</span></span>  
 <span data-ttu-id="2f0df-124">若要解决此错误，请确保交换中的所有段具有所需的段终止符，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="2f0df-124">To resolve this error, ensure that all segments in the interchange have the required segment terminator, and then have the interchange resent.</span></span>