---
title: Doctype 无效 |Microsoft Docs
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
ms.openlocfilehash: 316413265084e2df64bf2ef5c2e4227f9a886829
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530819"
---
# <a name="doctype-is-invalid"></a><span data-ttu-id="ae7f2-102">Doctype 无效</span><span class="sxs-lookup"><span data-stu-id="ae7f2-102">Doctype is invalid</span></span>
## <a name="details"></a><span data-ttu-id="ae7f2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ae7f2-103">Details</span></span>  
  
|                 |                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ae7f2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ae7f2-104">Product Name</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                |
| <span data-ttu-id="ae7f2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ae7f2-105">Product Version</span></span> |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                            |
|    <span data-ttu-id="ae7f2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ae7f2-106">Event ID</span></span>     |                                                        -                                                        |
|  <span data-ttu-id="ae7f2-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ae7f2-107">Event Source</span></span>   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ae7f2-108">EDI</span><span class="sxs-lookup"><span data-stu-id="ae7f2-108">EDI</span></span>              |
|    <span data-ttu-id="ae7f2-109">组件</span><span class="sxs-lookup"><span data-stu-id="ae7f2-109">Component</span></span>    |                                                   <span data-ttu-id="ae7f2-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ae7f2-110">EDI Engine</span></span>                                                    |
|  <span data-ttu-id="ae7f2-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ae7f2-111">Symbolic Name</span></span>  |                                              <span data-ttu-id="ae7f2-112">DocTypeInvalidFormat</span><span class="sxs-lookup"><span data-stu-id="ae7f2-112">DocTypeInvalidFormat</span></span>                                               |
|  <span data-ttu-id="ae7f2-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ae7f2-113">Message Text</span></span>   | <span data-ttu-id="ae7f2-114">Doctype{0}无效。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-114">Doctype {0} is invalid.</span></span> <span data-ttu-id="ae7f2-115">不能确定一个或多个命名空间、 版本或事务集 id</span><span class="sxs-lookup"><span data-stu-id="ae7f2-115">It is not possible to determine one or more of namespace, version or transaction set id</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ae7f2-116">解释</span><span class="sxs-lookup"><span data-stu-id="ae7f2-116">Explanation</span></span>  
 <span data-ttu-id="ae7f2-117">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的交换，因为未正确发现架构。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-117">This Error/Warning/Information event indicates that the EDI receive pipeline was not able to process the incoming interchange, because the schema was not discovered correctly.</span></span>  
  
 <span data-ttu-id="ae7f2-118">对于 X12，确定目标命名空间是在"启用自定义事务集定义"网格中的 x12 交换处理属性页的 EDI 属性对话框。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-118">For X12, the target namespace is determined in the "Enable custom transaction set definitions" grid of the X12 Interchange Processing Properties page of the EDI Properties dialog box.</span></span> <span data-ttu-id="ae7f2-119">消息中的 GS02 和 ST01 值必须与某行网格中，若要正确标识目标命名空间中进行匹配。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-119">The GS02 and ST01 values in the message must match those in a row of the grid, to correctly identify the target namespace.</span></span> <span data-ttu-id="ae7f2-120">通过在传入的事务集标识的目标命名空间中添加的版本 （GS08 的前五个字符） 和 doctype (ST01) 创建要用于该事务集的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-120">The name of the schema to be used for the transaction set is created by adding the version (the first five characters of GS08) and the doctype (ST01) in the incoming transaction set to the target namespace identified.</span></span>  
  
 <span data-ttu-id="ae7f2-121">对于 EDIFACT，在 EDI 属性对话框的 EDIFACT 交换处理属性页的"启用自定义事务集定义"网格中确定目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-121">For EDIFACT, the target namespace is determined in the "Enable custom transaction set definitions" grid of the EDIFACT Interchange Processing Properties page of the EDI Properties dialog box.</span></span> <span data-ttu-id="ae7f2-122">消息中的 UNH2.1、 UNH2.2、 UNH2.3、 UNH2.5、 UNG2.1 和 UNG2.2 值必须与某行网格中，若要正确标识目标命名空间中进行匹配。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-122">The UNH2.1, UNH2.2, UNH2.3, UNH2.5, UNG2.1, and UNG2.2 values in the message must match those in a row of the grid, to correctly identify the target namespace.</span></span> <span data-ttu-id="ae7f2-123">通过在 UNH2.2、 UNH2.3 中的消息发行版号以及 UNH2.1 中的传入事务集标识的目标命名空间中的消息类型中添加的消息版本号创建要用于该事务集的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-123">The name of the schema to be used for the transaction set is created by adding the message version number in UNH2.2, the message release number in UNH2.3, and the message type in UNH2.1 in the incoming transaction set to the target namespace identified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ae7f2-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="ae7f2-124">User Action</span></span>  
 <span data-ttu-id="ae7f2-125">若要解决此错误，请执行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ae7f2-125">To resolve this error, do as follows:</span></span>  
  
1.  <span data-ttu-id="ae7f2-126">请确保"启用自定义事务集定义"网格中的交换处理属性页的 EDI 属性对话框中的行正确标识事务集的架构的命名空间。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-126">Ensure that the namespace for the schema for the transaction set is correctly identified by a row in the "Enable custom transaction set definitions" grid of the Interchange Processing Properties page of the EDI Properties dialog box.</span></span> <span data-ttu-id="ae7f2-127">如果没有，请更改网格中的值。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-127">If not, change the values in the grid.</span></span>  
  
2.  <span data-ttu-id="ae7f2-128">如果已正确标识命名空间，确定用于标识架构的值是否正确。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-128">If the namespace has been correctly identified, determine whether the values that are used to identify the schema are correct.</span></span> <span data-ttu-id="ae7f2-129">对于 X12，它们的版本 （GS08 的前五个字符） 和 doctype (ST01) 中传入的事务集。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-129">For X12, they are the version (the first five characters of GS08) and the doctype (ST01) in the incoming transaction set.</span></span> <span data-ttu-id="ae7f2-130">对于 EDIFACT，它们是在 UNH2.2、 UNH2.3 中的消息发行版号和消息类型 UNH2.1 中的传入事务集中的消息版本号。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-130">For EDIFACT, they are message version number in UNH2.2, the message release number in UNH2.3, and the message type in UNH2.1 in the incoming transaction set.</span></span> <span data-ttu-id="ae7f2-131">如果这些值不正确，请让发送方的事务集更改这些字段的值然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="ae7f2-131">If the values are incorrectly, have the sender of the transaction set change the values of those fields, and then resend the message.</span></span>