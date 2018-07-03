---
title: 在批处理业务流程的批提交期间出现持久性异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6e832f-9d01-46e7-aaf5-2b402d509fac
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8a1277dd26fcb2036e3378f7fa6d22067a1f7e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020915"
---
# <a name="a-persistence-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a><span data-ttu-id="7c2d2-102">批处理业务流程的批提交过程中发生了一个持久性异常</span><span class="sxs-lookup"><span data-stu-id="7c2d2-102">A persistence exception has occurred during the batch submission in the batching Orchestration</span></span>
## <a name="details"></a><span data-ttu-id="7c2d2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7c2d2-103">Details</span></span>  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7c2d2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7c2d2-104">Product Name</span></span>   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| <span data-ttu-id="7c2d2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7c2d2-105">Product Version</span></span> |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    <span data-ttu-id="7c2d2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7c2d2-106">Event ID</span></span>     |                                                                                             -                                                                                              |
|  <span data-ttu-id="7c2d2-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7c2d2-107">Event Source</span></span>   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7c2d2-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7c2d2-108"> EDI</span></span>                                                   |
|    <span data-ttu-id="7c2d2-109">组件</span><span class="sxs-lookup"><span data-stu-id="7c2d2-109">Component</span></span>    |                                                                                      <span data-ttu-id="7c2d2-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="7c2d2-110">Batching Engine</span></span>                                                                                       |
|  <span data-ttu-id="7c2d2-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7c2d2-111">Symbolic Name</span></span>  |                                                                                <span data-ttu-id="7c2d2-112">PersistenceExceptionOccured</span><span class="sxs-lookup"><span data-stu-id="7c2d2-112">PersistenceExceptionOccured</span></span>                                                                                 |
|  <span data-ttu-id="7c2d2-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="7c2d2-113">Message Text</span></span>   | <span data-ttu-id="7c2d2-114">在批处理业务流程中的批处理提交期间出现持久性异常。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-114">A persistence exception has occured during the batch submission in the batching Orchestration.</span></span> <span data-ttu-id="7c2d2-115">批处理 Id = {0}，ErrorMessage = {1}。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-115">Batch Id = {0}, ErrorMessage = {1}.</span></span> <span data-ttu-id="7c2d2-116">请检查发送端口订阅并进行修改。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-116">Please check your send port subscriptions and fix them.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7c2d2-117">解释</span><span class="sxs-lookup"><span data-stu-id="7c2d2-117">Explanation</span></span>  
 <span data-ttu-id="7c2d2-118">此错误/警告/信息事件表明 BizTalk Server 无法发送批处理交换，因为该交换未订阅任何发送端口。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-118">This Error/Warning/Information event indicates that BizTalk Server could not send a batched interchange because no send port subscribed to the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7c2d2-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="7c2d2-119">User Action</span></span>  
 <span data-ttu-id="7c2d2-120">若要解决此错误，请确保发送端口订阅通过设置以下筛选器属性的发送端口的批处理： EDI。DestinationPartyName = \<PartyName\>，EDI。BatchEncodingType = EDIFACT 或 X12 以及 EDI。ToBeBatched = False。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-120">To resolve this error, ensure that a send port subscribes to the batch by setting the following filter properties for the send port: EDI.DestinationPartyName = \<PartyName\>, EDI.BatchEncodingType = EDIFACT or X12, and EDI.ToBeBatched = False.</span></span>