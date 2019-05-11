---
title: 可接受 Edifact 事务集控制编号已达到参与方的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a64cc5d3-a845-4044-9c6e-879ecda15fce
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58c2495b0e7eecf7c16ecdf067ed03d8e1a333d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347446"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-party"></a><span data-ttu-id="71ec5-102">可接受 Edifact 事务集控制编号的最大限制已达到参与方</span><span class="sxs-lookup"><span data-stu-id="71ec5-102">Max limit of acceptable Edifact transaction set control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="71ec5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="71ec5-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="71ec5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="71ec5-104">Product Name</span></span>   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                        |
| <span data-ttu-id="71ec5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="71ec5-105">Product Version</span></span> |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                    |
|    <span data-ttu-id="71ec5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="71ec5-106">Event ID</span></span>     |                                                                                                -                                                                                                 |
|  <span data-ttu-id="71ec5-107">事件源</span><span class="sxs-lookup"><span data-stu-id="71ec5-107">Event Source</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="71ec5-108">EDI</span><span class="sxs-lookup"><span data-stu-id="71ec5-108">EDI</span></span>                                                      |
|    <span data-ttu-id="71ec5-109">组件</span><span class="sxs-lookup"><span data-stu-id="71ec5-109">Component</span></span>    |                                                                                            <span data-ttu-id="71ec5-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="71ec5-110">EDI Engine</span></span>                                                                                            |
|  <span data-ttu-id="71ec5-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="71ec5-111">Symbolic Name</span></span>  |                                                                                   <span data-ttu-id="71ec5-112">GlobalEdifactUnhNumberError</span><span class="sxs-lookup"><span data-stu-id="71ec5-112">GlobalEdifactUnhNumberError</span></span>                                                                                    |
|  <span data-ttu-id="71ec5-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="71ec5-113">Message Text</span></span>   | <span data-ttu-id="71ec5-114">可接受 Edifact 事务集控制编号已达到参与方的最大限制{0}。</span><span class="sxs-lookup"><span data-stu-id="71ec5-114">Max limit of acceptable Edifact transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="71ec5-115">导航到参与方在接收方角色屏幕、 合作伙伴协议管理器中的字段 UNH 1 可重置计数器</span><span class="sxs-lookup"><span data-stu-id="71ec5-115">Reset counter by navigating to Party in receiver role screen, field UNH 1 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="71ec5-116">解释</span><span class="sxs-lookup"><span data-stu-id="71ec5-116">Explanation</span></span>  
 <span data-ttu-id="71ec5-117">此错误/警告/信息事件表明发送管道无法处理传出的交换，因为事务集控制编号在参与方设置中，特别是字段 UNH1.2 中的参考编号指定的 UNH1 字段中，已大于允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="71ec5-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the transaction set control number in the UNH1 field specified in the party settings, specifically the reference number in field UNH1.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="71ec5-118">事务集控制编号的最大值取决于 UNH1 中三个字段的值。</span><span class="sxs-lookup"><span data-stu-id="71ec5-118">The maximum allowable value for the transaction set control number depends upon the values of the three fields in UNH1.</span></span> <span data-ttu-id="71ec5-119">最大字符数是 14 个字段 UNH1.2，13 个 UNH1.1 中的前缀和 UNH1.3 中的后缀的 13 和 14 个所有三个字段的组合中的参考编号。</span><span class="sxs-lookup"><span data-stu-id="71ec5-119">The maximum number of characters is 14 for the reference number in field UNH1.2, 13 for the prefix in UNH1.1 and 13 for the suffix in UNH1.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="71ec5-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="71ec5-120">User Action</span></span>  
 <span data-ttu-id="71ec5-121">若要解决此错误，请按照如下方式重置事务集控制编号的参考编号字段 (UNH1.2)：</span><span class="sxs-lookup"><span data-stu-id="71ec5-121">To resolve this error, reset the reference number field (UNH1.2) of the transaction set control number, as follows:</span></span>  
  
1.  <span data-ttu-id="71ec5-122">在为交换解析的参与方的“EDI 属性”对话框中，打开“UNG 和 UNH 段定义”页。</span><span class="sxs-lookup"><span data-stu-id="71ec5-122">In the EDI Properties dialog box for the party resolved for the interchange, open the UNG and UNH Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="71ec5-123">单击与 UNH1 字段关联的“编辑”字段。</span><span class="sxs-lookup"><span data-stu-id="71ec5-123">Click the Edit field associated with the UNH1 field.</span></span>  
  
3.  <span data-ttu-id="71ec5-124">将事务集控制编号的中间字段（UNH1.2 中的参考编号）设置为新值，以便该字段具有可接受的位数。</span><span class="sxs-lookup"><span data-stu-id="71ec5-124">Set the middle field of the transaction set control number (the reference number in UNH1.2) to a new value such that the field has an acceptable number of digits.</span></span>