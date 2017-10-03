---
title: "对 Oracle 数据库适配器进行故障排除 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: troubleshooting
ms.assetid: 2a3da42b-413b-479a-90d2-02f262abff41
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3cf2e8c5f9a3f0baa743f86eaf6527ed9847019
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-the-oracle-database-adapter"></a><span data-ttu-id="79d94-102">对 Oracle 数据库适配器进行故障排除</span><span class="sxs-lookup"><span data-stu-id="79d94-102">Troubleshoot the Oracle Database adapter</span></span>
<span data-ttu-id="79d94-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]使用或依赖于多个 Microsoft 技术，包括但不是限于[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，与 Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="79d94-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="79d94-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]之上生成[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，这反过来又要求[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="79d94-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="79d94-105">可以使用适配器，或者通过编写应用程序使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或通过创建 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="79d94-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="79d94-106">有关与每个这些技术和产品相关的问题，请参阅各自的文档。</span><span class="sxs-lookup"><span data-stu-id="79d94-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="79d94-107">本部分提供有关疑难解答的信息[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，包括：</span><span class="sxs-lookup"><span data-stu-id="79d94-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="79d94-108">启用跟踪以诊断适配器的问题。</span><span class="sxs-lookup"><span data-stu-id="79d94-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="79d94-109">处理安装和运行时使用的适配器，请包括可能的原因和解决可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="79d94-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="79d94-110">使用性能计数器用于衡量适配器性能。</span><span class="sxs-lookup"><span data-stu-id="79d94-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="79d94-111">处理的异常和错误，包括可能的原因和解决方法。</span><span class="sxs-lookup"><span data-stu-id="79d94-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79d94-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="79d94-112">In This Section</span></span>  
  
-   [<span data-ttu-id="79d94-113">诊断跟踪和消息日志记录为 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="79d94-113">Diagnostic tracing and message logging for the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="79d94-114">解决与 Oracle 数据库适配器的安装问题</span><span class="sxs-lookup"><span data-stu-id="79d94-114">Troubleshoot installation issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="79d94-115">排除与 Oracle 数据库适配器的操作问题</span><span class="sxs-lookup"><span data-stu-id="79d94-115">Troubleshoot operational issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="79d94-116">解决与 Oracle 数据库适配器的性能问题</span><span class="sxs-lookup"><span data-stu-id="79d94-116">Troubleshoot performance issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-performance-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="79d94-117">使用与 Oracle 数据库适配器的性能计数器</span><span class="sxs-lookup"><span data-stu-id="79d94-117">Use performance counters with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/use-performance-counters-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="79d94-118">异常和错误处理使用 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="79d94-118">Exceptions and error handling with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)