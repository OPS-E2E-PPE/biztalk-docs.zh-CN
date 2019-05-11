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
ms.openlocfilehash: 4a86b4b04b481e094efe703190c8da7dd86e0c14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387607"
---
# <a name="handling-string-values"></a><span data-ttu-id="3b68b-102">处理字符串值</span><span class="sxs-lookup"><span data-stu-id="3b68b-102">Handling String Values</span></span>
<span data-ttu-id="3b68b-103">本主题介绍如何将某些字符串参数配置为右对齐 （并向左填充）。</span><span class="sxs-lookup"><span data-stu-id="3b68b-103">This topic describes how to configure certain string arguments as right-justified (and left padded).</span></span>  
  
## <a name="types-of-string-values"></a><span data-ttu-id="3b68b-104">字符串值的类型</span><span class="sxs-lookup"><span data-stu-id="3b68b-104">Types of String Values</span></span>  
 <span data-ttu-id="3b68b-105">JD Edwards OneWorld 公开两种类型的字符串值，通过其互操作性层：</span><span class="sxs-lookup"><span data-stu-id="3b68b-105">JD Edwards OneWorld exposes two kinds of string values through its interoperability layer:</span></span>  
  
- <span data-ttu-id="3b68b-106">单个字符的字符：</span><span class="sxs-lookup"><span data-stu-id="3b68b-106">Char: a single character</span></span>  
  
- <span data-ttu-id="3b68b-107">最大长度的字符串</span><span class="sxs-lookup"><span data-stu-id="3b68b-107">maximum length string</span></span>  
  
  <span data-ttu-id="3b68b-108">JD Edwards OneWorld 使用匈牙利表示法来命名业务函数中这些类型的参数。</span><span class="sxs-lookup"><span data-stu-id="3b68b-108">JD Edwards OneWorld uses Hungarian notation to name the arguments of these types in the business functions.</span></span> <span data-ttu-id="3b68b-109">例如，这些类型的参数以开始使用：</span><span class="sxs-lookup"><span data-stu-id="3b68b-109">For example, arguments of these types begin with:</span></span>  
  
- <span data-ttu-id="3b68b-110">c</span><span class="sxs-lookup"><span data-stu-id="3b68b-110">c</span></span>  
  
- <span data-ttu-id="3b68b-111">sz</span><span class="sxs-lookup"><span data-stu-id="3b68b-111">sz</span></span>  
  
### <a name="left-justified-values"></a><span data-ttu-id="3b68b-112">左对齐值</span><span class="sxs-lookup"><span data-stu-id="3b68b-112">Left-Justified Values</span></span>  
 <span data-ttu-id="3b68b-113">对于大多数 sz 类型参数，最大长度字符串或字符数组，JD Edwards OneWorld 期望左对齐值。</span><span class="sxs-lookup"><span data-stu-id="3b68b-113">For a majority of sz-type arguments, maximum length string or char array, JD Edwards OneWorld expects a left-justified value.</span></span> <span data-ttu-id="3b68b-114">街道地址行，其最大长度为 40，JD Edwards OneWorld 期望 （例如）：</span><span class="sxs-lookup"><span data-stu-id="3b68b-114">For a street address line, which is of maximum length 40, JD Edwards OneWorld expects (for example):</span></span>  
  
 <span data-ttu-id="3b68b-115">"4567 Main St."</span><span class="sxs-lookup"><span data-stu-id="3b68b-115">"4567 Main St.       "</span></span>  
  
 <span data-ttu-id="3b68b-116">填充到长度 40 具有空白。</span><span class="sxs-lookup"><span data-stu-id="3b68b-116">padded to length 40 with blanks.</span></span> <span data-ttu-id="3b68b-117">不是你输入填充，因为用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供这为你所必需的。</span><span class="sxs-lookup"><span data-stu-id="3b68b-117">It is not necessary for you to enter the padding because Microsoft BizTalk Adapter for JD Edwards OneWorld provides this for you.</span></span> <span data-ttu-id="3b68b-118">只需在客户端代码中输入"4567 Main St."。</span><span class="sxs-lookup"><span data-stu-id="3b68b-118">You only need to enter "4567 Main St.", in your client code.</span></span>  
  
