---
title: "在序列化期间遇到错误。 出现以下错误正在挂起事务集功能组中包含 X12 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49b13038-2637-4435-91e9-d6fe2b80ca7a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c8b1402974c53007e8488df3fbdedc666ac2753
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-serialization-the-x12-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="705c3-103">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="705c3-103">Error encountered during serialization.</span></span> <span data-ttu-id="705c3-104">功能组中包含的 X12 事务集由于以下错误被挂起</span><span class="sxs-lookup"><span data-stu-id="705c3-104">The X12 transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="705c3-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="705c3-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="705c3-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="705c3-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="705c3-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="705c3-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="705c3-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="705c3-108">Event ID</span></span>|-|  
|<span data-ttu-id="705c3-109">事件源</span><span class="sxs-lookup"><span data-stu-id="705c3-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="705c3-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="705c3-110"> EDI</span></span>|  
|<span data-ttu-id="705c3-111">组件</span><span class="sxs-lookup"><span data-stu-id="705c3-111">Component</span></span>|<span data-ttu-id="705c3-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="705c3-112">EDI Engine</span></span>|  
|<span data-ttu-id="705c3-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="705c3-113">Symbolic Name</span></span>|<span data-ttu-id="705c3-114">X12TransactionSetSendError</span><span class="sxs-lookup"><span data-stu-id="705c3-114">X12TransactionSetSendError</span></span>|  
|<span data-ttu-id="705c3-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="705c3-115">Message Text</span></span>|<span data-ttu-id="705c3-116">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="705c3-116">Error encountered during serialization.</span></span> <span data-ttu-id="705c3-117">事务集 id 为"{0}"中包含的 X12 功能组 id {1}，id 为 {2} 交换中使用发件人 id {3}，接收方 id \ {4 \ 正在挂起出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="705c3-117">The X12 transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="705c3-118">解释</span><span class="sxs-lookup"><span data-stu-id="705c3-118">Explanation</span></span>  
 <span data-ttu-id="705c3-119">此错误/警告/信息事件表明由于通过标识的事务集指明的错误，在序列化传出的 X12 交换期间 EDI 发送管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="705c3-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing X12 interchange because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="705c3-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="705c3-120">User Action</span></span>  
 <span data-ttu-id="705c3-121">若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="705c3-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>