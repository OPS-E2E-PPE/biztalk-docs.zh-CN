---
title: "X12 事务集 SE01 中有不匹配的计数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a90079f5-5939-40b6-9756-d7943240c125
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41539f0492f90d3f7276b0d80af28c568593ef4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-x12-transaction-set-had-a-mismatched-count-in-se01"></a><span data-ttu-id="bf410-102">X12 事务集在 SE01 中的计数不匹配</span><span class="sxs-lookup"><span data-stu-id="bf410-102">The X12 Transaction set had a mismatched count in SE01</span></span>
## <a name="details"></a><span data-ttu-id="bf410-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="bf410-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf410-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="bf410-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="bf410-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="bf410-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="bf410-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bf410-106">Event ID</span></span>|-|  
|<span data-ttu-id="bf410-107">事件源</span><span class="sxs-lookup"><span data-stu-id="bf410-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bf410-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="bf410-108"> EDI</span></span>|  
|<span data-ttu-id="bf410-109">组件</span><span class="sxs-lookup"><span data-stu-id="bf410-109">Component</span></span>|<span data-ttu-id="bf410-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="bf410-110">EDI Engine</span></span>|  
|<span data-ttu-id="bf410-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="bf410-111">Symbolic Name</span></span>|<span data-ttu-id="bf410-112">X12StSeCountMismatch</span><span class="sxs-lookup"><span data-stu-id="bf410-112">X12StSeCountMismatch</span></span>|  
|<span data-ttu-id="bf410-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="bf410-113">Message Text</span></span>|<span data-ttu-id="bf410-114">X12 事务集在 SE01 中的计数不匹配。</span><span class="sxs-lookup"><span data-stu-id="bf410-114">The X12 Transaction set had a mismatched count in SE01.</span></span> <span data-ttu-id="bf410-115">将已 SE01 {0}，而应已 {1}。</span><span class="sxs-lookup"><span data-stu-id="bf410-115">SE01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="bf410-116">此错误已纠正。</span><span class="sxs-lookup"><span data-stu-id="bf410-116">It has been corrected.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bf410-117">解释</span><span class="sxs-lookup"><span data-stu-id="bf410-117">Explanation</span></span>  
 <span data-ttu-id="bf410-118">此警告表明事务集尾部中的数字（SE01 字段）与交换的事务集中的段数不匹配。</span><span class="sxs-lookup"><span data-stu-id="bf410-118">This Warning indicates that the number in the transaction set trailer (SE01 field) did not match the number of segments in the transaction set of the interchange.</span></span> <span data-ttu-id="bf410-119">发送管道纠正了 SE01 字段中的计数并发布了此警告。</span><span class="sxs-lookup"><span data-stu-id="bf410-119">The send pipeline corrects the count in the SE01 field and posts the warning.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bf410-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="bf410-120">User Action</span></span>  
 <span data-ttu-id="bf410-121">无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="bf410-121">No action is necessary.</span></span>