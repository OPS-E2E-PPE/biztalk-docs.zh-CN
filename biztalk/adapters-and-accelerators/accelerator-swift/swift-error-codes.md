---
title: BizTalk Server 中的 SWIFT 错误代码 |Microsoft Docs
description: SWIFT 加速器在 BizTalk Server 中查看的类和验证类型
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
ms.openlocfilehash: eeefb9fc918893b8caaab6852d77a417cab340e3
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529791"
---
# <a name="swift-error-codes"></a><span data-ttu-id="b333c-103">SWIFT 错误代码</span><span class="sxs-lookup"><span data-stu-id="b333c-103">SWIFT Error Codes</span></span>
<span data-ttu-id="b333c-104">SWIFT 定义财务 (FIN) 消息的一组的多个网络造成的验证。</span><span class="sxs-lookup"><span data-stu-id="b333c-104">SWIFT defines many network-imposed validations against the set of financial (FIN) messages.</span></span> <span data-ttu-id="b333c-105">每个验证与针对该消息，内容检查的类型相关，并且与三个字符的错误代码相关联。</span><span class="sxs-lookup"><span data-stu-id="b333c-105">Each validation relates to a type of check against the contents of the message, and is associated with a three-character error code.</span></span> <span data-ttu-id="b333c-106">错误代码的第一个字符表示检测到，此问题的类和是一个字母。</span><span class="sxs-lookup"><span data-stu-id="b333c-106">The first character of the error code implies the class of the problem detected, and is a letter.</span></span> <span data-ttu-id="b333c-107">剩余的两个字符表示错误 （如果与此类结合使用） 的详细信息，并且始终显示为两位数字代码。</span><span class="sxs-lookup"><span data-stu-id="b333c-107">The remaining two characters denote the detail of the error (when combined with the class) and always appear as a two-digit code.</span></span>  

## <a name="class-of-errors"></a><span data-ttu-id="b333c-108">类的错误</span><span class="sxs-lookup"><span data-stu-id="b333c-108">Class of errors</span></span>  
 <span data-ttu-id="b333c-109">下表列出了字母命名、 验证类型，每个类别的错误，与关联的规则更改，该值指示是否支持错误的类。</span><span class="sxs-lookup"><span data-stu-id="b333c-109">The following table lists the letter designations, validation type, rule change associated with each class of error, and whether or not the class of error is supported.</span></span>  
  
