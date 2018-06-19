---
title: '交换发生了结构错误。 最后一个结构有效功能组 ID 是: |Microsoft 文档'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd62855b-ecc6-4cfd-be9c-0025348eb841
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 565a4865455cabef3cd53988d601a89ecf1549e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241405"
---
# <a name="the-interchange-had-structural-error-last-structurally-valid-functional-group-id-was"></a><span data-ttu-id="33431-103">交换发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="33431-103">The interchange had structural error.</span></span> <span data-ttu-id="33431-104">上一个具有有效结构的功能组 ID 为：</span><span class="sxs-lookup"><span data-stu-id="33431-104">Last structurally valid functional group ID was:</span></span>
## <a name="details"></a><span data-ttu-id="33431-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="33431-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33431-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="33431-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="33431-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="33431-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="33431-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="33431-108">Event ID</span></span>|-|  
|<span data-ttu-id="33431-109">事件源</span><span class="sxs-lookup"><span data-stu-id="33431-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="33431-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="33431-110"> EDI</span></span>|  
|<span data-ttu-id="33431-111">组件</span><span class="sxs-lookup"><span data-stu-id="33431-111">Component</span></span>|<span data-ttu-id="33431-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="33431-112">EDI Engine</span></span>|  
|<span data-ttu-id="33431-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="33431-113">Symbolic Name</span></span>|<span data-ttu-id="33431-114">X12InterchangeStructuralErrorAfter1stGroup</span><span class="sxs-lookup"><span data-stu-id="33431-114">X12InterchangeStructuralErrorAfter1stGroup</span></span>|  
|<span data-ttu-id="33431-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="33431-115">Message Text</span></span>|<span data-ttu-id="33431-116">Id 为"{0}"，发件人 id {1} 交换，接收方 id {2} 在结构化错误。</span><span class="sxs-lookup"><span data-stu-id="33431-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="33431-117">最后一个结构有效功能组 ID 为 {3}</span><span class="sxs-lookup"><span data-stu-id="33431-117">Last structurally valid functional group ID was '{3}'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="33431-118">解释</span><span class="sxs-lookup"><span data-stu-id="33431-118">Explanation</span></span>  
 <span data-ttu-id="33431-119">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为指明功能组之后在该交换中发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="33431-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange, because a structural error occurred in the interchange after the indicated functional group.</span></span> <span data-ttu-id="33431-120">这可能出现了具有在错误上挂起的事务集，正在保存的交换。</span><span class="sxs-lookup"><span data-stu-id="33431-120">This may have occurred with an interchange that was being preserved, with transaction sets suspended on the error.</span></span> <span data-ttu-id="33431-121">由于此错误，包含此错误的事务集被挂起，但是作为保留的批处理的一部分对其余事务集进行处理。</span><span class="sxs-lookup"><span data-stu-id="33431-121">As a result of this error, the transaction set (or sets) that included the error was suspended, but the rest of the transaction sets were processed as part of the preserved batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="33431-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="33431-122">User Action</span></span>  
 <span data-ttu-id="33431-123">若要解决此错误，请让交换的发送方解决此结构错误，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="33431-123">To resolve this error, have the sender of the interchange fix the structural error, and then resend the interchange.</span></span>