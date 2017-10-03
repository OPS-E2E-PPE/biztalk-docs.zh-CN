---
title: "解决 SQL 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1be376ba-ad4c-4fa7-b94b-82bfbc8f34cc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8b574a372ed365a22ff9d87d40bf4ab9af8ae4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-the-sql-adapter"></a><span data-ttu-id="43c96-102">解决 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="43c96-102">Troubleshoot the SQL adapter</span></span>
<span data-ttu-id="43c96-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]使用或依赖于多个 Microsoft 技术，包括但不是限于[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]，和[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="43c96-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)], and [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="43c96-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]之上生成[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，这反过来又要求[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]或[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="43c96-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] or [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="43c96-105">可以使用适配器，或者通过编写应用程序使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或通过创建 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="43c96-105">The adapters can be consumed either by writing applications using the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="43c96-106">有关与每个这些技术和产品相关的问题，请参阅各自的文档。</span><span class="sxs-lookup"><span data-stu-id="43c96-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="43c96-107">本部分提供有关疑难解答的信息[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，包括：</span><span class="sxs-lookup"><span data-stu-id="43c96-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="43c96-108">启用跟踪以诊断适配器的问题。</span><span class="sxs-lookup"><span data-stu-id="43c96-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="43c96-109">处理安装和运行时使用的适配器，请包括可能的原因和解决可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="43c96-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="43c96-110">使用性能计数器用于衡量适配器性能。</span><span class="sxs-lookup"><span data-stu-id="43c96-110">Using performance counters to gauge adapter performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43c96-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="43c96-111">In This Section</span></span>  
  
-   [<span data-ttu-id="43c96-112">诊断跟踪和消息日志记录中的 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="43c96-112">Diagnostic Tracing and Message Logging in the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)  
  
-   [<span data-ttu-id="43c96-113">解决 SQl 适配器的安装问题</span><span class="sxs-lookup"><span data-stu-id="43c96-113">Troubleshoot Installation Issues with the SQl adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-installation-issues-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="43c96-114">使用 SQL 适配器进行故障排除操作问题：</span><span class="sxs-lookup"><span data-stu-id="43c96-114">Troubleshoot Operational Issues with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-operational-issues-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="43c96-115">使用 SQL 适配器使用性能计数器</span><span class="sxs-lookup"><span data-stu-id="43c96-115">Use Performance Counters with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)