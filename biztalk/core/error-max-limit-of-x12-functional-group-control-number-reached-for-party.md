---
title: 可接受 X12 功能组控制编号已达到参与方的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a920a66c-1e38-4f4a-8113-cbad01940839
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 527f6709d48124f7ffcc0823bdc5ff84e92256ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978398"
---
# <a name="max-limit-of-acceptable-x12-functional-group-control-number-has-reached-for-party"></a><span data-ttu-id="e26f7-102">已达到参与方的可接受 X12 功能组控制编号最大限制</span><span class="sxs-lookup"><span data-stu-id="e26f7-102">Max limit of acceptable X12 functional group control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="e26f7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e26f7-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e26f7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e26f7-104">Product Name</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| <span data-ttu-id="e26f7-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e26f7-105">Product Version</span></span> |                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    <span data-ttu-id="e26f7-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e26f7-106">Event ID</span></span>     |                                                                                              -                                                                                               |
|  <span data-ttu-id="e26f7-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e26f7-107">Event Source</span></span>   |                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e26f7-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e26f7-108"> EDI</span></span>                                                    |
|    <span data-ttu-id="e26f7-109">组件</span><span class="sxs-lookup"><span data-stu-id="e26f7-109">Component</span></span>    |                                                                                          <span data-ttu-id="e26f7-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e26f7-110">EDI Engine</span></span>                                                                                          |
|  <span data-ttu-id="e26f7-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e26f7-111">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="e26f7-112">PartyX12GsNumberError</span><span class="sxs-lookup"><span data-stu-id="e26f7-112">PartyX12GsNumberError</span></span>                                                                                     |
|  <span data-ttu-id="e26f7-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="e26f7-113">Message Text</span></span>   | <span data-ttu-id="e26f7-114">可接受 X12 功能组控制编号已达到参与方的最大限制{0}。</span><span class="sxs-lookup"><span data-stu-id="e26f7-114">Max limit of acceptable X12 functional group control number has reached for party {0}.</span></span> <span data-ttu-id="e26f7-115">导航到接收方角色屏幕中的“参与方”、合作伙伴协议管理器中的字段 GS 6 可重置计数器</span><span class="sxs-lookup"><span data-stu-id="e26f7-115">Reset counter by navigating to Party in receiver role screen, field GS 6 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e26f7-116">解释</span><span class="sxs-lookup"><span data-stu-id="e26f7-116">Explanation</span></span>  
 <span data-ttu-id="e26f7-117">此错误/警告/信息事件表明发送管道无法处理传出的 X12 交换，因为在参与方设置中指定的 GS06 字段中的组控制编号大于所允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="e26f7-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the group control number in the GS06 field specified in the party settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="e26f7-118">组控制编号的最大字符数为 9。</span><span class="sxs-lookup"><span data-stu-id="e26f7-118">The maximum number of characters for the group control number is 9.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e26f7-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="e26f7-119">User Action</span></span>  
 <span data-ttu-id="e26f7-120">若要解决此错误，请按照如下方式重置组控制编号：</span><span class="sxs-lookup"><span data-stu-id="e26f7-120">To resolve this error, reset the group control number, as follows:</span></span>  
  
1.  <span data-ttu-id="e26f7-121">在用于参与方解决交换的“EDI 属性”对话框中，打开“作为交换接收方的参与方”的“GS 和 ST 段定义”页。</span><span class="sxs-lookup"><span data-stu-id="e26f7-121">In the EDI Properties dialog box for the party resolved for the interchange, open the GS and ST Segment Definition page for the party as interchange receiver.</span></span>  
  
2.  <span data-ttu-id="e26f7-122">单击与 GS06 字段关联的“编辑”字段。</span><span class="sxs-lookup"><span data-stu-id="e26f7-122">Click the Edit field associated with the GS06 field.</span></span>  
  
3.  <span data-ttu-id="e26f7-123">将组控制编号设置为一个新值，以便该字段具有 9 个或更少的数字。</span><span class="sxs-lookup"><span data-stu-id="e26f7-123">Set the group control number to a new value such that the field has nine or fewer digits.</span></span>