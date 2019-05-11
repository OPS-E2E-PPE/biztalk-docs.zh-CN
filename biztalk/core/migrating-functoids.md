---
title: 迁移 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids, migrating
- migrating, maps
- Migrating functoids, about Migrating functoids
- Migrating functoids
- Scripting functoids
- migrating, functoids
- migrating, Scripting functoids
ms.assetid: fc5b3ac9-28c6-41df-b779-15a8c3188528
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc93b7bfd5e6bfb2097e3f190003b63e093b8e64
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394447"
---
# <a name="migrating-functoids"></a><span data-ttu-id="c0e05-102">迁移 Functoid</span><span class="sxs-lookup"><span data-stu-id="c0e05-102">Migrating Functoids</span></span>
<span data-ttu-id="c0e05-103">映射从以前版本的 BizTalk Server 迁移到 BizTalk Server 时，在映射中包含的所有 functoid 也会被都迁移。</span><span class="sxs-lookup"><span data-stu-id="c0e05-103">When you migrate a map from previous versions of BizTalk Server to BizTalk Server, any functoids included in the map are also migrated.</span></span> <span data-ttu-id="c0e05-104">如果不包括迁移的 functoid**脚本**functoid 所需任何其他迁移任务。</span><span class="sxs-lookup"><span data-stu-id="c0e05-104">If the functoids you migrate do not include **Scripting** functoids, no additional migration tasks are required.</span></span> <span data-ttu-id="c0e05-105">但是如果映射中包含**脚本**functoid 或自定义 functoid，您可能必须执行一些其他步骤。</span><span class="sxs-lookup"><span data-stu-id="c0e05-105">However if your map includes **Scripting** functoids or custom functoids, you may have additional steps to perform.</span></span>  
  
 <span data-ttu-id="c0e05-106">在以前版本的 BizTalk Server 中，所有自定义脚本随附**脚本**functoid 编写内联。</span><span class="sxs-lookup"><span data-stu-id="c0e05-106">In previous versions of BizTalk Server, all custom script included with a **Scripting** functoid was written inline.</span></span> <span data-ttu-id="c0e05-107">也就是说时创建该 functoid 后，提取 functoid 在运行时调用的所有脚本与该 functoid 一起都存储。</span><span class="sxs-lookup"><span data-stu-id="c0e05-107">That is, when you created the functoid, all the script the functoid called during run time was stored with the functoid.</span></span> <span data-ttu-id="c0e05-108">如果你想要使用其他 functoid 使用的同一个脚本，您可以复制并粘贴它从一个**脚本**functoid 到另一个，也重写从零开始的脚本。</span><span class="sxs-lookup"><span data-stu-id="c0e05-108">If you wanted to use the same script with a different functoid, you either copied and pasted it from one **Scripting** functoid to another, or you rewrote the script from scratch.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c0e05-109">迁移映射时，如果现有的 functoid 的内联脚本的副本。</span><span class="sxs-lookup"><span data-stu-id="c0e05-109">copies existing inline scripts with the functoids when you migrate a map.</span></span> <span data-ttu-id="c0e05-110">但是，并非所有的脚本可能正常工作。</span><span class="sxs-lookup"><span data-stu-id="c0e05-110">However, not all of the scripts may function correctly.</span></span> <span data-ttu-id="c0e05-111">BizTalk Server 使用 Visual Basic.NET 和 JScript.NET，而不是 VBScript 和 JScript 早期版本中使用。</span><span class="sxs-lookup"><span data-stu-id="c0e05-111">BizTalk Server uses Visual Basic .NET and JScript .NET rather than the VBScript and JScript used in previous versions.</span></span> <span data-ttu-id="c0e05-112">.NET 版本的语言在语法中包括一些更改。</span><span class="sxs-lookup"><span data-stu-id="c0e05-112">The .NET versions of the languages include some changes in syntax.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0e05-113">确保测试你**脚本**迁移后的 functoid。</span><span class="sxs-lookup"><span data-stu-id="c0e05-113">Be sure to test your **Scripting** functoids after migration.</span></span>  
  
 <span data-ttu-id="c0e05-114">你将需要重写自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="c0e05-114">You will need to rewrite custom functoids.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c0e05-115">要求使用.NET framework 自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="c0e05-115">expects custom functoids to use the .NET framework.</span></span> <span data-ttu-id="c0e05-116">它不能使用较旧的、 基于 COM 的自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="c0e05-116">It cannot use the older, COM-based custom functoids.</span></span> <span data-ttu-id="c0e05-117">可以重写自定义 functoid 以使用.NET framework。</span><span class="sxs-lookup"><span data-stu-id="c0e05-117">Custom functoids can be rewritten to use the .NET framework.</span></span> <span data-ttu-id="c0e05-118">自定义 functoid 示例代码，请参阅[自定义 Functoid （BizTalk Server 示例）](../core/custom-functoid-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="c0e05-118">For sample code of a custom functoid, see [Custom Functoid (BizTalk Server Sample)](../core/custom-functoid-biztalk-server-sample.md).</span></span>  
  
 <span data-ttu-id="c0e05-119">一种替代方法是将自定义 functoid 的功能封装在外部程序集并调用通过此程序集**脚本**functoid。</span><span class="sxs-lookup"><span data-stu-id="c0e05-119">An alternative is to wrap the functionality of the custom functoid in an external assembly and call this assembly through a **Scripting** functoid.</span></span> <span data-ttu-id="c0e05-120">以下部分介绍了此过程。</span><span class="sxs-lookup"><span data-stu-id="c0e05-120">The following section describes this process.</span></span>  
  
