---
title: MSMQT 弃用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 007d65ce-d2a2-4602-80c8-55b26617f397
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a54e775d9a7f683b11440f1d6ad0e43bdbecb43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263637"
---
# <a name="msmqt-deprecation"></a><span data-ttu-id="2fe66-102">MSMQT 弃用</span><span class="sxs-lookup"><span data-stu-id="2fe66-102">MSMQT Deprecation</span></span>
<span data-ttu-id="2fe66-103">已从 BizTalk Server 删除 MSMQT 功能。</span><span class="sxs-lookup"><span data-stu-id="2fe66-103">The MSMQT feature has been removed from BizTalk Server.</span></span> <span data-ttu-id="2fe66-104">在业务流程设计器中，MSMQT 传输选项仍可在设计时端口配置向导时选择下图中所示**立即指定**选项**端口绑定**.</span><span class="sxs-lookup"><span data-stu-id="2fe66-104">In Orchestration Designer, the MSMQT transport option remains available in the design-time Port Configuration Wizard as shown in the image below when you choose the **Specify now** option for **Port binding**.</span></span>  
  
 <span data-ttu-id="2fe66-105">**显示 MSMQT 传输的端口配置向导**</span><span class="sxs-lookup"><span data-stu-id="2fe66-105">**Port Configuration Wizard showing MSMQT transport**</span></span>  
  
 <span data-ttu-id="2fe66-106">![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")</span><span class="sxs-lookup"><span data-stu-id="2fe66-106">![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")</span></span>  
  
## <a name="biztalk-server-projects"></a><span data-ttu-id="2fe66-107">BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="2fe66-107">BizTalk Server Projects</span></span>  
 <span data-ttu-id="2fe66-108">新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目不应使用 MSMQT 传输选项。</span><span class="sxs-lookup"><span data-stu-id="2fe66-108">New [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] projects should not use the MSMQT transport option.</span></span> <span data-ttu-id="2fe66-109">应用程序部署到 BizTalk Server 将失败并出现错误**协议类型"MSMQT"找不到**。</span><span class="sxs-lookup"><span data-stu-id="2fe66-109">Application deployment to BizTalk Server will fail with the error **Protocol type “MSMQT” not found**.</span></span>  
  
## <a name="migrated-biztalk-server-projects"></a><span data-ttu-id="2fe66-110">迁移的 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="2fe66-110">Migrated BizTalk Server Projects</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="2fe66-111">项目可以使用迁移到 BizTalk Server[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]转换向导中所述[迁移 BizTalk Server 项目](../core/migrating-a-biztalk-server-project.md)。</span><span class="sxs-lookup"><span data-stu-id="2fe66-111">projects can be migrated to BizTalk Server by using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Conversion Wizard as documented in [Migrating a BizTalk Server Project](../core/migrating-a-biztalk-server-project.md).</span></span> <span data-ttu-id="2fe66-112">必须手动重新包含配置为使用 MSMQT 传输的端口的项目配置，然后才能部署到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="2fe66-112">Projects containing ports configured to use the MSMQT transport must be manually reconfigured before deployment to BizTalk Server.</span></span> <span data-ttu-id="2fe66-113">建议的重新配置是使用 MSMQ 适配器。</span><span class="sxs-lookup"><span data-stu-id="2fe66-113">The recommended reconfiguration is to use the MSMQ adapter.</span></span>  <span data-ttu-id="2fe66-114">有关 MSMQ 适配器的详细信息请参阅[什么是 MSMQ 适配器？](../core/what-is-the-msmq-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="2fe66-114">For more information about the MSMQ adapter see [What Is the MSMQ Adapter?](../core/what-is-the-msmq-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fe66-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fe66-115">See Also</span></span>  
 [<span data-ttu-id="2fe66-116">从 MSMQT 适配器迁移到 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="2fe66-116">Migrating from the MSMQT Adapter to the MSMQ Adapter</span></span>](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)