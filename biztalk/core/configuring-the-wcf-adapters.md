---
title: 配置 WCF 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- NetTcpBinding [WCF adapters]
- configuring [WCF adapters]
- WCF adapters, pre-defined bindings
- configuring [WCF adapters], about configuring WCF adapters
- WsHttpBinding [WCF adapters]
- BasicHttpBinding [WCF adapters]
- NetNamedPipeBinding [WCF adapters]
- NetMsmqBinding [WCF adapters]
- bindings, pre-defined [WCF adapters]
- WCF adapters, configuring
ms.assetid: af01e2d4-303d-407a-b853-dd90b0246a8a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dde69bb5b2014a20509778e27230840e47c0b36d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233157"
---
# <a name="configuring-the-wcf-adapters"></a><span data-ttu-id="611a3-102">配置 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="611a3-102">Configuring the WCF Adapters</span></span>
<span data-ttu-id="611a3-103">用于 Windows Communication Foundation (WCF) 的 BizTalk 适配器允许 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与基于 WCF 的应用程序通信。</span><span class="sxs-lookup"><span data-stu-id="611a3-103">The BizTalk Adapters for Windows Communication Foundation (WCF) allow  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to communicate with WCF-based applications.</span></span> <span data-ttu-id="611a3-104">BizTalk WCF 适配器包括表示的预定义的 WCF 绑定的五个物理适配器-**BasicHttpBinding**， **WsHttpBinding**， **NetTcpBinding**， **NetNamedPipeBinding**，和**NetMsmqBinding**。</span><span class="sxs-lookup"><span data-stu-id="611a3-104">The BizTalk WCF adapters include five physical adapters that represent the WCF predefined bindings—**BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="611a3-105">通过用于预定义绑定的 WCF 适配器，您可以轻松配置大多数应用程序要求的必需信息。</span><span class="sxs-lookup"><span data-stu-id="611a3-105">The WCF adapters for the predefined bindings are provided to enable you to easily configure necessary information for most application requirements.</span></span>  
  
 <span data-ttu-id="611a3-106">BizTalk WCF 适配器还包括用于随意配置接收位置和发送端口的 WCF 绑定和行为信息的两个适配器。</span><span class="sxs-lookup"><span data-stu-id="611a3-106">The BizTalk WCF adapters also include two adapters that enable you to freely configure WCF binding and behavior information for the receive location and send port.</span></span>  
  
 <span data-ttu-id="611a3-107">所有 WCF 适配器都为发送端口和接收位置提供相似的传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="611a3-107">All the WCF adapters provide similar transport properties dialog boxes for send ports and receive locations.</span></span> <span data-ttu-id="611a3-108">不过，配置 WCF 适配器的具体任务因物理适配器而异。</span><span class="sxs-lookup"><span data-stu-id="611a3-108">However, the detailed tasks to configure the WCF adapters vary depending on the physical adapter.</span></span> <span data-ttu-id="611a3-109">就不与适配器绑定直接相关的任务而言，比如安装证书，对于所有 WCF 适配器都是相同的。</span><span class="sxs-lookup"><span data-stu-id="611a3-109">Tasks not directly related to the adapter bindings, such as installing certificates, are the same for all the WCF adapters.</span></span> <span data-ttu-id="611a3-110">本部分讨论的是所有 WCF 适配器共有的任务。</span><span class="sxs-lookup"><span data-stu-id="611a3-110">This section discusses the tasks that are common to all the WCF adapters.</span></span> <span data-ttu-id="611a3-111">有关为每个适配器与不同的任务的信息，请参阅中的适配器的相应主题[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="611a3-111">For information about tasks that differ for each adapter, see the appropriate topics for the adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="611a3-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="611a3-112">In This Section</span></span>  
  
-   [<span data-ttu-id="611a3-113">WCF 适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="611a3-113">WCF Adapters Property Schema and Properties</span></span>](../core/wcf-adapters-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="611a3-114">WCF 适配器安全建议</span><span class="sxs-lookup"><span data-stu-id="611a3-114">WCF Adapters Security Recommendations</span></span>](../core/wcf-adapters-security-recommendations.md)  
  
-   [<span data-ttu-id="611a3-115">将证书安装适用于这些 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="611a3-115">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="611a3-116">为 WCF 适配器指定消息正文</span><span class="sxs-lookup"><span data-stu-id="611a3-116">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="611a3-117">如何启用与 WCF 适配器 WCF 扩展点</span><span class="sxs-lookup"><span data-stu-id="611a3-117">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="611a3-118">WCF 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="611a3-118">WCF Adapters Performance Counters</span></span>](../core/wcf-adapters-performance-counters.md)  
  
-   [<span data-ttu-id="611a3-119">WCF 适配器的的单一登录支持</span><span class="sxs-lookup"><span data-stu-id="611a3-119">Single Sign-On Support for the WCF Adapters</span></span>](../core/single-sign-on-support-for-the-wcf-adapters.md)  
  
## <a name="see-also"></a><span data-ttu-id="611a3-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="611a3-120">See Also</span></span>  
 [<span data-ttu-id="611a3-121">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="611a3-121">WCF Adapters</span></span>](../core/wcf-adapters.md)