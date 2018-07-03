---
title: 已达到可接受 Edifact 功能组控制编号的最大限制来宾设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93ea1bd6-8c39-4d11-81a5-75d4a861e041
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 533f1067effa99f4152c908c70adf16eeb067c7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010446"
---
# <a name="max-limit-of-acceptable-edifact-functional-group-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="96df4-102">已达到“来宾”设置的可接受 EDIFACT 功能组控制编号最大限制</span><span class="sxs-lookup"><span data-stu-id="96df4-102">Max limit of acceptable Edifact functional group control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="96df4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="96df4-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="96df4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="96df4-104">Product Name</span></span>   |                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                 |
| <span data-ttu-id="96df4-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="96df4-105">Product Version</span></span> |                                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                             |
|    <span data-ttu-id="96df4-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="96df4-106">Event ID</span></span>     |                                                                                                         -                                                                                                          |
|  <span data-ttu-id="96df4-107">事件源</span><span class="sxs-lookup"><span data-stu-id="96df4-107">Event Source</span></span>   |                                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="96df4-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="96df4-108"> EDI</span></span>                                                               |
|    <span data-ttu-id="96df4-109">组件</span><span class="sxs-lookup"><span data-stu-id="96df4-109">Component</span></span>    |                                                                                                     <span data-ttu-id="96df4-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="96df4-110">EDI Engine</span></span>                                                                                                     |
|  <span data-ttu-id="96df4-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="96df4-111">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="96df4-112">GlobalEdifactUngNumberError</span><span class="sxs-lookup"><span data-stu-id="96df4-112">GlobalEdifactUngNumberError</span></span>                                                                                             |
|  <span data-ttu-id="96df4-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="96df4-113">Message Text</span></span>   | <span data-ttu-id="96df4-114">已达到“来宾”设置的可接受 Edifact 功能组控制编号最大限制。</span><span class="sxs-lookup"><span data-stu-id="96df4-114">Max limit of acceptable Edifact functional group control number has reached for Guest settings.</span></span> <span data-ttu-id="96df4-115">导航到“全局”配置接收方角色屏幕、合作伙伴协议管理器中的字段 UNG 5 可重置计数器</span><span class="sxs-lookup"><span data-stu-id="96df4-115">Reset counter by navigating to Global configuration receiver role screen, field UNG 5 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="96df4-116">解释</span><span class="sxs-lookup"><span data-stu-id="96df4-116">Explanation</span></span>  
 <span data-ttu-id="96df4-117">此错误/警告/信息事件表明发送管道无法处理传出的交换，因为在全局设置中指定的 UNG5 字段中的组控制编号（具体来说就是字段 UNG5.2 中的参考编号）大于所允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="96df4-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the group control number in the UNG5 field specified in the global settings, specifically the reference number in field UNG5.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="96df4-118">所允许的组控制编号的最大值取决于 UNG5 中三个字段的值。</span><span class="sxs-lookup"><span data-stu-id="96df4-118">The maximum allowable value for the group control number depends upon the values of the three fields in UNG5.</span></span> <span data-ttu-id="96df4-119">最大字符数是 14（对于字段 UNG5.2 中的参考编号）、13（对于 UNG5.1 中的前缀）、13（对于 UNG5.3 中的后缀）以及 14（对于所有三个字段的组合）。</span><span class="sxs-lookup"><span data-stu-id="96df4-119">The maximum number of characters is 14 for the reference number in field UNG5.2, 13 for the prefix in UNG5.1 and 13 for the suffix in UNG5.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="96df4-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="96df4-120">User Action</span></span>  
 <span data-ttu-id="96df4-121">若要解决此错误，请按照如下方式重置组控制编号的参考编号字段 (UNG5.2)：</span><span class="sxs-lookup"><span data-stu-id="96df4-121">To resolve this error, reset the reference number field (UNG5.2) of the group control number, as follows:</span></span>  
  
1.  <span data-ttu-id="96df4-122">在“EDI 全局属性”对话框中，打开“UNG 和 UNH 段定义”页。</span><span class="sxs-lookup"><span data-stu-id="96df4-122">In the EDI Global Properties dialog box, open the UNG and UNH Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="96df4-123">单击与 UNG5 字段关联的“编辑”字段。</span><span class="sxs-lookup"><span data-stu-id="96df4-123">Click the Edit field associated with the UNG5 field.</span></span>  
  
3.  <span data-ttu-id="96df4-124">将组控制编号的中间字段（UNG5.2 中的参考编号）设置为新值，以便该字段具有可接受的位数。</span><span class="sxs-lookup"><span data-stu-id="96df4-124">Set the middle field of the group control number (the reference number in UNG5.2) to a new value such that the field has an acceptable number of digits.</span></span>