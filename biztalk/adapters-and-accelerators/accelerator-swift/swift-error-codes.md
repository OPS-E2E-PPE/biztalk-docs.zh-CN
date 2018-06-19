---
title: BizTalk Server 中的 SWIFT 错误代码 |Microsoft 文档
description: SWIFT 快捷键 BizTalk Server 中查看的类和验证类型
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03699986-965b-4a28-ab2e-09f110fb4db6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d8e027eb9cce1cf66342484070310141e10b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215021"
---
# <a name="swift-error-codes"></a><span data-ttu-id="f2d43-103">SWIFT 错误代码</span><span class="sxs-lookup"><span data-stu-id="f2d43-103">SWIFT Error Codes</span></span>
<span data-ttu-id="f2d43-104">SWIFT 定义许多网络施加验证针对的一组财务 (FIN) 消息。</span><span class="sxs-lookup"><span data-stu-id="f2d43-104">SWIFT defines many network-imposed validations against the set of financial (FIN) messages.</span></span> <span data-ttu-id="f2d43-105">每个验证与一种针对消息，内容检查，并且与三个字符错误代码相关联。</span><span class="sxs-lookup"><span data-stu-id="f2d43-105">Each validation relates to a type of check against the contents of the message, and is associated with a three-character error code.</span></span> <span data-ttu-id="f2d43-106">错误代码的第一个字符表示检测到，此问题的类和是一个字母。</span><span class="sxs-lookup"><span data-stu-id="f2d43-106">The first character of the error code implies the class of the problem detected, and is a letter.</span></span> <span data-ttu-id="f2d43-107">剩余的两个字符表示的错误 （与类结合使用） 时的详细信息，并始终显示为两位数字代码。</span><span class="sxs-lookup"><span data-stu-id="f2d43-107">The remaining two characters denote the detail of the error (when combined with the class) and always appear as a two-digit code.</span></span>  

## <a name="class-of-errors"></a><span data-ttu-id="f2d43-108">类的错误</span><span class="sxs-lookup"><span data-stu-id="f2d43-108">Class of errors</span></span>  
 <span data-ttu-id="f2d43-109">下表列出了字母命名、 验证类型，每个类别的错误，与关联的规则更改，是否受支持的错误的类。</span><span class="sxs-lookup"><span data-stu-id="f2d43-109">The following table lists the letter designations, validation type, rule change associated with each class of error, and whether or not the class of error is supported.</span></span>  
  
|<span data-ttu-id="f2d43-110">类</span><span class="sxs-lookup"><span data-stu-id="f2d43-110">Class</span></span>|<span data-ttu-id="f2d43-111">验证类型和规则更改</span><span class="sxs-lookup"><span data-stu-id="f2d43-111">Validation type and rule change</span></span>|<span data-ttu-id="f2d43-112">是否支持？</span><span class="sxs-lookup"><span data-stu-id="f2d43-112">Supported?</span></span>|  
|-----------|-------------------------------------|----------------|  
|<span data-ttu-id="f2d43-113">**C，D，E**</span><span class="sxs-lookup"><span data-stu-id="f2d43-113">**C, D, E**</span></span>|<span data-ttu-id="f2d43-114">语义验证规则 0 299</span><span class="sxs-lookup"><span data-stu-id="f2d43-114">Semantic validation rules 0-299</span></span>|<span data-ttu-id="f2d43-115">是否支持</span><span class="sxs-lookup"><span data-stu-id="f2d43-115">Supported</span></span>|  
|<span data-ttu-id="f2d43-116">**Knn**</span><span class="sxs-lookup"><span data-stu-id="f2d43-116">**Knn**</span></span>|<span data-ttu-id="f2d43-117">字段中的无效代码字*nn*</span><span class="sxs-lookup"><span data-stu-id="f2d43-117">Invalid code word in field *nn*</span></span>|<span data-ttu-id="f2d43-118">是否支持</span><span class="sxs-lookup"><span data-stu-id="f2d43-118">Supported</span></span>|  
|<span data-ttu-id="f2d43-119">**M50**</span><span class="sxs-lookup"><span data-stu-id="f2d43-119">**M50**</span></span>|<span data-ttu-id="f2d43-120">已超过消息长度</span><span class="sxs-lookup"><span data-stu-id="f2d43-120">Message length exceeded</span></span>|<span data-ttu-id="f2d43-121">不支持</span><span class="sxs-lookup"><span data-stu-id="f2d43-121">Unsupported</span></span>|  
|<span data-ttu-id="f2d43-122">**M60**</span><span class="sxs-lookup"><span data-stu-id="f2d43-122">**M60**</span></span>|<span data-ttu-id="f2d43-123">遇到的非 SWIFT 字符</span><span class="sxs-lookup"><span data-stu-id="f2d43-123">Non-SWIFT character encountered</span></span>|<span data-ttu-id="f2d43-124">是否支持</span><span class="sxs-lookup"><span data-stu-id="f2d43-124">Supported</span></span>|  
|<span data-ttu-id="f2d43-125">**T**</span><span class="sxs-lookup"><span data-stu-id="f2d43-125">**T**</span></span>|<span data-ttu-id="f2d43-126">文本验证错误代码</span><span class="sxs-lookup"><span data-stu-id="f2d43-126">Text validation error codes</span></span>|<span data-ttu-id="f2d43-127">是否支持</span><span class="sxs-lookup"><span data-stu-id="f2d43-127">Supported</span></span>|  
|<span data-ttu-id="f2d43-128">**G**</span><span class="sxs-lookup"><span data-stu-id="f2d43-128">**G**</span></span>|<span data-ttu-id="f2d43-129">消息用户组 （咖啡杯） Textval 规则的特定错误代码</span><span class="sxs-lookup"><span data-stu-id="f2d43-129">Specific error codes for message user group (MUG) Textval rules</span></span>|<span data-ttu-id="f2d43-130">不支持</span><span class="sxs-lookup"><span data-stu-id="f2d43-130">Unsupported</span></span>|  
|<span data-ttu-id="f2d43-131">**B**</span><span class="sxs-lookup"><span data-stu-id="f2d43-131">**B**</span></span>|<span data-ttu-id="f2d43-132">增值服务的特殊的错误代码</span><span class="sxs-lookup"><span data-stu-id="f2d43-132">Special error codes for value-added services</span></span>|<span data-ttu-id="f2d43-133">不支持</span><span class="sxs-lookup"><span data-stu-id="f2d43-133">Unsupported</span></span>|  
  
 <span data-ttu-id="f2d43-134">应在中引用所有 SWIFT 错误*SWIFT 用户手册*。</span><span class="sxs-lookup"><span data-stu-id="f2d43-134">All SWIFT errors should be referenced in the *SWIFT User Handbook*.</span></span> <span data-ttu-id="f2d43-135">有关详细信息和有关 SWIFT 错误代码的完整列表，请参阅*消息格式验证规则*量*SWIFT 用户手册*。</span><span class="sxs-lookup"><span data-stu-id="f2d43-135">For more information and for a complete list of SWIFT error codes, refer to the *Message Format Validation Rules* volume of the *SWIFT User Handbook*.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="f2d43-136">在此发布的 2003 年 9 月版本中实施规则。</span><span class="sxs-lookup"><span data-stu-id="f2d43-136"> implements the rules in the September 2003 edition of this publication.</span></span> <span data-ttu-id="f2d43-137">你可以访问位于的 SWIFT 网站[http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885)。</span><span class="sxs-lookup"><span data-stu-id="f2d43-137">You can access the SWIFT Web site at [http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885).</span></span>  

