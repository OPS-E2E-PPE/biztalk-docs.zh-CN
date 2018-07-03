---
title: 贸易合作伙伴管理使用 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f31a5e49-ef19-41a3-9cf3-cf85d0685a59
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed1a3591314634c41cfd598aa074e497dd19ec03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983718"
---
# <a name="trading-partner-management-using-biztalk-server"></a><span data-ttu-id="2dce7-102">使用 BizTalk Server 进行贸易合作伙伴管理</span><span class="sxs-lookup"><span data-stu-id="2dce7-102">Trading Partner Management Using BizTalk Server</span></span>
## <a name="introduction-to-tpm"></a><span data-ttu-id="2dce7-103">TPM 简介</span><span class="sxs-lookup"><span data-stu-id="2dce7-103">Introduction to TPM</span></span>
<span data-ttu-id="2dce7-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 贸易合作伙伴管理 (TPM) 围绕如何管理和存储有关合作伙伴及其业务的信息重建基本概念。</span><span class="sxs-lookup"><span data-stu-id="2dce7-104">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Trading Partner Management (TPM) rebuilds the fundamental concepts around how to manage and store information about partners and their business.</span></span> <span data-ttu-id="2dce7-105">增强 TPM 解决方案反映了字段中的业务实体和关系，从而使组织能够更好地管理与贸易合作伙伴的业务伙伴关系。</span><span class="sxs-lookup"><span data-stu-id="2dce7-105">The enhanced TPM solution reflects the business entities and relationships in the field, thereby enabling organizations to better manage your business partnerships with trading partners.</span></span> <span data-ttu-id="2dce7-106">TPM 解决方案如何塑造 BizTalk 环境中的贸易伙伴关系的详细信息，请参阅[贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="2dce7-106">For more information on how the TPM solution models trading partnerships in a BizTalk environment, see [Building Blocks of a Trading Partner Management Solution](../core/building-blocks-of-a-trading-partner-management-solution.md).</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2dce7-107"> 包括对电子数据交换 (EDI) 数据交换和 AS2 数据传输的本机支持。</span><span class="sxs-lookup"><span data-stu-id="2dce7-107"> includes native support for Electronic Data Interchange (EDI) data exchange and AS2 data transport.</span></span> <span data-ttu-id="2dce7-108">凭借这种支持，企业可以将基于 EDI 的业务流程管理解决方案加以扩展，充分利用 EDI 事务的自动化交换能力所提供的生产力改进。</span><span class="sxs-lookup"><span data-stu-id="2dce7-108">This support enables businesses to extend their EDI-based business process management solutions, taking advantage of the productivity improvements that the automated exchange of EDI transactions provides.</span></span> <span data-ttu-id="2dce7-109">使用 BizTalk Server 后，这些企业可使用 EDI 和 EDIINT/AS2 以更为安全和可靠的方式将合作伙伴连接到关键的供应链业务流程。</span><span class="sxs-lookup"><span data-stu-id="2dce7-109">BizTalk Server provides these businesses with the means to more securely and reliably connect partners to critical supply-chain business processes using EDI and EDIINT/AS2.</span></span>  
  
 <span data-ttu-id="2dce7-110">TPM 解决方案结合了 EDI 和 AS2 支持中管理贸易合作伙伴提供功能强大且可扩展的解决方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2dce7-110">The TPM solution coupled with the EDI and AS2 support provide a robust and scalable solution for managing trading partners in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="2dce7-111">本部分中的主题和下面列出的其他主题提供了 TPM 和如何使用 TPM 管理贸易合作伙伴的高级概述。</span><span class="sxs-lookup"><span data-stu-id="2dce7-111">The topics in this section, and other topics listed below, provide a high-level overview of TPM and how to use TPM to manage trading partners.</span></span> <span data-ttu-id="2dce7-112">该主题还提供了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何执行 EDI 和 AS2 处理的概述。</span><span class="sxs-lookup"><span data-stu-id="2dce7-112">The topics also provide description of how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performs EDI and AS2 processing.</span></span>  
  
## <a name="in-this-section-and-more-good-info"></a><span data-ttu-id="2dce7-113">在本部分和良好的详细信息</span><span class="sxs-lookup"><span data-stu-id="2dce7-113">In this section and more good info</span></span>

<span data-ttu-id="2dce7-114">**了解，开始，和教程**</span><span class="sxs-lookup"><span data-stu-id="2dce7-114">**Learn, get started, and tutorials**</span></span>  

