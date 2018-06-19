---
title: 设置量验证偏移量 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- amounts, validating
- validating, amounts
- amounts, offsets
- offsets
ms.assetid: 39d5510c-52e6-4fd9-9632-582b508f04d7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cfae474407daa7dd3c0b95db3fed076a581cf1c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961251"
---
# <a name="setting-offsets-for-amount-validation"></a><span data-ttu-id="af80c-102">设置量验证偏移量</span><span class="sxs-lookup"><span data-stu-id="af80c-102">Setting Offsets for Amount Validation</span></span>
<span data-ttu-id="af80c-103">通过其各自的验证策略中的规则进行验证的消息类型 MT102，MT103 和 MT103PLUS 量字段使用规则。</span><span class="sxs-lookup"><span data-stu-id="af80c-103">The usage rules for Amount fields in message types MT102, MT103, and MT103PLUS are validated by rules in their respective validation policies.</span></span> <span data-ttu-id="af80c-104">量字段可以完全匹配，或可以验证为金额的范围之内。</span><span class="sxs-lookup"><span data-stu-id="af80c-104">The Amount fields can be matched exactly or can be validated to be within a range of amounts.</span></span>  
  
 <span data-ttu-id="af80c-105">若要启用的范围内的验证，可以在相关验证策略中的方法调用中指定偏移量的百分比。</span><span class="sxs-lookup"><span data-stu-id="af80c-105">To enable validation within a range, you specify an offset percentage in the method call in the relevant validation policy.</span></span> <span data-ttu-id="af80c-106">例如，如果量为字段设置为 100，且偏移量的百分比为 10%，有效金额将从 90 为 110，包括任何值。</span><span class="sxs-lookup"><span data-stu-id="af80c-106">For example, if the amount that you set for the field is 100, and the offset percentage is 10 percent, a valid amount would be any value from 90 to 110, inclusive.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="af80c-107">为 MT102、 MT102PLUS 和 MT103 消息类型提供此支持。</span><span class="sxs-lookup"><span data-stu-id="af80c-107"> provides this support for the MT102, MT102PLUS, and MT103 message types.</span></span>  
  
 <span data-ttu-id="af80c-108">中指定的偏移量的百分比**IsValidSettlementAmount**或**IsValidInterbankSettledAmount**验证策略中的方法。</span><span class="sxs-lookup"><span data-stu-id="af80c-108">The offset percentage is specified in either the **IsValidSettlementAmount** or **IsValidInterbankSettledAmount** method in the validation policy.</span></span> <span data-ttu-id="af80c-109">**IsValidSettlementAmount**方法实现 MT102 和 MT102PLUS 消息量字段的用法规则。</span><span class="sxs-lookup"><span data-stu-id="af80c-109">The **IsValidSettlementAmount** method implements the usage rule for Amount fields of MT102 and MT102PLUS messages.</span></span> <span data-ttu-id="af80c-110">**IsValidInterbankSettledAmount**方法实现的 MT103 消息量字段的用法规则。</span><span class="sxs-lookup"><span data-stu-id="af80c-110">The **IsValidInterbankSettledAmount** method implements the usage rule for Amount fields of MT103 messages.</span></span> <span data-ttu-id="af80c-111">OffsetPercent 参数，即任一这些方法的第 10 个自变量中指定的偏移量的百分比。</span><span class="sxs-lookup"><span data-stu-id="af80c-111">You specify the offset percentage in the OffsetPercent argument, which is the tenth argument of either of those methods.</span></span>  
  
 <span data-ttu-id="af80c-112">百分比偏移量设置时，适用于以下字段：</span><span class="sxs-lookup"><span data-stu-id="af80c-112">When set, the percentage offset applies to the following fields:</span></span>  
  
|<span data-ttu-id="af80c-113">消息类型</span><span class="sxs-lookup"><span data-stu-id="af80c-113">Message type</span></span>|<span data-ttu-id="af80c-114">字段验证偏移量</span><span class="sxs-lookup"><span data-stu-id="af80c-114">Fields validated with offsets</span></span>|  
|------------------|-----------------------------------|  
|<span data-ttu-id="af80c-115">MT102 或 MT102PLUS</span><span class="sxs-lookup"><span data-stu-id="af80c-115">MT102 or MT102PLUS</span></span>|<span data-ttu-id="af80c-116">32</span><span class="sxs-lookup"><span data-stu-id="af80c-116">32</span></span><br /><br /> <span data-ttu-id="af80c-117">33B</span><span class="sxs-lookup"><span data-stu-id="af80c-117">33B</span></span>|  
|<span data-ttu-id="af80c-118">MT103</span><span class="sxs-lookup"><span data-stu-id="af80c-118">MT103</span></span>|<span data-ttu-id="af80c-119">19，序列 C</span><span class="sxs-lookup"><span data-stu-id="af80c-119">19, Sequence C</span></span><br /><br /> <span data-ttu-id="af80c-120">31A，序列 C</span><span class="sxs-lookup"><span data-stu-id="af80c-120">31A, Sequence C</span></span><br /><br /> <span data-ttu-id="af80c-121">72 G</span><span class="sxs-lookup"><span data-stu-id="af80c-121">72G</span></span>|  
  
### <a name="to-set-an-offset-percentage"></a><span data-ttu-id="af80c-122">若要设置偏移量的百分比</span><span class="sxs-lookup"><span data-stu-id="af80c-122">To set an offset percentage</span></span>  
  
1.  <span data-ttu-id="af80c-123">打开文本编辑器，例如记事本。</span><span class="sxs-lookup"><span data-stu-id="af80c-123">Open a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="af80c-124">在编辑器中，浏览到你要在其中设置偏移量的百分比的消息验证策略的位置。</span><span class="sxs-lookup"><span data-stu-id="af80c-124">In the editor, browse to the location of the message validation policy in which you want to set an offset percentage.</span></span> <span data-ttu-id="af80c-125">例如，你可以找到消息验证策略对于 MT103 消息类型，MT103_Validation_Policy.xml，在*\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT \<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MT103。</span><span class="sxs-lookup"><span data-stu-id="af80c-125">For example, you can find the message validation policy for the MT103 message type, MT103_Validation_Policy.xml, in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MT103.</span></span> <span data-ttu-id="af80c-126">打开验证策略。</span><span class="sxs-lookup"><span data-stu-id="af80c-126">Open the validation policy.</span></span>  
  
3.  <span data-ttu-id="af80c-127">在策略中，搜索上 IsValidSettlementAmount MT102 和 MT102PLUS 消息或 IsValidInterbankSettledAmount MT103 消息。</span><span class="sxs-lookup"><span data-stu-id="af80c-127">In the policy, search on IsValidSettlementAmount for MT102 and MT102PLUS messages or IsValidInterbankSettledAmount for MT103 messages.</span></span>  
  
4.  <span data-ttu-id="af80c-128">倒计时到第 10 个自变量。</span><span class="sxs-lookup"><span data-stu-id="af80c-128">Count down to the tenth argument.</span></span> <span data-ttu-id="af80c-129">参数中输入的偏移量的百分比。</span><span class="sxs-lookup"><span data-stu-id="af80c-129">Enter the percentage of the offset in the argument.</span></span>  
  
5.  <span data-ttu-id="af80c-130">保存该文件，，然后关闭编辑器。</span><span class="sxs-lookup"><span data-stu-id="af80c-130">Save the file, and then close the editor.</span></span>