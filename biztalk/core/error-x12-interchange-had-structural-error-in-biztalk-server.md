---
title: '交换发生了结构错误。 最后一个具有有效结构的功能组 ID 为: |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd62855b-ecc6-4cfd-be9c-0025348eb841
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23055c421a847835ceac3ea96286794e73cb5dcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346224"
---
# <a name="the-interchange-had-structural-error-last-structurally-valid-functional-group-id-was"></a><span data-ttu-id="db3ea-103">交换发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="db3ea-103">The interchange had structural error.</span></span> <span data-ttu-id="db3ea-104">上一个具有有效结构的功能组 ID 为：</span><span class="sxs-lookup"><span data-stu-id="db3ea-104">Last structurally valid functional group ID was:</span></span>
## <a name="details"></a><span data-ttu-id="db3ea-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="db3ea-105">Details</span></span>  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="db3ea-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="db3ea-106">Product Name</span></span>   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                 |
| <span data-ttu-id="db3ea-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="db3ea-107">Product Version</span></span> |                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                             |
|    <span data-ttu-id="db3ea-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="db3ea-108">Event ID</span></span>     |                                                                         -                                                                          |
|  <span data-ttu-id="db3ea-109">事件源</span><span class="sxs-lookup"><span data-stu-id="db3ea-109">Event Source</span></span>   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="db3ea-110">EDI</span><span class="sxs-lookup"><span data-stu-id="db3ea-110">EDI</span></span>                               |
|    <span data-ttu-id="db3ea-111">组件</span><span class="sxs-lookup"><span data-stu-id="db3ea-111">Component</span></span>    |                                                                     <span data-ttu-id="db3ea-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="db3ea-112">EDI Engine</span></span>                                                                     |
|  <span data-ttu-id="db3ea-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="db3ea-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="db3ea-114">X12InterchangeStructuralErrorAfter1stGroup</span><span class="sxs-lookup"><span data-stu-id="db3ea-114">X12InterchangeStructuralErrorAfter1stGroup</span></span>                                                     |
|  <span data-ttu-id="db3ea-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="db3ea-115">Message Text</span></span>   | <span data-ttu-id="db3ea-116">交换 id 为 '{0}，发送方 id{1}，接收方 id{2}发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="db3ea-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="db3ea-117">最后一个具有有效结构的功能组 ID 为{3}</span><span class="sxs-lookup"><span data-stu-id="db3ea-117">Last structurally valid functional group ID was '{3}'</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="db3ea-118">解释</span><span class="sxs-lookup"><span data-stu-id="db3ea-118">Explanation</span></span>  
 <span data-ttu-id="db3ea-119">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为指明功能组后，在交换中发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="db3ea-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange, because a structural error occurred in the interchange after the indicated functional group.</span></span> <span data-ttu-id="db3ea-120">这可能会发生的事务集被挂起的错误，正在保留交换。</span><span class="sxs-lookup"><span data-stu-id="db3ea-120">This may have occurred with an interchange that was being preserved, with transaction sets suspended on the error.</span></span> <span data-ttu-id="db3ea-121">此错误，事务集 （或集） 的结果，包括错误被挂起，但是其余事务设置为已处理保留的批处理的一部分。</span><span class="sxs-lookup"><span data-stu-id="db3ea-121">As a result of this error, the transaction set (or sets) that included the error was suspended, but the rest of the transaction sets were processed as part of the preserved batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="db3ea-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="db3ea-122">User Action</span></span>  
 <span data-ttu-id="db3ea-123">若要解决此错误，请让交换的修复方法结构错误，发送方，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="db3ea-123">To resolve this error, have the sender of the interchange fix the structural error, and then resend the interchange.</span></span>