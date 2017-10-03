---
title: "在序列化期间遇到错误。 出现以下错误正在挂起 Edifact 事务集包含在功能组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b76086-334b-45fb-85f8-82e3335daac4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb09bfecc2efc5e6878b7cc3d0149f2b56c07b68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-serialization-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="f6093-103">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="f6093-103">Error encountered during serialization.</span></span> <span data-ttu-id="f6093-104">功能组中包含的 EDIFACT 事务集由于以下错误被挂起</span><span class="sxs-lookup"><span data-stu-id="f6093-104">The Edifact transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="f6093-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="f6093-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6093-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="f6093-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f6093-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="f6093-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f6093-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f6093-108">Event ID</span></span>|-|  
|<span data-ttu-id="f6093-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f6093-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f6093-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="f6093-110"> EDI</span></span>|  
|<span data-ttu-id="f6093-111">组件</span><span class="sxs-lookup"><span data-stu-id="f6093-111">Component</span></span>|<span data-ttu-id="f6093-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="f6093-112">EDI Engine</span></span>|  
|<span data-ttu-id="f6093-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f6093-113">Symbolic Name</span></span>|<span data-ttu-id="f6093-114">EfactTransactionSetSendError</span><span class="sxs-lookup"><span data-stu-id="f6093-114">EfactTransactionSetSendError</span></span>|  
|<span data-ttu-id="f6093-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f6093-115">Message Text</span></span>|<span data-ttu-id="f6093-116">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="f6093-116">Error encountered during serialization.</span></span> <span data-ttu-id="f6093-117">Id 为"{0}"中 id 为 {1} 功能组包含设置 Edifact 事务 id 为 {2} 发件人 id {3} 使用的交换中接收方 id \ {4 \ 正在挂起出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="f6093-117">The Edifact transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f6093-118">解释</span><span class="sxs-lookup"><span data-stu-id="f6093-118">Explanation</span></span>  
 <span data-ttu-id="f6093-119">此错误/警告/信息事件表明由于通过标识的事务集指明的错误，在序列化传出的 EDIFACT 交换期间 EDI 发送管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="f6093-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6093-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="f6093-120">User Action</span></span>  
 <span data-ttu-id="f6093-121">若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="f6093-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>