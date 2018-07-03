---
title: 可接受 Edifact 交换控制编号的最大限制已达到参与方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c00c357-4c7b-42ea-a031-15bad0195a75
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c11029af5b2f87e4e1bf3e7fc4225bfc5ba46105
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998198"
---
# <a name="max-limit-of-acceptable-edifact-interchange-control-number-has-reached-for-party"></a><span data-ttu-id="8df5e-102">已达到参与方的可接受 EDIFACT 交换控制编号最大限制</span><span class="sxs-lookup"><span data-stu-id="8df5e-102">Max limit of acceptable Edifact interchange control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="8df5e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8df5e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8df5e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8df5e-104">Product Name</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| <span data-ttu-id="8df5e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8df5e-105">Product Version</span></span> |                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    <span data-ttu-id="8df5e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8df5e-106">Event ID</span></span>     |                                                                                              -                                                                                               |
|  <span data-ttu-id="8df5e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="8df5e-107">Event Source</span></span>   |                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8df5e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="8df5e-108"> EDI</span></span>                                                    |
|    <span data-ttu-id="8df5e-109">组件</span><span class="sxs-lookup"><span data-stu-id="8df5e-109">Component</span></span>    |                                                                                          <span data-ttu-id="8df5e-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="8df5e-110">EDI Engine</span></span>                                                                                          |
|  <span data-ttu-id="8df5e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="8df5e-111">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="8df5e-112">PartyEdifactUnbNumberError</span><span class="sxs-lookup"><span data-stu-id="8df5e-112">PartyEdifactUnbNumberError</span></span>                                                                                  |
|  <span data-ttu-id="8df5e-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="8df5e-113">Message Text</span></span>   | <span data-ttu-id="8df5e-114">可接受 Edifact 交换控制编号的最大限制已达到参与方{0}。</span><span class="sxs-lookup"><span data-stu-id="8df5e-114">Max limit of acceptable Edifact interchange control number has reached for party {0}.</span></span> <span data-ttu-id="8df5e-115">导航到合作伙伴协议管理器的接收方角色屏幕中“参与方”中的字段 UNB 5 可重置计数器</span><span class="sxs-lookup"><span data-stu-id="8df5e-115">Reset counter by navigating to Party in receiver role screen, field UNB 5 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8df5e-116">解释</span><span class="sxs-lookup"><span data-stu-id="8df5e-116">Explanation</span></span>  
 <span data-ttu-id="8df5e-117">此错误/警告/信息事件表明发送管道无法处理传出的交换，因为在参与方设置中指定的 UNB5 字段中的交换控制编号（具体来说就是字段 UNB5.2 中的参考编号）大于所允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="8df5e-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the interchange control number in the UNB5 field specified in the party settings, specifically the reference number in field UNB5.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="8df5e-118">所允许的交换控制编号的最大值取决于 UNB5 中三个字段的值。</span><span class="sxs-lookup"><span data-stu-id="8df5e-118">The maximum allowable value for the interchange control number depends upon the values of the three fields in UNB5.</span></span> <span data-ttu-id="8df5e-119">最大字符数是 14（对于字段 UNB5.2 中的参考编号）、13（对于 UNB5.1 中的前缀）、13（对于 UNB5.3 中的后缀）以及 14（对于所有三个字段的组合）。</span><span class="sxs-lookup"><span data-stu-id="8df5e-119">The maximum number of characters is 14 for the reference number in field UNB5.2, 13 for the prefix in UNB5.1 and 13 for the suffix in UNB5.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8df5e-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="8df5e-120">User Action</span></span>  
 <span data-ttu-id="8df5e-121">若要解决此错误，请按照如下方式重置交换控制编号的参考编号字段 (UNB5.2)：</span><span class="sxs-lookup"><span data-stu-id="8df5e-121">To resolve this error, reset the reference number field (UNB5.2) of the interchange control number, as follows:</span></span>  
  
1.  <span data-ttu-id="8df5e-122">在为交换解析的参与方的“EDI 属性”对话框中，打开作为交换接收方的参与方的“UNB 段定义”页。</span><span class="sxs-lookup"><span data-stu-id="8df5e-122">In the EDI Properties dialog box for the party resolved for the interchange, open the UNB Segment Definition page for the party as interchange receiver.</span></span>  
  
2.  <span data-ttu-id="8df5e-123">单击与 UNB5 字段关联的“编辑”字段。</span><span class="sxs-lookup"><span data-stu-id="8df5e-123">Click the Edit field associated with the UNB5 field.</span></span>  
  
3.  <span data-ttu-id="8df5e-124">将交换控制编号的中间字段（UNB5.2 中的参考编号）设置为新值，以便该字段具有可接受的位数。</span><span class="sxs-lookup"><span data-stu-id="8df5e-124">Set the middle field of the interchange control number (the reference number in UNB5.2) to a new value such that the field has an acceptable number of digits.</span></span>