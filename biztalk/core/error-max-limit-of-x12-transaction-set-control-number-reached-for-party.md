---
title: 可接受 X12 事务集控制编号已达到参与方的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a402f6d0-4399-47c9-a39a-56d7fa1efa86
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76aade02065fbfb001bf1a02ceea26f0901854f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388659"
---
# <a name="max-limit-of-acceptable-x12-transaction-set-control-number-has-reached-for-party"></a><span data-ttu-id="12f92-102">可接受 X12 事务集控制编号已达到参与方的最大限制</span><span class="sxs-lookup"><span data-stu-id="12f92-102">Max limit of acceptable X12 transaction set control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="12f92-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="12f92-103">Details</span></span>  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="12f92-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="12f92-104">Product Name</span></span>   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| <span data-ttu-id="12f92-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="12f92-105">Product Version</span></span> |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    <span data-ttu-id="12f92-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="12f92-106">Event ID</span></span>     |                                                                                              -                                                                                              |
|  <span data-ttu-id="12f92-107">事件源</span><span class="sxs-lookup"><span data-stu-id="12f92-107">Event Source</span></span>   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="12f92-108">EDI</span><span class="sxs-lookup"><span data-stu-id="12f92-108">EDI</span></span>                                                    |
|    <span data-ttu-id="12f92-109">组件</span><span class="sxs-lookup"><span data-stu-id="12f92-109">Component</span></span>    |                                                                                         <span data-ttu-id="12f92-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="12f92-110">EDI Engine</span></span>                                                                                          |
|  <span data-ttu-id="12f92-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="12f92-111">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="12f92-112">PartyX12TsNumberError</span><span class="sxs-lookup"><span data-stu-id="12f92-112">PartyX12TsNumberError</span></span>                                                                                    |
|  <span data-ttu-id="12f92-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="12f92-113">Message Text</span></span>   | <span data-ttu-id="12f92-114">可接受 X12 事务集控制编号已达到参与方的最大限制{0}。</span><span class="sxs-lookup"><span data-stu-id="12f92-114">Max limit of acceptable X12 transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="12f92-115">导航到合作伙伴协议管理器的接收方角色屏幕中“参与方”中的字段 ST 2 可重置计数器</span><span class="sxs-lookup"><span data-stu-id="12f92-115">Reset counter by navigating to Party in receiver role screen, field ST 2 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="12f92-116">解释</span><span class="sxs-lookup"><span data-stu-id="12f92-116">Explanation</span></span>  
 <span data-ttu-id="12f92-117">此错误/警告/信息事件表明发送管道无法处理传出的 X12 交换，因为在参与方设置中指定的 ST02 字段中的事务集控制编号（具体来说就是字段 ST02.2 中的参考编号）大于所允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="12f92-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the transaction set control number in the ST02 field specified in the party settings, specifically the reference number in field ST02.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="12f92-118">所允许的事务集控制编号的最大值取决于 ST02 中三个字段的值。</span><span class="sxs-lookup"><span data-stu-id="12f92-118">The maximum allowable value for the transaction set control number depends upon the values of the three fields in ST02.</span></span> <span data-ttu-id="12f92-119">最大字符数分别是 9（对于字段 ST02.2 中的参考编号）、8（对于 ST02.1 中的前缀）、8（对于 ST02.3 中的后缀）以及 9（对于所有三个字段的组合）。</span><span class="sxs-lookup"><span data-stu-id="12f92-119">The maximum number of characters is 9 for the reference number in field ST02.2, 8 for the prefix in ST02.1 and 8 for the suffix in ST02.3, and 9 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="12f92-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="12f92-120">User Action</span></span>  
 <span data-ttu-id="12f92-121">若要解决此错误，请按照如下方式重置事务集控制编号的参考编号字段 (UNH1.2)：</span><span class="sxs-lookup"><span data-stu-id="12f92-121">To resolve this error, reset the reference number field (UNH1.2) of the transaction set control number, as follows:</span></span>  
  
1.  <span data-ttu-id="12f92-122">在为交换解析的参与方的“EDI 属性”对话框中，打开“UNG 和 UNH 段定义”页。</span><span class="sxs-lookup"><span data-stu-id="12f92-122">In the EDI Properties dialog box for the party resolved for the interchange, open the UNG and UNH Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="12f92-123">单击与 UNH1 字段关联的“编辑”字段。</span><span class="sxs-lookup"><span data-stu-id="12f92-123">Click the Edit field associated with the UNH1 field.</span></span>  
  
3.  <span data-ttu-id="12f92-124">将事务集控制编号的中间字段（UNH1.2 中的参考编号）设置为新值，以便该字段具有可接受的位数。</span><span class="sxs-lookup"><span data-stu-id="12f92-124">Set the middle field of the transaction set control number (the reference number in UNH1.2) to a new value such that the field has an acceptable number of digits.</span></span>