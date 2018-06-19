---
title: 脚本使用内联 C#、 JScript.NET 和 Visual Basic.NET |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, JScript
- Scripting functoids, warnings
- Scripting functoids, Visual Basic .NET
- Scripting functoids, inline C#
- Scripting functoids, .NET
ms.assetid: dda60024-58bd-483f-a750-31b21059eded
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe2002bd92342a953406a21e076b801d3e90b938
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974539"
---
# <a name="scripting-using-inline-c-jscript-net-and-visual-basic-net"></a><span data-ttu-id="20c18-102">使用内联 C#、JScript .NET 和 Visual Basic .NET 编写脚本</span><span class="sxs-lookup"><span data-stu-id="20c18-102">Scripting Using Inline C#, JScript .NET, and Visual Basic .NET</span></span>
<span data-ttu-id="20c18-103">对于在应用程序中其他地方不太可能使用的自定义代码，使用内联脚本非常方便。</span><span class="sxs-lookup"><span data-stu-id="20c18-103">Inline scripts are convenient for custom code that you are unlikely to use elsewhere in your application.</span></span>  
  
 <span data-ttu-id="20c18-104">BizTalk 将内联脚本保存在定义映射的可扩展样式表语言转换 (XSLT) 样式表中。</span><span class="sxs-lookup"><span data-stu-id="20c18-104">BizTalk saves inline scripts in the Extensible Stylesheet Language Transformations (XSLT) stylesheet defining the map.</span></span> <span data-ttu-id="20c18-105">因此，内联脚本可以与其他任何 XSLT 样式表脚本使用相同的命名空间。</span><span class="sxs-lookup"><span data-stu-id="20c18-105">Because of this, inline scripts may use the same namespaces as any other XSLT stylesheet script.</span></span> <span data-ttu-id="20c18-106">下表显示了可用的命名空间：</span><span class="sxs-lookup"><span data-stu-id="20c18-106">The following table shows the available namespaces.</span></span>  
  
|<span data-ttu-id="20c18-107">命名空间</span><span class="sxs-lookup"><span data-stu-id="20c18-107">Namespace</span></span>|<span data-ttu-id="20c18-108">Description</span><span class="sxs-lookup"><span data-stu-id="20c18-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="20c18-109">系统</span><span class="sxs-lookup"><span data-stu-id="20c18-109">System</span></span>|<span data-ttu-id="20c18-110">系统类。</span><span class="sxs-lookup"><span data-stu-id="20c18-110">The System class.</span></span>|  
|<span data-ttu-id="20c18-111">System.Collection</span><span class="sxs-lookup"><span data-stu-id="20c18-111">System.Collection</span></span>|<span data-ttu-id="20c18-112">集合类。</span><span class="sxs-lookup"><span data-stu-id="20c18-112">The collection classes.</span></span>|  
|<span data-ttu-id="20c18-113">System.Text</span><span class="sxs-lookup"><span data-stu-id="20c18-113">System.Text</span></span>|<span data-ttu-id="20c18-114">文本类。</span><span class="sxs-lookup"><span data-stu-id="20c18-114">The text classes.</span></span>|  
|<span data-ttu-id="20c18-115">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="20c18-115">System.Text.RegularExpressions</span></span>|<span data-ttu-id="20c18-116">正则表达式类。</span><span class="sxs-lookup"><span data-stu-id="20c18-116">The regular expression classes.</span></span>|  
|<span data-ttu-id="20c18-117">System.Xml</span><span class="sxs-lookup"><span data-stu-id="20c18-117">System.Xml</span></span>|<span data-ttu-id="20c18-118">核心 XML 类。</span><span class="sxs-lookup"><span data-stu-id="20c18-118">The core XML classes.</span></span>|  
|<span data-ttu-id="20c18-119">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="20c18-119">System.Xml.Xsl</span></span>|<span data-ttu-id="20c18-120">XSLT 类。</span><span class="sxs-lookup"><span data-stu-id="20c18-120">The XSLT classes.</span></span>|  
|<span data-ttu-id="20c18-121">System.Xml.Xpath</span><span class="sxs-lookup"><span data-stu-id="20c18-121">System.Xml.Xpath</span></span>|<span data-ttu-id="20c18-122">XPath 类。</span><span class="sxs-lookup"><span data-stu-id="20c18-122">The XPath classes.</span></span>|  
|<span data-ttu-id="20c18-123">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="20c18-123">Microsoft.VisualBasic</span></span>|<span data-ttu-id="20c18-124">Visual Basic 脚本类。</span><span class="sxs-lookup"><span data-stu-id="20c18-124">The Visual Basic script classes.</span></span>|  
  
 <span data-ttu-id="20c18-125">有关命名空间和数据类型的详细信息，搜索"XSLT 样式表脚本使用\<msxsl: script\>"和"System.Xml.Xsl.XslCompiledTransform".NET Framework 集合中。</span><span class="sxs-lookup"><span data-stu-id="20c18-125">For more information about namespaces and data types, search on "XSLT Stylesheet Scripting using \<msxsl:script\>" and on "System.Xml.Xsl.XslCompiledTransform" in the .NET Framework collection.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="20c18-126">应避免多次使用同一个方法签名。</span><span class="sxs-lookup"><span data-stu-id="20c18-126">Avoid using the same method signature more than once.</span></span> <span data-ttu-id="20c18-127">如果多个“脚本”functoid 具有相同的方法签名，则 BizTalk 会选择实现的第一个方法签名，而忽略其他签名。</span><span class="sxs-lookup"><span data-stu-id="20c18-127">When several Scripting functoids have the same method signature, BizTalk selects the first implementation and disregards the others.</span></span>  
  
 <span data-ttu-id="20c18-128">除对于一次性脚本很方便之外，内联脚本对于声明在多个脚本中使用的全局变量也很有用。</span><span class="sxs-lookup"><span data-stu-id="20c18-128">In addition to being convenient for one-time scripts, inline scripts are also useful for declaring global variables for use among a number of scripts.</span></span> <span data-ttu-id="20c18-129">例如，在 C# 内联脚本中，可以将以下代码行放在任何类之外：</span><span class="sxs-lookup"><span data-stu-id="20c18-129">For example, in a C# inline script, you could place the following line of code outside of any class.</span></span>  
  
```  
ArrayList statusList = new ArrayList();  
```  
  
 <span data-ttu-id="20c18-130">这将创建**ArrayList**， `statusList`，供在映射中的所有内联脚本。</span><span class="sxs-lookup"><span data-stu-id="20c18-130">This creates an **ArrayList**, `statusList`, available to all inline scripts in the map.</span></span>  
  
 <span data-ttu-id="20c18-131">一个内联脚本示例，请参阅[（BizTalk Server 示例文件夹中） 的 XML 工具](../core/xml-tools-biztalk-server-samples-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="20c18-131">For a sample inline script, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20c18-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20c18-132">See Also</span></span>  
 <span data-ttu-id="20c18-133">[脚本 Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="20c18-133">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="20c18-134">[脚本使用外部程序集](../core/scripting-using-external-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="20c18-134">[Scripting Using External Assemblies](../core/scripting-using-external-assemblies.md) </span></span>  
 <span data-ttu-id="20c18-135">[脚本使用内联 XSLT 和 XSLT 调用模板](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="20c18-135">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 <span data-ttu-id="20c18-136">[如何在向地图添加脚本 Functoid](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="20c18-136">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="20c18-137">如何配置脚本 Functoid</span><span class="sxs-lookup"><span data-stu-id="20c18-137">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)