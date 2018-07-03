---
title: 在解析过程中遇到错误。 以下错误被挂起事务集功能组中包含的 X12 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c6fa8e-d81c-4ccb-93b4-852ab184c4e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dcb735fb74892f8652741060c3f9ce849cb12b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004366"
---
# <a name="error-encountered-during-parsing-the-x12-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="7dec9-103">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="7dec9-103">Error encountered during parsing.</span></span> <span data-ttu-id="7dec9-104">功能组中包含的 X12 事务集由于以下错误被挂起</span><span class="sxs-lookup"><span data-stu-id="7dec9-104">The X12 transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="7dec9-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="7dec9-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7dec9-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="7dec9-106">Product Name</span></span>   |                                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                          |
| <span data-ttu-id="7dec9-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="7dec9-107">Product Version</span></span> |                                                                                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                      |
|    <span data-ttu-id="7dec9-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7dec9-108">Event ID</span></span>     |                                                                                                                  -                                                                                                                   |
|  <span data-ttu-id="7dec9-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7dec9-109">Event Source</span></span>   |                                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7dec9-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="7dec9-110"> EDI</span></span>                                                                        |
|    <span data-ttu-id="7dec9-111">组件</span><span class="sxs-lookup"><span data-stu-id="7dec9-111">Component</span></span>    |                                                                                                              <span data-ttu-id="7dec9-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="7dec9-112">EDI Engine</span></span>                                                                                                              |
|  <span data-ttu-id="7dec9-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7dec9-113">Symbolic Name</span></span>  |                                                                                                    <span data-ttu-id="7dec9-114">X12TransactionSetReceiveError</span><span class="sxs-lookup"><span data-stu-id="7dec9-114">X12TransactionSetReceiveError</span></span>                                                                                                     |
|  <span data-ttu-id="7dec9-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7dec9-115">Message Text</span></span>   | <span data-ttu-id="7dec9-116">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="7dec9-116">Error encountered during parsing.</span></span> <span data-ttu-id="7dec9-117">X12 事务集 id 为 '{0}功能组 id 中包含{1}，交换中包含的 id{2}，发送方 id{3}，接收方 id{4}以下错误被挂起：</span><span class="sxs-lookup"><span data-stu-id="7dec9-117">The X12 transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7dec9-118">解释</span><span class="sxs-lookup"><span data-stu-id="7dec9-118">Explanation</span></span>  
 <span data-ttu-id="7dec9-119">此错误/警告/信息事件表明由于通过标识的事务集指明的错误，在分析传入的 X12 交换时 EDI 接收管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="7dec9-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming X12 interchange because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7dec9-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="7dec9-120">User Action</span></span>  
 <span data-ttu-id="7dec9-121">若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="7dec9-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>