-   [<span data-ttu-id="2dce7-115">贸易合作伙伴管理解决方案的构建基块</span><span class="sxs-lookup"><span data-stu-id="2dce7-115">Building Blocks of a Trading Partner Management Solution</span></span>](../core/building-blocks-of-a-trading-partner-management-solution.md)  
  
-   [<span data-ttu-id="2dce7-116">BizTalk Server EDI 功能</span><span class="sxs-lookup"><span data-stu-id="2dce7-116">BizTalk Server EDI Functionality</span></span>](../core/biztalk-server-edi-functionality.md)  
  
-   [<span data-ttu-id="2dce7-117">BizTalk Server AS2 功能</span><span class="sxs-lookup"><span data-stu-id="2dce7-117">BizTalk Server AS2 Functionality</span></span>](../core/biztalk-server-as2-functionality.md)  

- [<span data-ttu-id="2dce7-118">EDI 和 AS2 解决方案体系结构</span><span class="sxs-lookup"><span data-stu-id="2dce7-118">EDI and AS2 solution architecture</span></span>](../core/edi-and-as2-solution-architecture.md)

-   [<span data-ttu-id="2dce7-119">用于优化环境的配置后步骤</span><span class="sxs-lookup"><span data-stu-id="2dce7-119">Post-configuration steps to optimize your environment</span></span>](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md) 

- [<span data-ttu-id="2dce7-120">EDI、AS2 和 EDIFACT 的教程和演练</span><span class="sxs-lookup"><span data-stu-id="2dce7-120">Tutorials and walkthroughs for EDI, AS2, and EDIFACT</span></span>](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)


<span data-ttu-id="2dce7-121">**在创建 EDI 和 AS2 解决方案的深入探讨**</span><span class="sxs-lookup"><span data-stu-id="2dce7-121">**Deep-dive in creating EDI and AS2 solutions**</span></span>
- [<span data-ttu-id="2dce7-122">创建 EDI 和 AS2 项目</span><span class="sxs-lookup"><span data-stu-id="2dce7-122">Create EDI and AS2 artifacts</span></span>](../core/managing-edi-and-as2-solutions.md)

- [<span data-ttu-id="2dce7-123">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="2dce7-123">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)

- [<span data-ttu-id="2dce7-124">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="2dce7-124">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)

-   [<span data-ttu-id="2dce7-125">EDI 和 AS2 SDK 示例）</span><span class="sxs-lookup"><span data-stu-id="2dce7-125">EDI and AS2 SDK samples)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)  


 <span data-ttu-id="2dce7-126">**使用绑定文件**</span><span class="sxs-lookup"><span data-stu-id="2dce7-126">**Using binding files**</span></span>  

- [<span data-ttu-id="2dce7-127">使用绑定文件导入或导出的新 BizTalk Server 2016 中</span><span class="sxs-lookup"><span data-stu-id="2dce7-127">Use binding files to import or export - NEW in BizTalk Server 2016</span></span>](../core/use-binding-files-to-import-or-export.md)  

-   [<span data-ttu-id="2dce7-128">如何导出 EDI-AS2 解决方案的绑定</span><span class="sxs-lookup"><span data-stu-id="2dce7-128">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)  
  
-   [<span data-ttu-id="2dce7-129">如何导入 EDI-AS2 解决方案的绑定</span><span class="sxs-lookup"><span data-stu-id="2dce7-129">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)  
  
-   [<span data-ttu-id="2dce7-130">自定义绑定文件</span><span class="sxs-lookup"><span data-stu-id="2dce7-130">Customizing Binding Files</span></span>](../core/customizing-binding-files.md)  


<span data-ttu-id="2dce7-131">**监视和故障排除**</span><span class="sxs-lookup"><span data-stu-id="2dce7-131">**Monitor and troubleshoot**</span></span>

- [<span data-ttu-id="2dce7-132">监视 EDI 和 AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="2dce7-132">Monitoring EDI and AS2 Solutions</span></span>](../core/monitoring-edi-and-as2-solutions.md)

- [<span data-ttu-id="2dce7-133">EDI 和 AS2 解决方案的疑难解答</span><span class="sxs-lookup"><span data-stu-id="2dce7-133">Troubleshooting EDI and AS2 Solutions</span></span>](../core/troubleshooting-edi-and-as2-solutions.md)
  
- <span data-ttu-id="2dce7-134">查看 UI 详细信息 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="2dce7-134">View UI details [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span> 
  
- [<span data-ttu-id="2dce7-135">EDI 和 AS2 事件和错误</span><span class="sxs-lookup"><span data-stu-id="2dce7-135">EDI and AS2 Events and Errors</span></span>](../core/edi-and-as2-events-and-errors.md)
 


  