### <a name="right-justified-values"></a><span data-ttu-id="3b68b-119">右对齐值</span><span class="sxs-lookup"><span data-stu-id="3b68b-119">Right-Justified Values</span></span>  
 <span data-ttu-id="3b68b-120">此类型的值的一些子集，JD Edwards OneWorld 预期值右对齐，左边填充。</span><span class="sxs-lookup"><span data-stu-id="3b68b-120">For some subset of values for this type, JD Edwards OneWorld expects values that are right justified with padding on the left.</span></span> <span data-ttu-id="3b68b-121">例如，对于 B4200310 源模块中的业务函数，参数 szBusinessUnit 是长度为 12。</span><span class="sxs-lookup"><span data-stu-id="3b68b-121">For example, for business functions in the B4200310 source module, the argument szBusinessUnit is of length 12.</span></span> <span data-ttu-id="3b68b-122">此参数表示工厂，例如生产设施。</span><span class="sxs-lookup"><span data-stu-id="3b68b-122">This argument represents a plant, such as a production facility.</span></span> <span data-ttu-id="3b68b-123">为 30，J.D.工厂数</span><span class="sxs-lookup"><span data-stu-id="3b68b-123">For a plant number of 30, J.D.</span></span> <span data-ttu-id="3b68b-124">Edwards OneWorld XE 预期值：</span><span class="sxs-lookup"><span data-stu-id="3b68b-124">Edwards OneWorld XE expects a value of:</span></span>  
  
 <span data-ttu-id="3b68b-125">"          30"</span><span class="sxs-lookup"><span data-stu-id="3b68b-125">"          30"</span></span>  
  
 <span data-ttu-id="3b68b-126">若要输入一个值，将为右对齐，必须在称为 jdearglist.txt 文件中输入参数。</span><span class="sxs-lookup"><span data-stu-id="3b68b-126">To enter a value that will be right-justified, you must enter the parameter in a file called jdearglist.txt.</span></span> <span data-ttu-id="3b68b-127">生成架构时将读取 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="3b68b-127">The jdearglist.txt is read when you generate the schema.</span></span> <span data-ttu-id="3b68b-128">此文本文件中列出的任何值自动转换为右对齐值并填充在左边空白区域。</span><span class="sxs-lookup"><span data-stu-id="3b68b-128">Any value that is listed in this text file is automatically converted to a right-justified value and padded on the left with blanks.</span></span>  
  
 <span data-ttu-id="3b68b-129">必须创建 jdearglist.txt 使用文本编辑器中，具有条目描述这些参数，并将其保存在以下文件夹中： %BizTalk_Install_Adapter%\config\JDE\\</span><span class="sxs-lookup"><span data-stu-id="3b68b-129">You must create jdearglist.txt using a text editor, with entries describing these parameters, and save it in the following folder: %BizTalk_Install_Adapter%\config\JDE\\</span></span>  
  
 <span data-ttu-id="3b68b-130">其中 **%biztalk_install_adapter%** 是适用于 JD Edwards OneWorld 安装 BizTalk 适配器的目录。</span><span class="sxs-lookup"><span data-stu-id="3b68b-130">Where **%BizTalk_Install_Adapter%** is the directory in which you installed BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
 <span data-ttu-id="3b68b-131">如果此文件不存在或为空，适配器首次打开时在 JD Edwards OneWorld 日志的 BizTalk 适配器将显示一条信息性消息。</span><span class="sxs-lookup"><span data-stu-id="3b68b-131">If this file does not exist or is empty, an informational message appears in the BizTalk Adapter for JD Edwards OneWorld log when the adapter first opens.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b68b-132">如果您生成架构后更改此文件，必须重新生成架构以刷新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="3b68b-132">If you change this file after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span>  
  
 <span data-ttu-id="3b68b-133">若要验证此文件中使用的最新信息，可以使用任务管理器重新生成架构; 先停止 browsingagent.exe 进程但是，这应不是必要。</span><span class="sxs-lookup"><span data-stu-id="3b68b-133">To verify that you are using the latest information in this file, you can use the Task Manager to stop the browsingagent.exe process before regenerating your schema; however, this should not be necessary.</span></span>  
  
 <span data-ttu-id="3b68b-134">以下是 jdearglist.txt 文件中的条目的格式示例：</span><span class="sxs-lookup"><span data-stu-id="3b68b-134">The following is an example of the format for entries in the jdearglist.txt file:</span></span>  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
```  
  
 <span data-ttu-id="3b68b-135">例如：</span><span class="sxs-lookup"><span data-stu-id="3b68b-135">For example:</span></span>  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 <span data-ttu-id="3b68b-136">对于属于同一业务模块的业务功能集，在某些或所有业务功能共享 like-named 参数 （属于同一类型）。</span><span class="sxs-lookup"><span data-stu-id="3b68b-136">For a set of business functions belonging to the same business module, like-named arguments (of the same type) are shared across some or all of the business functions.</span></span> <span data-ttu-id="3b68b-137">您可以使用通配符 （\*） 代替业务功能名称。</span><span class="sxs-lookup"><span data-stu-id="3b68b-137">You can use the wildcard character (\*) instead of the business function name.</span></span> <span data-ttu-id="3b68b-138">例如：</span><span class="sxs-lookup"><span data-stu-id="3b68b-138">For example:</span></span>  
  
```  
B4200310.*.szBusinessUnit  
```  
  
> [!NOTE]
>  <span data-ttu-id="3b68b-139">当 JD Edwards OneWorld 业务流程导入另一台计算机，则必须手动复制 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="3b68b-139">When importing a JD Edwards OneWorld business process to another computer, you must copy jdearglist.txt manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b68b-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b68b-140">See Also</span></span>  
 <span data-ttu-id="3b68b-141">[在 Jdearglist 中设置字符串对齐](../core/setting-string-justification-in-jdearglist.md) </span><span class="sxs-lookup"><span data-stu-id="3b68b-141">[Setting String Justification in Jdearglist](../core/setting-string-justification-in-jdearglist.md) </span></span>  
 [<span data-ttu-id="3b68b-142">附录 a:数据类型</span><span class="sxs-lookup"><span data-stu-id="3b68b-142">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)