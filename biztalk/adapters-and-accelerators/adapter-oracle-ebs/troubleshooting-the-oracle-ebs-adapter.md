---
title: "故障排除 Oracle EBS 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d78d5335-b860-47d9-9f3a-7f74d628d8ff
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7b36316612bda541d9bf608f7da22c399ade045
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-oracle-ebs-adapter"></a><span data-ttu-id="24465-102">故障排除 Oracle EBS 适配器</span><span class="sxs-lookup"><span data-stu-id="24465-102">Troubleshooting the Oracle EBS adapter</span></span>
## <a name="overview"></a><span data-ttu-id="24465-103">概述</span><span class="sxs-lookup"><span data-stu-id="24465-103">Overview</span></span>
<span data-ttu-id="24465-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]使用或依赖于多个 Microsoft 技术，包括但不是限于[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，和[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="24465-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="24465-105">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]之上生成[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，该列也会使用[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="24465-105">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which also uses the [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="24465-106">可以使用适配器，或者通过编写应用程序使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或通过创建 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="24465-106">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> 
  
 <span data-ttu-id="24465-107">本部分提供了疑难解答信息，包括：</span><span class="sxs-lookup"><span data-stu-id="24465-107">This section provides information about troubleshooting, including:</span></span>  
  
-   <span data-ttu-id="24465-108">启用跟踪以诊断适配器的问题</span><span class="sxs-lookup"><span data-stu-id="24465-108">Enabling tracing to diagnose issues with the adapters</span></span>
  
-   <span data-ttu-id="24465-109">处理安装和运行时使用的适配器，请包括可能的原因和解决可能遇到的问题</span><span class="sxs-lookup"><span data-stu-id="24465-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause and a resolution</span></span>
  
-   <span data-ttu-id="24465-110">使用性能计数器查看适配器性能</span><span class="sxs-lookup"><span data-stu-id="24465-110">Using performance counters to review adapter performance</span></span>
  
-   <span data-ttu-id="24465-111">处理的异常和错误，包括可能的原因和解决方法</span><span class="sxs-lookup"><span data-stu-id="24465-111">Handling exceptions and errors, including probable cause, and a resolution</span></span>
  
## <a name="lets-get-started"></a><span data-ttu-id="24465-112">让我们开始吧</span><span class="sxs-lookup"><span data-stu-id="24465-112">Let's get started</span></span>  
  
-   [<span data-ttu-id="24465-113">诊断跟踪和消息日志记录与 Oracle E-business Suite 适配器中</span><span class="sxs-lookup"><span data-stu-id="24465-113">Diagnostic Tracing and Message Logging in the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md) 
  
-   [<span data-ttu-id="24465-114">与 Oracle E-business Suite 适配器解决安装问题</span><span class="sxs-lookup"><span data-stu-id="24465-114">Troubleshoot Installation Issues with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshoot-installation-issues-with-the-oracle-e-business-suite-adapter.md)  
  
-   [<span data-ttu-id="24465-115">与 Oracle E-business Suite 适配器排除操作问题</span><span class="sxs-lookup"><span data-stu-id="24465-115">Troubleshoot Operational Issues with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter.md)
  
-   [<span data-ttu-id="24465-116">用于 Oracle E-business Suite 适配器的性能计数器</span><span class="sxs-lookup"><span data-stu-id="24465-116">Use Performance Counters with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/use-performance-counters-with-the-oracle-e-business-suite-adapter.md)