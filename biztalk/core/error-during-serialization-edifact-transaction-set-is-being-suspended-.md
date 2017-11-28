---
title: "Edifact 事务集包含在交换错误 |Microsoft 文档"
description: "在序列化期间遇到错误。 正在挂起 Edifact 事务集包含 （没有组） 的交换中出现以下错误"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a0a33ac-d83e-495c-ba75-88c15ad7cfcd
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f089e49941ffec7d3392b3bc35edcbc4eefec5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edifact-transaction-set-is-suspended-error-and-details"></a><span data-ttu-id="e46d9-104">Edifact 事务集是挂起的错误和详细信息</span><span class="sxs-lookup"><span data-stu-id="e46d9-104">Edifact transaction set is suspended error and details</span></span>

`Error encountered during serialization. The Edifact transaction set contained in interchange (without group) is being suspended with following errors`

## <a name="details"></a><span data-ttu-id="e46d9-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="e46d9-105">Details</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="e46d9-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="e46d9-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e46d9-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="e46d9-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e46d9-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e46d9-108">Event ID</span></span>|-|  
|<span data-ttu-id="e46d9-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e46d9-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e46d9-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="e46d9-110"> EDI</span></span>|  
|<span data-ttu-id="e46d9-111">组件</span><span class="sxs-lookup"><span data-stu-id="e46d9-111">Component</span></span>|<span data-ttu-id="e46d9-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e46d9-112">EDI Engine</span></span>|  
|<span data-ttu-id="e46d9-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e46d9-113">Symbolic Name</span></span>|<span data-ttu-id="e46d9-114">EfactTransactionSetSendErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="e46d9-114">EfactTransactionSetSendErrorWithoutGroup</span></span>|  
|<span data-ttu-id="e46d9-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e46d9-115">Message Text</span></span>|<span data-ttu-id="e46d9-116">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="e46d9-116">Error encountered during serialization.</span></span> <span data-ttu-id="e46d9-117">Id 为"{0}"中 （不带组） 的交换 id {1}，发件人 id {2} 的包含设置 Edifact 事务正在与挂起接收方 id {3} 以下错误：</span><span class="sxs-lookup"><span data-stu-id="e46d9-117">The Edifact transaction set with id '{0}' contained in interchange (without group)  with id '{1}', with sender id '{2}', receiver id '{3}' is being suspended with following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e46d9-118">解释</span><span class="sxs-lookup"><span data-stu-id="e46d9-118">Explanation</span></span>  
 <span data-ttu-id="e46d9-119">此错误/警告/信息事件表明由于通过标识的事务集指明的错误，在序列化传出的 EDIFACT 交换期间 EDI 发送管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="e46d9-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified transaction set.</span></span> <span data-ttu-id="e46d9-120">请注意，该事务集不在交换的组中。</span><span class="sxs-lookup"><span data-stu-id="e46d9-120">Note that the transaction set is not in a group in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e46d9-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="e46d9-121">User Action</span></span>  
 <span data-ttu-id="e46d9-122">若要解决此错误，需要使用错误消息中的信息确定在事务集中的错误，然后确定问题解决方法。</span><span class="sxs-lookup"><span data-stu-id="e46d9-122">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution.</span></span>