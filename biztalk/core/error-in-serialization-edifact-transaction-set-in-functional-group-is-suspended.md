---
title: 在序列化期间遇到错误。 以下错误被挂起的 Edifact 事务集功能组中包含 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b76086-334b-45fb-85f8-82e3335daac4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c89d4300d54bc7e524f9f33aea4689a6cdc4bc27
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007654"
---
# <a name="error-encountered-during-serialization-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="68bb7-103">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="68bb7-103">Error encountered during serialization.</span></span> <span data-ttu-id="68bb7-104">功能组中包含的 EDIFACT 事务集由于以下错误被挂起</span><span class="sxs-lookup"><span data-stu-id="68bb7-104">The Edifact transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="68bb7-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="68bb7-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="68bb7-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="68bb7-106">Product Name</span></span>   |                                                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                               |
| <span data-ttu-id="68bb7-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="68bb7-107">Product Version</span></span> |                                                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                           |
|    <span data-ttu-id="68bb7-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="68bb7-108">Event ID</span></span>     |                                                                                                                       -                                                                                                                        |
|  <span data-ttu-id="68bb7-109">事件源</span><span class="sxs-lookup"><span data-stu-id="68bb7-109">Event Source</span></span>   |                                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="68bb7-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="68bb7-110"> EDI</span></span>                                                                             |
|    <span data-ttu-id="68bb7-111">组件</span><span class="sxs-lookup"><span data-stu-id="68bb7-111">Component</span></span>    |                                                                                                                   <span data-ttu-id="68bb7-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="68bb7-112">EDI Engine</span></span>                                                                                                                   |
|  <span data-ttu-id="68bb7-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="68bb7-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="68bb7-114">EfactTransactionSetSendError</span><span class="sxs-lookup"><span data-stu-id="68bb7-114">EfactTransactionSetSendError</span></span>                                                                                                          |
|  <span data-ttu-id="68bb7-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="68bb7-115">Message Text</span></span>   | <span data-ttu-id="68bb7-116">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="68bb7-116">Error encountered during serialization.</span></span> <span data-ttu-id="68bb7-117">Edifact 事务集 id 为 '{0}功能组 id 中包含{1}，交换中包含的 id{2}，发送方 id{3}，接收方 id{4}以下错误被挂起：</span><span class="sxs-lookup"><span data-stu-id="68bb7-117">The Edifact transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="68bb7-118">解释</span><span class="sxs-lookup"><span data-stu-id="68bb7-118">Explanation</span></span>  
 <span data-ttu-id="68bb7-119">此错误/警告/信息事件表明由于通过标识的事务集指明的错误，在序列化传出的 EDIFACT 交换期间 EDI 发送管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="68bb7-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68bb7-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="68bb7-120">User Action</span></span>  
 <span data-ttu-id="68bb7-121">若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="68bb7-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>