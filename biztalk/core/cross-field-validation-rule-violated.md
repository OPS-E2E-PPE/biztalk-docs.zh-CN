---
title: "跨违反字段验证规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d606a80-9046-4572-9cfb-a3434ed8073e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ba6e7b5e81caf3b091c146755ba37896fb1120b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="cross-field-validation-rule-violated"></a><span data-ttu-id="c9c9d-102">违反跨字段验证规则</span><span class="sxs-lookup"><span data-stu-id="c9c9d-102">Cross field validation rule violated</span></span>
## <a name="details"></a><span data-ttu-id="c9c9d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c9c9d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9c9d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c9c9d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c9c9d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c9c9d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c9c9d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c9c9d-106">Event ID</span></span>|-|  
|<span data-ttu-id="c9c9d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c9c9d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c9c9d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c9c9d-108"> EDI</span></span>|  
|<span data-ttu-id="c9c9d-109">组件</span><span class="sxs-lookup"><span data-stu-id="c9c9d-109">Component</span></span>|<span data-ttu-id="c9c9d-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c9c9d-110">EDI Engine</span></span>|  
|<span data-ttu-id="c9c9d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c9c9d-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="c9c9d-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="c9c9d-112">Message Text</span></span>|<span data-ttu-id="c9c9d-113">违反跨字段验证规则</span><span class="sxs-lookup"><span data-stu-id="c9c9d-113">Cross field validation rule violated</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c9c9d-114">解释</span><span class="sxs-lookup"><span data-stu-id="c9c9d-114">Explanation</span></span>  
 <span data-ttu-id="c9c9d-115">此错误/警告/信息事件表明接收管道或发送管道中的 X12 交换未通过跨字段验证。</span><span class="sxs-lookup"><span data-stu-id="c9c9d-115">This Error/Warning/Information event indicates that the X12 interchange failed cross-field validation in the receive pipeline or the send pipeline.</span></span> <span data-ttu-id="c9c9d-116">这表明 X12ConditionDesignator_Check 标志设置为“是”，并且至少交换中的一个元素未通过前缀“X12ConditionDesignatorX”标识的规则。</span><span class="sxs-lookup"><span data-stu-id="c9c9d-116">This indicates that the X12ConditionDesignator_Check flag is set to "Yes", and that at least one element in the interchange failed a rule identified by the prefix "X12ConditionDesignatorX".</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9c9d-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="c9c9d-117">User Action</span></span>  
 <span data-ttu-id="c9c9d-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="c9c9d-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="c9c9d-119">确定哪个数据元素未通过跨字段验证规则。</span><span class="sxs-lookup"><span data-stu-id="c9c9d-119">Identify which data element failed a cross-field validation rule.</span></span> <span data-ttu-id="c9c9d-120">请与交换的发送方联系并且指出创建交换时必须遵循该规则。</span><span class="sxs-lookup"><span data-stu-id="c9c9d-120">Contact the sender of the interchange and indicate that the rule must be followed when creating the interchange.</span></span>  
  
-   <span data-ttu-id="c9c9d-121">打开交换的架构，并将未通过验证的数据元素的 X12ConditionDesignator_Check 标志设置为“否”。</span><span class="sxs-lookup"><span data-stu-id="c9c9d-121">Open the schema for the interchange, and set the X12ConditionDesignator_Check flag for the data element that failed validation to "No".</span></span>