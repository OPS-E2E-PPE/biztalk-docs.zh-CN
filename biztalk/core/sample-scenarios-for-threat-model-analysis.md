---
title: "示例方案的威胁模型分析 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TMA, security
- security examples [TMA]
- TMA, examples
- examples, TMA
ms.assetid: e35d1d7f-a71a-42f5-b1f4-fe3234ba7686
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afc1e375945ec7b40c56274adc5e18cb1ee67f97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-scenarios-for-threat-model-analysis"></a><span data-ttu-id="468b2-102">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="468b2-102">Sample Scenarios for Threat Model Analysis</span></span>
<span data-ttu-id="468b2-103">本部分提供的步骤和结果的威胁模型分析 (TMA) 示例体系结构中标识每种使用方案[适用于小型和 Medium-Sized 公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)。</span><span class="sxs-lookup"><span data-stu-id="468b2-103">This section provides the steps and results of a threat model analysis (TMA) for each usage scenario for the sample architecture identified in [Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md).</span></span> <span data-ttu-id="468b2-104">本部分的用途是为您显示 TMA 的步骤。</span><span class="sxs-lookup"><span data-stu-id="468b2-104">The purpose of this section is to show you the steps of a TMA.</span></span> <span data-ttu-id="468b2-105">这有助于您了解 TMA 的工作方式，并为您介绍对示例结构标识的潜在威胁分类以及建议您减少这些威胁的影响的方式。</span><span class="sxs-lookup"><span data-stu-id="468b2-105">This helps you understand how a TMA works, and describes for you the potential threats we identified for the sample architecture and how we recommend that you reduce their effect.</span></span>  
  
 <span data-ttu-id="468b2-106">我们对其进行分类基于不同的适配器可以使用与 Microsoft 的使用方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并使用的企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="468b2-106">We categorize the usage scenarios based on the different adapters you can use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and the use of Enterprise Single-Sign On.</span></span>  
  
 <span data-ttu-id="468b2-107">对于每个方案，请遵循以下步骤完成威胁模型分析：</span><span class="sxs-lookup"><span data-stu-id="468b2-107">For each scenario, we followed these steps to complete the Threat Model Analysis:</span></span>  
  
-   <span data-ttu-id="468b2-108">收集的背景信息</span><span class="sxs-lookup"><span data-stu-id="468b2-108">Collect background information</span></span>  
  
-   <span data-ttu-id="468b2-109">创建和分析的威胁模型</span><span class="sxs-lookup"><span data-stu-id="468b2-109">Create and analyze the threat model</span></span>  
  
-   <span data-ttu-id="468b2-110">查看威胁</span><span class="sxs-lookup"><span data-stu-id="468b2-110">Review threats</span></span>  
  
-   <span data-ttu-id="468b2-111">标识缓解技术和技术</span><span class="sxs-lookup"><span data-stu-id="468b2-111">Identify mitigation techniques and technologies</span></span>  
  
 <span data-ttu-id="468b2-112">有关威胁模型分析的详细信息，请参阅[威胁模型分析](../core/threat-model-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="468b2-112">For more information Threat Model Analysis, see [Threat Model Analysis](../core/threat-model-analysis.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="468b2-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="468b2-113">In This Section</span></span>  
  
-   [<span data-ttu-id="468b2-114">示例方案的背景信息</span><span class="sxs-lookup"><span data-stu-id="468b2-114">Background Information for Sample Scenarios</span></span>](../core/background-information-for-sample-scenarios.md)  
  
-   [<span data-ttu-id="468b2-115">示例 TMA: HTTP 和 SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="468b2-115">Sample TMA: HTTP and SOAP Adapters</span></span>](../core/sample-tma-http-and-soap-adapters.md)  
  
-   [<span data-ttu-id="468b2-116">示例 TMA: BizTalk 消息队列适配器</span><span class="sxs-lookup"><span data-stu-id="468b2-116">Sample TMA: BizTalk Message Queuing Adapter</span></span>](../core/sample-tma-biztalk-message-queuing-adapter.md)  
  
-   [<span data-ttu-id="468b2-117">示例 TMA： 文件适配器</span><span class="sxs-lookup"><span data-stu-id="468b2-117">Sample TMA: File Adapter</span></span>](../core/sample-tma-file-adapter.md)  
  
-   [<span data-ttu-id="468b2-118">示例 TMA: FTP 适配器</span><span class="sxs-lookup"><span data-stu-id="468b2-118">Sample TMA: FTP Adapter</span></span>](../core/sample-tma-ftp-adapter.md)  
  
-   [<span data-ttu-id="468b2-119">示例 TMA: Enterprise 上单一登录</span><span class="sxs-lookup"><span data-stu-id="468b2-119">Sample TMA: Enterprise Single Sign-On</span></span>](../core/sample-tma-enterprise-single-sign-on.md)