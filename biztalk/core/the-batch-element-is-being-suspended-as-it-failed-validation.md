---
title: 因为验证失败，批元素被挂起 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea5e19e8-4592-40f4-bffe-85ab27653fd5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0198f6091b1d7dd6e4ade10260e8f8ffe5b59765
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298986"
---
# <a name="the-batch-element-is-being-suspended-as-it-failed-validation"></a><span data-ttu-id="13701-102">因为验证失败，批元素被挂起</span><span class="sxs-lookup"><span data-stu-id="13701-102">The batch element is being suspended as it failed validation</span></span>
## <a name="details"></a><span data-ttu-id="13701-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="13701-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="13701-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="13701-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="13701-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="13701-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="13701-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="13701-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="13701-107">事件源</span><span class="sxs-lookup"><span data-stu-id="13701-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="13701-108">EDI</span><span class="sxs-lookup"><span data-stu-id="13701-108">EDI</span></span> |
|    <span data-ttu-id="13701-109">组件</span><span class="sxs-lookup"><span data-stu-id="13701-109">Component</span></span>    |                                    <span data-ttu-id="13701-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="13701-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="13701-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="13701-111">Symbolic Name</span></span>  |                                 <span data-ttu-id="13701-112">BatchElementSuspended</span><span class="sxs-lookup"><span data-stu-id="13701-112">BatchElementSuspended</span></span>                                  |
|  <span data-ttu-id="13701-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="13701-113">Message Text</span></span>   |    <span data-ttu-id="13701-114">因为验证失败，批元素被挂起。</span><span class="sxs-lookup"><span data-stu-id="13701-114">The batch element is being suspended as it failed validation.</span></span> <span data-ttu-id="13701-115">错误为： {0}</span><span class="sxs-lookup"><span data-stu-id="13701-115">The error is : {0}</span></span>    |
  
## <a name="explanation"></a><span data-ttu-id="13701-116">解释</span><span class="sxs-lookup"><span data-stu-id="13701-116">Explanation</span></span>  
 <span data-ttu-id="13701-117">此错误/警告/信息事件表明批处理业务流程无法添加设置为批处理交换，因为事务集未能通过验证由批处理业务流程执行的事务。</span><span class="sxs-lookup"><span data-stu-id="13701-117">This Error/Warning/Information event indicates that the batching orchestration could not add a transaction set to a batched interchange because the transaction set failed the validation performed by the batching orchestration.</span></span> <span data-ttu-id="13701-118">将不验证失败的事务集生成交换。</span><span class="sxs-lookup"><span data-stu-id="13701-118">The interchange will be generated without the transaction set that failed validation.</span></span> <span data-ttu-id="13701-119">批处理业务流程设置 EDI。BatchElementValidationFailure 上下文属性设置为"True"。</span><span class="sxs-lookup"><span data-stu-id="13701-119">The batching orchestration sets the EDI.BatchElementValidationFailure context property to "True".</span></span> <span data-ttu-id="13701-120">BatchSuspend 业务流程提取消息根据该上下文属性，发布错误信息，然后被挂起。</span><span class="sxs-lookup"><span data-stu-id="13701-120">The BatchSuspend orchestration picks up the message based upon that context property, posts error information, and then is suspended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="13701-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="13701-121">User Action</span></span>  
 <span data-ttu-id="13701-122">若要解决此错误，指示向事务集的发件人发生了什么错误，错误消息中所示。</span><span class="sxs-lookup"><span data-stu-id="13701-122">To resolve this error, indicate to the sender of the transaction set what error occurred, as indicated in the error message.</span></span> <span data-ttu-id="13701-123">让发送方解决的问题，导致未能通过验证，然后重新发送事务集。</span><span class="sxs-lookup"><span data-stu-id="13701-123">Have the sender resolve the issue that caused it to fail validation, and then resend the transaction set.</span></span>