---
title: 可接受 Edifact 事务集控制编号已达到来宾设置的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3924a18c-87bc-4727-b7cd-598d3e5ade2a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0de9240d2fd5ea701f701e34698b645b272b904b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978958"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="ca1c2-102">已达到来宾设置的可接受 Edifact 事务集控制编号最大限制</span><span class="sxs-lookup"><span data-stu-id="ca1c2-102">Max limit of acceptable Edifact transaction set control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="ca1c2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ca1c2-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ca1c2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ca1c2-104">Product Name</span></span>   |                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                 |
| <span data-ttu-id="ca1c2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ca1c2-105">Product Version</span></span> |                                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                             |
|    <span data-ttu-id="ca1c2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ca1c2-106">Event ID</span></span>     |                                                                                                         -                                                                                                          |
|  <span data-ttu-id="ca1c2-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ca1c2-107">Event Source</span></span>   |                                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ca1c2-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ca1c2-108"> EDI</span></span>                                                               |
|    <span data-ttu-id="ca1c2-109">组件</span><span class="sxs-lookup"><span data-stu-id="ca1c2-109">Component</span></span>    |                                                                                                     <span data-ttu-id="ca1c2-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ca1c2-110">EDI Engine</span></span>                                                                                                     |
|  <span data-ttu-id="ca1c2-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ca1c2-111">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="ca1c2-112">GlobalEdifactUnhNumberError</span><span class="sxs-lookup"><span data-stu-id="ca1c2-112">GlobalEdifactUnhNumberError</span></span>                                                                                             |
|  <span data-ttu-id="ca1c2-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ca1c2-113">Message Text</span></span>   | <span data-ttu-id="ca1c2-114">已达到来宾设置的可接受 Edifact 事务集控制编号最大限制。</span><span class="sxs-lookup"><span data-stu-id="ca1c2-114">Max limit of acceptable Edifact transaction set control number has reached for Guest settings.</span></span> <span data-ttu-id="ca1c2-115">导航到合作伙伴协议管理器的全局配置接收方角色屏幕中的字段 UNH 1 可重置计数器</span><span class="sxs-lookup"><span data-stu-id="ca1c2-115">Reset counter by  navigating to Global configuration receiver role screen, field UNH 1 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ca1c2-116">解释</span><span class="sxs-lookup"><span data-stu-id="ca1c2-116">Explanation</span></span>  
 <span data-ttu-id="ca1c2-117">此错误/警告/信息事件表明发送管道无法处理传出的交换，因为在全局设置中指定的 UNH1 字段中的事务集控制编号（具体来说就是字段 UNH1.2 中的参考编号）大于所允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="ca1c2-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the transaction set control number in the UNH1 field specified in the global settings, specifically the reference number in field UNH1.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="ca1c2-118">所允许的组控制编号的最大值取决于 UNH1 中三个字段的值。</span><span class="sxs-lookup"><span data-stu-id="ca1c2-118">The maximum allowable value for the group control number depends upon the values of the three fields in UNH1.</span></span> <span data-ttu-id="ca1c2-119">最大字符数是 14 个字段 UNH1.2，13 个 UNH1.1 中的前缀和 UNH1.3 中的后缀的 13 和 14 个所有三个字段的组合中的参考编号。</span><span class="sxs-lookup"><span data-stu-id="ca1c2-119">The maximum number of characters is 14 for the reference number in field UNH1.2, 13 for the prefix in UNH1.1 and 13 for the suffix in UNH1.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ca1c2-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="ca1c2-120">User Action</span></span>  
 <span data-ttu-id="ca1c2-121">若要解决此错误，请按照如下方式重置事务集控制编号的参考编号字段 (UNH1.2)：</span><span class="sxs-lookup"><span data-stu-id="ca1c2-121">To resolve this error, reset the reference number field (UNH1.2) of the transaction set control number, as follows:</span></span>  
  
1.  <span data-ttu-id="ca1c2-122">在“EDI 全局属性”对话框中，打开“UNH 段定义”页。</span><span class="sxs-lookup"><span data-stu-id="ca1c2-122">In the EDI Global Properties dialog box, open the UNH Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="ca1c2-123">单击与 UNH1 字段关联的“编辑”字段。</span><span class="sxs-lookup"><span data-stu-id="ca1c2-123">Click the Edit field associated with the UNH1 field.</span></span>  
  
3.  <span data-ttu-id="ca1c2-124">将组控制编号的中间字段（UNH1.2 中的参考编号）设置为新值，以便该字段具有可接受的位数。</span><span class="sxs-lookup"><span data-stu-id="ca1c2-124">Set the middle field of the group control number (the reference number in UNH1.2) to a new value such that the field has an acceptable number of digits.</span></span>