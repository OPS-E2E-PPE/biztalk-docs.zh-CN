---
title: Oracle 数据库适配器疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 2a3da42b-413b-479a-90d2-02f262abff41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33afecfb511595cec0dc556f479968f073516a31
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375896"
---
# <a name="troubleshoot-the-oracle-database-adapter"></a><span data-ttu-id="1392d-102">Oracle 数据库适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="1392d-102">Troubleshoot the Oracle Database adapter</span></span>
<span data-ttu-id="1392d-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]使用或依赖于多个 Microsoft 技术，包括但不是限于[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，以及 Microsoft 的[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1392d-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="1392d-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]构建的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，这反过来又要求[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1392d-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="1392d-105">可以使用适配器，或者通过编写应用程序使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或通过创建 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1392d-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="1392d-106">有关与每个这些技术和产品相关的问题，请参阅各自的文档。</span><span class="sxs-lookup"><span data-stu-id="1392d-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="1392d-107">本部分提供有关疑难解答的信息[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，其中包括：</span><span class="sxs-lookup"><span data-stu-id="1392d-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="1392d-108">启用跟踪来诊断适配器的问题。</span><span class="sxs-lookup"><span data-stu-id="1392d-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="1392d-109">处理安装和运行时使用的适配器，包括可能原因和解决方法可能会遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="1392d-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="1392d-110">使用性能计数器以衡量适配器性能。</span><span class="sxs-lookup"><span data-stu-id="1392d-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="1392d-111">处理异常和错误，包括可能原因和解决方法。</span><span class="sxs-lookup"><span data-stu-id="1392d-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1392d-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="1392d-112">In This Section</span></span>  
  
-   [<span data-ttu-id="1392d-113">诊断跟踪和 Oracle 数据库适配器的消息日志记录</span><span class="sxs-lookup"><span data-stu-id="1392d-113">Diagnostic tracing and message logging for the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="1392d-114">对 Oracle 数据库适配器的安装问题进行故障排除</span><span class="sxs-lookup"><span data-stu-id="1392d-114">Troubleshoot installation issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="1392d-115">使用 Oracle 数据库适配器的操作问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="1392d-115">Troubleshoot operational issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="1392d-116">对 Oracle 数据库适配器的性能问题进行故障排除</span><span class="sxs-lookup"><span data-stu-id="1392d-116">Troubleshoot performance issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-performance-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="1392d-117">使用性能计数器与 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="1392d-117">Use performance counters with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/use-performance-counters-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="1392d-118">异常和错误处理与 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="1392d-118">Exceptions and error handling with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)