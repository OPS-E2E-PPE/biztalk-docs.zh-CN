---
title: "确认生成已失败，因为已达到最大限制为 Edifact 事务集控制编号方设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcbb6374-0403-42b0-892b-b35157a2c74a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1879d55de163615d5a4fab19cd50839e7ab2b17f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgement-generation-has-failed-as-maximum-limit-of-edifact-transaction-set-control-number-has-been-reached-for-party-settings"></a><span data-ttu-id="25a76-102">确认生成失败，因为已达到参与方设置的 EDIFACT 事务集控制编号的上限</span><span class="sxs-lookup"><span data-stu-id="25a76-102">Acknowledgement generation has failed as maximum limit of Edifact transaction set control number has been reached for party settings</span></span>
## <a name="details"></a><span data-ttu-id="25a76-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="25a76-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25a76-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="25a76-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="25a76-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="25a76-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="25a76-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="25a76-106">Event ID</span></span>|-|  
|<span data-ttu-id="25a76-107">事件源</span><span class="sxs-lookup"><span data-stu-id="25a76-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="25a76-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="25a76-108"> EDI</span></span>|  
|<span data-ttu-id="25a76-109">组件</span><span class="sxs-lookup"><span data-stu-id="25a76-109">Component</span></span>|<span data-ttu-id="25a76-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="25a76-110">EDI Engine</span></span>|  
|<span data-ttu-id="25a76-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="25a76-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="25a76-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="25a76-112">Message Text</span></span>|<span data-ttu-id="25a76-113">确认生成已失败，因为可接受的 Edifact 事务集控制编号为方 {0} 已达到最大限制。</span><span class="sxs-lookup"><span data-stu-id="25a76-113">Acknowledgement generation has failed as max limit of acceptable Edifact transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="25a76-114">通过在发件人角色屏幕中，字段新罕布什尔大学 1 合作伙伴协议管理器中导航到方重置计数器。</span><span class="sxs-lookup"><span data-stu-id="25a76-114">Reset counter by navigating to Party in sender role screen, field UNH 1 in Partner Agreement manager.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="25a76-115">解释</span><span class="sxs-lookup"><span data-stu-id="25a76-115">Explanation</span></span>  
 <span data-ttu-id="25a76-116">此错误/警告/信息事件表明 BizTalk Server 无法生成对 EDIFACT 交换的确认，因为在确认的事务集参考编号 (UNH1) 中输入的控制编号大于 UNH1 所允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="25a76-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an acknowledgment to the EDIFACT interchange because the control number that it entered in the Transaction set reference number (UNH1) of the acknowledgment is greater than the maximum value allowed for UNH1.</span></span> <span data-ttu-id="25a76-117">在这种情况下，BizTalk Server 使用 EDI 参与方属性来创建确认。</span><span class="sxs-lookup"><span data-stu-id="25a76-117">In this instance, BizTalk Server used the EDI party properties to create the acknowledgment.</span></span>  
  
 <span data-ttu-id="25a76-118">事务集参考编号的最大值取决于用于参考编号的位数。</span><span class="sxs-lookup"><span data-stu-id="25a76-118">The maximum value of the transaction set reference number depends upon the number of digits used for the reference number.</span></span> <span data-ttu-id="25a76-119">参考编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。</span><span class="sxs-lookup"><span data-stu-id="25a76-119">The maximum number of characters is 14 for the reference number, 13 for the prefix and suffix, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25a76-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="25a76-120">User Action</span></span>  
 <span data-ttu-id="25a76-121">若要解决此错误，请将“UNG 和 UNH 段定义”页的事务集参考编号 (UNH1) 的参考编号字段 (UNH1.2) 重置为低于最大限制的值。</span><span class="sxs-lookup"><span data-stu-id="25a76-121">To resolve this error, reset the reference number field (UNH1.2) of the Transaction set reference number (UNH1) in the UNG and UNH Segment Definition Page to a value that is lower than the maximum limit.</span></span> <span data-ttu-id="25a76-122">在 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 管理控制台的“EDI 属性”对话框中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="25a76-122">Set this property in the EDI Properties dialog box in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Administration Console.</span></span>