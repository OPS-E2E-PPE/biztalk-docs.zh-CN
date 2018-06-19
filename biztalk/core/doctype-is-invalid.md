---
title: Doctype 无效 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67233aae-65c0-4689-a4b3-60a48132343a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fec7dc4f2dfed0c8e8b8fcde13593d4e29997f7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239141"
---
# <a name="doctype-is-invalid"></a><span data-ttu-id="b2b81-102">Doctype 无效</span><span class="sxs-lookup"><span data-stu-id="b2b81-102">Doctype is invalid</span></span>
## <a name="details"></a><span data-ttu-id="b2b81-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b2b81-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b2b81-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b2b81-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b2b81-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="b2b81-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b2b81-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b2b81-106">Event ID</span></span>|-|  
|<span data-ttu-id="b2b81-107">事件源</span><span class="sxs-lookup"><span data-stu-id="b2b81-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b2b81-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="b2b81-108"> EDI</span></span>|  
|<span data-ttu-id="b2b81-109">组件</span><span class="sxs-lookup"><span data-stu-id="b2b81-109">Component</span></span>|<span data-ttu-id="b2b81-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="b2b81-110">EDI Engine</span></span>|  
|<span data-ttu-id="b2b81-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="b2b81-111">Symbolic Name</span></span>|<span data-ttu-id="b2b81-112">DocTypeInvalidFormat</span><span class="sxs-lookup"><span data-stu-id="b2b81-112">DocTypeInvalidFormat</span></span>|  
|<span data-ttu-id="b2b81-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="b2b81-113">Message Text</span></span>|<span data-ttu-id="b2b81-114">Doctype {0} 无效。</span><span class="sxs-lookup"><span data-stu-id="b2b81-114">Doctype {0} is invalid.</span></span> <span data-ttu-id="b2b81-115">无法确定一个或多个命名空间、版本或事务集 ID</span><span class="sxs-lookup"><span data-stu-id="b2b81-115">It is not possible to determine one or more of namespace, version or transaction set id</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b2b81-116">解释</span><span class="sxs-lookup"><span data-stu-id="b2b81-116">Explanation</span></span>  
 <span data-ttu-id="b2b81-117">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的交换，因为未正确发现架构。</span><span class="sxs-lookup"><span data-stu-id="b2b81-117">This Error/Warning/Information event indicates that the EDI receive pipeline was not able to process the incoming interchange, because the schema was not discovered correctly.</span></span>  
  
 <span data-ttu-id="b2b81-118">对于 X12，目标命名空间是在“EDI 属性”对话框的“X12 交换处理属性”页的“启用自定义事务集定义”网格中确定的。</span><span class="sxs-lookup"><span data-stu-id="b2b81-118">For X12, the target namespace is determined in the "Enable custom transaction set definitions" grid of the X12 Interchange Processing Properties page of the EDI Properties dialog box.</span></span> <span data-ttu-id="b2b81-119">消息中的 GS02 和 ST01 值必须与某行网格中的相应值匹配，才能正确标识目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="b2b81-119">The GS02 and ST01 values in the message must match those in a row of the grid, to correctly identify the target namespace.</span></span> <span data-ttu-id="b2b81-120">用于事务集的架构名称是通过将传入事务集中的版本（GS08 的前 5 个字符）和 doctype (ST01) 添加到指定的目标命名空间来创建的。</span><span class="sxs-lookup"><span data-stu-id="b2b81-120">The name of the schema to be used for the transaction set is created by adding the version (the first five characters of GS08) and the doctype (ST01) in the incoming transaction set to the target namespace identified.</span></span>  
  
 <span data-ttu-id="b2b81-121">对于 EDIFACT，目标命名空间是在“EDI 属性”对话框的“EDIFACT 交换处理属性”页的“启用自定义事务集定义”网格中确定的。</span><span class="sxs-lookup"><span data-stu-id="b2b81-121">For EDIFACT, the target namespace is determined in the "Enable custom transaction set definitions" grid of the EDIFACT Interchange Processing Properties page of the EDI Properties dialog box.</span></span> <span data-ttu-id="b2b81-122">消息中的 UNH2.1、UNH2.2、UNH2.3、UNH2.5、UNG2.1 和 UNG2.2 值必须与某行网格中的对应值匹配，才能正确标识目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="b2b81-122">The UNH2.1, UNH2.2, UNH2.3, UNH2.5, UNG2.1, and UNG2.2 values in the message must match those in a row of the grid, to correctly identify the target namespace.</span></span> <span data-ttu-id="b2b81-123">通过向所标识的目标命名空间中添加传入的事务集的 UNH2.2 中的消息版本号、UNH2.3 中的消息发行版号以及 UNH2.1 中的消息类型来创建将用于事务集的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="b2b81-123">The name of the schema to be used for the transaction set is created by adding the message version number in UNH2.2, the message release number in UNH2.3, and the message type in UNH2.1 in the incoming transaction set to the target namespace identified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b2b81-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="b2b81-124">User Action</span></span>  
 <span data-ttu-id="b2b81-125">若要解决此错误，请执行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2b81-125">To resolve this error, do as follows:</span></span>  
  
1.  <span data-ttu-id="b2b81-126">确保事务集的架构的命名空间能够由“EDI 属性”对话框的“交换处理属性”页的“启用自定义事务集定义”网格中的某一行正确标识。</span><span class="sxs-lookup"><span data-stu-id="b2b81-126">Ensure that the namespace for the schema for the transaction set is correctly identified by a row in the "Enable custom transaction set definitions" grid of the Interchange Processing Properties page of the EDI Properties dialog box.</span></span> <span data-ttu-id="b2b81-127">否则，请更改网格中的相应值。</span><span class="sxs-lookup"><span data-stu-id="b2b81-127">If not, change the values in the grid.</span></span>  
  
2.  <span data-ttu-id="b2b81-128">如果命名空间已正确标识，则确定用于标识架构的值是否正确。</span><span class="sxs-lookup"><span data-stu-id="b2b81-128">If the namespace has been correctly identified, determine whether the values that are used to identify the schema are correct.</span></span> <span data-ttu-id="b2b81-129">对于 X12，这些值是传入事务集中的版本（GS08 的前 5 个字符）和 doctype (ST01)。</span><span class="sxs-lookup"><span data-stu-id="b2b81-129">For X12, they are the version (the first five characters of GS08) and the doctype (ST01) in the incoming transaction set.</span></span> <span data-ttu-id="b2b81-130">对于 EDIFACT，它们是传入的事务集的 UNH2.2 中的消息版本号、UNH2.3 中的消息发行版号以及 UNH2.1 中的消息类型。</span><span class="sxs-lookup"><span data-stu-id="b2b81-130">For EDIFACT, they are message version number in UNH2.2, the message release number in UNH2.3, and the message type in UNH2.1 in the incoming transaction set.</span></span> <span data-ttu-id="b2b81-131">如果这些值不正确，则让事务集的发送方更改这些字段的值，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="b2b81-131">If the values are incorrectly, have the sender of the transaction set change the values of those fields, and then resend the message.</span></span>