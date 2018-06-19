---
title: 支持前导零量字段验证中的 |Microsoft 文档
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
ms.openlocfilehash: 3559b63ec7588fa2d7451779947a476cf19b7bf0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961363"
---
# <a name="supporting-leading-zeros-in-amount-field-validations"></a><span data-ttu-id="bf2f1-102">支持前导零量字段验证中</span><span class="sxs-lookup"><span data-stu-id="bf2f1-102">Supporting Leading Zeros in Amount Field Validations</span></span>
<span data-ttu-id="bf2f1-103">某些消息类型的验证策略对量字段进行验证。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-103">The validation policies of some message types perform validations on Amount fields.</span></span> <span data-ttu-id="bf2f1-104">若要启用量字段中的前导零，必须编辑消息类型的验证策略。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-104">To enable leading zeros in Amount fields, you must edit the validation policy for the message type.</span></span> <span data-ttu-id="bf2f1-105">您可以创建新版本的默认验证策略，并编辑业务规则编辑器中的自变量或部署该策略之前，你可以编辑在文本编辑器中手动的默认策略。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-105">You can create a new version of the default validation policy, and edit the argument in the Business Rule Composer, or you can edit the default policy manually in a text editor before the policy is deployed.</span></span>  
  
 <span data-ttu-id="bf2f1-106">下表列出的方法的启用或禁用前导零。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-106">The following table lists the methods that enable or disable leading zeros.</span></span> <span data-ttu-id="bf2f1-107">此表还指示你需要在方法中设置的自变量的序号。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-107">The table also indicates the ordinal number of the argument that you need to set in the method.</span></span> <span data-ttu-id="bf2f1-108">为 true 以启用前导零，或为 False 可禁止它们设置到它。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-108">Set it to True to enable leading zeros, or to False to disable them.</span></span>  
  
|<span data-ttu-id="bf2f1-109">方法</span><span class="sxs-lookup"><span data-stu-id="bf2f1-109">Method</span></span>|<span data-ttu-id="bf2f1-110">参数号</span><span class="sxs-lookup"><span data-stu-id="bf2f1-110">Argument number</span></span>|  
|------------|---------------------|  
|<span data-ttu-id="bf2f1-111">**CheckValidAmount**</span><span class="sxs-lookup"><span data-stu-id="bf2f1-111">**CheckValidAmount**</span></span>|<span data-ttu-id="bf2f1-112">6</span><span class="sxs-lookup"><span data-stu-id="bf2f1-112">6</span></span>|  
|<span data-ttu-id="bf2f1-113">**CheckCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="bf2f1-113">**CheckCurrencyAmount**</span></span>|<span data-ttu-id="bf2f1-114">4</span><span class="sxs-lookup"><span data-stu-id="bf2f1-114">4</span></span>|  
|<span data-ttu-id="bf2f1-115">**CheckValidSignCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="bf2f1-115">**CheckValidSignCurrencyAmount**</span></span>|<span data-ttu-id="bf2f1-116">3</span><span class="sxs-lookup"><span data-stu-id="bf2f1-116">3</span></span>|  
|<span data-ttu-id="bf2f1-117">**CheckValidSignDateCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="bf2f1-117">**CheckValidSignDateCurrencyAmount**</span></span>|<span data-ttu-id="bf2f1-118">4</span><span class="sxs-lookup"><span data-stu-id="bf2f1-118">4</span></span>|  
|<span data-ttu-id="bf2f1-119">**IsValidTransactionDetailsCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="bf2f1-119">**IsValidTransactionDetailsCurrencyAmount**</span></span>|<span data-ttu-id="bf2f1-120">4</span><span class="sxs-lookup"><span data-stu-id="bf2f1-120">4</span></span>|  
  
 <span data-ttu-id="bf2f1-121">上表中的每个方法包含在一个或多个消息验证策略。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-121">Each method in the preceding table is contained in one or more message validation policies.</span></span> <span data-ttu-id="bf2f1-122">若要将参数设置在策略中，你必须搜索以验证它是否包含策略的方法名称的选项。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-122">To set the argument in a policy, you must search on the method name to verify whether the policy contains it.</span></span> <span data-ttu-id="bf2f1-123">一种方法可能会多次出现一条消息的策略中。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-123">A method may appear multiple times in a message's policy.</span></span>  
  
### <a name="to-enable-or-disable-leading-zeros"></a><span data-ttu-id="bf2f1-124">若要启用或禁用前导零</span><span class="sxs-lookup"><span data-stu-id="bf2f1-124">To enable or disable leading zeros</span></span>  
  
1.  <span data-ttu-id="bf2f1-125">打开文本编辑器，例如记事本。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-125">Open a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="bf2f1-126">在编辑器中，浏览到想要启用或禁用前导零的消息验证策略的位置。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-126">In the editor, browse to the location of the message validation policy in which you want to enable or disable leading zeros.</span></span> <span data-ttu-id="bf2f1-127">例如，你可以找到消息验证策略对于 MT103 消息类型，MT103_Validation_Policy.xml，在*\<驱动器\>*: / 程序文件/Microsoft BizTalk Accelerator for SWIFT/SWIFT 消息/ 类别 1/MT103。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-127">For example, you can find the message validation policy for the MT103 message type, MT103_Validation_Policy.xml, in *\<drive\>*:/Program Files/Microsoft BizTalk Accelerator for SWIFT/SWIFT Messages/Category 1/MT103.</span></span> <span data-ttu-id="bf2f1-128">打开验证策略。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-128">Open the validation policy.</span></span>  
  
3.  <span data-ttu-id="bf2f1-129">在策略中，搜索**CheckValidAmount**方法。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-129">In the policy, search on the **CheckValidAmount** method.</span></span>  
  
4.  <span data-ttu-id="bf2f1-130">如果找到该方法，递减至相应的自变量。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-130">If you find the method, count down to the appropriate argument.</span></span> <span data-ttu-id="bf2f1-131">例如，对于**CheckValidAmount**方法下的第六个自变量的计数。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-131">For example, for the **CheckValidAmount** method, count down to the sixth argument.</span></span> <span data-ttu-id="bf2f1-132">将参数设置为**True**启用前导零或 False，则禁用它们。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-132">Set the argument to **True** to enable leading zeros or False to disable them.</span></span>  
  
5.  <span data-ttu-id="bf2f1-133">对于上表中每个方法重复步骤 3 和 4。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-133">Repeat steps 3 and 4 for each method in the preceding table.</span></span>  
  
6.  <span data-ttu-id="bf2f1-134">保存该文件，，然后关闭编辑器。</span><span class="sxs-lookup"><span data-stu-id="bf2f1-134">Save the file, and then close the editor.</span></span>