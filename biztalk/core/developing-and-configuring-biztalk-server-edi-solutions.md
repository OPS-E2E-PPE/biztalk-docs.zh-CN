---
title: 开发和配置 BizTalk Server EDI 解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65629eb1-8e08-4233-9331-c53ae0abaed4
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6520b062ebc5c106e2f162cc92ff4c793a417b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240197"
---
# <a name="developing-and-configuring-biztalk-server-edi-solutions"></a><span data-ttu-id="9a239-102">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="9a239-102">Developing and Configuring BizTalk Server EDI Solutions</span></span>
<span data-ttu-id="9a239-103">有关开发人员创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 解决方案。</span><span class="sxs-lookup"><span data-stu-id="9a239-103">Information for developers to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI solutions.</span></span> <span data-ttu-id="9a239-104">使用 BizTalk 项目系统设计环境创建这些解决方案与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="9a239-104">These solutions are created using the BizTalk project system design environment and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="9a239-105">在开发 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 解决方案之前，请确保您已经完全安装和配置具有 EDI 功能的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9a239-105">Before developing a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI solution, make sure that you have fully installed and configured [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with the EDI feature.</span></span> <span data-ttu-id="9a239-106">请参阅[BizTalk Server 的最新内容、 安装、 配置和升级](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="9a239-106">See [BizTalk Server - What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span> <span data-ttu-id="9a239-107">开发 EDI 解决方案所需的其他 EDI 特定配置，请参阅[后配置步骤来优化您的环境](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="9a239-107">For additional EDI-specific configuration required for developing an EDI solution, see [Post-configuration steps to optimize your environment](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a239-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="9a239-108">In This Section</span></span>  
  
-   [<span data-ttu-id="9a239-109">配置 EDI 属性</span><span class="sxs-lookup"><span data-stu-id="9a239-109">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)  
  
-   [<span data-ttu-id="9a239-110">配置全局或后备协议属性</span><span class="sxs-lookup"><span data-stu-id="9a239-110">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)  
  
-   [<span data-ttu-id="9a239-111">配置 EDI 管道属性</span><span class="sxs-lookup"><span data-stu-id="9a239-111">Configuring EDI Pipeline Properties</span></span>](../core/configuring-edi-pipeline-properties.md)  
  
-   [<span data-ttu-id="9a239-112">为 EDI 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="9a239-112">Configuring Ports for an EDI Solution</span></span>](../core/configuring-ports-for-an-edi-solution.md)  
  
-   [<span data-ttu-id="9a239-113">配置 EDI 确认</span><span class="sxs-lookup"><span data-stu-id="9a239-113">Configuring EDI Acknowledgments</span></span>](../core/configuring-edi-acknowledgments.md)  
  
-   [<span data-ttu-id="9a239-114">配置 EDI 批处理</span><span class="sxs-lookup"><span data-stu-id="9a239-114">Configuring EDI Batches</span></span>](../core/configuring-edi-batches.md)  
  
-   [<span data-ttu-id="9a239-115">开发 EDI 架构</span><span class="sxs-lookup"><span data-stu-id="9a239-115">Developing EDI Schemas</span></span>](../core/developing-edi-schemas.md)  
  
-   [<span data-ttu-id="9a239-116">通过使用设计时 XML 工具</span><span class="sxs-lookup"><span data-stu-id="9a239-116">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)  
  
-   [<span data-ttu-id="9a239-117">EDI 上下文属性</span><span class="sxs-lookup"><span data-stu-id="9a239-117">EDI Context Properties</span></span>](../core/edi-context-properties.md)  
  
-   [<span data-ttu-id="9a239-118">EDI 替代上下文属性</span><span class="sxs-lookup"><span data-stu-id="9a239-118">EDI Override Context Properties</span></span>](../core/edi-override-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="9a239-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a239-119">See Also</span></span>  

[<span data-ttu-id="9a239-120">教程和演练 EDI、 AS2 和 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="9a239-120">Tutorials and walkthroughs for EDI, AS2, and EDIFACT</span></span>](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)  
[<span data-ttu-id="9a239-121">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="9a239-121">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)