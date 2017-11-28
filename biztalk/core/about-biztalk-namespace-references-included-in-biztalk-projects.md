---
title: "有关 BizTalk Namespace 引用包含在 BizTalk 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- System.Xml namespace
- Microsoft.BizTalk.GlobalPropertySchemas namespace
- namespaces, System.Xml namespace
- System namespace
- namespaces, System namespace
- namespaces, Microsoft.BizTalk.GlobalPropertySchemas namespace
- Microsoft.BizTalk.DefaultPipelines namespace
- projects, namespaces
- namespaces, warnings
- namespaces, Microsoft.BIzTalk.DefaultPipelines namespace
- namespaces
ms.assetid: cb642eac-7307-44f8-bbba-3ae364e11ea2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 820e15eb3524713dfd7d3f86311ca262fde191d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="about-biztalk-namespace-references-included-in-biztalk-projects"></a><span data-ttu-id="cb94c-102">有关 BizTalk 项目中包含的 BizTalk Namespace 引用</span><span class="sxs-lookup"><span data-stu-id="cb94c-102">About BizTalk Namespace References Included in BizTalk Projects</span></span>
<span data-ttu-id="cb94c-103">在添加新的 BizTalk 项目时，默认情况下包括以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="cb94c-103">When you add a new BizTalk project, the following namespaces are included by default:</span></span>  
  
-   <span data-ttu-id="cb94c-104">**Microsoft.BizTalk.DefaultPipelines**</span><span class="sxs-lookup"><span data-stu-id="cb94c-104">**Microsoft.BizTalk.DefaultPipelines**</span></span>  
  
-   <span data-ttu-id="cb94c-105">**Microsoft.BizTalk.GlobalPropertySchemas**</span><span class="sxs-lookup"><span data-stu-id="cb94c-105">**Microsoft.BizTalk.GlobalPropertySchemas**</span></span>  
  
-   <span data-ttu-id="cb94c-106">**系统**</span><span class="sxs-lookup"><span data-stu-id="cb94c-106">**System**</span></span>  
  
-   <span data-ttu-id="cb94c-107">**System.Xml**</span><span class="sxs-lookup"><span data-stu-id="cb94c-107">**System.Xml**</span></span>  
  
 <span data-ttu-id="cb94c-108">您也可以向项目中添加新的引用和 Web 引用。</span><span class="sxs-lookup"><span data-stu-id="cb94c-108">You can also add new references and Web references to your project.</span></span> <span data-ttu-id="cb94c-109">有关详细信息添加引用使用**项目**菜单上，请参阅[使用 Visual Studio](../core/using-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="cb94c-109">For more information about adding references using the **Project** menu, see [Using Visual Studio](../core/using-visual-studio.md).</span></span> <span data-ttu-id="cb94c-110">有关如何添加 Web 引用的信息，请参阅[添加 Web 引用](../core/adding-web-references.md)。</span><span class="sxs-lookup"><span data-stu-id="cb94c-110">For information about adding Web references, see [Adding Web References](../core/adding-web-references.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="cb94c-111">请不要删除默认引用。</span><span class="sxs-lookup"><span data-stu-id="cb94c-111">Do not remove the default references.</span></span> <span data-ttu-id="cb94c-112">如果删除默认引用，则在项目中引用 BizTalk 项时可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="cb94c-112">If you remove the default references, you might encounter problems when referencing BizTalk items in your project.</span></span> <span data-ttu-id="cb94c-113">可以在解决方案资源管理器中还原默认引用。</span><span class="sxs-lookup"><span data-stu-id="cb94c-113">You can restore default references in Solution Explorer.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="cb94c-114">如果 BizTalk 项目引用另一程序集，而该程序集进行了更新，不会在 BizTalk 项目中自动提取这些更新或更改。</span><span class="sxs-lookup"><span data-stu-id="cb94c-114">If your BizTalk project references another assembly, and that assembly is updated, the updates or changes are not automatically picked up in your BizTalk project.</span></span> <span data-ttu-id="cb94c-115">应在解决方案资源管理器中删除过期的引用，然后重新添加引用（重新引用该程序集）。</span><span class="sxs-lookup"><span data-stu-id="cb94c-115">You should remove the outdated reference in Solution Explorer, and then add the reference back (re-reference the assembly).</span></span> <span data-ttu-id="cb94c-116">或者，也可以关闭解决方案并重新打开该解决方案。</span><span class="sxs-lookup"><span data-stu-id="cb94c-116">Alternatively, you can close your solution and reopen it.</span></span> <span data-ttu-id="cb94c-117">无论采用哪一种方法，都可以在项目中使用对所引用的程序集的最新更新。</span><span class="sxs-lookup"><span data-stu-id="cb94c-117">In either case, the latest updates to the referenced assembly are available to your project.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cb94c-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="cb94c-118">In This Section</span></span>  
  
-   [<span data-ttu-id="cb94c-119">Microsoft.BizTalk.DefaultPipelines 引用</span><span class="sxs-lookup"><span data-stu-id="cb94c-119">Microsoft.BizTalk.DefaultPipelines Reference</span></span>](../core/microsoft-biztalk-defaultpipelines-reference.md)  
  
-   [<span data-ttu-id="cb94c-120">Microsoft.BizTalk.GlobalPropertySchemas 引用</span><span class="sxs-lookup"><span data-stu-id="cb94c-120">Microsoft.BizTalk.GlobalPropertySchemas Reference</span></span>](../core/microsoft-biztalk-globalpropertyschemas-reference.md)  
  
-   [<span data-ttu-id="cb94c-121">系统参考</span><span class="sxs-lookup"><span data-stu-id="cb94c-121">System Reference</span></span>](../core/system-reference.md)  
  
-   [<span data-ttu-id="cb94c-122">System.Xml 引用</span><span class="sxs-lookup"><span data-stu-id="cb94c-122">System.Xml Reference</span></span>](../core/system-xml-reference.md)