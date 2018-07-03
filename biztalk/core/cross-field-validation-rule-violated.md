---
title: 跨字段验证规则违反 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d606a80-9046-4572-9cfb-a3434ed8073e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d590fc318e7d833a067f4275986bef88da10364
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976654"
---
# <a name="cross-field-validation-rule-violated"></a><span data-ttu-id="2d069-102">违反跨字段验证规则</span><span class="sxs-lookup"><span data-stu-id="2d069-102">Cross field validation rule violated</span></span>
## <a name="details"></a><span data-ttu-id="2d069-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2d069-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="2d069-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2d069-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="2d069-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="2d069-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="2d069-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2d069-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="2d069-107">事件源</span><span class="sxs-lookup"><span data-stu-id="2d069-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2d069-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="2d069-108"> EDI</span></span> |
|    <span data-ttu-id="2d069-109">组件</span><span class="sxs-lookup"><span data-stu-id="2d069-109">Component</span></span>    |                                       <span data-ttu-id="2d069-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="2d069-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="2d069-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="2d069-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="2d069-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="2d069-112">Message Text</span></span>   |                          <span data-ttu-id="2d069-113">违反跨字段验证规则</span><span class="sxs-lookup"><span data-stu-id="2d069-113">Cross field validation rule violated</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="2d069-114">解释</span><span class="sxs-lookup"><span data-stu-id="2d069-114">Explanation</span></span>  
 <span data-ttu-id="2d069-115">此错误/警告/信息事件表明接收管道或发送管道中的 X12 交换未通过跨字段验证。</span><span class="sxs-lookup"><span data-stu-id="2d069-115">This Error/Warning/Information event indicates that the X12 interchange failed cross-field validation in the receive pipeline or the send pipeline.</span></span> <span data-ttu-id="2d069-116">这表明 X12ConditionDesignator_Check 标志设置为“是”，并且至少交换中的一个元素未通过前缀“X12ConditionDesignatorX”标识的规则。</span><span class="sxs-lookup"><span data-stu-id="2d069-116">This indicates that the X12ConditionDesignator_Check flag is set to "Yes", and that at least one element in the interchange failed a rule identified by the prefix "X12ConditionDesignatorX".</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2d069-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="2d069-117">User Action</span></span>  
 <span data-ttu-id="2d069-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="2d069-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="2d069-119">确定哪个数据元素未通过跨字段验证规则。</span><span class="sxs-lookup"><span data-stu-id="2d069-119">Identify which data element failed a cross-field validation rule.</span></span> <span data-ttu-id="2d069-120">请与交换的发送方联系并且指出创建交换时必须遵循该规则。</span><span class="sxs-lookup"><span data-stu-id="2d069-120">Contact the sender of the interchange and indicate that the rule must be followed when creating the interchange.</span></span>  
  
-   <span data-ttu-id="2d069-121">打开交换的架构，并将未通过验证的数据元素的 X12ConditionDesignator_Check 标志设置为“否”。</span><span class="sxs-lookup"><span data-stu-id="2d069-121">Open the schema for the interchange, and set the X12ConditionDesignator_Check flag for the data element that failed validation to "No".</span></span>