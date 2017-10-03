---
title: "开发和配置 BizTalk Server AS2 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62aa76f2-b692-41d9-862a-3e0089635800
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3cd1bfb6bba469f6096242f3e57fd199a4439e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="developing-and-configuring-biztalk-server-as2-solutions"></a><span data-ttu-id="f7bb4-102">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="f7bb4-102">Developing and Configuring BizTalk Server AS2 Solutions</span></span>
## <a name="overview"></a><span data-ttu-id="f7bb4-103">概述</span><span class="sxs-lookup"><span data-stu-id="f7bb4-103">Overview</span></span>
<span data-ttu-id="f7bb4-104">开发人员创建 BizTalk AS2 解决方案的信息。</span><span class="sxs-lookup"><span data-stu-id="f7bb4-104">Information for developers to create BizTalk AS2 solutions.</span></span> <span data-ttu-id="f7bb4-105">使用 BizTalk 项目系统设计环境创建这些解决方案与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f7bb4-105">These solutions are created using the BizTalk project system design environment and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>
  
 <span data-ttu-id="f7bb4-106">在开发 BizTalk Server AS2 解决方案之前，请确保您已经完全安装和配置了具有 AS2 功能的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f7bb4-106">Before developing a BizTalk Server AS2 solution, make sure that you have fully installed and configured [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with the AS2 feature.</span></span> <span data-ttu-id="f7bb4-107">请参阅[BizTalk Server 的最新内容、 安装、 配置和升级](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="f7bb4-107">See [BizTalk Server - What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span> <span data-ttu-id="f7bb4-108">有关所需的开发的 EDI 解决方案的其他 AS2 特定配置，请参阅[后配置步骤来优化您的环境](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="f7bb4-108">For additional AS2-specific configuration that is required for developing an EDI solution, see [Post-configuration steps to optimize your environment](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f7bb4-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="f7bb4-109">In This Section</span></span>  
  
-   [<span data-ttu-id="f7bb4-110">通过文件发送端口发送 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="f7bb4-110">Sending an AS2 Message over a FILE Send Port</span></span>](../core/sending-an-as2-message-over-a-file-send-port.md)  
  
-   [<span data-ttu-id="f7bb4-111">配置 AS2 属性</span><span class="sxs-lookup"><span data-stu-id="f7bb4-111">Configuring AS2 Properties</span></span>](../core/configuring-as2-properties.md)  
  
-   [<span data-ttu-id="f7bb4-112">配置 AS2 管道属性</span><span class="sxs-lookup"><span data-stu-id="f7bb4-112">Configuring AS2 Pipeline Properties</span></span>](../core/configuring-as2-pipeline-properties.md)  
  
-   [<span data-ttu-id="f7bb4-113">为 AS2 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="f7bb4-113">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)  
  
-   [<span data-ttu-id="f7bb4-114">AS2 安全</span><span class="sxs-lookup"><span data-stu-id="f7bb4-114">AS2 Security</span></span>](../core/as2-security.md)  
  
-   [<span data-ttu-id="f7bb4-115">为出站的参与方解析编写 AS2 上下文属性</span><span class="sxs-lookup"><span data-stu-id="f7bb4-115">Writing AS2 Context Properties for Outbound Party Resolution</span></span>](../core/writing-as2-context-properties-for-outbound-party-resolution.md)  
  
-   [<span data-ttu-id="f7bb4-116">AS2 上下文属性</span><span class="sxs-lookup"><span data-stu-id="f7bb4-116">AS2 Context Properties</span></span>](../core/as2-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="f7bb4-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7bb4-117">See Also</span></span>  
[<span data-ttu-id="f7bb4-118">教程和演练 EDI、 AS2 和 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="f7bb4-118">Tutorials and walkthroughs for EDI, AS2, and EDIFACT</span></span>](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)  
[<span data-ttu-id="f7bb4-119">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="f7bb4-119">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)