|<span data-ttu-id="b333c-110">类</span><span class="sxs-lookup"><span data-stu-id="b333c-110">Class</span></span>|<span data-ttu-id="b333c-111">验证类型和规则的更改</span><span class="sxs-lookup"><span data-stu-id="b333c-111">Validation type and rule change</span></span>|<span data-ttu-id="b333c-112">支持？</span><span class="sxs-lookup"><span data-stu-id="b333c-112">Supported?</span></span>|  
|-----------|-------------------------------------|----------------|  
|<span data-ttu-id="b333c-113">**C，D，E**</span><span class="sxs-lookup"><span data-stu-id="b333c-113">**C, D, E**</span></span>|<span data-ttu-id="b333c-114">语义验证规则 0 299</span><span class="sxs-lookup"><span data-stu-id="b333c-114">Semantic validation rules 0-299</span></span>|<span data-ttu-id="b333c-115">支持</span><span class="sxs-lookup"><span data-stu-id="b333c-115">Supported</span></span>|  
|<span data-ttu-id="b333c-116">**Knn**</span><span class="sxs-lookup"><span data-stu-id="b333c-116">**Knn**</span></span>|<span data-ttu-id="b333c-117">字段中的无效代码字*nn*</span><span class="sxs-lookup"><span data-stu-id="b333c-117">Invalid code word in field *nn*</span></span>|<span data-ttu-id="b333c-118">支持</span><span class="sxs-lookup"><span data-stu-id="b333c-118">Supported</span></span>|  
|<span data-ttu-id="b333c-119">**M50**</span><span class="sxs-lookup"><span data-stu-id="b333c-119">**M50**</span></span>|<span data-ttu-id="b333c-120">已超过消息长度</span><span class="sxs-lookup"><span data-stu-id="b333c-120">Message length exceeded</span></span>|<span data-ttu-id="b333c-121">不支持</span><span class="sxs-lookup"><span data-stu-id="b333c-121">Unsupported</span></span>|  
|<span data-ttu-id="b333c-122">**M60**</span><span class="sxs-lookup"><span data-stu-id="b333c-122">**M60**</span></span>|<span data-ttu-id="b333c-123">遇到非 SWIFT 字符</span><span class="sxs-lookup"><span data-stu-id="b333c-123">Non-SWIFT character encountered</span></span>|<span data-ttu-id="b333c-124">支持</span><span class="sxs-lookup"><span data-stu-id="b333c-124">Supported</span></span>|  
|<span data-ttu-id="b333c-125">**T**</span><span class="sxs-lookup"><span data-stu-id="b333c-125">**T**</span></span>|<span data-ttu-id="b333c-126">文本验证错误代码</span><span class="sxs-lookup"><span data-stu-id="b333c-126">Text validation error codes</span></span>|<span data-ttu-id="b333c-127">支持</span><span class="sxs-lookup"><span data-stu-id="b333c-127">Supported</span></span>|  
|<span data-ttu-id="b333c-128">**G**</span><span class="sxs-lookup"><span data-stu-id="b333c-128">**G**</span></span>|<span data-ttu-id="b333c-129">消息用户组 （杯褐色） Textval 规则的特定错误代码</span><span class="sxs-lookup"><span data-stu-id="b333c-129">Specific error codes for message user group (MUG) Textval rules</span></span>|<span data-ttu-id="b333c-130">不支持</span><span class="sxs-lookup"><span data-stu-id="b333c-130">Unsupported</span></span>|  
|<span data-ttu-id="b333c-131">**B**</span><span class="sxs-lookup"><span data-stu-id="b333c-131">**B**</span></span>|<span data-ttu-id="b333c-132">增值服务的特殊的错误代码</span><span class="sxs-lookup"><span data-stu-id="b333c-132">Special error codes for value-added services</span></span>|<span data-ttu-id="b333c-133">不支持</span><span class="sxs-lookup"><span data-stu-id="b333c-133">Unsupported</span></span>|  
  
 <span data-ttu-id="b333c-134">应在中引用所有 SWIFT 错误*SWIFT 用户手册*。</span><span class="sxs-lookup"><span data-stu-id="b333c-134">All SWIFT errors should be referenced in the *SWIFT User Handbook*.</span></span> <span data-ttu-id="b333c-135">有关详细信息和有关 SWIFT 错误代码的完整列表，请参阅*消息格式的验证规则*量*SWIFT 用户手册*。</span><span class="sxs-lookup"><span data-stu-id="b333c-135">For more information and for a complete list of SWIFT error codes, refer to the *Message Format Validation Rules* volume of the *SWIFT User Handbook*.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="b333c-136">在此发布的 2003 年 9 月版本中实施规则。</span><span class="sxs-lookup"><span data-stu-id="b333c-136">implements the rules in the September 2003 edition of this publication.</span></span> <span data-ttu-id="b333c-137">您可以访问 SWIFT 网站下载，网址[ http://go.microsoft.com/fwlink/?LinkId=27885 ](http://go.microsoft.com/fwlink/?LinkId=27885)。</span><span class="sxs-lookup"><span data-stu-id="b333c-137">You can access the SWIFT Web site at [http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885).</span></span>  

## <a name="validation-errors"></a><span data-ttu-id="b333c-138">验证错误</span><span class="sxs-lookup"><span data-stu-id="b333c-138">Validation errors</span></span>  
 <span data-ttu-id="b333c-139">有一些代码由 A4SWIFT 定义的。</span><span class="sxs-lookup"><span data-stu-id="b333c-139">There are some codes which are defined by A4SWIFT.</span></span> <span data-ttu-id="b333c-140">创建和实现通过 A4SWIFT，因此没有为此类规则定义 SWIFT 没有相应的错误代码的验证/网络规则中使用这些错误代码。</span><span class="sxs-lookup"><span data-stu-id="b333c-140">These error codes are used in the validation/network rules created and implemented by A4SWIFT, so there is no corresponding error code defined by SWIFT for such rules.</span></span> <span data-ttu-id="b333c-141">下表显示了错误代码和相应的用例中引发错误。</span><span class="sxs-lookup"><span data-stu-id="b333c-141">Below table shows the error code and corresponding case in which the error is thrown.</span></span> <span data-ttu-id="b333c-142">是将引发错误的特定字段。</span><span class="sxs-lookup"><span data-stu-id="b333c-142">is the particular field which throws the error.</span></span>  
  
|<span data-ttu-id="b333c-143">错误代码</span><span class="sxs-lookup"><span data-stu-id="b333c-143">Error Code</span></span>|<span data-ttu-id="b333c-144">Description</span><span class="sxs-lookup"><span data-stu-id="b333c-144">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="b333c-145">A4SWIFT001</span><span class="sxs-lookup"><span data-stu-id="b333c-145">A4SWIFT001</span></span>|<span data-ttu-id="b333c-146">多行的字段的第一个字符不能为: 或-字符的第二个和后续行。</span><span class="sxs-lookup"><span data-stu-id="b333c-146">The first character of multiline field cannot be ':' or '-' character for second and  subsequent lines.</span></span>|  
|<span data-ttu-id="b333c-147">A4SWIFT002</span><span class="sxs-lookup"><span data-stu-id="b333c-147">A4SWIFT002</span></span>|<span data-ttu-id="b333c-148">字段包含无效值。</span><span class="sxs-lookup"><span data-stu-id="b333c-148">Field contains invalid value.</span></span>|  
  
> [!NOTE]
>  [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] <span data-ttu-id="b333c-149">包含对一些旧的消息的支持，因为内部应用程序可能会使用这些消息。</span><span class="sxs-lookup"><span data-stu-id="b333c-149">includes support for some legacy messages, because internal applications might use these messages.</span></span> <span data-ttu-id="b333c-150">因此，A4SWIFT 维护关联的 SWIFT 规则和错误代码。</span><span class="sxs-lookup"><span data-stu-id="b333c-150">Therefore, A4SWIFT maintains the associated SWIFT rules and error codes.</span></span>

## <a name="more-good-info"></a><span data-ttu-id="b333c-151">更多有用信息</span><span class="sxs-lookup"><span data-stu-id="b333c-151">More good info</span></span>
[<span data-ttu-id="b333c-152">故障排除：问题和解决方法</span><span class="sxs-lookup"><span data-stu-id="b333c-152">Troubleshooting: Issues and Resolutions</span></span>](troubleshooting-issues-and-resolutions1.md)  
[<span data-ttu-id="b333c-153">已知问题</span><span class="sxs-lookup"><span data-stu-id="b333c-153">Known Issues</span></span>](known-issues5.md)  
[<span data-ttu-id="b333c-154">通用术语和定义</span><span class="sxs-lookup"><span data-stu-id="b333c-154">Common terms and definitions</span></span>](glossary6.md)