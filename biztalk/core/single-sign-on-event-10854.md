---
title: 单一登录： 事件 10854 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8faed9d-5c7e-4b99-bcd9-ea5f670d5e72
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42f9e9e761689b2ed21ec37acdbb8a63f1f88070
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
ms.locfileid: "22277573"
---
# <a name="single-sign-on-event-10854"></a><span data-ttu-id="f50de-102">单一登录： 事件 10854</span><span class="sxs-lookup"><span data-stu-id="f50de-102">Single Sign-On: Event 10854</span></span>
## <a name="details"></a><span data-ttu-id="f50de-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f50de-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f50de-104">產品名稱</span><span class="sxs-lookup"><span data-stu-id="f50de-104">Product Name</span></span>|<span data-ttu-id="f50de-105">企業單一登入</span><span class="sxs-lookup"><span data-stu-id="f50de-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f50de-106">產品版本</span><span class="sxs-lookup"><span data-stu-id="f50de-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f50de-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f50de-107">Event ID</span></span>|<span data-ttu-id="f50de-108">10854</span><span class="sxs-lookup"><span data-stu-id="f50de-108">10854</span></span>|  
|<span data-ttu-id="f50de-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f50de-109">Event Source</span></span>|<span data-ttu-id="f50de-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f50de-110">ENTSSO</span></span>|  
|<span data-ttu-id="f50de-111">元件</span><span class="sxs-lookup"><span data-stu-id="f50de-111">Component</span></span>|<span data-ttu-id="f50de-112">不適用</span><span class="sxs-lookup"><span data-stu-id="f50de-112">N/A</span></span>|  
|<span data-ttu-id="f50de-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f50de-113">Symbolic Name</span></span>|<span data-ttu-id="f50de-114">ENTSSO_E_INVALID_STRING_FORMAT</span><span class="sxs-lookup"><span data-stu-id="f50de-114">ENTSSO_E_INVALID_STRING_FORMAT</span></span>|  
|<span data-ttu-id="f50de-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f50de-115">Message Text</span></span>|<span data-ttu-id="f50de-116">对于此函数来说，此字符串格式不正确。</span><span class="sxs-lookup"><span data-stu-id="f50de-116">The string format is incorrect for this function.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f50de-117">解释</span><span class="sxs-lookup"><span data-stu-id="f50de-117">Explanation</span></span>  
 <span data-ttu-id="f50de-118">对于此函数来说，此字符串格式不正确。</span><span class="sxs-lookup"><span data-stu-id="f50de-118">The string format is incorrect for this function.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f50de-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="f50de-119">User Action</span></span>  
 <span data-ttu-id="f50de-120">密码字符串的正确格式说明如下：</span><span class="sxs-lookup"><span data-stu-id="f50de-120">Proper formatting for password strings is described below:</span></span>  
  
 <span data-ttu-id="f50de-121">VT_BSTR 类型属性</span><span class="sxs-lookup"><span data-stu-id="f50de-121">VT_BSTR type property</span></span>  
  
 <span data-ttu-id="f50de-122">分隔符是 /（斜杠）</span><span class="sxs-lookup"><span data-stu-id="f50de-122">The delimiter is / (slash)</span></span>  
  
 <span data-ttu-id="f50de-123">dc = 默认情况（无操作-不执行任何操作）</span><span class="sxs-lookup"><span data-stu-id="f50de-123">dc = default case (no operation - do nothing)</span></span>  
  
 <span data-ttu-id="f50de-124">示例︰ dc /</span><span class="sxs-lookup"><span data-stu-id="f50de-124">Example: dc/</span></span>  
  
 <span data-ttu-id="f50de-125">（无更改 - 'Cat' 到 'Cat'）</span><span class="sxs-lookup"><span data-stu-id="f50de-125">(no change - 'Cat' to 'Cat')</span></span>  
  
 <span data-ttu-id="f50de-126">uc = 大写</span><span class="sxs-lookup"><span data-stu-id="f50de-126">uc = upper case</span></span>  
  
 <span data-ttu-id="f50de-127">示例︰ uc /</span><span class="sxs-lookup"><span data-stu-id="f50de-127">Example: uc/</span></span>  
  
 <span data-ttu-id="f50de-128">（将密码更改为大写 - 'Cat' 到 'CAT'）</span><span class="sxs-lookup"><span data-stu-id="f50de-128">(change password to upper case - 'Cat' to 'CAT')</span></span>  
  
 <span data-ttu-id="f50de-129">lc = 小写</span><span class="sxs-lookup"><span data-stu-id="f50de-129">lc = lower case</span></span>  
  
 <span data-ttu-id="f50de-130">示例︰ lc /</span><span class="sxs-lookup"><span data-stu-id="f50de-130">Example: lc/</span></span>  
  
 <span data-ttu-id="f50de-131">（将密码更改为小写 - 'Cat' 到 'cat'）</span><span class="sxs-lookup"><span data-stu-id="f50de-131">(change password to lower case - 'Cat' to 'cat')</span></span>  
  
 <span data-ttu-id="f50de-132">rc = 删除字符 - 后接计数和字符</span><span class="sxs-lookup"><span data-stu-id="f50de-132">rc = remove chars - followed by count followed by chars</span></span>  
  
 <span data-ttu-id="f50de-133">示例： rc/2 / #@/</span><span class="sxs-lookup"><span data-stu-id="f50de-133">Example: rc/2/#@/</span></span>  
  
 <span data-ttu-id="f50de-134">(删除字符 '#' 和 ' @' 密码-从C@t# 到 Ct)</span><span class="sxs-lookup"><span data-stu-id="f50de-134">(remove the characters '#' and '@' from the password - 'C@t#' to 'Ct')</span></span>  
  
 <span data-ttu-id="f50de-135">sc = 替换字符 - 后接计数、将被替换的字符、用来替换的字符</span><span class="sxs-lookup"><span data-stu-id="f50de-135">sc = substitute chars - followed by count followed by chars to replace followed by substitute chars</span></span>  
  
 <span data-ttu-id="f50de-136">示例︰ sc/3/abc/def /</span><span class="sxs-lookup"><span data-stu-id="f50de-136">Example: sc/3/abc/def/</span></span>  
  
 <span data-ttu-id="f50de-137">（删除密码中的 'a'、'b' 和 'c'，并分别以 'd'、'e' 和 'f' 替换）</span><span class="sxs-lookup"><span data-stu-id="f50de-137">(remove the characters 'a', 'b' and 'c' from the password and replace with 'd', 'e' and 'f' respectively)</span></span>  
  
 <span data-ttu-id="f50de-138">（'Cat' 到 'Cdt'）</span><span class="sxs-lookup"><span data-stu-id="f50de-138">('Cat' to 'Cdt')</span></span>  
  
 <span data-ttu-id="f50de-139">ps = 开始键盘 - 后接计数（最小密码长度）、单个键盘字符</span><span class="sxs-lookup"><span data-stu-id="f50de-139">ps = pad from start - followed by count (min password length) followed by single pad char</span></span>  
  
 <span data-ttu-id="f50de-140">示例︰ ps/8 / #/</span><span class="sxs-lookup"><span data-stu-id="f50de-140">Example: ps/8/#/</span></span>  
  
 <span data-ttu-id="f50de-141">（如果密码没有达到最少 8 个字符的长度，则以键盘字符 '#' 开始，直到总共达到 8 个字符）</span><span class="sxs-lookup"><span data-stu-id="f50de-141">(if the password is not at least 8 chars in length then pad from the start with the character '#' until there are 8 chars total)</span></span>  
  
 <span data-ttu-id="f50de-142">（'Cat' 到 '#####Cat'）</span><span class="sxs-lookup"><span data-stu-id="f50de-142">('Cat' to '#####Cat')</span></span>  
  
 <span data-ttu-id="f50de-143">pe = 结束键盘 - 后接计数（最小密码长度）、单个键盘字符</span><span class="sxs-lookup"><span data-stu-id="f50de-143">pe = pad from end - followed by count (min password length) followed by single pad char</span></span>  
  
 <span data-ttu-id="f50de-144">示例︰ pe/10 / $/</span><span class="sxs-lookup"><span data-stu-id="f50de-144">Example: pe/10/$/</span></span>  
  
 <span data-ttu-id="f50de-145">（如果密码没有达到最少 10 个字符的长度，则以键盘字符 '$' 结束，直到总共达到 10 个字符）</span><span class="sxs-lookup"><span data-stu-id="f50de-145">(if the password is not at least 10 chars in length then pad to the end with the character '$' until there are 10 chars total)</span></span>  
  
 <span data-ttu-id="f50de-146">（'Cat' 到 'Cat$$$$$$$'）</span><span class="sxs-lookup"><span data-stu-id="f50de-146">('Cat' to 'Cat$$$$$$$')</span></span>  
  
 <span data-ttu-id="f50de-147">tr = 截断 - 字符串长度限制 - 后接计数</span><span class="sxs-lookup"><span data-stu-id="f50de-147">tr = truncate - limit length of string - followed by count</span></span>  
  
 <span data-ttu-id="f50de-148">示例︰ tr/11 /</span><span class="sxs-lookup"><span data-stu-id="f50de-148">Example: tr/11/</span></span>  
  
 <span data-ttu-id="f50de-149">（'Cat123456789' 到 'Cat12345678'）；</span><span class="sxs-lookup"><span data-stu-id="f50de-149">('Cat123456789' to 'Cat12345678');</span></span>  
  
 <span data-ttu-id="f50de-150">按照字符串中的顺序处理标记。</span><span class="sxs-lookup"><span data-stu-id="f50de-150">The tokens are processed in their order in the string.</span></span>  
  
 <span data-ttu-id="f50de-151">例如：</span><span class="sxs-lookup"><span data-stu-id="f50de-151">Example:</span></span>  
  
 <span data-ttu-id="f50de-152">uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/</span><span class="sxs-lookup"><span data-stu-id="f50de-152">uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/</span></span>