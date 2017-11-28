---
title: "如何调试映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1ee1e26-fced-4126-b48a-71007043424d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e40964b267ad0788308a92490a106f940a6cb33e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-debug-maps"></a><span data-ttu-id="c2e0b-102">如何调试映射</span><span class="sxs-lookup"><span data-stu-id="c2e0b-102">How to Debug Maps</span></span>
<span data-ttu-id="c2e0b-103">**调试映射**功能可在确定并修复复杂映射问题。</span><span class="sxs-lookup"><span data-stu-id="c2e0b-103">The **Debug Map** feature is useful in identifying and fixing complex mapping issues.</span></span> <span data-ttu-id="c2e0b-104">本主题提供了使用内联 XSLT 调试程序调试映射的分步说明。</span><span class="sxs-lookup"><span data-stu-id="c2e0b-104">This topic provides step-by-step instructions for debugging maps using the inline XSLT debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2e0b-105">当调试图，**调试映射**功能使用地图文件属性**测试映射输入实例**和**测试映射输出实例**。</span><span class="sxs-lookup"><span data-stu-id="c2e0b-105">When debugging the map, the **Debug Map** feature uses the map file properties **TestMap Input Instance** and **TestMap Output Instance**.</span></span> <span data-ttu-id="c2e0b-106">因此，在调试映射之前，我们建议您在映射文件中配置输入和输出实例属性。</span><span class="sxs-lookup"><span data-stu-id="c2e0b-106">Therefore, before you debug the map, we recommend that you configure the input and output instance properties in the map file.</span></span>  
  
### <a name="to-debug-a-biztalk-map"></a><span data-ttu-id="c2e0b-107">调试 BizTalk 映射</span><span class="sxs-lookup"><span data-stu-id="c2e0b-107">To debug a BizTalk map</span></span>  
  
1.  <span data-ttu-id="c2e0b-108">在解决方案资源管理器，右键单击你想要测试，然后单击的地图**调试映射**。</span><span class="sxs-lookup"><span data-stu-id="c2e0b-108">In Solution Explorer, right-click the map you want to test, and then click **Debug Map**.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="c2e0b-109">在其编辑器中的 XSLT 格式显示地图。</span><span class="sxs-lookup"><span data-stu-id="c2e0b-109"> displays the map in XSLT format in its editor.</span></span>  
  
2.  <span data-ttu-id="c2e0b-110">按 F10 或 F11 来调试 XSL 代码。</span><span class="sxs-lookup"><span data-stu-id="c2e0b-110">Press F10 or F11 to debug the XSL code.</span></span> <span data-ttu-id="c2e0b-111">按 functoid 调用上的 F11 时，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 会开始处理 functoid 的 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="c2e0b-111">When you press F11 on a functoid call, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] steps into the C# code for the functoid.</span></span> <span data-ttu-id="c2e0b-112">您可以在本地 Windows 调试器中查看用在 functoid 源代码中的变量的值。</span><span class="sxs-lookup"><span data-stu-id="c2e0b-112">You can view the values of variables used in the functoid source code in the Local Windows Debugger.</span></span>