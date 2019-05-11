---
title: 解析期间遇到错误。 以下错误被挂起的 Edifact 事务集 （没有组） 的交换中包含 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 901fef68-4649-480a-997c-b061d7d069d6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fe401b82d9492590d332dcbdb7d6d59bfaf3c91
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348902"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="05d62-103">解析期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="05d62-103">Error encountered during parsing.</span></span> <span data-ttu-id="05d62-104">以下错误被挂起的 Edifact 事务集包含在交换 （没有组）</span><span class="sxs-lookup"><span data-stu-id="05d62-104">The Edifact transaction set contained in interchange (without group) is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="05d62-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="05d62-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="05d62-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="05d62-106">Product Name</span></span>   |                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                   |
| <span data-ttu-id="05d62-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="05d62-107">Product Version</span></span> |                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                               |
|    <span data-ttu-id="05d62-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="05d62-108">Event ID</span></span>     |                                                                                                           -                                                                                                           |
|  <span data-ttu-id="05d62-109">事件源</span><span class="sxs-lookup"><span data-stu-id="05d62-109">Event Source</span></span>   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="05d62-110">EDI</span><span class="sxs-lookup"><span data-stu-id="05d62-110">EDI</span></span>                                                                 |
|    <span data-ttu-id="05d62-111">组件</span><span class="sxs-lookup"><span data-stu-id="05d62-111">Component</span></span>    |                                                                                                      <span data-ttu-id="05d62-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="05d62-112">EDI Engine</span></span>                                                                                                       |
|  <span data-ttu-id="05d62-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="05d62-113">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="05d62-114">EfactTransactionSetReceiveErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="05d62-114">EfactTransactionSetReceiveErrorWithoutGroup</span></span>                                                                                      |
|  <span data-ttu-id="05d62-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="05d62-115">Message Text</span></span>   | <span data-ttu-id="05d62-116">解析期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="05d62-116">Error encountered during parsing.</span></span> <span data-ttu-id="05d62-117">Edifact 事务集 id 为 '{0}（没有组） id 的交换中包含{1}，发送方 id{2}，接收方 id{3}以下错误被挂起：</span><span class="sxs-lookup"><span data-stu-id="05d62-117">The Edifact transaction set with id '{0}' contained in interchange (without group) with id '{1}', with sender id '{2}', receiver id '{3}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="05d62-118">解释</span><span class="sxs-lookup"><span data-stu-id="05d62-118">Explanation</span></span>  
 <span data-ttu-id="05d62-119">此错误/警告/信息事件表明 EDI 接收管道遇到错误时在交换中指出的错误，标识的事务由于分析传入的 EDIFACT 交换没有组设置。</span><span class="sxs-lookup"><span data-stu-id="05d62-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange without a group because of the stated errors with the identified transaction set in the interchange.</span></span> <span data-ttu-id="05d62-120">请注意，事务集不在交换中组中。</span><span class="sxs-lookup"><span data-stu-id="05d62-120">Note that the transaction set is not in a group in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="05d62-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="05d62-121">User Action</span></span>  
 <span data-ttu-id="05d62-122">若要解决此错误，需要使用错误消息中的信息来标识事务集中的错误，然后确定问题解决方案产品帮助中。</span><span class="sxs-lookup"><span data-stu-id="05d62-122">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>