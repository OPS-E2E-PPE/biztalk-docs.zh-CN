---
title: MQSeries 适配器的组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, BizTalk component
- MQSeries adapters, components
- MQSeries components, MQSeries adapters
- BizTalk components
- MQSeries adapters, MQSeries component
ms.assetid: 923974cb-371d-47dc-99a7-2f7b93f60ada
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c6a97bd38a68eef866549f980624a92ee2b3143
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391635"
---
# <a name="components-of-the-mqseries-adapter"></a><span data-ttu-id="d8455-102">MQSeries 适配器的组件</span><span class="sxs-lookup"><span data-stu-id="d8455-102">Components of the MQSeries Adapter</span></span>
<span data-ttu-id="d8455-103">MQSeries 适配器使用两个组件之间进行文档传输[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 MQSeries Server for Windows。</span><span class="sxs-lookup"><span data-stu-id="d8455-103">The MQSeries adapter uses two components to facilitate document transfer between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and MQSeries Server for Windows.</span></span>  
  
- <span data-ttu-id="d8455-104">**BizTalk 组件。**</span><span class="sxs-lookup"><span data-stu-id="d8455-104">**BizTalk component.**</span></span> <span data-ttu-id="d8455-105">Microsoft 在同一台计算机上安装此组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d8455-105">Install this component on the same computer as Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d8455-106">此组件与 BizTalk Server 进行通信。</span><span class="sxs-lookup"><span data-stu-id="d8455-106">This component communicates with BizTalk Server.</span></span>  
  
- <span data-ttu-id="d8455-107">**MQSeries 组件。**</span><span class="sxs-lookup"><span data-stu-id="d8455-107">**MQSeries component.**</span></span> <span data-ttu-id="d8455-108">对于 Windows MQSeries 服务器上安装此组件。</span><span class="sxs-lookup"><span data-stu-id="d8455-108">Install this component on the MQSeries Server for Windows.</span></span> <span data-ttu-id="d8455-109">MQSeries Server for Windows 上运行[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d8455-109">MQSeries Server for Windows runs on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span></span> <span data-ttu-id="d8455-110">此组件 （称为 MQSAgent） 与 IBM MQSeries 服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="d8455-110">This component (referred to as MQSAgent) communicates with IBM MQSeries Server.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="d8455-111">MQSeries 适配器的 MQSAgent 组件是支持的运行 MQSeries Server 5.3、 CSD10 或更高版本，并在 Windows 上的 WebSphere MQSeries Server 6.0。</span><span class="sxs-lookup"><span data-stu-id="d8455-111">The MQSAgent component of the MQSeries Adapter is supported running against MQSeries Server 5.3, CSD10 or above, and WebSphere MQSeries Server 6.0 on Windows.</span></span>  
  
  <span data-ttu-id="d8455-112">下图概述了该适配器的典型用法。</span><span class="sxs-lookup"><span data-stu-id="d8455-112">The following figure outlines a typical use of the adapter.</span></span>  
  
  <span data-ttu-id="d8455-113">![文档 MQSeries Server 和 BizTalk 之间的流](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")</span><span class="sxs-lookup"><span data-stu-id="d8455-113">![Document flow between MQSeries Server and BizTalk](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")</span></span>  
  
  <span data-ttu-id="d8455-114">MQSeries 适配器是一种连接解决方案，使您可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的企业中使用 MQSeries 作为所选的消息传送标准。</span><span class="sxs-lookup"><span data-stu-id="d8455-114">The MQSeries adapter is a connectivity solution that lets you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in an enterprise with MQSeries as the chosen messaging standard.</span></span> <span data-ttu-id="d8455-115">开发此解决方案时的部分原因，由以下问题：</span><span class="sxs-lookup"><span data-stu-id="d8455-115">Developing this solution was motivated, in part, by the following issues:</span></span>  
  
- <span data-ttu-id="d8455-116">对于简单的安装和配置以及 MQSeries 连接解决方案如何适应客户请求</span><span class="sxs-lookup"><span data-stu-id="d8455-116">Accommodating customer requests for simple installation and configuration, and an MQSeries connectivity solution</span></span>  
  
- <span data-ttu-id="d8455-117">支持的消息大小最大 100 MB</span><span class="sxs-lookup"><span data-stu-id="d8455-117">Supporting message sizes up to 100 MB</span></span>  
  
- <span data-ttu-id="d8455-118">提供 MQSeries 支持</span><span class="sxs-lookup"><span data-stu-id="d8455-118">Providing MQSeries support</span></span>  
  
- <span data-ttu-id="d8455-119">提供的 MQSeries 消息插连接解决方案 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8455-119">Providing a Plug and Play connectivity solution for MQSeries messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
  <span data-ttu-id="d8455-120">MQSeries 适配器是一个重要的补充[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为各种通信协议标准提供了一组侦听器接收服务套件。</span><span class="sxs-lookup"><span data-stu-id="d8455-120">The MQSeries adapter is a key addition to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suite of receive services that provide a set of listeners for various communication protocol standards.</span></span> <span data-ttu-id="d8455-121">侦听器将一种协议，例如 HTTP、 FTP 或 MQSeries，附加到的企业应用程序集成 (EAI)，企业到企业或应用程序集成贸易关系。</span><span class="sxs-lookup"><span data-stu-id="d8455-121">The listeners attach a protocol, for example HTTP, FTP, or MQSeries, to an enterprise application integration (EAI), business-to-business, or application-to-application integration trading relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8455-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8455-122">See Also</span></span>  
 <span data-ttu-id="d8455-123">[MQSeries 适配器体系结构](../core/mqseries-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d8455-123">[MQSeries Adapter Architecture](../core/mqseries-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="d8455-124">MQSeries 适配器概述</span><span class="sxs-lookup"><span data-stu-id="d8455-124">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)