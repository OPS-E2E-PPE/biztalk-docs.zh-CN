---
title: 为金额验证设置偏移量 |Microsoft Docs
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
ms.openlocfilehash: b194445499f2506b1dcb8309cb20f4aa17e6ca83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377046"
---
# <a name="setting-offsets-for-amount-validation"></a><span data-ttu-id="946b7-102">为金额验证设置偏移量</span><span class="sxs-lookup"><span data-stu-id="946b7-102">Setting Offsets for Amount Validation</span></span>
<span data-ttu-id="946b7-103">使用规则的消息类型 MT102，MT103 和 MT103PLUS 金额字段由其各自的验证策略中的规则进行验证。</span><span class="sxs-lookup"><span data-stu-id="946b7-103">The usage rules for Amount fields in message types MT102, MT103, and MT103PLUS are validated by rules in their respective validation policies.</span></span> <span data-ttu-id="946b7-104">金额字段可以精确匹配或可以对其进行验证，以在的金额范围内。</span><span class="sxs-lookup"><span data-stu-id="946b7-104">The Amount fields can be matched exactly or can be validated to be within a range of amounts.</span></span>  
  
 <span data-ttu-id="946b7-105">若要启用的范围内的验证，请相关验证策略中的方法调用中指定偏移量的百分比。</span><span class="sxs-lookup"><span data-stu-id="946b7-105">To enable validation within a range, you specify an offset percentage in the method call in the relevant validation policy.</span></span> <span data-ttu-id="946b7-106">例如，如果为字段设置量为 100，且偏移量的百分比为 10%，有效金额将从 90 到为 110 时，非独占的任何值。</span><span class="sxs-lookup"><span data-stu-id="946b7-106">For example, if the amount that you set for the field is 100, and the offset percentage is 10 percent, a valid amount would be any value from 90 to 110, inclusive.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="946b7-107">为 MT102、 MT102PLUS 和 MT103 消息类型提供此支持。</span><span class="sxs-lookup"><span data-stu-id="946b7-107">provides this support for the MT102, MT102PLUS, and MT103 message types.</span></span>  
  
 <span data-ttu-id="946b7-108">中指定的偏移量的百分比**IsValidSettlementAmount**或**IsValidInterbankSettledAmount**中验证策略的方法。</span><span class="sxs-lookup"><span data-stu-id="946b7-108">The offset percentage is specified in either the **IsValidSettlementAmount** or **IsValidInterbankSettledAmount** method in the validation policy.</span></span> <span data-ttu-id="946b7-109">**IsValidSettlementAmount**方法实现 MT102 和 MT102PLUS 消息量字段的用法规则。</span><span class="sxs-lookup"><span data-stu-id="946b7-109">The **IsValidSettlementAmount** method implements the usage rule for Amount fields of MT102 and MT102PLUS messages.</span></span> <span data-ttu-id="946b7-110">**IsValidInterbankSettledAmount**方法实现的 MT103 消息量字段的用法规则。</span><span class="sxs-lookup"><span data-stu-id="946b7-110">The **IsValidInterbankSettledAmount** method implements the usage rule for Amount fields of MT103 messages.</span></span> <span data-ttu-id="946b7-111">OffsetPercent 参数，该变量的任一这些方法的第十个参数中指定的偏移量的百分比。</span><span class="sxs-lookup"><span data-stu-id="946b7-111">You specify the offset percentage in the OffsetPercent argument, which is the tenth argument of either of those methods.</span></span>  
  
 <span data-ttu-id="946b7-112">百分比偏移量设置时，适用于以下字段：</span><span class="sxs-lookup"><span data-stu-id="946b7-112">When set, the percentage offset applies to the following fields:</span></span>  
  
|<span data-ttu-id="946b7-113">消息类型</span><span class="sxs-lookup"><span data-stu-id="946b7-113">Message type</span></span>|<span data-ttu-id="946b7-114">字段的偏移量与验证</span><span class="sxs-lookup"><span data-stu-id="946b7-114">Fields validated with offsets</span></span>|  
|------------------|-----------------------------------|  
|<span data-ttu-id="946b7-115">MT102 或 MT102PLUS</span><span class="sxs-lookup"><span data-stu-id="946b7-115">MT102 or MT102PLUS</span></span>|<span data-ttu-id="946b7-116">32</span><span class="sxs-lookup"><span data-stu-id="946b7-116">32</span></span><br /><br /> <span data-ttu-id="946b7-117">33B</span><span class="sxs-lookup"><span data-stu-id="946b7-117">33B</span></span>|  
|<span data-ttu-id="946b7-118">MT103</span><span class="sxs-lookup"><span data-stu-id="946b7-118">MT103</span></span>|<span data-ttu-id="946b7-119">19，序列 C</span><span class="sxs-lookup"><span data-stu-id="946b7-119">19, Sequence C</span></span><br /><br /> <span data-ttu-id="946b7-120">31A，序列 C</span><span class="sxs-lookup"><span data-stu-id="946b7-120">31A, Sequence C</span></span><br /><br /> <span data-ttu-id="946b7-121">72G</span><span class="sxs-lookup"><span data-stu-id="946b7-121">72G</span></span>|  
  
### <a name="to-set-an-offset-percentage"></a><span data-ttu-id="946b7-122">若要设置偏移量的百分比</span><span class="sxs-lookup"><span data-stu-id="946b7-122">To set an offset percentage</span></span>  
  
1.  <span data-ttu-id="946b7-123">打开文本编辑器，如记事本。</span><span class="sxs-lookup"><span data-stu-id="946b7-123">Open a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="946b7-124">在编辑器中，浏览到想要设置偏移量的百分比的消息验证策略的位置。</span><span class="sxs-lookup"><span data-stu-id="946b7-124">In the editor, browse to the location of the message validation policy in which you want to set an offset percentage.</span></span> <span data-ttu-id="946b7-125">例如，您可以找到消息验证策略对于 MT103 消息类型，MT103_Validation_Policy.xml，在*\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT \<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MT103。</span><span class="sxs-lookup"><span data-stu-id="946b7-125">For example, you can find the message validation policy for the MT103 message type, MT103_Validation_Policy.xml, in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MT103.</span></span> <span data-ttu-id="946b7-126">打开验证策略。</span><span class="sxs-lookup"><span data-stu-id="946b7-126">Open the validation policy.</span></span>  
  
3.  <span data-ttu-id="946b7-127">在策略中，搜索 IsValidSettlementAmount MT102 和 MT102PLUS 消息或 IsValidInterbankSettledAmount 的 MT103 消息。</span><span class="sxs-lookup"><span data-stu-id="946b7-127">In the policy, search on IsValidSettlementAmount for MT102 and MT102PLUS messages or IsValidInterbankSettledAmount for MT103 messages.</span></span>  
  
4.  <span data-ttu-id="946b7-128">倒计数到第十个参数。</span><span class="sxs-lookup"><span data-stu-id="946b7-128">Count down to the tenth argument.</span></span> <span data-ttu-id="946b7-129">参数中输入偏移量的百分比。</span><span class="sxs-lookup"><span data-stu-id="946b7-129">Enter the percentage of the offset in the argument.</span></span>  
  
5.  <span data-ttu-id="946b7-130">保存该文件，然后关闭编辑器。</span><span class="sxs-lookup"><span data-stu-id="946b7-130">Save the file, and then close the editor.</span></span>