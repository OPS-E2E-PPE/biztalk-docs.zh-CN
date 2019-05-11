---
title: 循环包含叶节点。 它只能包含其他循环或段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a0ee5e6-519d-4c95-8681-de5a37741d56
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d603e961218bf3f1c0c2597d46fa4be0d7b8e93
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277997"
---
# <a name="the-loop-contains-a-leaf-node-it-can-only-contain-other-loops-or-segments"></a><span data-ttu-id="49681-103">循环包含叶节点。</span><span class="sxs-lookup"><span data-stu-id="49681-103">The loop contains a leaf node.</span></span> <span data-ttu-id="49681-104">它只能包含其他循环或段</span><span class="sxs-lookup"><span data-stu-id="49681-104">It can only contain other Loops or Segments</span></span>
## <a name="details"></a><span data-ttu-id="49681-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="49681-105">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="49681-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="49681-106">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="49681-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="49681-107">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="49681-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="49681-108">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="49681-109">事件源</span><span class="sxs-lookup"><span data-stu-id="49681-109">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="49681-110">EDI</span><span class="sxs-lookup"><span data-stu-id="49681-110">EDI</span></span> |
|    <span data-ttu-id="49681-111">组件</span><span class="sxs-lookup"><span data-stu-id="49681-111">Component</span></span>    |                                       <span data-ttu-id="49681-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="49681-112">EDI Engine</span></span>                                       |
|  <span data-ttu-id="49681-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="49681-113">Symbolic Name</span></span>  |                           <span data-ttu-id="49681-114">SchemaCode125ELoopContainsLeafNode</span><span class="sxs-lookup"><span data-stu-id="49681-114">SchemaCode125ELoopContainsLeafNode</span></span>                           |
|  <span data-ttu-id="49681-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="49681-115">Message Text</span></span>   |       <span data-ttu-id="49681-116">循环包含叶节点。</span><span class="sxs-lookup"><span data-stu-id="49681-116">The loop contains a leaf node.</span></span> <span data-ttu-id="49681-117">它只能包含其他循环或段</span><span class="sxs-lookup"><span data-stu-id="49681-117">It can only contain other Loops or Segments</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="49681-118">解释</span><span class="sxs-lookup"><span data-stu-id="49681-118">Explanation</span></span>  
 <span data-ttu-id="49681-119">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换不符合文档架构。</span><span class="sxs-lookup"><span data-stu-id="49681-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, because the interchange did not conform to the document schema.</span></span> <span data-ttu-id="49681-120">在这种情况下，循环包含一个 childless 叶节点，而其他循环或段，该循环可能仅包含指定的架构。</span><span class="sxs-lookup"><span data-stu-id="49681-120">In this case, a loop contained a childless leaf node, whereas the schema specified that the loop could only contain other loops or segments.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="49681-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="49681-121">User Action</span></span>  
 <span data-ttu-id="49681-122">若要解决此错误，具有发送方的交换修复循环，以便它不包含叶节点，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="49681-122">To resolve this error, have the sender of the interchange fix the loop so that it does not contain leaf nodes, and then resend the interchange.</span></span>