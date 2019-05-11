---
title: 开发和配置 BizTalk Server EDI 解决方案 |Microsoft Docs
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
ms.openlocfilehash: e846048a8aa90cd671bae085459632c807dd5d65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389419"
---
# <a name="developing-and-configuring-biztalk-server-edi-solutions"></a><span data-ttu-id="df5d5-102">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="df5d5-102">Developing and Configuring BizTalk Server EDI Solutions</span></span>
<span data-ttu-id="df5d5-103">开发人员能够创建信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 解决方案。</span><span class="sxs-lookup"><span data-stu-id="df5d5-103">Information for developers to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI solutions.</span></span> <span data-ttu-id="df5d5-104">这些解决方案创建使用 BizTalk 项目系统设计环境和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="df5d5-104">These solutions are created using the BizTalk project system design environment and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="df5d5-105">在开发前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 解决方案，请确保您已经完全安装和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有 EDI 功能。</span><span class="sxs-lookup"><span data-stu-id="df5d5-105">Before developing a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI solution, make sure that you have fully installed and configured [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with the EDI feature.</span></span> <span data-ttu-id="df5d5-106">请参阅[BizTalk Server 的最新内容、 安装、 配置和升级](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="df5d5-106">See [BizTalk Server - What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span> <span data-ttu-id="df5d5-107">有关开发 EDI 解决方案所需的其他特定于 EDI 的配置，请参阅[用于优化环境的配置后步骤](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="df5d5-107">For additional EDI-specific configuration required for developing an EDI solution, see [Post-configuration steps to optimize your environment](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="df5d5-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="df5d5-108">In This Section</span></span>  
  
-   [<span data-ttu-id="df5d5-109">配置 EDI 属性</span><span class="sxs-lookup"><span data-stu-id="df5d5-109">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)  
  
-   [<span data-ttu-id="df5d5-110">配置全局或后备协议属性</span><span class="sxs-lookup"><span data-stu-id="df5d5-110">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)  
  
-   [<span data-ttu-id="df5d5-111">配置 EDI 管道属性</span><span class="sxs-lookup"><span data-stu-id="df5d5-111">Configuring EDI Pipeline Properties</span></span>](../core/configuring-edi-pipeline-properties.md)  
  
-   [<span data-ttu-id="df5d5-112">为 EDI 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="df5d5-112">Configuring Ports for an EDI Solution</span></span>](../core/configuring-ports-for-an-edi-solution.md)  
  
-   [<span data-ttu-id="df5d5-113">配置 EDI 确认</span><span class="sxs-lookup"><span data-stu-id="df5d5-113">Configuring EDI Acknowledgments</span></span>](../core/configuring-edi-acknowledgments.md)  
  
-   [<span data-ttu-id="df5d5-114">配置 EDI 批</span><span class="sxs-lookup"><span data-stu-id="df5d5-114">Configuring EDI Batches</span></span>](../core/configuring-edi-batches.md)  
  
-   [<span data-ttu-id="df5d5-115">开发 EDI 架构</span><span class="sxs-lookup"><span data-stu-id="df5d5-115">Developing EDI Schemas</span></span>](../core/developing-edi-schemas.md)  
  
-   [<span data-ttu-id="df5d5-116">通过使用设计时 XML 工具</span><span class="sxs-lookup"><span data-stu-id="df5d5-116">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)  
  
-   [<span data-ttu-id="df5d5-117">EDI 上下文属性</span><span class="sxs-lookup"><span data-stu-id="df5d5-117">EDI Context Properties</span></span>](../core/edi-context-properties.md)  
  
-   [<span data-ttu-id="df5d5-118">EDI 替代上下文属性</span><span class="sxs-lookup"><span data-stu-id="df5d5-118">EDI Override Context Properties</span></span>](../core/edi-override-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="df5d5-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="df5d5-119">See Also</span></span>  

[<span data-ttu-id="df5d5-120">EDI、AS2 和 EDIFACT 的教程和演练</span><span class="sxs-lookup"><span data-stu-id="df5d5-120">Tutorials and walkthroughs for EDI, AS2, and EDIFACT</span></span>](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)  
[<span data-ttu-id="df5d5-121">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="df5d5-121">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)