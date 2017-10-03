---
title: "因为它未能通过验证正在挂起 batch 元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea5e19e8-4592-40f4-bffe-85ab27653fd5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7022041d8d47e1bfa52eb7ef45764c17ed1a2d8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-batch-element-is-being-suspended-as-it-failed-validation"></a><span data-ttu-id="15863-102">因为验证失败，批元素被挂起</span><span class="sxs-lookup"><span data-stu-id="15863-102">The batch element is being suspended as it failed validation</span></span>
## <a name="details"></a><span data-ttu-id="15863-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="15863-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="15863-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="15863-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="15863-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="15863-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="15863-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="15863-106">Event ID</span></span>|-|  
|<span data-ttu-id="15863-107">事件源</span><span class="sxs-lookup"><span data-stu-id="15863-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="15863-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="15863-108"> EDI</span></span>|  
|<span data-ttu-id="15863-109">组件</span><span class="sxs-lookup"><span data-stu-id="15863-109">Component</span></span>|<span data-ttu-id="15863-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="15863-110">Batching Engine</span></span>|  
|<span data-ttu-id="15863-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="15863-111">Symbolic Name</span></span>|<span data-ttu-id="15863-112">BatchElementSuspended</span><span class="sxs-lookup"><span data-stu-id="15863-112">BatchElementSuspended</span></span>|  
|<span data-ttu-id="15863-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="15863-113">Message Text</span></span>|<span data-ttu-id="15863-114">因为验证失败，批元素被挂起。</span><span class="sxs-lookup"><span data-stu-id="15863-114">The batch element is being suspended as it failed validation.</span></span> <span data-ttu-id="15863-115">错误的原因在于： {0}</span><span class="sxs-lookup"><span data-stu-id="15863-115">The error is : {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="15863-116">解释</span><span class="sxs-lookup"><span data-stu-id="15863-116">Explanation</span></span>  
 <span data-ttu-id="15863-117">此错误/警告/信息事件指示批处理的业务流程无法添加事务设置为批处理的交换，因为事务集未由批处理业务流程执行验证。</span><span class="sxs-lookup"><span data-stu-id="15863-117">This Error/Warning/Information event indicates that the batching orchestration could not add a transaction set to a batched interchange because the transaction set failed the validation performed by the batching orchestration.</span></span> <span data-ttu-id="15863-118">将无事务集未通过验证需生成的交换。</span><span class="sxs-lookup"><span data-stu-id="15863-118">The interchange will be generated without the transaction set that failed validation.</span></span> <span data-ttu-id="15863-119">批处理的业务流程设置 EDI。BatchElementValidationFailure 上下文属性设置为"True"。</span><span class="sxs-lookup"><span data-stu-id="15863-119">The batching orchestration sets the EDI.BatchElementValidationFailure context property to "True".</span></span> <span data-ttu-id="15863-120">BatchSuspend 业务流程根据该上下文属性提取消息，发布错误信息，然后就会被挂起。</span><span class="sxs-lookup"><span data-stu-id="15863-120">The BatchSuspend orchestration picks up the message based upon that context property, posts error information, and then is suspended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="15863-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="15863-121">User Action</span></span>  
 <span data-ttu-id="15863-122">若要解决此错误，请指出发生错误的事务集的发送方，如错误消息中所示。</span><span class="sxs-lookup"><span data-stu-id="15863-122">To resolve this error, indicate to the sender of the transaction set what error occurred, as indicated in the error message.</span></span> <span data-ttu-id="15863-123">让发送方解决导致其未通过验证的问题，然后重新发送该事务集。</span><span class="sxs-lookup"><span data-stu-id="15863-123">Have the sender resolve the issue that caused it to fail validation, and then resend the transaction set.</span></span>