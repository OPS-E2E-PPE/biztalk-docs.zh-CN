---
title: 配置 WCF 适配器 |Microsoft Docs
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
ms.openlocfilehash: d3dbe2541a85879f21d6d2393280933d8335dac0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355132"
---
# <a name="configuring-the-wcf-adapters"></a><span data-ttu-id="29895-102">配置 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="29895-102">Configuring the WCF Adapters</span></span>
<span data-ttu-id="29895-103">BizTalk 适配器的 Windows Communication Foundation (WCF) 允许[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与基于 WCF 的应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="29895-103">The BizTalk Adapters for Windows Communication Foundation (WCF) allow  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to communicate with WCF-based applications.</span></span> <span data-ttu-id="29895-104">BizTalk WCF 适配器包括五个物理适配器，分别表示 WCF 预定义绑定 —**BasicHttpBinding**， **WsHttpBinding**， **NetTcpBinding**， **NetNamedPipeBinding**，并**NetMsmqBinding**。</span><span class="sxs-lookup"><span data-stu-id="29895-104">The BizTalk WCF adapters include five physical adapters that represent the WCF predefined bindings—**BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="29895-105">预定义绑定的 WCF 适配器提供以便您可以轻松配置大多数应用程序要求所需的信息。</span><span class="sxs-lookup"><span data-stu-id="29895-105">The WCF adapters for the predefined bindings are provided to enable you to easily configure necessary information for most application requirements.</span></span>  
  
 <span data-ttu-id="29895-106">BizTalk WCF 适配器还包括两个适配器，您可以自由地配置 WCF 绑定和行为信息的接收位置和发送端口。</span><span class="sxs-lookup"><span data-stu-id="29895-106">The BizTalk WCF adapters also include two adapters that enable you to freely configure WCF binding and behavior information for the receive location and send port.</span></span>  
  
 <span data-ttu-id="29895-107">所有 WCF 适配器提供相似的传输属性对话框，发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="29895-107">All the WCF adapters provide similar transport properties dialog boxes for send ports and receive locations.</span></span> <span data-ttu-id="29895-108">但是，配置 WCF 适配器的具体的任务因物理适配器。</span><span class="sxs-lookup"><span data-stu-id="29895-108">However, the detailed tasks to configure the WCF adapters vary depending on the physical adapter.</span></span> <span data-ttu-id="29895-109">与适配器绑定，比如安装证书，不能直接相关的任务是相同的所有 WCF 适配器。</span><span class="sxs-lookup"><span data-stu-id="29895-109">Tasks not directly related to the adapter bindings, such as installing certificates, are the same for all the WCF adapters.</span></span> <span data-ttu-id="29895-110">本部分讨论所有 WCF 适配器都共有的任务。</span><span class="sxs-lookup"><span data-stu-id="29895-110">This section discusses the tasks that are common to all the WCF adapters.</span></span> <span data-ttu-id="29895-111">有关每个适配器不同的任务的信息，请参阅中的适配器的相应主题[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="29895-111">For information about tasks that differ for each adapter, see the appropriate topics for the adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="29895-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="29895-112">In This Section</span></span>  
  
-   [<span data-ttu-id="29895-113">WCF 适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="29895-113">WCF Adapters Property Schema and Properties</span></span>](../core/wcf-adapters-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="29895-114">WCF 适配器的安全建议</span><span class="sxs-lookup"><span data-stu-id="29895-114">WCF Adapters Security Recommendations</span></span>](../core/wcf-adapters-security-recommendations.md)  
  
-   [<span data-ttu-id="29895-115">安装用于 WCF 适配器的证书</span><span class="sxs-lookup"><span data-stu-id="29895-115">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="29895-116">指定 WCF 适配器的消息正文</span><span class="sxs-lookup"><span data-stu-id="29895-116">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="29895-117">如何启用 WCF 适配器的 WCF 扩展点</span><span class="sxs-lookup"><span data-stu-id="29895-117">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="29895-118">WCF 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="29895-118">WCF Adapters Performance Counters</span></span>](../core/wcf-adapters-performance-counters.md)  
  
-   [<span data-ttu-id="29895-119">WCF 适配器的单一登录支持</span><span class="sxs-lookup"><span data-stu-id="29895-119">Single Sign-On Support for the WCF Adapters</span></span>](../core/single-sign-on-support-for-the-wcf-adapters.md)  
  
## <a name="see-also"></a><span data-ttu-id="29895-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="29895-120">See Also</span></span>  
 [<span data-ttu-id="29895-121">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="29895-121">WCF Adapters</span></span>](../core/wcf-adapters.md)