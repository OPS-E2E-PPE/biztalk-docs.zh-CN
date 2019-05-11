---
title: 如何调试映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1ee1e26-fced-4126-b48a-71007043424d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9459cc2d2d51347e508ac989a9aeb54b9ac1059d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338890"
---
# <a name="how-to-debug-maps"></a><span data-ttu-id="720c0-102">如何调试映射</span><span class="sxs-lookup"><span data-stu-id="720c0-102">How to Debug Maps</span></span>
<span data-ttu-id="720c0-103">**调试映射**功能是用于识别和修复复杂的映射问题。</span><span class="sxs-lookup"><span data-stu-id="720c0-103">The **Debug Map** feature is useful in identifying and fixing complex mapping issues.</span></span> <span data-ttu-id="720c0-104">本主题提供调试映射使用内联 XSLT 调试程序的分步说明。</span><span class="sxs-lookup"><span data-stu-id="720c0-104">This topic provides step-by-step instructions for debugging maps using the inline XSLT debugger.</span></span>  

> [!NOTE]
>  <span data-ttu-id="720c0-105">调试映射时**调试映射**功能使用映射文件属性**测试映射输入实例**并**测试映射输出实例**。</span><span class="sxs-lookup"><span data-stu-id="720c0-105">When debugging the map, the **Debug Map** feature uses the map file properties **TestMap Input Instance** and **TestMap Output Instance**.</span></span> <span data-ttu-id="720c0-106">因此，在调试映射之前，我们建议您配置输入和输出实例属性映射文件中。</span><span class="sxs-lookup"><span data-stu-id="720c0-106">Therefore, before you debug the map, we recommend that you configure the input and output instance properties in the map file.</span></span>  

### <a name="to-debug-a-biztalk-map"></a><span data-ttu-id="720c0-107">若要调试 BizTalk 映射</span><span class="sxs-lookup"><span data-stu-id="720c0-107">To debug a BizTalk map</span></span>  

1. <span data-ttu-id="720c0-108">在解决方案资源管理器，右键单击你想要测试，然后单击的地图**调试映射**。</span><span class="sxs-lookup"><span data-stu-id="720c0-108">In Solution Explorer, right-click the map you want to test, and then click **Debug Map**.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] <span data-ttu-id="720c0-109">在其编辑器中的 XSLT 格式显示的映射。</span><span class="sxs-lookup"><span data-stu-id="720c0-109">displays the map in XSLT format in its editor.</span></span>  

2. <span data-ttu-id="720c0-110">按 F10 或 F11 来调试 XSL 代码。</span><span class="sxs-lookup"><span data-stu-id="720c0-110">Press F10 or F11 to debug the XSL code.</span></span> <span data-ttu-id="720c0-111">当在 functoid 调用上，按 F11 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] functoid 代码的 C# 的步骤。</span><span class="sxs-lookup"><span data-stu-id="720c0-111">When you press F11 on a functoid call, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] steps into the C# code for the functoid.</span></span> <span data-ttu-id="720c0-112">您可以查看本地 Windows 调试器中的 functoid 源代码中使用的变量的值。</span><span class="sxs-lookup"><span data-stu-id="720c0-112">You can view the values of variables used in the functoid source code in the Local Windows Debugger.</span></span>
