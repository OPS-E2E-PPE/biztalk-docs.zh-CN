---
title: "MSMQT 弃用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 007d65ce-d2a2-4602-80c8-55b26617f397
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e7095c73cd337a1fb08f2d867e817ad5838206
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="msmqt-deprecation"></a><span data-ttu-id="f8e8c-102">MSMQT 弃用</span><span class="sxs-lookup"><span data-stu-id="f8e8c-102">MSMQT Deprecation</span></span>
<span data-ttu-id="f8e8c-103">已从 BizTalk Server 中删除 MSMQT 功能。</span><span class="sxs-lookup"><span data-stu-id="f8e8c-103">The MSMQT feature has been removed from BizTalk Server.</span></span> <span data-ttu-id="f8e8c-104">业务流程的设计器中 MSMQT 传输选项仍可在设计时端口配置向导时选择下面的图中所示**现在指定**选项**端口绑定**.</span><span class="sxs-lookup"><span data-stu-id="f8e8c-104">In Orchestration Designer, the MSMQT transport option remains available in the design-time Port Configuration Wizard as shown in the image below when you choose the **Specify now** option for **Port binding**.</span></span>  
  
 <span data-ttu-id="f8e8c-105">**显示 MSMQT 传输的端口配置向导**</span><span class="sxs-lookup"><span data-stu-id="f8e8c-105">**Port Configuration Wizard showing MSMQT transport**</span></span>  
  
 ![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")  
  
## <a name="biztalk-server-projects"></a><span data-ttu-id="f8e8c-106">BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="f8e8c-106">BizTalk Server Projects</span></span>  
 <span data-ttu-id="f8e8c-107">新的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目不应使用 MSMQT 传输选项。</span><span class="sxs-lookup"><span data-stu-id="f8e8c-107">New [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] projects should not use the MSMQT transport option.</span></span> <span data-ttu-id="f8e8c-108">应用程序部署到[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]将失败并出现错误**协议类型"MSMQT"找不到**。</span><span class="sxs-lookup"><span data-stu-id="f8e8c-108">Application deployment to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] will fail with the error **Protocol type “MSMQT” not found**.</span></span>  
  
## <a name="migrated-biztalk-server-projects"></a><span data-ttu-id="f8e8c-109">迁移的 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="f8e8c-109">Migrated BizTalk Server Projects</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f8e8c-110">能够将项目迁移到[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]转换向导中所述[迁移 BizTalk 服务器项目](../core/migrating-a-biztalk-server-project.md)。</span><span class="sxs-lookup"><span data-stu-id="f8e8c-110"> projects can be migrated to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] by using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Conversion Wizard as documented in [Migrating a BizTalk Server Project](../core/migrating-a-biztalk-server-project.md).</span></span> <span data-ttu-id="f8e8c-111">对于包含配置为使用 MSMQT 传输的端口的项目，必须对其手动重新配置，然后才能部署到 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f8e8c-111">Projects containing ports configured to use the MSMQT transport must be manually reconfigured before deployment to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span> <span data-ttu-id="f8e8c-112">建议使用 MSMQ 适配器进行重新配置。</span><span class="sxs-lookup"><span data-stu-id="f8e8c-112">The recommended reconfiguration is to use the MSMQ adapter.</span></span>  <span data-ttu-id="f8e8c-113">有关 MSMQ 适配器的详细信息请参阅[MSMQ 适配器是什么？](../core/what-is-the-msmq-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="f8e8c-113">For more information about the MSMQ adapter see [What Is the MSMQ Adapter?](../core/what-is-the-msmq-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e8c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8e8c-114">See Also</span></span>  
 [<span data-ttu-id="f8e8c-115">从 MSMQT 适配器迁移到 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="f8e8c-115">Migrating from the MSMQT Adapter to the MSMQ Adapter</span></span>](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)