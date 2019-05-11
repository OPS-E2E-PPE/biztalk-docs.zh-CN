---
title: 有关 BizTalk 项目中包含的 BizTalk Namespace 引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01344253a75033650b0e6326ff11420d0ed6fef5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362404"
---
# <a name="about-biztalk-namespace-references-included-in-biztalk-projects"></a><span data-ttu-id="4073f-102">有关 BizTalk 项目中包含的 BizTalk Namespace 引用</span><span class="sxs-lookup"><span data-stu-id="4073f-102">About BizTalk Namespace References Included in BizTalk Projects</span></span>
<span data-ttu-id="4073f-103">当添加新的 BizTalk 项目时，默认情况下包括以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="4073f-103">When you add a new BizTalk project, the following namespaces are included by default:</span></span>  
  
- <span data-ttu-id="4073f-104">**Microsoft.BizTalk.DefaultPipelines**</span><span class="sxs-lookup"><span data-stu-id="4073f-104">**Microsoft.BizTalk.DefaultPipelines**</span></span>  
  
- <span data-ttu-id="4073f-105">**Microsoft.BizTalk.GlobalPropertySchemas**</span><span class="sxs-lookup"><span data-stu-id="4073f-105">**Microsoft.BizTalk.GlobalPropertySchemas**</span></span>  
  
- <span data-ttu-id="4073f-106">**系统**</span><span class="sxs-lookup"><span data-stu-id="4073f-106">**System**</span></span>  
  
- <span data-ttu-id="4073f-107">**System.Xml**</span><span class="sxs-lookup"><span data-stu-id="4073f-107">**System.Xml**</span></span>  
  
  <span data-ttu-id="4073f-108">此外可以添加新的引用和对你的项目的 Web 引用。</span><span class="sxs-lookup"><span data-stu-id="4073f-108">You can also add new references and Web references to your project.</span></span> <span data-ttu-id="4073f-109">有关添加详细信息引用使用**项目**菜单中，请参阅[使用 Visual Studio](../core/using-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="4073f-109">For more information about adding references using the **Project** menu, see [Using Visual Studio](../core/using-visual-studio.md).</span></span> <span data-ttu-id="4073f-110">有关添加 Web 引用的信息，请参阅[添加 Web 引用](../core/adding-web-references.md)。</span><span class="sxs-lookup"><span data-stu-id="4073f-110">For information about adding Web references, see [Adding Web References](../core/adding-web-references.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4073f-111">不要删除默认引用。</span><span class="sxs-lookup"><span data-stu-id="4073f-111">Do not remove the default references.</span></span> <span data-ttu-id="4073f-112">如果删除默认引用，你的项目中引用 BizTalk 项时可能遇到问题。</span><span class="sxs-lookup"><span data-stu-id="4073f-112">If you remove the default references, you might encounter problems when referencing BizTalk items in your project.</span></span> <span data-ttu-id="4073f-113">可以还原在解决方案资源管理器中的默认引用。</span><span class="sxs-lookup"><span data-stu-id="4073f-113">You can restore default references in Solution Explorer.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4073f-114">如果你的 BizTalk 项目引用另一个程序集，并更新该程序集，这些更新或更改不会自动选取您的 BizTalk 项目中。</span><span class="sxs-lookup"><span data-stu-id="4073f-114">If your BizTalk project references another assembly, and that assembly is updated, the updates or changes are not automatically picked up in your BizTalk project.</span></span> <span data-ttu-id="4073f-115">应在解决方案资源管理器中删除过期的引用，然后重新添加引用 （重新引用程序集）。</span><span class="sxs-lookup"><span data-stu-id="4073f-115">You should remove the outdated reference in Solution Explorer, and then add the reference back (re-reference the assembly).</span></span> <span data-ttu-id="4073f-116">或者，可以关闭解决方案并重新打开它。</span><span class="sxs-lookup"><span data-stu-id="4073f-116">Alternatively, you can close your solution and reopen it.</span></span> <span data-ttu-id="4073f-117">在任一情况下，引用的程序集最新的更新可供你的项目。</span><span class="sxs-lookup"><span data-stu-id="4073f-117">In either case, the latest updates to the referenced assembly are available to your project.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4073f-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="4073f-118">In This Section</span></span>  
  
-   [<span data-ttu-id="4073f-119">Microsoft.BizTalk.DefaultPipelines 引用</span><span class="sxs-lookup"><span data-stu-id="4073f-119">Microsoft.BizTalk.DefaultPipelines Reference</span></span>](../core/microsoft-biztalk-defaultpipelines-reference.md)  
  
-   [<span data-ttu-id="4073f-120">Microsoft.BizTalk.GlobalPropertySchemas 引用</span><span class="sxs-lookup"><span data-stu-id="4073f-120">Microsoft.BizTalk.GlobalPropertySchemas Reference</span></span>](../core/microsoft-biztalk-globalpropertyschemas-reference.md)  
  
-   [<span data-ttu-id="4073f-121">系统引用</span><span class="sxs-lookup"><span data-stu-id="4073f-121">System Reference</span></span>](../core/system-reference.md)  
  
-   [<span data-ttu-id="4073f-122">System.Xml 引用</span><span class="sxs-lookup"><span data-stu-id="4073f-122">System.Xml Reference</span></span>](../core/system-xml-reference.md)