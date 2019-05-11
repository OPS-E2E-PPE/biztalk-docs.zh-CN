---
title: 支持具有前导零金额字段验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- amounts, amount fields
- amounts, leading zeros
- validating, amount fields
ms.assetid: 7c202422-019f-43da-9c2a-4b9fdf0b2859
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e68cb3f776fd177bfaf437c6ae84b3e1da36f084
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529798"
---
# <a name="supporting-leading-zeros-in-amount-field-validations"></a><span data-ttu-id="28c2a-102">支持具有前导零金额字段验证</span><span class="sxs-lookup"><span data-stu-id="28c2a-102">Supporting Leading Zeros in Amount Field Validations</span></span>
<span data-ttu-id="28c2a-103">某些消息类型的验证策略在金额字段上执行验证。</span><span class="sxs-lookup"><span data-stu-id="28c2a-103">The validation policies of some message types perform validations on Amount fields.</span></span> <span data-ttu-id="28c2a-104">若要启用在金额字段中的前导零，必须编辑消息类型的验证策略。</span><span class="sxs-lookup"><span data-stu-id="28c2a-104">To enable leading zeros in Amount fields, you must edit the validation policy for the message type.</span></span> <span data-ttu-id="28c2a-105">可以创建新版本的默认验证策略和编辑业务规则编辑器中的参数或部署该策略之前，可以编辑在文本编辑器中手动的默认策略。</span><span class="sxs-lookup"><span data-stu-id="28c2a-105">You can create a new version of the default validation policy, and edit the argument in the Business Rule Composer, or you can edit the default policy manually in a text editor before the policy is deployed.</span></span>  
  
 <span data-ttu-id="28c2a-106">下表列出了启用或禁用前导零的方法。</span><span class="sxs-lookup"><span data-stu-id="28c2a-106">The following table lists the methods that enable or disable leading zeros.</span></span> <span data-ttu-id="28c2a-107">此表还指示您需要在方法中设置的参数的序号。</span><span class="sxs-lookup"><span data-stu-id="28c2a-107">The table also indicates the ordinal number of the argument that you need to set in the method.</span></span> <span data-ttu-id="28c2a-108">将其设置为 true 以启用前导零，或为 False 可禁用它们。</span><span class="sxs-lookup"><span data-stu-id="28c2a-108">Set it to True to enable leading zeros, or to False to disable them.</span></span>  
  
|<span data-ttu-id="28c2a-109">方法</span><span class="sxs-lookup"><span data-stu-id="28c2a-109">Method</span></span>|<span data-ttu-id="28c2a-110">参数号</span><span class="sxs-lookup"><span data-stu-id="28c2a-110">Argument number</span></span>|  
|------------|---------------------|  
|<span data-ttu-id="28c2a-111">**CheckValidAmount**</span><span class="sxs-lookup"><span data-stu-id="28c2a-111">**CheckValidAmount**</span></span>|<span data-ttu-id="28c2a-112">6</span><span class="sxs-lookup"><span data-stu-id="28c2a-112">6</span></span>|  
|<span data-ttu-id="28c2a-113">**CheckCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="28c2a-113">**CheckCurrencyAmount**</span></span>|<span data-ttu-id="28c2a-114">4</span><span class="sxs-lookup"><span data-stu-id="28c2a-114">4</span></span>|  
|<span data-ttu-id="28c2a-115">**CheckValidSignCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="28c2a-115">**CheckValidSignCurrencyAmount**</span></span>|<span data-ttu-id="28c2a-116">3</span><span class="sxs-lookup"><span data-stu-id="28c2a-116">3</span></span>|  
|<span data-ttu-id="28c2a-117">**CheckValidSignDateCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="28c2a-117">**CheckValidSignDateCurrencyAmount**</span></span>|<span data-ttu-id="28c2a-118">4</span><span class="sxs-lookup"><span data-stu-id="28c2a-118">4</span></span>|  
|<span data-ttu-id="28c2a-119">**IsValidTransactionDetailsCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="28c2a-119">**IsValidTransactionDetailsCurrencyAmount**</span></span>|<span data-ttu-id="28c2a-120">4</span><span class="sxs-lookup"><span data-stu-id="28c2a-120">4</span></span>|  
  
 <span data-ttu-id="28c2a-121">上表中的每个方法都包含在一个或多个消息验证策略。</span><span class="sxs-lookup"><span data-stu-id="28c2a-121">Each method in the preceding table is contained in one or more message validation policies.</span></span> <span data-ttu-id="28c2a-122">若要在策略中设置参数，必须搜索要验证的策略是否包含它的方法名称。</span><span class="sxs-lookup"><span data-stu-id="28c2a-122">To set the argument in a policy, you must search on the method name to verify whether the policy contains it.</span></span> <span data-ttu-id="28c2a-123">一种方法可能会多次出现一条消息的策略中。</span><span class="sxs-lookup"><span data-stu-id="28c2a-123">A method may appear multiple times in a message's policy.</span></span>  
  
