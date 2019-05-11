---
title: 处理字符串 Values2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- string values, configuring
- formatting strings
- strings, formatting
- left-justified string values
- jdearglist.txt
- strings, left-justified
- right-justified string values
- strings, right-justified
ms.assetid: 23d54731-b2b9-4610-a533-e041237e0bb3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54d6e6ca9af087139b48465624a681aa5e6125d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344361"
---
# <a name="handling-string-values"></a><span data-ttu-id="0b460-102">处理字符串值</span><span class="sxs-lookup"><span data-stu-id="0b460-102">Handling String Values</span></span>
<span data-ttu-id="0b460-103">本主题介绍如何将某些字符串参数配置为右对齐 （并向左填充）。</span><span class="sxs-lookup"><span data-stu-id="0b460-103">This topic describes how to configure certain string arguments as right-justified (and left padded).</span></span>  
  
## <a name="types-of-string-values"></a><span data-ttu-id="0b460-104">字符串值的类型</span><span class="sxs-lookup"><span data-stu-id="0b460-104">Types of String Values</span></span>  
 <span data-ttu-id="0b460-105">JD Edwards EnterpriseOne 公开两种类型的字符串值，通过其互操作性层：</span><span class="sxs-lookup"><span data-stu-id="0b460-105">JD Edwards EnterpriseOne exposes two kinds of string values through its interoperability layer:</span></span>  
  
- <span data-ttu-id="0b460-106">单个字符的字符：</span><span class="sxs-lookup"><span data-stu-id="0b460-106">char: a single character</span></span>  
  
- <span data-ttu-id="0b460-107">最大长度的字符串</span><span class="sxs-lookup"><span data-stu-id="0b460-107">maximum length string</span></span>  
  
  <span data-ttu-id="0b460-108">JD Edwards EnterpriseOne 使用匈牙利表示法来命名业务函数中这些类型的参数。</span><span class="sxs-lookup"><span data-stu-id="0b460-108">JD Edwards EnterpriseOne uses Hungarian notation to name the arguments of these types in the business functions.</span></span> <span data-ttu-id="0b460-109">例如，这些类型的参数以开始使用：</span><span class="sxs-lookup"><span data-stu-id="0b460-109">For example, arguments of these types begin with:</span></span>  
  
- <span data-ttu-id="0b460-110">c</span><span class="sxs-lookup"><span data-stu-id="0b460-110">c</span></span>  
  
- <span data-ttu-id="0b460-111">sz</span><span class="sxs-lookup"><span data-stu-id="0b460-111">sz</span></span>  
  
### <a name="left-justified-values"></a><span data-ttu-id="0b460-112">左对齐值</span><span class="sxs-lookup"><span data-stu-id="0b460-112">Left-Justified Values</span></span>  
 <span data-ttu-id="0b460-113">对于大多数 sz 类型参数，最大长度字符串或字符数组，JD Edwards EnterpriseOne 期望左对齐值。</span><span class="sxs-lookup"><span data-stu-id="0b460-113">For a majority of sz-type arguments, maximum length string or char array, JD Edwards EnterpriseOne expects a left-justified value.</span></span> <span data-ttu-id="0b460-114">例如，对于街道地址行，即的最大长度为 40，JD Edwards EnterpriseOne 期望 （例如）：</span><span class="sxs-lookup"><span data-stu-id="0b460-114">For examples, for a street address line, which is of maximum length 40, JD Edwards EnterpriseOne expects (for example):</span></span>  
  
 <span data-ttu-id="0b460-115">"4567 Main St."</span><span class="sxs-lookup"><span data-stu-id="0b460-115">"4567 Main St.    "</span></span>  
  
 <span data-ttu-id="0b460-116">填充到长度 40 具有空白。</span><span class="sxs-lookup"><span data-stu-id="0b460-116">padded to length 40 with blanks.</span></span> <span data-ttu-id="0b460-117">不是你输入填充，因为用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器提供这为你所必需的。</span><span class="sxs-lookup"><span data-stu-id="0b460-117">It is not necessary for you to enter the padding because Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides this for you.</span></span> <span data-ttu-id="0b460-118">只需在客户端代码中输入"4567 Main St."。</span><span class="sxs-lookup"><span data-stu-id="0b460-118">You only need to enter "4567 Main St ", in your client code.</span></span>  
  