### <a name="to-migrate-your-custom-functoids"></a><span data-ttu-id="c0e05-121">若要迁移自定义 functoid</span><span class="sxs-lookup"><span data-stu-id="c0e05-121">To migrate your custom functoids</span></span>  
  
1. <span data-ttu-id="c0e05-122">重新创建该 functoid 的.NET 语言，如 Microsoft Visual Basic.NET、 JScript.NET 或 Microsoft Visual C#.NET 功能。</span><span class="sxs-lookup"><span data-stu-id="c0e05-122">Re-create the functionality of the functoid in a .NET language, such as Microsoft Visual Basic .NET, JScript .NET, or Microsoft Visual C# .NET.</span></span>  
  
2. <span data-ttu-id="c0e05-123">创建程序集以包含新功能。</span><span class="sxs-lookup"><span data-stu-id="c0e05-123">Create an assembly to contain the new functionality.</span></span>  
  
3. <span data-ttu-id="c0e05-124">在全局程序集缓存 (GAC) 中注册该程序集。</span><span class="sxs-lookup"><span data-stu-id="c0e05-124">Register the assembly in the global assembly cache (GAC).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c0e05-125">若要在全局程序集缓存中注册程序集，它们必须是强名称并且已签名。</span><span class="sxs-lookup"><span data-stu-id="c0e05-125">To register assemblies in the global assembly cache, they must be strong named and signed.</span></span> <span data-ttu-id="c0e05-126">有关注册程序集的详细信息，请参阅"全局程序集缓存"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]组合集。</span><span class="sxs-lookup"><span data-stu-id="c0e05-126">For more information about registering assemblies, see "Global Assembly Cache" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection.</span></span>  
  
4. <span data-ttu-id="c0e05-127">创建之间的映射中包含的引用**脚本**functoid 和包含重写的功能的程序集。</span><span class="sxs-lookup"><span data-stu-id="c0e05-127">Create a reference between the map that contains the **Scripting** functoid and the assembly that contains the rewritten functionality.</span></span>  
  
5. <span data-ttu-id="c0e05-128">配置**脚本**属性**脚本**functoid。</span><span class="sxs-lookup"><span data-stu-id="c0e05-128">Configure the **Script** property for the **Scripting** functoid.</span></span> <span data-ttu-id="c0e05-129">此属性确定哪些脚本**脚本**functoid 在运行时调用。</span><span class="sxs-lookup"><span data-stu-id="c0e05-129">This property determines what script the **Scripting** functoid calls during run time.</span></span> <span data-ttu-id="c0e05-130">必须匹配的转换自定义脚本的语言为此属性的值。</span><span class="sxs-lookup"><span data-stu-id="c0e05-130">You must match the value of this property to the language into which you converted your custom script.</span></span> <span data-ttu-id="c0e05-131">有关如何配置脚本属性的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="c0e05-131">For more information about how to configure the Script property, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md).</span></span> <span data-ttu-id="c0e05-132">另请参阅[脚本 Functoid](../core/scripting-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="c0e05-132">Also see [Scripting Functoid](../core/scripting-functoid.md).</span></span>  
  
6. <span data-ttu-id="c0e05-133">生成 BizTalk 项目包含对地图**脚本**functoid。</span><span class="sxs-lookup"><span data-stu-id="c0e05-133">Build the BizTalk project that contains the map with the **Scripting** functoid.</span></span>  
  
7. <span data-ttu-id="c0e05-134">验证和测试映射。</span><span class="sxs-lookup"><span data-stu-id="c0e05-134">Validate and test the map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0e05-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0e05-135">See Also</span></span>  
 <span data-ttu-id="c0e05-136">[编辑 Functoid 属性和输入的参数](../core/editing-functoid-properties-and-input-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="c0e05-136">[Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md) </span></span>  
 [<span data-ttu-id="c0e05-137">“脚本编写”Functoid</span><span class="sxs-lookup"><span data-stu-id="c0e05-137">Scripting Functoid</span></span>](../core/scripting-functoid.md)