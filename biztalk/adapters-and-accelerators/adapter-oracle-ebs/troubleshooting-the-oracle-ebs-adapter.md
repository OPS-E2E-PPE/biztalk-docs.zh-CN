---
title: Oracle EBS 适配器故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d78d5335-b860-47d9-9f3a-7f74d628d8ff
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d4011252a27d2b7f4c86490ea9d55343d504ad3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374367"
---
# <a name="troubleshooting-the-oracle-ebs-adapter"></a><span data-ttu-id="dc83c-102">Oracle EBS 适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="dc83c-102">Troubleshooting the Oracle EBS adapter</span></span>
## <a name="overview"></a><span data-ttu-id="dc83c-103">概述</span><span class="sxs-lookup"><span data-stu-id="dc83c-103">Overview</span></span>
<span data-ttu-id="dc83c-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]使用或依赖于多个 Microsoft 技术，包括但不是限于[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，和[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dc83c-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="dc83c-105">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]构建的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，该列也会使用[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dc83c-105">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which also uses the [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="dc83c-106">可以使用适配器，或者通过编写应用程序使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或通过创建 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="dc83c-106">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> 
  
 <span data-ttu-id="dc83c-107">本部分提供了疑难解答信息，包括：</span><span class="sxs-lookup"><span data-stu-id="dc83c-107">This section provides information about troubleshooting, including:</span></span>  
  
-   <span data-ttu-id="dc83c-108">启用跟踪来诊断适配器的问题</span><span class="sxs-lookup"><span data-stu-id="dc83c-108">Enabling tracing to diagnose issues with the adapters</span></span>
  
-   <span data-ttu-id="dc83c-109">处理安装和运行时使用的适配器，包括可能的原因和解决方法可能会遇到的问题</span><span class="sxs-lookup"><span data-stu-id="dc83c-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause and a resolution</span></span>
  
-   <span data-ttu-id="dc83c-110">使用性能计数器以查看适配器性能</span><span class="sxs-lookup"><span data-stu-id="dc83c-110">Using performance counters to review adapter performance</span></span>
  
-   <span data-ttu-id="dc83c-111">处理异常和错误，包括可能原因和解决方法</span><span class="sxs-lookup"><span data-stu-id="dc83c-111">Handling exceptions and errors, including probable cause, and a resolution</span></span>
  
## <a name="lets-get-started"></a><span data-ttu-id="dc83c-112">让我们开始吧</span><span class="sxs-lookup"><span data-stu-id="dc83c-112">Let's get started</span></span>  
  
-   [<span data-ttu-id="dc83c-113">诊断跟踪和消息日志记录中的 Oracle E-business Suite 适配器</span><span class="sxs-lookup"><span data-stu-id="dc83c-113">Diagnostic Tracing and Message Logging in the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md) 
  
-   [<span data-ttu-id="dc83c-114">使用 Oracle E-business Suite 适配器进行故障排除安装问题：</span><span class="sxs-lookup"><span data-stu-id="dc83c-114">Troubleshoot Installation Issues with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshoot-installation-issues-with-the-oracle-e-business-suite-adapter.md)  
  
-   [<span data-ttu-id="dc83c-115">使用 Oracle E-business Suite 适配器进行的操作问题故障排除</span><span class="sxs-lookup"><span data-stu-id="dc83c-115">Troubleshoot Operational Issues with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter.md)
  
-   [<span data-ttu-id="dc83c-116">用于 Oracle E-business Suite 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="dc83c-116">Use Performance Counters with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/use-performance-counters-with-the-oracle-e-business-suite-adapter.md)