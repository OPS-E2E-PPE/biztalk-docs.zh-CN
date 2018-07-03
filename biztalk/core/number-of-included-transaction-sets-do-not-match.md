---
title: 包括的事务集数目不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db958803-4667-4558-81a6-70c62d6fe8bf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93d2f51abc20f9cb790d2e6df62443f428c03dc8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970102"
---
# <a name="number-of-included-transaction-sets-do-not-match"></a><span data-ttu-id="14526-102">包括的事务集的数目不匹配</span><span class="sxs-lookup"><span data-stu-id="14526-102">Number of included transaction sets do not match</span></span>
## <a name="details"></a><span data-ttu-id="14526-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="14526-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="14526-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="14526-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="14526-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="14526-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="14526-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="14526-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="14526-107">事件源</span><span class="sxs-lookup"><span data-stu-id="14526-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="14526-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="14526-108"> EDI</span></span> |
|    <span data-ttu-id="14526-109">组件</span><span class="sxs-lookup"><span data-stu-id="14526-109">Component</span></span>    |                                       <span data-ttu-id="14526-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="14526-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="14526-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="14526-111">Symbolic Name</span></span>  |                           <span data-ttu-id="14526-112">X12FaNumberOfTsMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="14526-112">X12FaNumberOfTsMismatchDescription</span></span>                           |
|  <span data-ttu-id="14526-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="14526-113">Message Text</span></span>   |                    <span data-ttu-id="14526-114">包括的事务集的数目不匹配</span><span class="sxs-lookup"><span data-stu-id="14526-114">Number of included transaction sets do not match</span></span>                    |
  
## <a name="explanation"></a><span data-ttu-id="14526-115">解释</span><span class="sxs-lookup"><span data-stu-id="14526-115">Explanation</span></span>  
 <span data-ttu-id="14526-116">此错误/警告/信息事件表明 X12 交换的组中的事务集数不等于组尾部中的数量（GE01 字段）。</span><span class="sxs-lookup"><span data-stu-id="14526-116">This Error/Warning/Information event indicates that the number of transaction sets in the group of the X12 interchange does not equal the number in the group trailer (GE01 field).</span></span> <span data-ttu-id="14526-117">保留交换并且出错时挂起交换时会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="14526-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span> <span data-ttu-id="14526-118">（如果保留交换并且出错时挂起事务集或者拆分交换，则不会发布此错误消息。）</span><span class="sxs-lookup"><span data-stu-id="14526-118">(The error message is not posted if the interchange is preserved and the transaction sets are suspended on an error, or if the interchange is split.)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14526-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="14526-119">User Action</span></span>  
 <span data-ttu-id="14526-120">若要解决此错误，请确保组尾部的 GE01 字段中的数量与交换的组中事务集的数量相同，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="14526-120">To resolve this error, make sure that the number in the GE01 field of the group trailer is the same as the number of transaction sets in the group of the interchange, and then resend the interchange.</span></span>