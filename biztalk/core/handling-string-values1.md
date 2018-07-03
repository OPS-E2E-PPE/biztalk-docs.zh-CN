---
title: 处理字符串 Values1 |Microsoft Docs
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
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51397965a416169c8f71ffef8d9466f99f30c093
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988910"
---
# <a name="handling-string-values"></a><span data-ttu-id="77138-102">处理字符串值</span><span class="sxs-lookup"><span data-stu-id="77138-102">Handling String Values</span></span>
<span data-ttu-id="77138-103">本主题介绍如何将某些字符串参数配置为右对齐（并向左填充）。</span><span class="sxs-lookup"><span data-stu-id="77138-103">This topic describes how to configure certain string arguments as right-justified (and left padded).</span></span>  
  
## <a name="types-of-string-values"></a><span data-ttu-id="77138-104">字符串值的类型</span><span class="sxs-lookup"><span data-stu-id="77138-104">Types of String Values</span></span>  
 <span data-ttu-id="77138-105">JD Edwards OneWorld 通过互操作性层显示两种字符串值：</span><span class="sxs-lookup"><span data-stu-id="77138-105">JD Edwards OneWorld exposes two kinds of string values through its interoperability layer:</span></span>  
  
- <span data-ttu-id="77138-106">单个字符的字符：</span><span class="sxs-lookup"><span data-stu-id="77138-106">Char: a single character</span></span>  
  
- <span data-ttu-id="77138-107">最大长度字符串</span><span class="sxs-lookup"><span data-stu-id="77138-107">maximum length string</span></span>  
  
  <span data-ttu-id="77138-108">JD Edwards OneWorld 使用匈牙利符号命名业务函数中这些类型的参数。</span><span class="sxs-lookup"><span data-stu-id="77138-108">JD Edwards OneWorld uses Hungarian notation to name the arguments of these types in the business functions.</span></span> <span data-ttu-id="77138-109">例如，这些类型的参数以下列字符开头：</span><span class="sxs-lookup"><span data-stu-id="77138-109">For example, arguments of these types begin with:</span></span>  
  
- <span data-ttu-id="77138-110">c</span><span class="sxs-lookup"><span data-stu-id="77138-110">c</span></span>  
  
- <span data-ttu-id="77138-111">sz</span><span class="sxs-lookup"><span data-stu-id="77138-111">sz</span></span>  
  
### <a name="left-justified-values"></a><span data-ttu-id="77138-112">左对齐值</span><span class="sxs-lookup"><span data-stu-id="77138-112">Left-Justified Values</span></span>  
 <span data-ttu-id="77138-113">对于大多数的 sz 类型参数，最大长度的字符串或字符数组，JD Edwards OneWorld 应该为左对齐值。</span><span class="sxs-lookup"><span data-stu-id="77138-113">For a majority of sz-type arguments, maximum length string or char array, JD Edwards OneWorld expects a left-justified value.</span></span> <span data-ttu-id="77138-114">对于街道地址行，最大长度为 40，JD Edwards OneWorld 最好为（示例）：</span><span class="sxs-lookup"><span data-stu-id="77138-114">For a street address line, which is of maximum length 40, JD Edwards OneWorld expects (for example):</span></span>  
  
 <span data-ttu-id="77138-115">"4567 Main St."</span><span class="sxs-lookup"><span data-stu-id="77138-115">"4567 Main St.       "</span></span>  
  
 <span data-ttu-id="77138-116">使用空白填充到长度 40。</span><span class="sxs-lookup"><span data-stu-id="77138-116">padded to length 40 with blanks.</span></span> <span data-ttu-id="77138-117">您无需输入填充，因为 JD Edwards OneWorld 的 Microsoft BizTalk 适配器将为您提供填充内容。</span><span class="sxs-lookup"><span data-stu-id="77138-117">It is not necessary for you to enter the padding because Microsoft BizTalk Adapter for JD Edwards OneWorld provides this for you.</span></span> <span data-ttu-id="77138-118">您只需要在客户端代码中输入“4567 Main St.”。</span><span class="sxs-lookup"><span data-stu-id="77138-118">You only need to enter "4567 Main St.", in your client code.</span></span>  
  
