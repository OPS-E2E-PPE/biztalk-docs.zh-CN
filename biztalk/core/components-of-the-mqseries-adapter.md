---
title: "组件 MQSeries 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, BizTalk component
- MQSeries adapters, components
- MQSeries components, MQSeries adapters
- BizTalk components
- MQSeries adapters, MQSeries component
ms.assetid: 923974cb-371d-47dc-99a7-2f7b93f60ada
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58726b6528af55da6554ff740208b3e03bdc806e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="components-of-the-mqseries-adapter"></a><span data-ttu-id="77925-102">MQSeries 适配器的组件</span><span class="sxs-lookup"><span data-stu-id="77925-102">Components of the MQSeries Adapter</span></span>
<span data-ttu-id="77925-103">MQSeries 适配器使用两个组件在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 MQSeries Server for Windows 之间进行文档传输。</span><span class="sxs-lookup"><span data-stu-id="77925-103">The MQSeries adapter uses two components to facilitate document transfer between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and MQSeries Server for Windows.</span></span>  
  
-   <span data-ttu-id="77925-104">**BizTalk 组件。**</span><span class="sxs-lookup"><span data-stu-id="77925-104">**BizTalk component.**</span></span> <span data-ttu-id="77925-105">将此组件与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="77925-105">Install this component on the same computer as Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="77925-106">此组件与 BizTalk Server 进行通信。</span><span class="sxs-lookup"><span data-stu-id="77925-106">This component communicates with BizTalk Server.</span></span>  
  
-   <span data-ttu-id="77925-107">**MQSeries 组件。**</span><span class="sxs-lookup"><span data-stu-id="77925-107">**MQSeries component.**</span></span> <span data-ttu-id="77925-108">将此组件安装在 MQSeries Server for Windows 中。</span><span class="sxs-lookup"><span data-stu-id="77925-108">Install this component on the MQSeries Server for Windows.</span></span> <span data-ttu-id="77925-109">MQSeries Server for Windows 在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 上运行。</span><span class="sxs-lookup"><span data-stu-id="77925-109">MQSeries Server for Windows runs on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span></span> <span data-ttu-id="77925-110">此组件（称为 MQSAgent）与 IBM MQSeries Server 进行通信。</span><span class="sxs-lookup"><span data-stu-id="77925-110">This component (referred to as MQSAgent) communicates with IBM MQSeries Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77925-111">MQSeries 适配器的 MQSAgent 组件可在 MQSeries Server 5.3、CSD10 或更高版本以及 WebSphere MQSeries Server 6.0 on Windows 中运行。</span><span class="sxs-lookup"><span data-stu-id="77925-111">The MQSAgent component of the MQSeries Adapter is supported running against MQSeries Server 5.3, CSD10 or above, and WebSphere MQSeries Server 6.0 on Windows.</span></span>  
  
 <span data-ttu-id="77925-112">下图简要介绍了该适配器的典型用法：</span><span class="sxs-lookup"><span data-stu-id="77925-112">The following figure outlines a typical use of the adapter.</span></span>  
  
 <span data-ttu-id="77925-113">![文档 MQSeries 服务器和 BizTalk 之间的流](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")</span><span class="sxs-lookup"><span data-stu-id="77925-113">![Document flow between MQSeries Server and BizTalk](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")</span></span>  
  
 <span data-ttu-id="77925-114">MQSeries 适配器是一种连接解决方案，使用该解决方案，您可以在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries 作为所选消息传递标准的企业中使用 MQSeries。</span><span class="sxs-lookup"><span data-stu-id="77925-114">The MQSeries adapter is a connectivity solution that lets you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in an enterprise with MQSeries as the chosen messaging standard.</span></span> <span data-ttu-id="77925-115">开发此解决方案的部分原因如下：</span><span class="sxs-lookup"><span data-stu-id="77925-115">Developing this solution was motivated, in part, by the following issues:</span></span>  
  
-   <span data-ttu-id="77925-116">适应客户对简单安装和配置以及 MQSeries 连接解决方案的要求</span><span class="sxs-lookup"><span data-stu-id="77925-116">Accommodating customer requests for simple installation and configuration, and an MQSeries connectivity solution</span></span>  
  
-   <span data-ttu-id="77925-117">支持的消息大小最大为 100 MB</span><span class="sxs-lookup"><span data-stu-id="77925-117">Supporting message sizes up to 100 MB</span></span>  
  
-   <span data-ttu-id="77925-118">提供 MQSeries 支持</span><span class="sxs-lookup"><span data-stu-id="77925-118">Providing MQSeries support</span></span>  
  
-   <span data-ttu-id="77925-119">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供即插即用的 MQSeries 消息连接解决方案</span><span class="sxs-lookup"><span data-stu-id="77925-119">Providing a Plug and Play connectivity solution for MQSeries messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
 <span data-ttu-id="77925-120">MQSeries 适配器是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收服务套件的重要组成部分，它为各种通信协议标准提供了一组侦听器。</span><span class="sxs-lookup"><span data-stu-id="77925-120">The MQSeries adapter is a key addition to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suite of receive services that provide a set of listeners for various communication protocol standards.</span></span> <span data-ttu-id="77925-121">侦听器可以向企业应用程序集成 (EAI)、企业对企业或应用程序对应用程序集成贸易关系附加协议（例如 HTTP、FTP 或 MQSeries）。</span><span class="sxs-lookup"><span data-stu-id="77925-121">The listeners attach a protocol, for example HTTP, FTP, or MQSeries, to an enterprise application integration (EAI), business-to-business, or application-to-application integration trading relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77925-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77925-122">See Also</span></span>  
 <span data-ttu-id="77925-123">[MQSeries 适配器体系结构](../core/mqseries-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="77925-123">[MQSeries Adapter Architecture](../core/mqseries-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="77925-124">什么是 MQSeries 适配器？</span><span class="sxs-lookup"><span data-stu-id="77925-124">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)