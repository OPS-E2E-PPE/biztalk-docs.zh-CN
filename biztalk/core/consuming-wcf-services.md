---
title: "使用 WCF 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- WCF services, consuming
ms.assetid: ca6c0514-c1df-43ad-8f02-df117271b0b5
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3fc0764295cbbc793b07757691e1f0c730a4049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="consuming-wcf-services"></a><span data-ttu-id="82a5a-102">使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="82a5a-102">Consuming WCF Services</span></span>
<span data-ttu-id="82a5a-103">通过使用 WCF 服务，可以将现有的 WCF 服务添加到业务流程中。</span><span class="sxs-lookup"><span data-stu-id="82a5a-103">Consuming WCF services enables you to add existing WCF services to your business process.</span></span> <span data-ttu-id="82a5a-104">您可以将若干 WCF 服务聚合成单个业务流程。</span><span class="sxs-lookup"><span data-stu-id="82a5a-104">You can aggregate several WCF services into a single orchestration.</span></span>  
  
 <span data-ttu-id="82a5a-105">使用 BizTalk WCF 服务使用向导，您可以从业务流程使用（调用）WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="82a5a-105">You can consume (call) a WCF service from your orchestration by using the BizTalk WCF Service Consuming Wizard.</span></span> <span data-ttu-id="82a5a-106">BizTalk WCF 服务使用向导创建使用 WCF 服务所需的端口类型和消息类型。</span><span class="sxs-lookup"><span data-stu-id="82a5a-106">The BizTalk WCF Service Consuming Wizard creates port types and message types necessary for consuming WCF services.</span></span> <span data-ttu-id="82a5a-107">BizTalk WCF 服务使用向导还会创建两个绑定文件，可使用开发命令行工具或向导导入该文件，以便配置带有系统提供的绑定 WCF 适配器和 WCF-Custom 适配器的发送端口。</span><span class="sxs-lookup"><span data-stu-id="82a5a-107">The BizTalk WCF Service Consuming Wizard also creates two binding files that can be imported by the development command-line tool or wizard to configure the send ports with the system-provided binding WCF adapters and the WCF-Custom adapter.</span></span> <span data-ttu-id="82a5a-108">通过向导，您可以将 SOAP 标头与使用的 WCF 服务一起使用，更改使用的 WCF 服务的 URI，并动态设置使用的 Web Services 的 WCF。</span><span class="sxs-lookup"><span data-stu-id="82a5a-108">The wizard allows you to use SOAP headers with a consumed WCF service, change the URI of a consumed WCF service, and dynamically set the WCF for a consumed Web service.</span></span> <span data-ttu-id="82a5a-109">WCF 发送适配器使用 WCF 服务和 WCF 接收位置发布 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="82a5a-109">WCF send adapters consume WCF services and WCF receive locations publish WCF services.</span></span>  
  
 <span data-ttu-id="82a5a-110">BizTalk WCF 发送适配器包括表示的预定义的 WCF 绑定的五个物理发送适配器**BasicHttpBinding**， **WsHttpBinding**， **NetTcpBinding**，**NetNamedPipeBinding**，和**NetMsmqBinding**。</span><span class="sxs-lookup"><span data-stu-id="82a5a-110">The BizTalk WCF send adapters include five physical send adapters that represent the WCF predefined bindings **BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="82a5a-111">BizTalk WCF 适配器还包括一个自定义的适配器，您可以使用该适配器随意配置发送端口的 WCF 绑定和行为信息。</span><span class="sxs-lookup"><span data-stu-id="82a5a-111">The BizTalk WCF adapters also include the custom adapters that enable you to freely configure WCF binding and behavior information for a send port.</span></span> <span data-ttu-id="82a5a-112">有关如何配置 WCF 发送处理程序和发送端口的详细信息，请参阅操作指南主题中的每个 WCF 适配器[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="82a5a-112">For more information about how to configure a WCF send handler and send port, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82a5a-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="82a5a-113">In This Section</span></span>  
  
-   [<span data-ttu-id="82a5a-114">使用 WCF 服务和 WCF 时的注意事项发送适配器</span><span class="sxs-lookup"><span data-stu-id="82a5a-114">Considerations When Consuming WCF Services with the WCF Send Adapters</span></span>](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)  
  
-   [<span data-ttu-id="82a5a-115">与使用的 WCF 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="82a5a-115">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)  
  
-   [<span data-ttu-id="82a5a-116">配置动态发送端口使用 WCF 适配器上下文属性</span><span class="sxs-lookup"><span data-stu-id="82a5a-116">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [<span data-ttu-id="82a5a-117">如何通过 BizTalk WCF 服务使用向导来使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="82a5a-117">How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service</span></span>](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)  
  
-   [<span data-ttu-id="82a5a-118">如何处理在业务流程中的类型化的错误协定</span><span class="sxs-lookup"><span data-stu-id="82a5a-118">How to Handle Typed Fault Contracts in Orchestrations</span></span>](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)  
  
-   [<span data-ttu-id="82a5a-119">指定的 SOAP 操作，wcf 发送适配器</span><span class="sxs-lookup"><span data-stu-id="82a5a-119">Specifying SOAP Actions for WCF Send Adapters</span></span>](../core/specifying-soap-actions-for-wcf-send-adapters.md)