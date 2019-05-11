---
title: 交换发生了结构错误。 之后的部分被挂起错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9071825d-7b90-42bf-bcf9-2a15ae36086d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ebfeec80fb9775fbb99c07fc1c694f38f6b11c7
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530756"
---
# <a name="the-interchange-had-structural-error-the-part-after-the-error-is-being-suspended"></a><span data-ttu-id="a6a3f-103">交换发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="a6a3f-103">The interchange had structural error.</span></span> <span data-ttu-id="a6a3f-104">正在挂起错误之后的部分</span><span class="sxs-lookup"><span data-stu-id="a6a3f-104">The part after the error is being suspended</span></span>
## <a name="details"></a><span data-ttu-id="a6a3f-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="a6a3f-105">Details</span></span>  
  
|                 |                                                                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a6a3f-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="a6a3f-106">Product Name</span></span>   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="a6a3f-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="a6a3f-107">Product Version</span></span> |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    <span data-ttu-id="a6a3f-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a6a3f-108">Event ID</span></span>     |                                                                                       -                                                                                        |
|  <span data-ttu-id="a6a3f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a6a3f-109">Event Source</span></span>   |                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a6a3f-110">EDI</span><span class="sxs-lookup"><span data-stu-id="a6a3f-110">EDI</span></span>                                             |
|    <span data-ttu-id="a6a3f-111">组件</span><span class="sxs-lookup"><span data-stu-id="a6a3f-111">Component</span></span>    |                                                                                   <span data-ttu-id="a6a3f-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="a6a3f-112">EDI Engine</span></span>                                                                                   |
|  <span data-ttu-id="a6a3f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a6a3f-113">Symbolic Name</span></span>  |                                                                        <span data-ttu-id="a6a3f-114">EfactInterchangeStructuralError</span><span class="sxs-lookup"><span data-stu-id="a6a3f-114">EfactInterchangeStructuralError</span></span>                                                                         |
|  <span data-ttu-id="a6a3f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="a6a3f-115">Message Text</span></span>   | <span data-ttu-id="a6a3f-116">交换 id 为 '{0}，发送方 id{1}，接收方 id{2}发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="a6a3f-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="a6a3f-117">有关详细信息到挂起队列参阅该错误被挂起之后, 的部分</span><span class="sxs-lookup"><span data-stu-id="a6a3f-117">The part after the error is being suspended, refer to Suspended Queue for details</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a6a3f-118">解释</span><span class="sxs-lookup"><span data-stu-id="a6a3f-118">Explanation</span></span>  
 <span data-ttu-id="a6a3f-119">此错误/警告/信息事件表明接收管道无法处理传入的 EDIFACT 交换，因为交换中发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="a6a3f-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange, because a structural error occurred in the interchange.</span></span> <span data-ttu-id="a6a3f-120">会发生此错误的事务集被挂起的错误，正在保留的交换。</span><span class="sxs-lookup"><span data-stu-id="a6a3f-120">This occurred with an interchange that was being preserved, with transaction sets suspended on the error.</span></span> <span data-ttu-id="a6a3f-121">此错误，事务集 （或集） 的结果，包括错误被挂起，但是其余事务设置为已处理保留的批处理的一部分。</span><span class="sxs-lookup"><span data-stu-id="a6a3f-121">As a result of this error, the transaction set (or sets) that included the error was suspended, but the rest of the transaction sets were processed as part of the preserved batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6a3f-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="a6a3f-122">User Action</span></span>  
 <span data-ttu-id="a6a3f-123">若要解决此错误，请让交换的修复方法结构错误，发送方，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="a6a3f-123">To resolve this error, have the sender of the interchange fix the structural error, and then resend the interchange.</span></span>