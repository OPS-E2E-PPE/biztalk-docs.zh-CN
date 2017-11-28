---
title: "可接受的 X12 交换控制编号已达到来宾设置的最大限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9737053d-6065-4c88-8dfa-5f69b48e0e82
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c72fc565367477d9dbd09f3c0d4c4f9d6ab686a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="c394b-102">可接受的 X12 交换控制编号已达到来宾设置的最大限制</span><span class="sxs-lookup"><span data-stu-id="c394b-102">Max limit of acceptable X12 interchange control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="c394b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c394b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c394b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c394b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c394b-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c394b-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c394b-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c394b-106">Event ID</span></span>|-|  
|<span data-ttu-id="c394b-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c394b-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c394b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c394b-108"> EDI</span></span>|  
|<span data-ttu-id="c394b-109">组件</span><span class="sxs-lookup"><span data-stu-id="c394b-109">Component</span></span>|<span data-ttu-id="c394b-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c394b-110">EDI Engine</span></span>|  
|<span data-ttu-id="c394b-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c394b-111">Symbolic Name</span></span>|<span data-ttu-id="c394b-112">GlobalX12IsaNumberError</span><span class="sxs-lookup"><span data-stu-id="c394b-112">GlobalX12IsaNumberError</span></span>|  
|<span data-ttu-id="c394b-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c394b-113">Message Text</span></span>|<span data-ttu-id="c394b-114">已达到“来宾”设置的可接受 X12 交换控制编号最大限制。</span><span class="sxs-lookup"><span data-stu-id="c394b-114">Max limit of acceptable X12 interchange control number has reached for Guest settings.</span></span> <span data-ttu-id="c394b-115">导航到“全局”配置接收方角色屏幕、合作伙伴协议管理器中的字段 ISA 13 可重置计数器</span><span class="sxs-lookup"><span data-stu-id="c394b-115">Reset counter by navigating to Global configuration receiver role screen, field ISA 13 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c394b-116">解释</span><span class="sxs-lookup"><span data-stu-id="c394b-116">Explanation</span></span>  
 <span data-ttu-id="c394b-117">此错误/警告/信息事件表明发送管道无法处理传出的 X12 交换，因为在全局设置中指定的 ISA13 字段中的交换控制编号大于所允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="c394b-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the interchange control number in the ISA13 field specified in the global settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="c394b-118">交换控制编号的最大字符数为 9。</span><span class="sxs-lookup"><span data-stu-id="c394b-118">The maximum number of characters for the interchange control number is nine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c394b-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="c394b-119">User Action</span></span>  
 <span data-ttu-id="c394b-120">若要解决此错误，请按照如下方式重置交换控制编号：</span><span class="sxs-lookup"><span data-stu-id="c394b-120">To resolve this error, reset the interchange control number, as follows:</span></span>  
  
1.  <span data-ttu-id="c394b-121">在“EDI 全局属性”对话框中，打开“ISA 段定义”页。</span><span class="sxs-lookup"><span data-stu-id="c394b-121">In the EDI Global Properties dialog box, open the ISA Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="c394b-122">单击与 ISA13 字段关联的“编辑”字段。</span><span class="sxs-lookup"><span data-stu-id="c394b-122">Click the Edit field associated with the ISA13 field.</span></span>  
  
3.  <span data-ttu-id="c394b-123">将交换控制编号设置为一个新值，以便该字段具有可接受的位数。</span><span class="sxs-lookup"><span data-stu-id="c394b-123">Set the interchange control number to a new value such that the field has an acceptable number of digits.</span></span>