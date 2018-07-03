---
title: Edifact 事务集包含在交换错误 |Microsoft Docs
description: 在序列化期间遇到错误。 以下错误被挂起的 Edifact 事务集包含在交换 （没有组）
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a0a33ac-d83e-495c-ba75-88c15ad7cfcd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5fcd7702ce791037d8a7320f647955fca1c9489
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981926"
---
# <a name="edifact-transaction-set-is-suspended-error-and-details"></a><span data-ttu-id="44a1f-104">Edifact 事务集是已挂起的错误和详细信息</span><span class="sxs-lookup"><span data-stu-id="44a1f-104">Edifact transaction set is suspended error and details</span></span>

`Error encountered during serialization. The Edifact transaction set contained in interchange (without group) is being suspended with following errors`

## <a name="details"></a><span data-ttu-id="44a1f-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="44a1f-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                              |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="44a1f-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="44a1f-106">Product Name</span></span>   |                                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                      |
| <span data-ttu-id="44a1f-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="44a1f-107">Product Version</span></span> |                                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                  |
|    <span data-ttu-id="44a1f-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44a1f-108">Event ID</span></span>     |                                                                                                              -                                                                                                               |
|  <span data-ttu-id="44a1f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="44a1f-109">Event Source</span></span>   |                                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="44a1f-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="44a1f-110"> EDI</span></span>                                                                    |
|    <span data-ttu-id="44a1f-111">组件</span><span class="sxs-lookup"><span data-stu-id="44a1f-111">Component</span></span>    |                                                                                                          <span data-ttu-id="44a1f-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="44a1f-112">EDI Engine</span></span>                                                                                                          |
|  <span data-ttu-id="44a1f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="44a1f-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="44a1f-114">EfactTransactionSetSendErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="44a1f-114">EfactTransactionSetSendErrorWithoutGroup</span></span>                                                                                           |
|  <span data-ttu-id="44a1f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="44a1f-115">Message Text</span></span>   | <span data-ttu-id="44a1f-116">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="44a1f-116">Error encountered during serialization.</span></span> <span data-ttu-id="44a1f-117">Edifact 事务集 id 为 '{0}（没有组） id 的交换中包含{1}，发送方 id{2}，接收方 id{3}以下错误被挂起：</span><span class="sxs-lookup"><span data-stu-id="44a1f-117">The Edifact transaction set with id '{0}' contained in interchange (without group)  with id '{1}', with sender id '{2}', receiver id '{3}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="44a1f-118">解释</span><span class="sxs-lookup"><span data-stu-id="44a1f-118">Explanation</span></span>  
 <span data-ttu-id="44a1f-119">此错误/警告/信息事件表明由于通过标识的事务集指明的错误，在序列化传出的 EDIFACT 交换期间 EDI 发送管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="44a1f-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified transaction set.</span></span> <span data-ttu-id="44a1f-120">请注意，该事务集不在交换的组中。</span><span class="sxs-lookup"><span data-stu-id="44a1f-120">Note that the transaction set is not in a group in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44a1f-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="44a1f-121">User Action</span></span>  
 <span data-ttu-id="44a1f-122">若要解决此错误，需要使用错误消息中的信息来标识事务集中的错误，然后确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="44a1f-122">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution.</span></span>