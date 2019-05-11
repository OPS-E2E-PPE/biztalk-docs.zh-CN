---
title: Siebel 适配器疑难解答 |Microsoft Docs
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
ms.openlocfilehash: 7474b75319dabe1f04a51df24ffe952b723fa624
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370387"
---
# <a name="troubleshoot-the-siebel-adapter"></a><span data-ttu-id="1eda4-102">Siebel 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="1eda4-102">Troubleshoot the Siebel adapter</span></span>
<span data-ttu-id="1eda4-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]使用或依赖于多个不同 Microsoft 技术，包括但不是限于[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，以及 Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] / [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1eda4-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several different Microsoft technologies including but not limited to [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]/[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="1eda4-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]构建的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，这反过来又要求[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]和[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1eda4-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] and [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="1eda4-105">可以使用适配器，或者通过编写应用程序使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或通过创建 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1eda4-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="1eda4-106">有关与每个这些技术和产品相关的问题，请参阅各自的文档。</span><span class="sxs-lookup"><span data-stu-id="1eda4-106">For issues related to each of these technologies and products, refer to the respective documentation.</span></span>  
  
 <span data-ttu-id="1eda4-107">本部分提供有关疑难解答的信息[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，其中包括：</span><span class="sxs-lookup"><span data-stu-id="1eda4-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="1eda4-108">启用跟踪来诊断适配器的问题。</span><span class="sxs-lookup"><span data-stu-id="1eda4-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="1eda4-109">处理安装和运行时使用的适配器，包括可能原因和解决方法可能会遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="1eda4-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="1eda4-110">使用性能计数器以衡量适配器性能。</span><span class="sxs-lookup"><span data-stu-id="1eda4-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="1eda4-111">处理异常和错误，包括可能原因和解决方法。</span><span class="sxs-lookup"><span data-stu-id="1eda4-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1eda4-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="1eda4-112">In This Section</span></span>  
  
-   [<span data-ttu-id="1eda4-113">诊断跟踪和 Siebel 适配器的消息日志记录</span><span class="sxs-lookup"><span data-stu-id="1eda4-113">Diagnostic Tracing and Message Logging for the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="1eda4-114">使用 Siebel 适配器进行故障排除安装问题：</span><span class="sxs-lookup"><span data-stu-id="1eda4-114">Troubleshoot Installation Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-installation-issues-with-the-siebel-adapter.md) 
  
-   [<span data-ttu-id="1eda4-115">使用 Siebel 适配器进行的操作问题故障排除</span><span class="sxs-lookup"><span data-stu-id="1eda4-115">Troubleshoot Operational Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-operational-issues-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="1eda4-116">使用 Siebel 适配器进行故障排除性能问题：</span><span class="sxs-lookup"><span data-stu-id="1eda4-116">Troubleshoot Performance Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-performance-issues-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="1eda4-117">Siebel 的数据提供程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="1eda4-117">Troubleshoot Issues with the Data Provider for Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-issues-with-the-data-provider-for-siebel.md) 
  
-   [<span data-ttu-id="1eda4-118">使用 Siebel 适配器的性能计数器</span><span class="sxs-lookup"><span data-stu-id="1eda4-118">Use Performance Counters with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/use-performance-counters-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="1eda4-119">异常和错误处理与 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="1eda4-119">Exceptions and Error Handling with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)