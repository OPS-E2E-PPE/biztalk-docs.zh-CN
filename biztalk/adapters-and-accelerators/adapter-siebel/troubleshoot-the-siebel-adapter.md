---
title: 解决在 Siebel 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: de11ffe3-3622-40df-b9c5-11c96f8460e0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e12b877eaabb629bb9e9e1da81cf5343e1780cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-the-siebel-adapter"></a><span data-ttu-id="cef71-102">解决在 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="cef71-102">Troubleshoot the Siebel adapter</span></span>
<span data-ttu-id="cef71-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]使用或依赖于多种不同的 Microsoft 技术包括但不是限于[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，与 Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] / [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cef71-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several different Microsoft technologies including but not limited to [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]/[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="cef71-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]之上生成[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，这反过来又要求[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]和[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cef71-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] and [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="cef71-105">可以使用适配器，或者通过编写应用程序使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或通过创建 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="cef71-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="cef71-106">有关与每个这些技术和产品相关的问题，请参阅各自的文档。</span><span class="sxs-lookup"><span data-stu-id="cef71-106">For issues related to each of these technologies and products, refer to the respective documentation.</span></span>  
  
 <span data-ttu-id="cef71-107">本部分提供有关疑难解答的信息[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，包括：</span><span class="sxs-lookup"><span data-stu-id="cef71-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="cef71-108">启用跟踪以诊断适配器的问题。</span><span class="sxs-lookup"><span data-stu-id="cef71-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="cef71-109">处理安装和运行时使用的适配器，请包括可能的原因和解决可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="cef71-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="cef71-110">使用性能计数器用于衡量适配器性能。</span><span class="sxs-lookup"><span data-stu-id="cef71-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="cef71-111">处理的异常和错误，包括可能的原因和解决方法。</span><span class="sxs-lookup"><span data-stu-id="cef71-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cef71-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="cef71-112">In This Section</span></span>  
  
-   [<span data-ttu-id="cef71-113">诊断跟踪和消息日志记录为 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="cef71-113">Diagnostic Tracing and Message Logging for the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="cef71-114">与 Siebel 适配器解决安装问题</span><span class="sxs-lookup"><span data-stu-id="cef71-114">Troubleshoot Installation Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-installation-issues-with-the-siebel-adapter.md) 
  
-   [<span data-ttu-id="cef71-115">与 Siebel 适配器排除操作问题</span><span class="sxs-lookup"><span data-stu-id="cef71-115">Troubleshoot Operational Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-operational-issues-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="cef71-116">与 Siebel 适配器解决性能问题</span><span class="sxs-lookup"><span data-stu-id="cef71-116">Troubleshoot Performance Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-performance-issues-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="cef71-117">解决与用于 Siebel 的数据提供程序的问题</span><span class="sxs-lookup"><span data-stu-id="cef71-117">Troubleshoot Issues with the Data Provider for Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-issues-with-the-data-provider-for-siebel.md) 
  
-   [<span data-ttu-id="cef71-118">用于 Siebel 适配器的性能计数器</span><span class="sxs-lookup"><span data-stu-id="cef71-118">Use Performance Counters with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/use-performance-counters-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="cef71-119">异常和错误处理，并在 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="cef71-119">Exceptions and Error Handling with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)