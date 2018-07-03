---
title: 在解析过程中遇到错误。 以下错误被挂起的 Edifact 事务集功能组中包含 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 986a7220-d35a-4047-8996-7d44c7d2b823
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b7e5dd86c995b78eb07aa9c7516274b748ee99b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014094"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="b0631-103">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="b0631-103">Error encountered during parsing.</span></span> <span data-ttu-id="b0631-104">功能组中包含的 EDIFACT 事务集由于以下错误被挂起</span><span class="sxs-lookup"><span data-stu-id="b0631-104">The Edifact transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="b0631-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="b0631-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b0631-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="b0631-106">Product Name</span></span>   |                                                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                            |
| <span data-ttu-id="b0631-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="b0631-107">Product Version</span></span> |                                                                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                        |
|    <span data-ttu-id="b0631-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b0631-108">Event ID</span></span>     |                                                                                                                    -                                                                                                                     |
|  <span data-ttu-id="b0631-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b0631-109">Event Source</span></span>   |                                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b0631-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="b0631-110"> EDI</span></span>                                                                          |
|    <span data-ttu-id="b0631-111">组件</span><span class="sxs-lookup"><span data-stu-id="b0631-111">Component</span></span>    |                                                                                                                <span data-ttu-id="b0631-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="b0631-112">EDI Engine</span></span>                                                                                                                |
|  <span data-ttu-id="b0631-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b0631-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="b0631-114">EfactTransactionSetReceiveError</span><span class="sxs-lookup"><span data-stu-id="b0631-114">EfactTransactionSetReceiveError</span></span>                                                                                                      |
|  <span data-ttu-id="b0631-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b0631-115">Message Text</span></span>   | <span data-ttu-id="b0631-116">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="b0631-116">Error encountered during parsing.</span></span> <span data-ttu-id="b0631-117">Edifact 事务集 id 为 '{0}功能组 id 中包含{1}，交换中包含的 id{2}，发送方 id{3}，接收方 id{4}以下错误被挂起：</span><span class="sxs-lookup"><span data-stu-id="b0631-117">The Edifact transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b0631-118">解释</span><span class="sxs-lookup"><span data-stu-id="b0631-118">Explanation</span></span>  
 <span data-ttu-id="b0631-119">此错误/警告/信息事件表明 EDI 接收管道无法分析传入的 EDIFACT 交换（该交换具有一个组），因为通过标识的事务集指明了错误。</span><span class="sxs-lookup"><span data-stu-id="b0631-119">This Error/Warning/Information event indicates that the EDI receive pipeline could not parse an incoming EDIFACT interchange with a group because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b0631-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="b0631-120">User Action</span></span>  
 <span data-ttu-id="b0631-121">若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在文档中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="b0631-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the documentation.</span></span>