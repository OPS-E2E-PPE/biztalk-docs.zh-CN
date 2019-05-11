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
ms.openlocfilehash: 762aa7fbbb76cb97e796fa85e89158cd594d8ce0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253872"
---
# <a name="the-x12-transaction-set-had-a-mismatched-count-in-se01"></a><span data-ttu-id="dee21-102">X12 事务集在 SE01 中有计数不匹配</span><span class="sxs-lookup"><span data-stu-id="dee21-102">The X12 Transaction set had a mismatched count in SE01</span></span>
## <a name="details"></a><span data-ttu-id="dee21-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="dee21-103">Details</span></span>  
  
|                 |                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="dee21-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="dee21-104">Product Name</span></span>   |                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                       |
| <span data-ttu-id="dee21-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="dee21-105">Product Version</span></span> |                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                   |
|    <span data-ttu-id="dee21-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="dee21-106">Event ID</span></span>     |                                                               -                                                               |
|  <span data-ttu-id="dee21-107">事件源</span><span class="sxs-lookup"><span data-stu-id="dee21-107">Event Source</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="dee21-108">EDI</span><span class="sxs-lookup"><span data-stu-id="dee21-108">EDI</span></span>                     |
|    <span data-ttu-id="dee21-109">组件</span><span class="sxs-lookup"><span data-stu-id="dee21-109">Component</span></span>    |                                                          <span data-ttu-id="dee21-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="dee21-110">EDI Engine</span></span>                                                           |
|  <span data-ttu-id="dee21-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="dee21-111">Symbolic Name</span></span>  |                                                     <span data-ttu-id="dee21-112">X12StSeCountMismatch</span><span class="sxs-lookup"><span data-stu-id="dee21-112">X12StSeCountMismatch</span></span>                                                      |
|  <span data-ttu-id="dee21-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="dee21-113">Message Text</span></span>   | <span data-ttu-id="dee21-114">X12 事务集在 SE01 中有计数不匹配。</span><span class="sxs-lookup"><span data-stu-id="dee21-114">The X12 Transaction set had a mismatched count in SE01.</span></span> <span data-ttu-id="dee21-115">SE01 为{0}，而它应该已{1}。</span><span class="sxs-lookup"><span data-stu-id="dee21-115">SE01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="dee21-116">已纠正。</span><span class="sxs-lookup"><span data-stu-id="dee21-116">It has been corrected.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="dee21-117">解释</span><span class="sxs-lookup"><span data-stu-id="dee21-117">Explanation</span></span>  
 <span data-ttu-id="dee21-118">此警告表明事务集尾部 （SE01 字段） 中的编号未与交换的事务集中的段数不匹配。</span><span class="sxs-lookup"><span data-stu-id="dee21-118">This Warning indicates that the number in the transaction set trailer (SE01 field) did not match the number of segments in the transaction set of the interchange.</span></span> <span data-ttu-id="dee21-119">发送管道纠正了 SE01 字段中的计数，发布了此警告。</span><span class="sxs-lookup"><span data-stu-id="dee21-119">The send pipeline corrects the count in the SE01 field and posts the warning.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dee21-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="dee21-120">User Action</span></span>  
 <span data-ttu-id="dee21-121">无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="dee21-121">No action is necessary.</span></span>