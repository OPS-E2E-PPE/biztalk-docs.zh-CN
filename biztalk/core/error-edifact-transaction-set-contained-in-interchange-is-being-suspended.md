---
title: 在解析过程中遇到错误。 正在挂起 Edifact 事务集包含 （没有组） 的交换中出现以下错误 |Microsoft 文档
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
ms.openlocfilehash: 2dc5633917c708f457f11fc824997fa7eb6d4c59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240229"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="c37bf-103">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="c37bf-103">Error encountered during parsing.</span></span> <span data-ttu-id="c37bf-104">正在挂起 Edifact 事务集包含 （没有组） 的交换中出现以下错误</span><span class="sxs-lookup"><span data-stu-id="c37bf-104">The Edifact transaction set contained in interchange (without group) is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="c37bf-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="c37bf-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c37bf-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="c37bf-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c37bf-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="c37bf-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c37bf-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c37bf-108">Event ID</span></span>|-|  
|<span data-ttu-id="c37bf-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c37bf-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c37bf-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="c37bf-110"> EDI</span></span>|  
|<span data-ttu-id="c37bf-111">组件</span><span class="sxs-lookup"><span data-stu-id="c37bf-111">Component</span></span>|<span data-ttu-id="c37bf-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c37bf-112">EDI Engine</span></span>|  
|<span data-ttu-id="c37bf-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c37bf-113">Symbolic Name</span></span>|<span data-ttu-id="c37bf-114">EfactTransactionSetReceiveErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="c37bf-114">EfactTransactionSetReceiveErrorWithoutGroup</span></span>|  
|<span data-ttu-id="c37bf-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c37bf-115">Message Text</span></span>|<span data-ttu-id="c37bf-116">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="c37bf-116">Error encountered during parsing.</span></span> <span data-ttu-id="c37bf-117">Id 为"{0}"中 （不带组） 的交换 id {1}，发件人 id {2} 的包含设置 Edifact 事务正在与挂起接收方 id {3} 以下错误：</span><span class="sxs-lookup"><span data-stu-id="c37bf-117">The Edifact transaction set with id '{0}' contained in interchange (without group) with id '{1}', with sender id '{2}', receiver id '{3}' is being suspended with following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c37bf-118">解释</span><span class="sxs-lookup"><span data-stu-id="c37bf-118">Explanation</span></span>  
 <span data-ttu-id="c37bf-119">此错误/警告/信息事件表明由于通过交换中标识的事务集指明的错误，在分析传入的 EDIFACT 交换（该交换没有组）时 EDI 接收管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="c37bf-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange without a group because of the stated errors with the identified transaction set in the interchange.</span></span> <span data-ttu-id="c37bf-120">请注意，该事务集不在交换的组中。</span><span class="sxs-lookup"><span data-stu-id="c37bf-120">Note that the transaction set is not in a group in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c37bf-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="c37bf-121">User Action</span></span>  
 <span data-ttu-id="c37bf-122">若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="c37bf-122">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>