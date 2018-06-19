---
title: 脚本使用外部程序集 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, warnings
- Scripting functoids, external assemblies
ms.assetid: 0bdf6adc-91b9-462e-8fd0-9cb48bfa7817
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 475a3b9781eecb0ccc79165bbe54e6dfd542ecfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269197"
---
# <a name="scripting-using-external-assemblies"></a><span data-ttu-id="839f3-102">使用外部程序集编写脚本</span><span class="sxs-lookup"><span data-stu-id="839f3-102">Scripting Using External Assemblies</span></span>
<span data-ttu-id="839f3-103">使用外部程序集编写脚本是在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中使用脚本的首选方式。</span><span class="sxs-lookup"><span data-stu-id="839f3-103">Scripting with external assemblies is the preferred way to use scripting in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="839f3-104">外部程序集具有多项优点：</span><span class="sxs-lookup"><span data-stu-id="839f3-104">External assemblies provide several advantages:</span></span>  
  
-   <span data-ttu-id="839f3-105">便于代码共享</span><span class="sxs-lookup"><span data-stu-id="839f3-105">Easy code sharing</span></span>  
  
-   <span data-ttu-id="839f3-106">维护更简单</span><span class="sxs-lookup"><span data-stu-id="839f3-106">Simpler maintenance</span></span>  
  
-   <span data-ttu-id="839f3-107">调试更方便</span><span class="sxs-lookup"><span data-stu-id="839f3-107">Easier debugging</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="839f3-108">如果测试映射失败**脚本**functoid 使用一个外部的程序集，它不在 GAC 中注册。</span><span class="sxs-lookup"><span data-stu-id="839f3-108">Test Map fails if the **Scripting** functoid uses an external assembly which is not registered in the GAC.</span></span> <span data-ttu-id="839f3-109">它适用如果外部程序集 （放置在生成后） 的当前项目的程序集所在的 bin 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="839f3-109">It works if the external assembly is in the same bin folder as the current project's assembly (placed after build).</span></span>  
  
 <span data-ttu-id="839f3-110">重新使用该脚本只需设置**脚本**属性**脚本**functoid。</span><span class="sxs-lookup"><span data-stu-id="839f3-110">Re-using the script only requires setting the **Script** property of the **Scripting** functoid.</span></span> <span data-ttu-id="839f3-111">由于脚本储存在映射之外，因此可以在不更改映射的情况下修改脚本。</span><span class="sxs-lookup"><span data-stu-id="839f3-111">Because the script is stored outside of the map, you can modify the script without changing the map.</span></span> <span data-ttu-id="839f3-112">并且你可以使用完整的数组的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]调试工具以确保你的脚本正确运行。</span><span class="sxs-lookup"><span data-stu-id="839f3-112">And you can use the full array of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debugging tools to ensure your script runs correctly.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="839f3-113">外部程序集中的代码必须为线程安全代码。</span><span class="sxs-lookup"><span data-stu-id="839f3-113">The code in the external assembly must be thread-safe.</span></span> <span data-ttu-id="839f3-114">在任务繁忙时，可以同时运行多个映射实例。</span><span class="sxs-lookup"><span data-stu-id="839f3-114">Under stress conditions, multiple instances of a map may be running concurrently.</span></span>  
  
 <span data-ttu-id="839f3-115">有关示例函数存放在外部程序集，请参阅[（BizTalk Server 示例文件夹中） 的 XML 工具](../core/xml-tools-biztalk-server-samples-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="839f3-115">For a sample function housed in an external assembly, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="839f3-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="839f3-116">See Also</span></span>  
 <span data-ttu-id="839f3-117">[脚本 Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="839f3-117">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="839f3-118">[脚本使用内联 C#、 JScript.NET 和 Visual Basic.NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span><span class="sxs-lookup"><span data-stu-id="839f3-118">[Scripting Using Inline C#, JScript .NET, and Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span></span>  
 <span data-ttu-id="839f3-119">[脚本使用内联 XSLT 和 XSLT 调用模板](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="839f3-119">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 <span data-ttu-id="839f3-120">[如何在向地图添加脚本 Functoid](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="839f3-120">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="839f3-121">如何配置脚本 Functoid</span><span class="sxs-lookup"><span data-stu-id="839f3-121">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)