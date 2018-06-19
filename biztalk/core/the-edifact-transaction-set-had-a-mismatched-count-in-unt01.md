---
title: Edifact 事务集 UNT01 中有不匹配的计数 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2859274-78e8-4e16-92b7-c143da6da421
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 180abe338441917afa6691400a02a42e88026052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278485"
---
# <a name="the-edifact-transaction-set-had-a-mismatched-count-in-unt01"></a><span data-ttu-id="4de15-102">EDIFACT 事务集在 UNT01 中的计数不匹配</span><span class="sxs-lookup"><span data-stu-id="4de15-102">The Edifact Transaction set had a mismatched count in UNT01</span></span>
## <a name="details"></a><span data-ttu-id="4de15-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4de15-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4de15-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4de15-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="4de15-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="4de15-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="4de15-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4de15-106">Event ID</span></span>|-|  
|<span data-ttu-id="4de15-107">事件源</span><span class="sxs-lookup"><span data-stu-id="4de15-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4de15-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="4de15-108"> EDI</span></span>|  
|<span data-ttu-id="4de15-109">组件</span><span class="sxs-lookup"><span data-stu-id="4de15-109">Component</span></span>|<span data-ttu-id="4de15-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="4de15-110">EDI Engine</span></span>|  
|<span data-ttu-id="4de15-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="4de15-111">Symbolic Name</span></span>|<span data-ttu-id="4de15-112">EfactUnhUntCountMismatch</span><span class="sxs-lookup"><span data-stu-id="4de15-112">EfactUnhUntCountMismatch</span></span>|  
|<span data-ttu-id="4de15-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="4de15-113">Message Text</span></span>|<span data-ttu-id="4de15-114">Edifact 事务集在 UNT01 中的计数不匹配。</span><span class="sxs-lookup"><span data-stu-id="4de15-114">The Edifact Transaction set had a mismatched count in UNT01.</span></span> <span data-ttu-id="4de15-115">将已 UNT01 {0}，而应已 {1}。</span><span class="sxs-lookup"><span data-stu-id="4de15-115">UNT01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="4de15-116">此错误已纠正。</span><span class="sxs-lookup"><span data-stu-id="4de15-116">It has been corrected.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4de15-117">解释</span><span class="sxs-lookup"><span data-stu-id="4de15-117">Explanation</span></span>  
 <span data-ttu-id="4de15-118">此警告表明 UNT01 字段（为段计数）与事务集中的段数不匹配。</span><span class="sxs-lookup"><span data-stu-id="4de15-118">This Warning indicates that the UNT01 field, which is the segment count, did not match the number of segments in the transaction set.</span></span> <span data-ttu-id="4de15-119">UNT01 的值被更改或已损坏，或者在确定计数之后添加或删除了段。</span><span class="sxs-lookup"><span data-stu-id="4de15-119">Either the value of UNT01 was changed or corrupted, or segments were added or deleted after the count was determined.</span></span> <span data-ttu-id="4de15-120">发送管道将 UNT01 字段重置为正确的段数，然后发送交换。</span><span class="sxs-lookup"><span data-stu-id="4de15-120">The send pipeline reset the UNT01 field to the correct number of segments, and then sent the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4de15-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="4de15-121">User Action</span></span>  
 <span data-ttu-id="4de15-122">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="4de15-122">No user action is necessary.</span></span>