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
ms.openlocfilehash: 99cb8d0456152b5a4e3dc24d9f0d71eeb414eb80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347017"
---
# <a name="a-persistence-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a><span data-ttu-id="53690-102">在批处理业务流程的批提交期间出现持久性异常</span><span class="sxs-lookup"><span data-stu-id="53690-102">A persistence exception has occurred during the batch submission in the batching Orchestration</span></span>
## <a name="details"></a><span data-ttu-id="53690-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="53690-103">Details</span></span>  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="53690-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="53690-104">Product Name</span></span>   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| <span data-ttu-id="53690-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="53690-105">Product Version</span></span> |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    <span data-ttu-id="53690-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="53690-106">Event ID</span></span>     |                                                                                             -                                                                                              |
|  <span data-ttu-id="53690-107">事件源</span><span class="sxs-lookup"><span data-stu-id="53690-107">Event Source</span></span>   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="53690-108">EDI</span><span class="sxs-lookup"><span data-stu-id="53690-108">EDI</span></span>                                                   |
|    <span data-ttu-id="53690-109">组件</span><span class="sxs-lookup"><span data-stu-id="53690-109">Component</span></span>    |                                                                                      <span data-ttu-id="53690-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="53690-110">Batching Engine</span></span>                                                                                       |
|  <span data-ttu-id="53690-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="53690-111">Symbolic Name</span></span>  |                                                                                <span data-ttu-id="53690-112">PersistenceExceptionOccured</span><span class="sxs-lookup"><span data-stu-id="53690-112">PersistenceExceptionOccured</span></span>                                                                                 |
|  <span data-ttu-id="53690-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="53690-113">Message Text</span></span>   | <span data-ttu-id="53690-114">在批处理业务流程的批提交期间出现持久性异常。</span><span class="sxs-lookup"><span data-stu-id="53690-114">A persistence exception has occured during the batch submission in the batching Orchestration.</span></span> <span data-ttu-id="53690-115">批处理 Id = {0}，ErrorMessage = {1}。</span><span class="sxs-lookup"><span data-stu-id="53690-115">Batch Id = {0}, ErrorMessage = {1}.</span></span> <span data-ttu-id="53690-116">请检查发送端口订阅并修复它们。</span><span class="sxs-lookup"><span data-stu-id="53690-116">Please check your send port subscriptions and fix them.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="53690-117">解释</span><span class="sxs-lookup"><span data-stu-id="53690-117">Explanation</span></span>  
 <span data-ttu-id="53690-118">此错误/警告/信息事件表明 BizTalk Server 无法因为该交换不订阅任何发送端口发送批处理的交换。</span><span class="sxs-lookup"><span data-stu-id="53690-118">This Error/Warning/Information event indicates that BizTalk Server could not send a batched interchange because no send port subscribed to the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53690-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="53690-119">User Action</span></span>  
 <span data-ttu-id="53690-120">若要解决此错误，请确保发送端口订阅通过设置以下筛选器属性的发送端口的批处理：EDI。DestinationPartyName = \<PartyName\>，EDI。BatchEncodingType = EDIFACT 或 X12 以及 EDI。ToBeBatched = False。</span><span class="sxs-lookup"><span data-stu-id="53690-120">To resolve this error, ensure that a send port subscribes to the batch by setting the following filter properties for the send port: EDI.DestinationPartyName = \<PartyName\>, EDI.BatchEncodingType = EDIFACT or X12, and EDI.ToBeBatched = False.</span></span>