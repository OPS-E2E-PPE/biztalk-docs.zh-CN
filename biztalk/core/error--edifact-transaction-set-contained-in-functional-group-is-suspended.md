---
title: "在解析过程中遇到错误。 出现以下错误正在挂起 Edifact 事务集包含在功能组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 986a7220-d35a-4047-8996-7d44c7d2b823
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70428ae8f430ea5ccb9ff13e068716cb35555f69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="939d3-103">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="939d3-103">Error encountered during parsing.</span></span> <span data-ttu-id="939d3-104">功能组中包含的 EDIFACT 事务集由于以下错误被挂起</span><span class="sxs-lookup"><span data-stu-id="939d3-104">The Edifact transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="939d3-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="939d3-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="939d3-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="939d3-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="939d3-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="939d3-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="939d3-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="939d3-108">Event ID</span></span>|-|  
|<span data-ttu-id="939d3-109">事件源</span><span class="sxs-lookup"><span data-stu-id="939d3-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="939d3-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="939d3-110"> EDI</span></span>|  
|<span data-ttu-id="939d3-111">组件</span><span class="sxs-lookup"><span data-stu-id="939d3-111">Component</span></span>|<span data-ttu-id="939d3-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="939d3-112">EDI Engine</span></span>|  
|<span data-ttu-id="939d3-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="939d3-113">Symbolic Name</span></span>|<span data-ttu-id="939d3-114">EfactTransactionSetReceiveError</span><span class="sxs-lookup"><span data-stu-id="939d3-114">EfactTransactionSetReceiveError</span></span>|  
|<span data-ttu-id="939d3-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="939d3-115">Message Text</span></span>|<span data-ttu-id="939d3-116">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="939d3-116">Error encountered during parsing.</span></span> <span data-ttu-id="939d3-117">Id 为"{0}"中 id 为 {1} 功能组包含设置 Edifact 事务 id 为 {2} 发件人 id {3} 使用的交换中接收方 id \ {4 \ 正在挂起出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="939d3-117">The Edifact transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="939d3-118">解释</span><span class="sxs-lookup"><span data-stu-id="939d3-118">Explanation</span></span>  
 <span data-ttu-id="939d3-119">此错误/警告/信息事件表明 EDI 接收管道无法分析传入的 EDIFACT 交换（该交换具有一个组），因为通过标识的事务集指明了错误。</span><span class="sxs-lookup"><span data-stu-id="939d3-119">This Error/Warning/Information event indicates that the EDI receive pipeline could not parse an incoming EDIFACT interchange with a group because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="939d3-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="939d3-120">User Action</span></span>  
 <span data-ttu-id="939d3-121">若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在文档中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="939d3-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the documentation.</span></span>