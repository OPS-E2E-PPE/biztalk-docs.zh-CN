---
title: 故障排除 SAP 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 2c554a7b-18be-4c94-8bf2-f22ac080794c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1994f7c2d6d32dc394783a68edb91532118434aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216333"
---
# <a name="troubleshoot-the-sap-adapter"></a><span data-ttu-id="4e65a-102">故障排除 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="4e65a-102">Troubleshoot the SAP adapter</span></span>
<span data-ttu-id="4e65a-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]使用或依赖于多个 Microsoft 技术，包括但不是限于[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，与 Microsoft[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]或[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4e65a-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] or [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="4e65a-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]之上生成[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，这反过来又要求[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]或[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4e65a-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] or [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="4e65a-105">可以使用适配器，或者通过编写应用程序使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或通过创建 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4e65a-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="4e65a-106">有关与每个这些技术和产品相关的问题，请参阅各自的文档。</span><span class="sxs-lookup"><span data-stu-id="4e65a-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="4e65a-107">本部分提供有关疑难解答的信息[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，包括：</span><span class="sxs-lookup"><span data-stu-id="4e65a-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="4e65a-108">启用跟踪以诊断适配器的问题。</span><span class="sxs-lookup"><span data-stu-id="4e65a-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="4e65a-109">处理安装和运行时使用的适配器，请包括可能的原因和解决可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="4e65a-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="4e65a-110">使用性能计数器用于衡量适配器性能。</span><span class="sxs-lookup"><span data-stu-id="4e65a-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="4e65a-111">处理的异常和错误，包括可能的原因和解决方法。</span><span class="sxs-lookup"><span data-stu-id="4e65a-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4e65a-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="4e65a-112">In This Section</span></span>  
  
-   [<span data-ttu-id="4e65a-113">诊断跟踪和消息日志记录为 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="4e65a-113">Diagnostic Tracing and Message Logging for the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md)  
  
-   [<span data-ttu-id="4e65a-114">与 SAP 适配器解决安装问题</span><span class="sxs-lookup"><span data-stu-id="4e65a-114">Troubleshoot Installation Issues with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-installation-issues-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="4e65a-115">与 SAP 适配器排除操作问题</span><span class="sxs-lookup"><span data-stu-id="4e65a-115">Troubleshoot Operational Issues with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="4e65a-116">与 SAP 适配器解决性能问题</span><span class="sxs-lookup"><span data-stu-id="4e65a-116">Troubleshoot Performance Issues with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-performance-issues-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="4e65a-117">解决与适用于 SAP 的数据提供程序的问题</span><span class="sxs-lookup"><span data-stu-id="4e65a-117">Troubleshoot Issues with the Data Provider for SAP</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-issues-with-the-data-provider-for-sap.md)  
  
-   [<span data-ttu-id="4e65a-118">使用 SAP 适配器使用性能计数器</span><span class="sxs-lookup"><span data-stu-id="4e65a-118">Use Performance Counters with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="4e65a-119">异常和错误处理与 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="4e65a-119">Exceptions and Error Handling with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)