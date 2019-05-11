---
title: Edifact 事务集在 UNT01 中有不匹配的计数 |Microsoft Docs
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
ms.openlocfilehash: 428704c78c3d6b615f0272927b03fb57aa66d91b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298794"
---
# <a name="the-edifact-transaction-set-had-a-mismatched-count-in-unt01"></a><span data-ttu-id="d79d2-102">Edifact 事务集在 UNT01 中有计数不匹配</span><span class="sxs-lookup"><span data-stu-id="d79d2-102">The Edifact Transaction set had a mismatched count in UNT01</span></span>
## <a name="details"></a><span data-ttu-id="d79d2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d79d2-103">Details</span></span>  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d79d2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d79d2-104">Product Name</span></span>   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| <span data-ttu-id="d79d2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d79d2-105">Product Version</span></span> |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    <span data-ttu-id="d79d2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d79d2-106">Event ID</span></span>     |                                                                  -                                                                  |
|  <span data-ttu-id="d79d2-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d79d2-107">Event Source</span></span>   |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d79d2-108">EDI</span><span class="sxs-lookup"><span data-stu-id="d79d2-108">EDI</span></span>                        |
|    <span data-ttu-id="d79d2-109">组件</span><span class="sxs-lookup"><span data-stu-id="d79d2-109">Component</span></span>    |                                                             <span data-ttu-id="d79d2-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="d79d2-110">EDI Engine</span></span>                                                              |
|  <span data-ttu-id="d79d2-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d79d2-111">Symbolic Name</span></span>  |                                                      <span data-ttu-id="d79d2-112">EfactUnhUntCountMismatch</span><span class="sxs-lookup"><span data-stu-id="d79d2-112">EfactUnhUntCountMismatch</span></span>                                                       |
|  <span data-ttu-id="d79d2-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="d79d2-113">Message Text</span></span>   | <span data-ttu-id="d79d2-114">Edifact 事务集在 UNT01 中有计数不匹配。</span><span class="sxs-lookup"><span data-stu-id="d79d2-114">The Edifact Transaction set had a mismatched count in UNT01.</span></span> <span data-ttu-id="d79d2-115">UNT01 为{0}，而它应该已{1}。</span><span class="sxs-lookup"><span data-stu-id="d79d2-115">UNT01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="d79d2-116">已纠正。</span><span class="sxs-lookup"><span data-stu-id="d79d2-116">It has been corrected.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d79d2-117">解释</span><span class="sxs-lookup"><span data-stu-id="d79d2-117">Explanation</span></span>  
 <span data-ttu-id="d79d2-118">此警告表明 UNT01 字段，它是段计数，没有与事务集中的段数不匹配。</span><span class="sxs-lookup"><span data-stu-id="d79d2-118">This Warning indicates that the UNT01 field, which is the segment count, did not match the number of segments in the transaction set.</span></span> <span data-ttu-id="d79d2-119">UNT01 的值已更改或损坏，或者添加或删除后确定计数段。</span><span class="sxs-lookup"><span data-stu-id="d79d2-119">Either the value of UNT01 was changed or corrupted, or segments were added or deleted after the count was determined.</span></span> <span data-ttu-id="d79d2-120">发送管道将 UNT01 字段重置为正确数量的段，，然后发送交换。</span><span class="sxs-lookup"><span data-stu-id="d79d2-120">The send pipeline reset the UNT01 field to the correct number of segments, and then sent the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d79d2-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="d79d2-121">User Action</span></span>  
 <span data-ttu-id="d79d2-122">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="d79d2-122">No user action is necessary.</span></span>