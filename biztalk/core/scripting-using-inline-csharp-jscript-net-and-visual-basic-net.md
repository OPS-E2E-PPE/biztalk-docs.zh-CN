---
title: 使用内联编写脚本C#，JScript.NET 和 Visual Basic.NET |Microsoft Docs
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
ms.openlocfilehash: 74eca3ecd01af709b6b8c7aefe250e02679445a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251228"
---
# <a name="scripting-using-inline-c-jscript-net-and-visual-basic-net"></a><span data-ttu-id="242ad-102">使用内联 C#、 JScript.NET 和 Visual Basic.NET 编写脚本</span><span class="sxs-lookup"><span data-stu-id="242ad-102">Scripting Using Inline C#, JScript .NET, and Visual Basic .NET</span></span>
<span data-ttu-id="242ad-103">内联脚本非常方便的应用程序中不太可能使用在其他位置的自定义代码。</span><span class="sxs-lookup"><span data-stu-id="242ad-103">Inline scripts are convenient for custom code that you are unlikely to use elsewhere in your application.</span></span>  
  
 <span data-ttu-id="242ad-104">BizTalk 将内联脚本保存在定义映射的可扩展样式表语言转换 (XSLT) 样式表中。</span><span class="sxs-lookup"><span data-stu-id="242ad-104">BizTalk saves inline scripts in the Extensible Stylesheet Language Transformations (XSLT) stylesheet defining the map.</span></span> <span data-ttu-id="242ad-105">因此，内联脚本可能会作为任何其他 XSLT 样式表脚本使用相同的命名空间。</span><span class="sxs-lookup"><span data-stu-id="242ad-105">Because of this, inline scripts may use the same namespaces as any other XSLT stylesheet script.</span></span> <span data-ttu-id="242ad-106">下表显示可用命名空间。</span><span class="sxs-lookup"><span data-stu-id="242ad-106">The following table shows the available namespaces.</span></span>  
  
|<span data-ttu-id="242ad-107">命名空间</span><span class="sxs-lookup"><span data-stu-id="242ad-107">Namespace</span></span>|<span data-ttu-id="242ad-108">Description</span><span class="sxs-lookup"><span data-stu-id="242ad-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="242ad-109">系统</span><span class="sxs-lookup"><span data-stu-id="242ad-109">System</span></span>|<span data-ttu-id="242ad-110">系统类。</span><span class="sxs-lookup"><span data-stu-id="242ad-110">The System class.</span></span>|  
|<span data-ttu-id="242ad-111">System.Collection</span><span class="sxs-lookup"><span data-stu-id="242ad-111">System.Collection</span></span>|<span data-ttu-id="242ad-112">集合类。</span><span class="sxs-lookup"><span data-stu-id="242ad-112">The collection classes.</span></span>|  
|<span data-ttu-id="242ad-113">System.Text</span><span class="sxs-lookup"><span data-stu-id="242ad-113">System.Text</span></span>|<span data-ttu-id="242ad-114">文本类。</span><span class="sxs-lookup"><span data-stu-id="242ad-114">The text classes.</span></span>|  
|<span data-ttu-id="242ad-115">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="242ad-115">System.Text.RegularExpressions</span></span>|<span data-ttu-id="242ad-116">中的正则表达式类。</span><span class="sxs-lookup"><span data-stu-id="242ad-116">The regular expression classes.</span></span>|  
|<span data-ttu-id="242ad-117">System.Xml</span><span class="sxs-lookup"><span data-stu-id="242ad-117">System.Xml</span></span>|<span data-ttu-id="242ad-118">核心 XML 类。</span><span class="sxs-lookup"><span data-stu-id="242ad-118">The core XML classes.</span></span>|  
|<span data-ttu-id="242ad-119">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="242ad-119">System.Xml.Xsl</span></span>|<span data-ttu-id="242ad-120">XSLT 类。</span><span class="sxs-lookup"><span data-stu-id="242ad-120">The XSLT classes.</span></span>|  
|<span data-ttu-id="242ad-121">System.Xml.Xpath</span><span class="sxs-lookup"><span data-stu-id="242ad-121">System.Xml.Xpath</span></span>|<span data-ttu-id="242ad-122">XPath 类。</span><span class="sxs-lookup"><span data-stu-id="242ad-122">The XPath classes.</span></span>|  
|<span data-ttu-id="242ad-123">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="242ad-123">Microsoft.VisualBasic</span></span>|<span data-ttu-id="242ad-124">Visual Basic 脚本类。</span><span class="sxs-lookup"><span data-stu-id="242ad-124">The Visual Basic script classes.</span></span>|  
  
 <span data-ttu-id="242ad-125">有关命名空间和数据类型的详细信息，搜索"使用 XSLT 样式表脚本\<msxsl: script\>"和"system.xml.xsl.xslcompiledtransform".NET Framework 集合中。</span><span class="sxs-lookup"><span data-stu-id="242ad-125">For more information about namespaces and data types, search on "XSLT Stylesheet Scripting using \<msxsl:script\>" and on "System.Xml.Xsl.XslCompiledTransform" in the .NET Framework collection.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="242ad-126">避免多次使用相同的方法签名。</span><span class="sxs-lookup"><span data-stu-id="242ad-126">Avoid using the same method signature more than once.</span></span> <span data-ttu-id="242ad-127">当多个脚本 functoid 具有相同的方法签名时，BizTalk 选择第一个实现，并忽略其他。</span><span class="sxs-lookup"><span data-stu-id="242ad-127">When several Scripting functoids have the same method signature, BizTalk selects the first implementation and disregards the others.</span></span>  
  
 <span data-ttu-id="242ad-128">除了便于一次性脚本之外，内联脚本还可以用于声明多个脚本中使用的全局变量。</span><span class="sxs-lookup"><span data-stu-id="242ad-128">In addition to being convenient for one-time scripts, inline scripts are also useful for declaring global variables for use among a number of scripts.</span></span> <span data-ttu-id="242ad-129">例如，在C#内联脚本，则可以放入以下任何类之外的代码行。</span><span class="sxs-lookup"><span data-stu-id="242ad-129">For example, in a C# inline script, you could place the following line of code outside of any class.</span></span>  
  
```  
ArrayList statusList = new ArrayList();  
```  
  
 <span data-ttu-id="242ad-130">这将创建**ArrayList**， `statusList`，供在映射中的所有内联脚本。</span><span class="sxs-lookup"><span data-stu-id="242ad-130">This creates an **ArrayList**, `statusList`, available to all inline scripts in the map.</span></span>  
  
 <span data-ttu-id="242ad-131">内联脚本的示例，请参阅[XML 工具 （BizTalk Server 示例文件夹）](../core/xml-tools-biztalk-server-samples-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="242ad-131">For a sample inline script, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="242ad-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="242ad-132">See Also</span></span>  
 <span data-ttu-id="242ad-133">[脚本 Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="242ad-133">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="242ad-134">[使用外部程序集编写脚本](../core/scripting-using-external-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="242ad-134">[Scripting Using External Assemblies](../core/scripting-using-external-assemblies.md) </span></span>  
 <span data-ttu-id="242ad-135">[使用内联 XSLT 和 XSLT 调用模板编写脚本](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="242ad-135">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 <span data-ttu-id="242ad-136">[如何向映射添加脚本 Functoid](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="242ad-136">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="242ad-137">如何配置脚本 Functoid</span><span class="sxs-lookup"><span data-stu-id="242ad-137">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)