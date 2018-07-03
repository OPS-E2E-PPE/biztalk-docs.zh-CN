---
title: 在解析过程中遇到错误。 以下错误被挂起的 Edifact 事务集 （没有组） 的交换中包含 |Microsoft Docs
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
ms.openlocfilehash: c2e0d8e2b03decf2db806a08f082b7aace276a8e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006414"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="4f7ee-103">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="4f7ee-103">Error encountered during parsing.</span></span> <span data-ttu-id="4f7ee-104">以下错误被挂起的 Edifact 事务集包含在交换 （没有组）</span><span class="sxs-lookup"><span data-stu-id="4f7ee-104">The Edifact transaction set contained in interchange (without group) is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="4f7ee-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="4f7ee-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4f7ee-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="4f7ee-106">Product Name</span></span>   |                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                   |
| <span data-ttu-id="4f7ee-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="4f7ee-107">Product Version</span></span> |                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                               |
|    <span data-ttu-id="4f7ee-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4f7ee-108">Event ID</span></span>     |                                                                                                           -                                                                                                           |
|  <span data-ttu-id="4f7ee-109">事件源</span><span class="sxs-lookup"><span data-stu-id="4f7ee-109">Event Source</span></span>   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4f7ee-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="4f7ee-110"> EDI</span></span>                                                                 |
|    <span data-ttu-id="4f7ee-111">组件</span><span class="sxs-lookup"><span data-stu-id="4f7ee-111">Component</span></span>    |                                                                                                      <span data-ttu-id="4f7ee-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="4f7ee-112">EDI Engine</span></span>                                                                                                       |
|  <span data-ttu-id="4f7ee-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="4f7ee-113">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="4f7ee-114">EfactTransactionSetReceiveErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="4f7ee-114">EfactTransactionSetReceiveErrorWithoutGroup</span></span>                                                                                      |
|  <span data-ttu-id="4f7ee-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="4f7ee-115">Message Text</span></span>   | <span data-ttu-id="4f7ee-116">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="4f7ee-116">Error encountered during parsing.</span></span> <span data-ttu-id="4f7ee-117">Edifact 事务集 id 为 '{0}（没有组） id 的交换中包含{1}，发送方 id{2}，接收方 id{3}以下错误被挂起：</span><span class="sxs-lookup"><span data-stu-id="4f7ee-117">The Edifact transaction set with id '{0}' contained in interchange (without group) with id '{1}', with sender id '{2}', receiver id '{3}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4f7ee-118">解释</span><span class="sxs-lookup"><span data-stu-id="4f7ee-118">Explanation</span></span>  
 <span data-ttu-id="4f7ee-119">此错误/警告/信息事件表明由于通过交换中标识的事务集指明的错误，在分析传入的 EDIFACT 交换（该交换没有组）时 EDI 接收管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="4f7ee-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange without a group because of the stated errors with the identified transaction set in the interchange.</span></span> <span data-ttu-id="4f7ee-120">请注意，该事务集不在交换的组中。</span><span class="sxs-lookup"><span data-stu-id="4f7ee-120">Note that the transaction set is not in a group in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4f7ee-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="4f7ee-121">User Action</span></span>  
 <span data-ttu-id="4f7ee-122">若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="4f7ee-122">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>