## <a name="validation-errors"></a><span data-ttu-id="f2d43-138">验证错误</span><span class="sxs-lookup"><span data-stu-id="f2d43-138">Validation errors</span></span>  
 <span data-ttu-id="f2d43-139">有一些代码 A4SWIFT 定义。</span><span class="sxs-lookup"><span data-stu-id="f2d43-139">There are some codes which are defined by A4SWIFT.</span></span> <span data-ttu-id="f2d43-140">创建和实现通过 A4SWIFT，因此没有为此类规则定义 SWIFT 相应错误代码的验证/网络规则用于这些错误代码。</span><span class="sxs-lookup"><span data-stu-id="f2d43-140">These error codes are used in the validation/network rules created and implemented by A4SWIFT, so there is no corresponding error code defined by SWIFT for such rules.</span></span> <span data-ttu-id="f2d43-141">下表显示的错误代码和相应的情况下引发错误的。</span><span class="sxs-lookup"><span data-stu-id="f2d43-141">Below table shows the error code and corresponding case in which the error is thrown.</span></span> <span data-ttu-id="f2d43-142">是将引发错误的特定字段。</span><span class="sxs-lookup"><span data-stu-id="f2d43-142">is the particular field which throws the error.</span></span>  
  
|<span data-ttu-id="f2d43-143">错误代码</span><span class="sxs-lookup"><span data-stu-id="f2d43-143">Error Code</span></span>|<span data-ttu-id="f2d43-144">Description</span><span class="sxs-lookup"><span data-stu-id="f2d43-144">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="f2d43-145">A4SWIFT001</span><span class="sxs-lookup"><span data-stu-id="f2d43-145">A4SWIFT001</span></span>|<span data-ttu-id="f2d43-146">多行的字段的第一个字符不能为: 或-字符的第二个和后续行。</span><span class="sxs-lookup"><span data-stu-id="f2d43-146">The first character of multiline field cannot be ':' or '-' character for second and  subsequent lines.</span></span>|  
|<span data-ttu-id="f2d43-147">A4SWIFT002</span><span class="sxs-lookup"><span data-stu-id="f2d43-147">A4SWIFT002</span></span>|<span data-ttu-id="f2d43-148">字段包含无效值。</span><span class="sxs-lookup"><span data-stu-id="f2d43-148">Field contains invalid value.</span></span>|  
  
> [!NOTE]
>  [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]<span data-ttu-id="f2d43-149">因为内部应用程序可能会使用这些消息，请包括对某些旧的消息，支持。</span><span class="sxs-lookup"><span data-stu-id="f2d43-149"> includes support for some legacy messages, because internal applications might use these messages.</span></span> <span data-ttu-id="f2d43-150">因此，A4SWIFT 维护关联的 SWIFT 规则和错误代码。</span><span class="sxs-lookup"><span data-stu-id="f2d43-150">Therefore, A4SWIFT maintains the associated SWIFT rules and error codes.</span></span>

## <a name="more-good-info"></a><span data-ttu-id="f2d43-151">良好的详细信息</span><span class="sxs-lookup"><span data-stu-id="f2d43-151">More good info</span></span>
[<span data-ttu-id="f2d43-152">疑难解答： 问题和解决方法</span><span class="sxs-lookup"><span data-stu-id="f2d43-152">Troubleshooting: Issues and Resolutions</span></span>](troubleshooting-issues-and-resolutions1.md)  
[<span data-ttu-id="f2d43-153">已知问题</span><span class="sxs-lookup"><span data-stu-id="f2d43-153">Known Issues</span></span>](known-issues5.md)  
[<span data-ttu-id="f2d43-154">常见术语和定义</span><span class="sxs-lookup"><span data-stu-id="f2d43-154">Common terms and definitions</span></span>](glossary6.md)