### <a name="to-enable-or-disable-leading-zeros"></a><span data-ttu-id="28c2a-124">若要启用或禁用前导零</span><span class="sxs-lookup"><span data-stu-id="28c2a-124">To enable or disable leading zeros</span></span>  
  
1.  <span data-ttu-id="28c2a-125">打开文本编辑器，如记事本。</span><span class="sxs-lookup"><span data-stu-id="28c2a-125">Open a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="28c2a-126">在编辑器中，浏览到想要启用或禁用前导零的消息验证策略的位置。</span><span class="sxs-lookup"><span data-stu-id="28c2a-126">In the editor, browse to the location of the message validation policy in which you want to enable or disable leading zeros.</span></span> <span data-ttu-id="28c2a-127">例如，您可以找到消息验证策略对于 MT103 消息类型，MT103_Validation_Policy.xml，在*\<驱动器\>*: / Program Files/Microsoft BizTalk Accelerator for SWIFT/SWIFT 消息/ 类别 1/MT103。</span><span class="sxs-lookup"><span data-stu-id="28c2a-127">For example, you can find the message validation policy for the MT103 message type, MT103_Validation_Policy.xml, in *\<drive\>*:/Program Files/Microsoft BizTalk Accelerator for SWIFT/SWIFT Messages/Category 1/MT103.</span></span> <span data-ttu-id="28c2a-128">打开验证策略。</span><span class="sxs-lookup"><span data-stu-id="28c2a-128">Open the validation policy.</span></span>  
  
3.  <span data-ttu-id="28c2a-129">在策略中，搜索**CheckValidAmount**方法。</span><span class="sxs-lookup"><span data-stu-id="28c2a-129">In the policy, search on the **CheckValidAmount** method.</span></span>  
  
4.  <span data-ttu-id="28c2a-130">如果找到该方法，倒计时到相应的自变量。</span><span class="sxs-lookup"><span data-stu-id="28c2a-130">If you find the method, count down to the appropriate argument.</span></span> <span data-ttu-id="28c2a-131">例如，对于**CheckValidAmount**方法，向第六个参数的计数。</span><span class="sxs-lookup"><span data-stu-id="28c2a-131">For example, for the **CheckValidAmount** method, count down to the sixth argument.</span></span> <span data-ttu-id="28c2a-132">将参数设置为 **，则返回 True**启用前导零或为 False，则禁用它们。</span><span class="sxs-lookup"><span data-stu-id="28c2a-132">Set the argument to **True** to enable leading zeros or False to disable them.</span></span>  
  
5.  <span data-ttu-id="28c2a-133">对于上表中每个方法重复步骤 3 和 4。</span><span class="sxs-lookup"><span data-stu-id="28c2a-133">Repeat steps 3 and 4 for each method in the preceding table.</span></span>  
  
6.  <span data-ttu-id="28c2a-134">保存该文件，然后关闭编辑器。</span><span class="sxs-lookup"><span data-stu-id="28c2a-134">Save the file, and then close the editor.</span></span>