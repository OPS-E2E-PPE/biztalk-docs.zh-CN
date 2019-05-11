---
title: 使用外部程序集编写脚本 |Microsoft Docs
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
ms.openlocfilehash: 4876d0b7c236be890649e5050b09e538b07742a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395527"
---
# <a name="scripting-using-external-assemblies"></a><span data-ttu-id="9037e-102">使用外部程序集编写脚本</span><span class="sxs-lookup"><span data-stu-id="9037e-102">Scripting Using External Assemblies</span></span>
<span data-ttu-id="9037e-103">使用外部程序集编写脚本是使用 Microsoft 中的脚本的首选的方式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9037e-103">Scripting with external assemblies is the preferred way to use scripting in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="9037e-104">外部程序集提供了几项优势：</span><span class="sxs-lookup"><span data-stu-id="9037e-104">External assemblies provide several advantages:</span></span>  
  
-   <span data-ttu-id="9037e-105">便于代码共享</span><span class="sxs-lookup"><span data-stu-id="9037e-105">Easy code sharing</span></span>  
  
-   <span data-ttu-id="9037e-106">维护更简单</span><span class="sxs-lookup"><span data-stu-id="9037e-106">Simpler maintenance</span></span>  
  
-   <span data-ttu-id="9037e-107">更轻松地调试</span><span class="sxs-lookup"><span data-stu-id="9037e-107">Easier debugging</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9037e-108">如果将测试映射失败**脚本**functoid 使用未在 GAC 中注册的外部程序集。</span><span class="sxs-lookup"><span data-stu-id="9037e-108">Test Map fails if the **Scripting** functoid uses an external assembly which is not registered in the GAC.</span></span> <span data-ttu-id="9037e-109">如果外部程序集在当前项目的程序集 （生成后放置） 所在的 bin 文件夹中，它有效。</span><span class="sxs-lookup"><span data-stu-id="9037e-109">It works if the external assembly is in the same bin folder as the current project's assembly (placed after build).</span></span>  
  
 <span data-ttu-id="9037e-110">重新使用脚本，只需要设置**脚本**的属性**脚本**functoid。</span><span class="sxs-lookup"><span data-stu-id="9037e-110">Re-using the script only requires setting the **Script** property of the **Scripting** functoid.</span></span> <span data-ttu-id="9037e-111">由于该脚本存储在映射之外，您可以修改脚本，而无需更改代码图。</span><span class="sxs-lookup"><span data-stu-id="9037e-111">Because the script is stored outside of the map, you can modify the script without changing the map.</span></span> <span data-ttu-id="9037e-112">您可以使用的完整阵列[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]调试工具，以确保您的脚本能够正常运行。</span><span class="sxs-lookup"><span data-stu-id="9037e-112">And you can use the full array of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debugging tools to ensure your script runs correctly.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="9037e-113">在外部程序集中的代码必须是线程安全。</span><span class="sxs-lookup"><span data-stu-id="9037e-113">The code in the external assembly must be thread-safe.</span></span> <span data-ttu-id="9037e-114">高负荷环境下可能会同时运行多个映射实例。</span><span class="sxs-lookup"><span data-stu-id="9037e-114">Under stress conditions, multiple instances of a map may be running concurrently.</span></span>  
  
 <span data-ttu-id="9037e-115">示例函数位于外部程序集，请参阅[XML 工具 （BizTalk Server 示例文件夹）](../core/xml-tools-biztalk-server-samples-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="9037e-115">For a sample function housed in an external assembly, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9037e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9037e-116">See Also</span></span>  
 <span data-ttu-id="9037e-117">[脚本 Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="9037e-117">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="9037e-118">[使用内联 C#、 JScript.NET 和 Visual Basic.NET 编写脚本](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span><span class="sxs-lookup"><span data-stu-id="9037e-118">[Scripting Using Inline C#, JScript .NET, and Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span></span>  
 <span data-ttu-id="9037e-119">[使用内联 XSLT 和 XSLT 调用模板编写脚本](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="9037e-119">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 <span data-ttu-id="9037e-120">[如何向映射添加脚本 Functoid](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="9037e-120">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="9037e-121">如何配置脚本 Functoid</span><span class="sxs-lookup"><span data-stu-id="9037e-121">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)