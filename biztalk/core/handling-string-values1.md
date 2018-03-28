---
title: 处理字符串 Values1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, configuring strings
- strings, left-justified
- strings, configuring
- strings, right-justified
ms.assetid: a180b818-1009-45f5-a503-d10ed7dd27fc
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f32b29b9a8688fe8402730c1db8f12e42a67bab
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="handling-string-values"></a><span data-ttu-id="790b6-102">处理字符串值</span><span class="sxs-lookup"><span data-stu-id="790b6-102">Handling String Values</span></span>
<span data-ttu-id="790b6-103">本主题介绍如何将某些字符串参数配置为右对齐（并向左填充）。</span><span class="sxs-lookup"><span data-stu-id="790b6-103">This topic describes how to configure certain string arguments as right-justified (and left padded).</span></span>  
  
## <a name="types-of-string-values"></a><span data-ttu-id="790b6-104">字符串值的类型</span><span class="sxs-lookup"><span data-stu-id="790b6-104">Types of String Values</span></span>  
 <span data-ttu-id="790b6-105">JD Edwards OneWorld 通过互操作性层显示两种字符串值：</span><span class="sxs-lookup"><span data-stu-id="790b6-105">JD Edwards OneWorld exposes two kinds of string values through its interoperability layer:</span></span>  
  
-   <span data-ttu-id="790b6-106">Char︰ 单个字符</span><span class="sxs-lookup"><span data-stu-id="790b6-106">Char: a single character</span></span>  
  
-   <span data-ttu-id="790b6-107">最大长度字符串</span><span class="sxs-lookup"><span data-stu-id="790b6-107">maximum length string</span></span>  
  
 <span data-ttu-id="790b6-108">JD Edwards OneWorld 使用匈牙利符号命名业务函数中这些类型的参数。</span><span class="sxs-lookup"><span data-stu-id="790b6-108">JD Edwards OneWorld uses Hungarian notation to name the arguments of these types in the business functions.</span></span> <span data-ttu-id="790b6-109">例如，这些类型的参数以下列字符开头：</span><span class="sxs-lookup"><span data-stu-id="790b6-109">For example, arguments of these types begin with:</span></span>  
  
-   <span data-ttu-id="790b6-110">c</span><span class="sxs-lookup"><span data-stu-id="790b6-110">c</span></span>  
  
-   <span data-ttu-id="790b6-111">sz</span><span class="sxs-lookup"><span data-stu-id="790b6-111">sz</span></span>  
  
### <a name="left-justified-values"></a><span data-ttu-id="790b6-112">左对齐值</span><span class="sxs-lookup"><span data-stu-id="790b6-112">Left-Justified Values</span></span>  
 <span data-ttu-id="790b6-113">对于大多数的 sz 类型参数，最大长度的字符串或字符数组，JD Edwards OneWorld 应该为左对齐值。</span><span class="sxs-lookup"><span data-stu-id="790b6-113">For a majority of sz-type arguments, maximum length string or char array, JD Edwards OneWorld expects a left-justified value.</span></span> <span data-ttu-id="790b6-114">对于街道地址行，最大长度为 40，JD Edwards OneWorld 最好为（示例）：</span><span class="sxs-lookup"><span data-stu-id="790b6-114">For a street address line, which is of maximum length 40, JD Edwards OneWorld expects (for example):</span></span>  
  
 <span data-ttu-id="790b6-115">"4567 Main St."</span><span class="sxs-lookup"><span data-stu-id="790b6-115">"4567 Main St.       "</span></span>  
  
 <span data-ttu-id="790b6-116">使用空白填充到长度 40。</span><span class="sxs-lookup"><span data-stu-id="790b6-116">padded to length 40 with blanks.</span></span> <span data-ttu-id="790b6-117">您无需输入填充，因为 JD Edwards OneWorld 的 Microsoft BizTalk 适配器将为您提供填充内容。</span><span class="sxs-lookup"><span data-stu-id="790b6-117">It is not necessary for you to enter the padding because Microsoft BizTalk Adapter for JD Edwards OneWorld provides this for you.</span></span> <span data-ttu-id="790b6-118">您只需要在客户端代码中输入“4567 Main St.”。</span><span class="sxs-lookup"><span data-stu-id="790b6-118">You only need to enter "4567 Main St.", in your client code.</span></span>  
  