### <a name="right-justified-values"></a><span data-ttu-id="0b460-119">右对齐值</span><span class="sxs-lookup"><span data-stu-id="0b460-119">Right-Justified Values</span></span>  
 <span data-ttu-id="0b460-120">此类型的值的一些子集，JD Edwards EnterpriseOne 期望右对齐，左边填充的值。</span><span class="sxs-lookup"><span data-stu-id="0b460-120">For some subset of values for this type, JD Edwards EnterpriseOne expects values that are right justified with padding on the left.</span></span> <span data-ttu-id="0b460-121">例如，对于 B4200310 源模块中的业务函数，参数 szBusinessUnit 是长度为 12。</span><span class="sxs-lookup"><span data-stu-id="0b460-121">For example, for business functions in the B4200310 source module, the argument szBusinessUnit is of length 12.</span></span> <span data-ttu-id="0b460-122">此参数表示工厂，例如生产设施。</span><span class="sxs-lookup"><span data-stu-id="0b460-122">This argument represents a plant, such as a production facility.</span></span> <span data-ttu-id="0b460-123">对于 30 的工厂号码，JD Edwards EnterpriseOne 期望的值：</span><span class="sxs-lookup"><span data-stu-id="0b460-123">For a plant number of 30, JD Edwards EnterpriseOne expects a value of:</span></span>  
  
 <span data-ttu-id="0b460-124">"           30"</span><span class="sxs-lookup"><span data-stu-id="0b460-124">"           30"</span></span>  
  
 <span data-ttu-id="0b460-125">若要输入一个值，将为右对齐，必须在称为 jdearglist.txt 文件中输入参数。</span><span class="sxs-lookup"><span data-stu-id="0b460-125">To enter a value that will be right-justified, you must enter the parameter in a file called jdearglist.txt.</span></span> <span data-ttu-id="0b460-126">生成架构时将读取 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="0b460-126">The jdearglist.txt is read when you generate the schema.</span></span> <span data-ttu-id="0b460-127">此文本文件中的任何值自动转换为右对齐值并填充在左边空白区域。</span><span class="sxs-lookup"><span data-stu-id="0b460-127">Any value in this text file is automatically converted to a right-justified value and padded on the left with blanks.</span></span>  
  
 <span data-ttu-id="0b460-128">必须创建 jdearglist.txt 使用文本编辑器中，具有条目描述这些参数，并将其保存在以下文件夹中：</span><span class="sxs-lookup"><span data-stu-id="0b460-128">You must create jdearglist.txt using a text editor, with entries describing these parameters, and save it in the following folder:</span></span>  
  
 <span data-ttu-id="0b460-129">C:\Program Files\Microsoft BizTalk Adapters\JDEEnterpriseOne\config</span><span class="sxs-lookup"><span data-stu-id="0b460-129">C:\Program Files\Microsoft BizTalk Adapters\JDEEnterpriseOne\config</span></span>  
  
 <span data-ttu-id="0b460-130">如果此文件不存在或为空，一条信息性消息将显示在 BizTalk 适配器用于 JD Edwards EnterpriseOne 日志适配器首次打开时。</span><span class="sxs-lookup"><span data-stu-id="0b460-130">If this file does not exist or is empty, an informational message appears in BizTalk Adapter for JD Edwards EnterpriseOne log when the adapter first opens.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b460-131">如果您生成架构后更改此文件，必须重新生成架构以刷新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="0b460-131">If you change this file after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="0b460-132">若要验证此文件中使用的最新信息，可以使用任务管理器重新生成架构; 先停止 browsingagent.exe 进程但是，这应不是必要。</span><span class="sxs-lookup"><span data-stu-id="0b460-132">To verify that you are using the latest information in this file, you can use the Task Manager to stop the browsingagent.exe process before regenerating your schema; however, this should not be necessary.</span></span>  
  
 <span data-ttu-id="0b460-133">以下是 jdearglist.txt 文件中的条目的格式示例：</span><span class="sxs-lookup"><span data-stu-id="0b460-133">The following is an example of the format for entries in the jdearglist.txt file:</span></span>  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
  
```  
  
 <span data-ttu-id="0b460-134">例如：</span><span class="sxs-lookup"><span data-stu-id="0b460-134">For example:</span></span>  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 <span data-ttu-id="0b460-135">对于属于同一业务模块的业务功能集，在某些或所有业务功能共享 like-named 参数 （属于同一类型）。</span><span class="sxs-lookup"><span data-stu-id="0b460-135">For a set of business functions belonging to the same business module, like-named arguments (of the same type) are shared across some or all of the business functions.</span></span> <span data-ttu-id="0b460-136">您可以使用通配符 （\*） 代替业务功能名称。</span><span class="sxs-lookup"><span data-stu-id="0b460-136">You can use the wildcard character (\*) instead of the business function name.</span></span> <span data-ttu-id="0b460-137">例如：</span><span class="sxs-lookup"><span data-stu-id="0b460-137">For example:</span></span>  
  
```  
B4200310.*.szBusinessUnit  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="0b460-138">当 JD Edwards EnterpriseOne 业务流程导入另一台计算机，则必须手动复制 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="0b460-138">When importing a JD Edwards EnterpriseOne business process to another computer, you must copy jdearglist.txt manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b460-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b460-139">See Also</span></span>  
 [<span data-ttu-id="0b460-140">附录 b:数据类型</span><span class="sxs-lookup"><span data-stu-id="0b460-140">Appendix B: Data Types</span></span>](../core/appendix-b-data-types.md)