### <a name="right-justified-values"></a><span data-ttu-id="77138-119">右对齐值</span><span class="sxs-lookup"><span data-stu-id="77138-119">Right-Justified Values</span></span>  
 <span data-ttu-id="77138-120">对于此类型的某些子集值，JD Edwards OneWorld 预期值右对齐，左边填充。</span><span class="sxs-lookup"><span data-stu-id="77138-120">For some subset of values for this type, JD Edwards OneWorld expects values that are right justified with padding on the left.</span></span> <span data-ttu-id="77138-121">例如，对于 B4200310 源模块中的业务函数，参数 szBusinessUnit 是长度为 12。</span><span class="sxs-lookup"><span data-stu-id="77138-121">For example, for business functions in the B4200310 source module, the argument szBusinessUnit is of length 12.</span></span> <span data-ttu-id="77138-122">此参数表示工厂，例如生产设施。</span><span class="sxs-lookup"><span data-stu-id="77138-122">This argument represents a plant, such as a production facility.</span></span> <span data-ttu-id="77138-123">为 30，J.D.工厂数</span><span class="sxs-lookup"><span data-stu-id="77138-123">For a plant number of 30, J.D.</span></span> <span data-ttu-id="77138-124">Edwards OneWorld XE 预期值：</span><span class="sxs-lookup"><span data-stu-id="77138-124">Edwards OneWorld XE expects a value of:</span></span>  
  
 <span data-ttu-id="77138-125">"          30"</span><span class="sxs-lookup"><span data-stu-id="77138-125">"          30"</span></span>  
  
 <span data-ttu-id="77138-126">若要输入一个值，将为右对齐，必须在称为 jdearglist.txt 文件中输入参数。</span><span class="sxs-lookup"><span data-stu-id="77138-126">To enter a value that will be right-justified, you must enter the parameter in a file called jdearglist.txt.</span></span> <span data-ttu-id="77138-127">生成架构时将读取 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="77138-127">The jdearglist.txt is read when you generate the schema.</span></span> <span data-ttu-id="77138-128">此文本文件中列出的任何值都会自动转化为右对齐的值，并且填充在左边空白区域。</span><span class="sxs-lookup"><span data-stu-id="77138-128">Any value that is listed in this text file is automatically converted to a right-justified value and padded on the left with blanks.</span></span>  
  
 <span data-ttu-id="77138-129">必须创建 jdearglist.txt 使用文本编辑器中，具有条目描述这些参数，并将其保存在以下文件夹中： %BizTalk_Install_Adapter%\config\JDE\\</span><span class="sxs-lookup"><span data-stu-id="77138-129">You must create jdearglist.txt using a text editor, with entries describing these parameters, and save it in the following folder: %BizTalk_Install_Adapter%\config\JDE\\</span></span>  
  
 <span data-ttu-id="77138-130">其中 **%biztalk_install_adapter%** 是适用于 JD Edwards OneWorld 安装 BizTalk 适配器的目录。</span><span class="sxs-lookup"><span data-stu-id="77138-130">Where **%BizTalk_Install_Adapter%** is the directory in which you installed BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
 <span data-ttu-id="77138-131">如果此文件不存在或为空，当适配器首次打开时，信息性消息将出现在 JD Edwards OneWorld 的 BizTalk 适配器日志中。</span><span class="sxs-lookup"><span data-stu-id="77138-131">If this file does not exist or is empty, an informational message appears in the BizTalk Adapter for JD Edwards OneWorld log when the adapter first opens.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77138-132">如果您在生成架构后更改此文件，则必须重新生成架构以刷新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="77138-132">If you change this file after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span>  
  
 <span data-ttu-id="77138-133">要验证您使用的是否是此文件中的最新信息，您可以在重新生成架构之前，使用任务管理器停止 browsingagent.exe 进程；但是，此操作不是必需的。</span><span class="sxs-lookup"><span data-stu-id="77138-133">To verify that you are using the latest information in this file, you can use the Task Manager to stop the browsingagent.exe process before regenerating your schema; however, this should not be necessary.</span></span>  
  
 <span data-ttu-id="77138-134">以下是 jdearglist.txt 文件中条目格式的示例：</span><span class="sxs-lookup"><span data-stu-id="77138-134">The following is an example of the format for entries in the jdearglist.txt file:</span></span>  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
```  
  
 <span data-ttu-id="77138-135">例如：</span><span class="sxs-lookup"><span data-stu-id="77138-135">For example:</span></span>  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 <span data-ttu-id="77138-136">对于属于同一业务模块的一组业务功能，在某些或所有业务功能中共享 like-named 参数（同一类型）。</span><span class="sxs-lookup"><span data-stu-id="77138-136">For a set of business functions belonging to the same business module, like-named arguments (of the same type) are shared across some or all of the business functions.</span></span> <span data-ttu-id="77138-137">您可以使用通配符 (\*) 代替业务功能名称。</span><span class="sxs-lookup"><span data-stu-id="77138-137">You can use the wildcard character (\*) instead of the business function name.</span></span> <span data-ttu-id="77138-138">例如：</span><span class="sxs-lookup"><span data-stu-id="77138-138">For example:</span></span>  
  
```  
B4200310.*.szBusinessUnit  
```  
  
> [!NOTE]
>  <span data-ttu-id="77138-139">当将 JD Edwards OneWorld 业务进程导入到另一台计算机中时，您必须手动复制 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="77138-139">When importing a JD Edwards OneWorld business process to another computer, you must copy jdearglist.txt manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77138-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="77138-140">See Also</span></span>  
 <span data-ttu-id="77138-141">[在 Jdearglist 中设置字符串对齐](../core/setting-string-justification-in-jdearglist.md) </span><span class="sxs-lookup"><span data-stu-id="77138-141">[Setting String Justification in Jdearglist](../core/setting-string-justification-in-jdearglist.md) </span></span>  
 [<span data-ttu-id="77138-142">附录 A：数据类型</span><span class="sxs-lookup"><span data-stu-id="77138-142">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)