### <a name="right-justified-values"></a><span data-ttu-id="790b6-119">右对齐值</span><span class="sxs-lookup"><span data-stu-id="790b6-119">Right-Justified Values</span></span>  
 <span data-ttu-id="790b6-120">对于此类型的某些子集值，JD Edwards OneWorld 预期值右对齐，左边填充。</span><span class="sxs-lookup"><span data-stu-id="790b6-120">For some subset of values for this type, JD Edwards OneWorld expects values that are right justified with padding on the left.</span></span> <span data-ttu-id="790b6-121">例如，对于业务 B4200310 源模块中的函数，参数 szBusinessUnit 是长度为 12。</span><span class="sxs-lookup"><span data-stu-id="790b6-121">For example, for business functions in the B4200310 source module, the argument szBusinessUnit is of length 12.</span></span> <span data-ttu-id="790b6-122">此自变量表示工厂，例如生产设施。</span><span class="sxs-lookup"><span data-stu-id="790b6-122">This argument represents a plant, such as a production facility.</span></span> <span data-ttu-id="790b6-123">工厂数 30，参考</span><span class="sxs-lookup"><span data-stu-id="790b6-123">For a plant number of 30, J.D.</span></span> <span data-ttu-id="790b6-124">Edwards OneWorld XE 需要的值︰</span><span class="sxs-lookup"><span data-stu-id="790b6-124">Edwards OneWorld XE expects a value of:</span></span>  
  
 <span data-ttu-id="790b6-125">"          30"</span><span class="sxs-lookup"><span data-stu-id="790b6-125">"          30"</span></span>  
  
 <span data-ttu-id="790b6-126">若要输入一个值，将为右对齐，必须在名为 jdearglist.txt 输入参数。</span><span class="sxs-lookup"><span data-stu-id="790b6-126">To enter a value that will be right-justified, you must enter the parameter in a file called jdearglist.txt.</span></span> <span data-ttu-id="790b6-127">生成架构时读取 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="790b6-127">The jdearglist.txt is read when you generate the schema.</span></span> <span data-ttu-id="790b6-128">此文本文件中列出的任何值都会自动转化为右对齐的值，并且填充在左边空白区域。</span><span class="sxs-lookup"><span data-stu-id="790b6-128">Any value that is listed in this text file is automatically converted to a right-justified value and padded on the left with blanks.</span></span>  
  
 <span data-ttu-id="790b6-129">必须创建 jdearglist.txt 使用文本编辑器中，项描述这些参数，并将其保存在以下文件夹︰ %BizTalk_Install_Adapter%\config\JDE\\</span><span class="sxs-lookup"><span data-stu-id="790b6-129">You must create jdearglist.txt using a text editor, with entries describing these parameters, and save it in the following folder: %BizTalk_Install_Adapter%\config\JDE\\</span></span>  
  
 <span data-ttu-id="790b6-130">其中 **%biztalk_install_adapter%** 是在其中你安装的 BizTalk Adapter for 博士 Edwards OneWorld 的目录。</span><span class="sxs-lookup"><span data-stu-id="790b6-130">Where **%BizTalk_Install_Adapter%** is the directory in which you installed BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
 <span data-ttu-id="790b6-131">如果此文件不存在或为空，当适配器首次打开时，信息性消息将出现在 JD Edwards OneWorld 的 BizTalk 适配器日志中。</span><span class="sxs-lookup"><span data-stu-id="790b6-131">If this file does not exist or is empty, an informational message appears in the BizTalk Adapter for JD Edwards OneWorld log when the adapter first opens.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="790b6-132">如果您在生成架构后更改此文件，则必须重新生成架构以刷新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="790b6-132">If you change this file after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span>  
  
 <span data-ttu-id="790b6-133">要验证您使用的是否是此文件中的最新信息，您可以在重新生成架构之前，使用任务管理器停止 browsingagent.exe 进程；但是，此操作不是必需的。</span><span class="sxs-lookup"><span data-stu-id="790b6-133">To verify that you are using the latest information in this file, you can use the Task Manager to stop the browsingagent.exe process before regenerating your schema; however, this should not be necessary.</span></span>  
  
 <span data-ttu-id="790b6-134">以下是 jdearglist.txt 文件中条目格式的示例：</span><span class="sxs-lookup"><span data-stu-id="790b6-134">The following is an example of the format for entries in the jdearglist.txt file:</span></span>  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
```  
  
 <span data-ttu-id="790b6-135">例如：</span><span class="sxs-lookup"><span data-stu-id="790b6-135">For example:</span></span>  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 <span data-ttu-id="790b6-136">对于属于同一业务模块的一组业务功能，在某些或所有业务功能中共享 like-named 参数（同一类型）。</span><span class="sxs-lookup"><span data-stu-id="790b6-136">For a set of business functions belonging to the same business module, like-named arguments (of the same type) are shared across some or all of the business functions.</span></span> <span data-ttu-id="790b6-137">您可以使用通配符 (\*) 代替业务功能名称。</span><span class="sxs-lookup"><span data-stu-id="790b6-137">You can use the wildcard character (\*) instead of the business function name.</span></span> <span data-ttu-id="790b6-138">例如：</span><span class="sxs-lookup"><span data-stu-id="790b6-138">For example:</span></span>  
  
```  
B4200310.*.szBusinessUnit  
```  
  
> [!NOTE]
>  <span data-ttu-id="790b6-139">当将 JD Edwards OneWorld 业务进程导入到另一台计算机中时，您必须手动复制 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="790b6-139">When importing a JD Edwards OneWorld business process to another computer, you must copy jdearglist.txt manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790b6-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="790b6-140">See Also</span></span>  
 <span data-ttu-id="790b6-141">[设置字符串理由 Jdearglist 中](../core/setting-string-justification-in-jdearglist.md) </span><span class="sxs-lookup"><span data-stu-id="790b6-141">[Setting String Justification in Jdearglist](../core/setting-string-justification-in-jdearglist.md) </span></span>  
 [<span data-ttu-id="790b6-142">附录 A：数据类型</span><span class="sxs-lookup"><span data-stu-id="790b6-142">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)