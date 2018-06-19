---
title: 如何作为数据源使用的.NET 程序集 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, data sources
ms.assetid: 14dbec48-acc9-4c3c-bd7f-737dabf29543
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa56370cf894d0d18a36320ca97c4d028fee487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256629"
---
# <a name="how-to-use-a-net-assembly-as-a-data-source"></a><span data-ttu-id="358f0-102">如何将 .NET 程序集用作数据源</span><span class="sxs-lookup"><span data-stu-id="358f0-102">How to Use a .NET Assembly as a Data Source</span></span>
<span data-ttu-id="358f0-103">您可以指定 .NET 程序集作为数据源。</span><span class="sxs-lookup"><span data-stu-id="358f0-103">You can specify a .NET assembly as a data source.</span></span> <span data-ttu-id="358f0-104">随后可以从该程序集，选择一个类或类成员，并将其拖到词汇定义或规则。</span><span class="sxs-lookup"><span data-stu-id="358f0-104">You can subsequently select a class or class member from the assembly, and drag it onto a vocabulary definition or rule.</span></span>  
  
### <a name="to-specify-a-net-assembly-as-a-data-source"></a><span data-ttu-id="358f0-105">指定 .NET 程序集作为数据源</span><span class="sxs-lookup"><span data-stu-id="358f0-105">To specify a .NET assembly as a data source</span></span>  
  
1.  <span data-ttu-id="358f0-106">在事实浏览器窗口中，单击 **.NET 类**选项卡。</span><span class="sxs-lookup"><span data-stu-id="358f0-106">In the Facts Explorer window, click the **.NET Classes** tab.</span></span>  
  
2.  <span data-ttu-id="358f0-107">右键单击**模块**节点。</span><span class="sxs-lookup"><span data-stu-id="358f0-107">Right-click the **Modules** node.</span></span>  
  
3.  <span data-ttu-id="358f0-108">从可用程序集中选择 .NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="358f0-108">From the available assemblies, select a .NET assembly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="358f0-109">可用程序集必须位于全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="358f0-109">The assemblies have to be in the global assembly cache (GAC).</span></span> <span data-ttu-id="358f0-110">业务规则编辑器加载.NET 程序集的.NET 程序集在浏览时**事实数据资源管理器**窗口中或在 **.NET 类或类成员定义**页**词汇定义**窗口。</span><span class="sxs-lookup"><span data-stu-id="358f0-110">The business rule composer loads a .NET assembly when you browse for the .NET assembly in the **Facts Explorer** window or in the **.NET Class or Class Member Definition** page of the **Vocabulary Definition** window.</span></span>  <span data-ttu-id="358f0-111">如果您在 GAC 中更新该程序集，则关闭业务规则编辑器然后重新启动它，以便加载已更新的 .NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="358f0-111">If you update the assembly in the GAC, close the business rule composer and restart it to load the updated .NET assembly.</span></span> <span data-ttu-id="358f0-112">业务规则编辑器并不自动刷新该程序集。</span><span class="sxs-lookup"><span data-stu-id="358f0-112">The business rule composer does not refresh the assembly automatically.</span></span>  
  
     <span data-ttu-id="358f0-113">![事实和定义树浏览器的屏幕截图。] (../core/media/ebiz-netbrowse.gif "ebiz_netbrowse")</span><span class="sxs-lookup"><span data-stu-id="358f0-113">![Screenshot of facts and definition tree browser.](../core/media/ebiz-netbrowse.gif "ebiz_netbrowse")</span></span>