---
title: X12 事务集在 SE01 中有不匹配的计数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a90079f5-5939-40b6-9756-d7943240c125
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 947a557a81c6857b5d31f447acb2ec5a46cfcef9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993342"
---
# <a name="the-x12-transaction-set-had-a-mismatched-count-in-se01"></a><span data-ttu-id="656cd-102">X12 事务集在 SE01 中的计数不匹配</span><span class="sxs-lookup"><span data-stu-id="656cd-102">The X12 Transaction set had a mismatched count in SE01</span></span>
## <a name="details"></a><span data-ttu-id="656cd-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="656cd-103">Details</span></span>  
  
|                 |                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="656cd-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="656cd-104">Product Name</span></span>   |                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                       |
| <span data-ttu-id="656cd-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="656cd-105">Product Version</span></span> |                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                   |
|    <span data-ttu-id="656cd-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="656cd-106">Event ID</span></span>     |                                                               -                                                               |
|  <span data-ttu-id="656cd-107">事件源</span><span class="sxs-lookup"><span data-stu-id="656cd-107">Event Source</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="656cd-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="656cd-108"> EDI</span></span>                     |
|    <span data-ttu-id="656cd-109">组件</span><span class="sxs-lookup"><span data-stu-id="656cd-109">Component</span></span>    |                                                          <span data-ttu-id="656cd-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="656cd-110">EDI Engine</span></span>                                                           |
|  <span data-ttu-id="656cd-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="656cd-111">Symbolic Name</span></span>  |                                                     <span data-ttu-id="656cd-112">X12StSeCountMismatch</span><span class="sxs-lookup"><span data-stu-id="656cd-112">X12StSeCountMismatch</span></span>                                                      |
|  <span data-ttu-id="656cd-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="656cd-113">Message Text</span></span>   | <span data-ttu-id="656cd-114">X12 事务集在 SE01 中的计数不匹配。</span><span class="sxs-lookup"><span data-stu-id="656cd-114">The X12 Transaction set had a mismatched count in SE01.</span></span> <span data-ttu-id="656cd-115">SE01 为{0}，而它应该已{1}。</span><span class="sxs-lookup"><span data-stu-id="656cd-115">SE01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="656cd-116">此错误已纠正。</span><span class="sxs-lookup"><span data-stu-id="656cd-116">It has been corrected.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="656cd-117">解释</span><span class="sxs-lookup"><span data-stu-id="656cd-117">Explanation</span></span>  
 <span data-ttu-id="656cd-118">此警告表明事务集尾部中的数字（SE01 字段）与交换的事务集中的段数不匹配。</span><span class="sxs-lookup"><span data-stu-id="656cd-118">This Warning indicates that the number in the transaction set trailer (SE01 field) did not match the number of segments in the transaction set of the interchange.</span></span> <span data-ttu-id="656cd-119">发送管道纠正了 SE01 字段中的计数并发布了此警告。</span><span class="sxs-lookup"><span data-stu-id="656cd-119">The send pipeline corrects the count in the SE01 field and posts the warning.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="656cd-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="656cd-120">User Action</span></span>  
 <span data-ttu-id="656cd-121">无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="656cd-121">No action is necessary.</span></span>