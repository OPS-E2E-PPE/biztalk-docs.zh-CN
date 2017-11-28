---
title: "当事方达到可接受的 Edifact 功能组控制编号的最大限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fde516b-59f1-49a1-8456-127469df0e02
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d4a47e0866c78e692f8c992afbd6b24cde95632
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="max-limit-of-acceptable-edifact-functional-group-control-number-has-reached-for-party"></a><span data-ttu-id="0a6dc-102">已达到参与方的可接受 EDIFACT 功能组控制编号最大限制</span><span class="sxs-lookup"><span data-stu-id="0a6dc-102">Max limit of acceptable Edifact functional group control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="0a6dc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0a6dc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a6dc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0a6dc-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0a6dc-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0a6dc-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0a6dc-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0a6dc-106">Event ID</span></span>|-|  
|<span data-ttu-id="0a6dc-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0a6dc-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0a6dc-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0a6dc-108"> EDI</span></span>|  
|<span data-ttu-id="0a6dc-109">组件</span><span class="sxs-lookup"><span data-stu-id="0a6dc-109">Component</span></span>|<span data-ttu-id="0a6dc-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0a6dc-110">EDI Engine</span></span>|  
|<span data-ttu-id="0a6dc-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0a6dc-111">Symbolic Name</span></span>|<span data-ttu-id="0a6dc-112">PartyEdifactUngNumberError</span><span class="sxs-lookup"><span data-stu-id="0a6dc-112">PartyEdifactUngNumberError</span></span>|  
|<span data-ttu-id="0a6dc-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0a6dc-113">Message Text</span></span>|<span data-ttu-id="0a6dc-114">已达到参与方 {0} 的可接受 Edifact 功能组控制编号最大限制。</span><span class="sxs-lookup"><span data-stu-id="0a6dc-114">Max limit of acceptable Edifact functional group control number has reached for party {0}.</span></span> <span data-ttu-id="0a6dc-115">导航到合作伙伴协议管理器的接收方角色屏幕中“参与方”中的字段 UNG 5 可重置计数器</span><span class="sxs-lookup"><span data-stu-id="0a6dc-115">Reset counter by navigating to Party in receiver role screen, field UNG 5 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0a6dc-116">解释</span><span class="sxs-lookup"><span data-stu-id="0a6dc-116">Explanation</span></span>  
 <span data-ttu-id="0a6dc-117">此错误/警告/信息事件表明发送管道无法处理传出的 EDIFACT 交换，因为在参与方设置中指定的 UNG5 字段中的组控制编号（具体来说就是字段 UNG5.2 中的参考编号）大于所允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="0a6dc-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing EDIFACT interchange because the group control number in the UNG5 field specified in the party settings, specifically the reference number in field UNG5.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="0a6dc-118">所允许的组控制编号的最大值取决于 UNG5 中三个字段的值。</span><span class="sxs-lookup"><span data-stu-id="0a6dc-118">The maximum allowable value for the group control number depends upon the values of the three fields in UNG5.</span></span> <span data-ttu-id="0a6dc-119">最大字符数是 14（对于字段 UNG5.2 中的参考编号）、13（对于 UNG5.1 中的前缀）、13（对于 UNG5.3 中的后缀）以及 14（对于所有三个字段的组合）。</span><span class="sxs-lookup"><span data-stu-id="0a6dc-119">The maximum number of characters is 14 for the reference number in field UNG5.2, 13 for the prefix in UNG5.1 and 13 for the suffix in UNG5.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a6dc-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="0a6dc-120">User Action</span></span>  
 <span data-ttu-id="0a6dc-121">若要解决此错误，请按照如下方式重置组控制编号的参考编号字段 (UNG5.2)：</span><span class="sxs-lookup"><span data-stu-id="0a6dc-121">To resolve this error, reset the reference number field (UNG5.2) of the group control number, as follows:</span></span>  
  
1.  <span data-ttu-id="0a6dc-122">在为交换解析的参与方的“EDI 属性”对话框中，打开作为交换接收方的参与方的“UNG 和 UNH 段定义”页。</span><span class="sxs-lookup"><span data-stu-id="0a6dc-122">In the EDI Properties dialog box for the party resolved for the interchange, open the UNG and UNH Segment Definition page for the party as interchange receiver.</span></span>  
  
2.  <span data-ttu-id="0a6dc-123">单击与 UNG5 字段关联的“编辑”字段。</span><span class="sxs-lookup"><span data-stu-id="0a6dc-123">Click the Edit field associated with the UNG5 field.</span></span>  
  
3.  <span data-ttu-id="0a6dc-124">将组控制编号的中间字段（UNG5.2 中的参考编号）设置为新值，以便该字段具有可接受的位数。</span><span class="sxs-lookup"><span data-stu-id="0a6dc-124">Set the middle field of the group control number (the reference number in UNG5.2) to a new value such that the field has an acceptable number of digits.</span></span>