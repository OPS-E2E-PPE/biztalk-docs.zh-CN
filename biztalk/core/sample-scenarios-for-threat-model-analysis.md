---
title: 示例方案的威胁模型分析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TMA, security
- security examples [TMA]
- TMA, examples
- examples, TMA
ms.assetid: e35d1d7f-a71a-42f5-b1f4-fe3234ba7686
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce179e4496ee9be3f9a5d3a2d019128a56485813
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023539"
---
# <a name="sample-scenarios-for-threat-model-analysis"></a><span data-ttu-id="82ed6-102">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="82ed6-102">Sample Scenarios for Threat Model Analysis</span></span>
<span data-ttu-id="82ed6-103">本部分提供的步骤和结果的威胁模型分析 (TMA) 中标识的示例体系结构每个使用方案[适用于小型和中小型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)。</span><span class="sxs-lookup"><span data-stu-id="82ed6-103">This section provides the steps and results of a threat model analysis (TMA) for each usage scenario for the sample architecture identified in [Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md).</span></span> <span data-ttu-id="82ed6-104">本部分的用途是为您显示 TMA 的步骤。</span><span class="sxs-lookup"><span data-stu-id="82ed6-104">The purpose of this section is to show you the steps of a TMA.</span></span> <span data-ttu-id="82ed6-105">这有助于您了解 TMA 的工作方式，并为您介绍对示例结构标识的潜在威胁分类以及建议您减少这些威胁的影响的方式。</span><span class="sxs-lookup"><span data-stu-id="82ed6-105">This helps you understand how a TMA works, and describes for you the potential threats we identified for the sample architecture and how we recommend that you reduce their effect.</span></span>  
  
 <span data-ttu-id="82ed6-106">我们将分类基于不同的适配器可以使用与 Microsoft 的使用方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，以及如何使用企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="82ed6-106">We categorize the usage scenarios based on the different adapters you can use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and the use of Enterprise Single-Sign On.</span></span>  
  
 <span data-ttu-id="82ed6-107">对于每个方案中，我们将遵循以下步骤来完成威胁模型分析：</span><span class="sxs-lookup"><span data-stu-id="82ed6-107">For each scenario, we followed these steps to complete the Threat Model Analysis:</span></span>  
  
- <span data-ttu-id="82ed6-108">收集背景信息</span><span class="sxs-lookup"><span data-stu-id="82ed6-108">Collect background information</span></span>  
  
- <span data-ttu-id="82ed6-109">创建和分析威胁模型</span><span class="sxs-lookup"><span data-stu-id="82ed6-109">Create and analyze the threat model</span></span>  
  
- <span data-ttu-id="82ed6-110">查看威胁</span><span class="sxs-lookup"><span data-stu-id="82ed6-110">Review threats</span></span>  
  
- <span data-ttu-id="82ed6-111">确定缓解措施</span><span class="sxs-lookup"><span data-stu-id="82ed6-111">Identify mitigation techniques and technologies</span></span>  
  
  <span data-ttu-id="82ed6-112">有关威胁模型分析的详细信息，请参阅[威胁模型分析](../core/threat-model-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="82ed6-112">For more information Threat Model Analysis, see [Threat Model Analysis](../core/threat-model-analysis.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82ed6-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="82ed6-113">In This Section</span></span>  
  
-   [<span data-ttu-id="82ed6-114">示例方案的背景信息</span><span class="sxs-lookup"><span data-stu-id="82ed6-114">Background Information for Sample Scenarios</span></span>](../core/background-information-for-sample-scenarios.md)  
  
-   [<span data-ttu-id="82ed6-115">示例 TMA：HTTP 和 SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="82ed6-115">Sample TMA: HTTP and SOAP Adapters</span></span>](../core/sample-tma-http-and-soap-adapters.md)  
  
-   [<span data-ttu-id="82ed6-116">示例 TMA：BizTalk 消息队列适配器</span><span class="sxs-lookup"><span data-stu-id="82ed6-116">Sample TMA: BizTalk Message Queuing Adapter</span></span>](../core/sample-tma-biztalk-message-queuing-adapter.md)  
  
-   [<span data-ttu-id="82ed6-117">示例 TMA：文件适配器</span><span class="sxs-lookup"><span data-stu-id="82ed6-117">Sample TMA: File Adapter</span></span>](../core/sample-tma-file-adapter.md)  
  
-   [<span data-ttu-id="82ed6-118">示例 TMA：FTP 适配器</span><span class="sxs-lookup"><span data-stu-id="82ed6-118">Sample TMA: FTP Adapter</span></span>](../core/sample-tma-ftp-adapter.md)  
  
-   [<span data-ttu-id="82ed6-119">示例 TMA：企业单一登录</span><span class="sxs-lookup"><span data-stu-id="82ed6-119">Sample TMA: Enterprise Single Sign-On</span></span>](../core/sample-tma-enterprise-single-sign-on.md)