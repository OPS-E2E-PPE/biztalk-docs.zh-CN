---
title: 循环包含叶节点。 它只能包含其他循环或段 |Microsoft 文档
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
ms.openlocfilehash: d03349389fb108d434cce67afc5be13fd2a3d513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278829"
---
# <a name="the-loop-contains-a-leaf-node-it-can-only-contain-other-loops-or-segments"></a><span data-ttu-id="9583b-103">循环包含叶节点。</span><span class="sxs-lookup"><span data-stu-id="9583b-103">The loop contains a leaf node.</span></span> <span data-ttu-id="9583b-104">它只能包含其他循环或段</span><span class="sxs-lookup"><span data-stu-id="9583b-104">It can only contain other Loops or Segments</span></span>
## <a name="details"></a><span data-ttu-id="9583b-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="9583b-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9583b-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="9583b-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9583b-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="9583b-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9583b-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9583b-108">Event ID</span></span>|-|  
|<span data-ttu-id="9583b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="9583b-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9583b-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="9583b-110"> EDI</span></span>|  
|<span data-ttu-id="9583b-111">组件</span><span class="sxs-lookup"><span data-stu-id="9583b-111">Component</span></span>|<span data-ttu-id="9583b-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="9583b-112">EDI Engine</span></span>|  
|<span data-ttu-id="9583b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="9583b-113">Symbolic Name</span></span>|<span data-ttu-id="9583b-114">SchemaCode125ELoopContainsLeafNode</span><span class="sxs-lookup"><span data-stu-id="9583b-114">SchemaCode125ELoopContainsLeafNode</span></span>|  
|<span data-ttu-id="9583b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="9583b-115">Message Text</span></span>|<span data-ttu-id="9583b-116">循环包含叶节点。</span><span class="sxs-lookup"><span data-stu-id="9583b-116">The loop contains a leaf node.</span></span> <span data-ttu-id="9583b-117">它只能包含其他循环或段</span><span class="sxs-lookup"><span data-stu-id="9583b-117">It can only contain other Loops or Segments</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9583b-118">解释</span><span class="sxs-lookup"><span data-stu-id="9583b-118">Explanation</span></span>  
 <span data-ttu-id="9583b-119">此错误/警告/信息事件指示接收管道无法处理传入的交换，因为文档架构不符合该交换。</span><span class="sxs-lookup"><span data-stu-id="9583b-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, because the interchange did not conform to the document schema.</span></span> <span data-ttu-id="9583b-120">在这种情况下，循环包含 childless 叶节点，而其他循环或段可能仅包含循环，则指定的架构。</span><span class="sxs-lookup"><span data-stu-id="9583b-120">In this case, a loop contained a childless leaf node, whereas the schema specified that the loop could only contain other loops or segments.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9583b-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="9583b-121">User Action</span></span>  
 <span data-ttu-id="9583b-122">若要解决此错误，具有交换修复循环的发送方，以便其不包含叶节点，然后重新发送该交换。</span><span class="sxs-lookup"><span data-stu-id="9583b-122">To resolve this error, have the sender of the interchange fix the loop so that it does not contain leaf nodes, and then resend the interchange.</span></span>