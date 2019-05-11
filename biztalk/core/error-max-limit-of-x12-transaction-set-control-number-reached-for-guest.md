---
title: 可接受 X12 事务集控制编号已达到来宾设置的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5a4aa5c-13a7-4234-916e-562b52644c51
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f35efea65a1ee4741c86679797f5f218a1cbaf0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347437"
---
# <a name="max-limit-of-acceptable-x12-transaction-set-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="9f05e-102">可接受 X12 事务集控制编号已达到来宾设置的最大限制</span><span class="sxs-lookup"><span data-stu-id="9f05e-102">Max limit of acceptable X12 transaction set control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="9f05e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9f05e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9f05e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9f05e-104">Product Name</span></span>   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| <span data-ttu-id="9f05e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="9f05e-105">Product Version</span></span> |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    <span data-ttu-id="9f05e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9f05e-106">Event ID</span></span>     |                                                                                                     -                                                                                                      |
|  <span data-ttu-id="9f05e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="9f05e-107">Event Source</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9f05e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="9f05e-108">EDI</span></span>                                                           |
|    <span data-ttu-id="9f05e-109">组件</span><span class="sxs-lookup"><span data-stu-id="9f05e-109">Component</span></span>    |                                                                                                 <span data-ttu-id="9f05e-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="9f05e-110">EDI Engine</span></span>                                                                                                 |
|  <span data-ttu-id="9f05e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="9f05e-111">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="9f05e-112">GlobalX12TsNumberError</span><span class="sxs-lookup"><span data-stu-id="9f05e-112">GlobalX12TsNumberError</span></span>                                                                                           |
|  <span data-ttu-id="9f05e-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="9f05e-113">Message Text</span></span>   | <span data-ttu-id="9f05e-114">可接受 X12 事务集控制编号已达到来宾设置的最大限制。</span><span class="sxs-lookup"><span data-stu-id="9f05e-114">Max limit of acceptable X12 transaction set control number has reached for Guest settings.</span></span> <span data-ttu-id="9f05e-115">导航到合作伙伴协议管理器的全局配置发送方角色屏幕中的字段 ST 2 可重置计数器</span><span class="sxs-lookup"><span data-stu-id="9f05e-115">Reset counter by navigating to Global configuration sender role screen, field ST 2 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9f05e-116">解释</span><span class="sxs-lookup"><span data-stu-id="9f05e-116">Explanation</span></span>  
 <span data-ttu-id="9f05e-117">此错误/警告/信息事件表明发送管道无法处理传出的 X12 交换，因为在全局设置中，特别是字段 ST02.2 中的参考编号指定的 ST02 字段中的事务集控制编号大于允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="9f05e-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the transaction set control number in the ST02 field specified in the global settings, specifically the reference number in field ST02.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="9f05e-118">所允许的事务集控制编号的最大值取决于 ST02 中三个字段的值。</span><span class="sxs-lookup"><span data-stu-id="9f05e-118">The maximum allowable value for the transaction set control number depends upon the values of the three fields in ST02.</span></span> <span data-ttu-id="9f05e-119">最大字符数是字段 UNH1.2，8 对于 UNH1.1 中的前缀和后缀中 UNH1.3，8 和 9 对于所有三个字段的组合中的参考编号的 9。</span><span class="sxs-lookup"><span data-stu-id="9f05e-119">The maximum number of characters is 9 for the reference number in field UNH1.2, 8 for the prefix in UNH1.1 and 8 for the suffix in UNH1.3, and 9 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9f05e-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="9f05e-120">User Action</span></span>  
 <span data-ttu-id="9f05e-121">若要解决此错误，请按如下所示重置事务集控制编号的参考编号字段 (ST02.2):</span><span class="sxs-lookup"><span data-stu-id="9f05e-121">To resolve this error, reset the reference number field (ST02.2) of the transaction set control number, as follows:</span></span>  
  
1.  <span data-ttu-id="9f05e-122">在“EDI 全局属性”对话框中，打开“GS 和 ST 段定义”页。</span><span class="sxs-lookup"><span data-stu-id="9f05e-122">In the EDI Global Properties dialog box, open the GS and ST Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="9f05e-123">单击与 ST02 字段关联的编辑字段。</span><span class="sxs-lookup"><span data-stu-id="9f05e-123">Click the Edit field associated with the ST02 field.</span></span>  
  
3.  <span data-ttu-id="9f05e-124">将组控制编号 （ST02.2 中的参考编号） 的中间字段设置为新值中，以便该字段具有可接受的位数。</span><span class="sxs-lookup"><span data-stu-id="9f05e-124">Set the middle field of the group control number (the reference number in ST02.2) to a new value such that the field has an acceptable number of digits.</span></span>