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
ms.openlocfilehash: e77100200a4fb2eacb24c6745fcd17011231b991
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967302"
---
# <a name="the-interchange-had-structural-error-the-part-after-the-error-is-being-suspended"></a><span data-ttu-id="ab5ee-103">交换发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="ab5ee-103">The interchange had structural error.</span></span> <span data-ttu-id="ab5ee-104">错误之后的部分被挂起</span><span class="sxs-lookup"><span data-stu-id="ab5ee-104">The part after the error is being suspended</span></span>
## <a name="details"></a><span data-ttu-id="ab5ee-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="ab5ee-105">Details</span></span>  
  
|                 |                                                                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ab5ee-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="ab5ee-106">Product Name</span></span>   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="ab5ee-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="ab5ee-107">Product Version</span></span> |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    <span data-ttu-id="ab5ee-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ab5ee-108">Event ID</span></span>     |                                                                                       -                                                                                        |
|  <span data-ttu-id="ab5ee-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ab5ee-109">Event Source</span></span>   |                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ab5ee-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="ab5ee-110"> EDI</span></span>                                             |
|    <span data-ttu-id="ab5ee-111">组件</span><span class="sxs-lookup"><span data-stu-id="ab5ee-111">Component</span></span>    |                                                                                   <span data-ttu-id="ab5ee-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ab5ee-112">EDI Engine</span></span>                                                                                   |
|  <span data-ttu-id="ab5ee-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ab5ee-113">Symbolic Name</span></span>  |                                                                        <span data-ttu-id="ab5ee-114">EfactInterchangeStructuralError</span><span class="sxs-lookup"><span data-stu-id="ab5ee-114">EfactInterchangeStructuralError</span></span>                                                                         |
|  <span data-ttu-id="ab5ee-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ab5ee-115">Message Text</span></span>   | <span data-ttu-id="ab5ee-116">交换 id 为 '{0}，发送方 id{1}，接收方 id{2}发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="ab5ee-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="ab5ee-117">错误之后的部分已被挂起，请参阅“挂起队列”以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="ab5ee-117">The part after the error is being suspended, refer to Suspended Queue for details</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ab5ee-118">解释</span><span class="sxs-lookup"><span data-stu-id="ab5ee-118">Explanation</span></span>  
 <span data-ttu-id="ab5ee-119">此错误/警告/信息事件表明接收管道无法处理传入的 EDIFACT 交换，因为该交换中发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="ab5ee-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange, because a structural error occurred in the interchange.</span></span> <span data-ttu-id="ab5ee-120">正在保留的交换会发生此错误，由于此错误事务集被挂起。</span><span class="sxs-lookup"><span data-stu-id="ab5ee-120">This occurred with an interchange that was being preserved, with transaction sets suspended on the error.</span></span> <span data-ttu-id="ab5ee-121">由于此错误，包含此错误的事务集被挂起，但是作为保留的批处理的一部分对其余事务集进行处理。</span><span class="sxs-lookup"><span data-stu-id="ab5ee-121">As a result of this error, the transaction set (or sets) that included the error was suspended, but the rest of the transaction sets were processed as part of the preserved batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ab5ee-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="ab5ee-122">User Action</span></span>  
 <span data-ttu-id="ab5ee-123">若要解决此错误，请让交换的发送方解决此结构错误，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="ab5ee-123">To resolve this error, have the sender of the interchange fix the structural error, and then resend the interchange.</span></span>