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
ms.openlocfilehash: 717260f8e45298c19756707ed042b97ab6e207fb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016044"
---
# <a name="the-edifact-transaction-set-had-a-mismatched-count-in-unt01"></a><span data-ttu-id="c1a70-102">EDIFACT 事务集在 UNT01 中的计数不匹配</span><span class="sxs-lookup"><span data-stu-id="c1a70-102">The Edifact Transaction set had a mismatched count in UNT01</span></span>
## <a name="details"></a><span data-ttu-id="c1a70-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c1a70-103">Details</span></span>  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c1a70-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c1a70-104">Product Name</span></span>   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| <span data-ttu-id="c1a70-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c1a70-105">Product Version</span></span> |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    <span data-ttu-id="c1a70-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c1a70-106">Event ID</span></span>     |                                                                  -                                                                  |
|  <span data-ttu-id="c1a70-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c1a70-107">Event Source</span></span>   |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c1a70-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c1a70-108"> EDI</span></span>                        |
|    <span data-ttu-id="c1a70-109">组件</span><span class="sxs-lookup"><span data-stu-id="c1a70-109">Component</span></span>    |                                                             <span data-ttu-id="c1a70-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c1a70-110">EDI Engine</span></span>                                                              |
|  <span data-ttu-id="c1a70-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c1a70-111">Symbolic Name</span></span>  |                                                      <span data-ttu-id="c1a70-112">EfactUnhUntCountMismatch</span><span class="sxs-lookup"><span data-stu-id="c1a70-112">EfactUnhUntCountMismatch</span></span>                                                       |
|  <span data-ttu-id="c1a70-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c1a70-113">Message Text</span></span>   | <span data-ttu-id="c1a70-114">Edifact 事务集在 UNT01 中的计数不匹配。</span><span class="sxs-lookup"><span data-stu-id="c1a70-114">The Edifact Transaction set had a mismatched count in UNT01.</span></span> <span data-ttu-id="c1a70-115">UNT01 为{0}，而它应该已{1}。</span><span class="sxs-lookup"><span data-stu-id="c1a70-115">UNT01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="c1a70-116">此错误已纠正。</span><span class="sxs-lookup"><span data-stu-id="c1a70-116">It has been corrected.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c1a70-117">解释</span><span class="sxs-lookup"><span data-stu-id="c1a70-117">Explanation</span></span>  
 <span data-ttu-id="c1a70-118">此警告表明 UNT01 字段（为段计数）与事务集中的段数不匹配。</span><span class="sxs-lookup"><span data-stu-id="c1a70-118">This Warning indicates that the UNT01 field, which is the segment count, did not match the number of segments in the transaction set.</span></span> <span data-ttu-id="c1a70-119">UNT01 的值被更改或已损坏，或者在确定计数之后添加或删除了段。</span><span class="sxs-lookup"><span data-stu-id="c1a70-119">Either the value of UNT01 was changed or corrupted, or segments were added or deleted after the count was determined.</span></span> <span data-ttu-id="c1a70-120">发送管道将 UNT01 字段重置为正确的段数，然后发送交换。</span><span class="sxs-lookup"><span data-stu-id="c1a70-120">The send pipeline reset the UNT01 field to the correct number of segments, and then sent the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c1a70-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="c1a70-121">User Action</span></span>  
 <span data-ttu-id="c1a70-122">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="c1a70-122">No user action is necessary.</span></span>