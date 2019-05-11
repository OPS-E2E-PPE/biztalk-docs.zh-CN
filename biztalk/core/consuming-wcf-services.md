---
title: 使用 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- WCF services, consuming
ms.assetid: ca6c0514-c1df-43ad-8f02-df117271b0b5
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0969fb98cbf9ea79f4e32138d795b6b4de81f513
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354622"
---
# <a name="consuming-wcf-services"></a><span data-ttu-id="882c6-102">使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="882c6-102">Consuming WCF Services</span></span>
<span data-ttu-id="882c6-103">使用 WCF 服务，可将现有的 WCF 服务添加到您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="882c6-103">Consuming WCF services enables you to add existing WCF services to your business process.</span></span> <span data-ttu-id="882c6-104">可以将若干 WCF 服务聚合成单个业务流程。</span><span class="sxs-lookup"><span data-stu-id="882c6-104">You can aggregate several WCF services into a single orchestration.</span></span>  
  
 <span data-ttu-id="882c6-105">您可以通过使用 BizTalk WCF 服务使用向导从您的业务流程使用 （调用） WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="882c6-105">You can consume (call) a WCF service from your orchestration by using the BizTalk WCF Service Consuming Wizard.</span></span> <span data-ttu-id="882c6-106">BizTalk WCF 服务使用向导创建端口类型和消息类型所需使用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="882c6-106">The BizTalk WCF Service Consuming Wizard creates port types and message types necessary for consuming WCF services.</span></span> <span data-ttu-id="882c6-107">BizTalk WCF 服务使用向导还会创建两个可开发命令行工具或向导以使用系统提供的绑定 WCF 适配器和 Wcf-custom 适配器配置发送端口导入的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="882c6-107">The BizTalk WCF Service Consuming Wizard also creates two binding files that can be imported by the development command-line tool or wizard to configure the send ports with the system-provided binding WCF adapters and the WCF-Custom adapter.</span></span> <span data-ttu-id="882c6-108">该向导允许你结合使用的 WCF 服务使用 SOAP 标头、 更改使用的 WCF 服务的 URI 而动态设置使用的 Web 服务的 WCF。</span><span class="sxs-lookup"><span data-stu-id="882c6-108">The wizard allows you to use SOAP headers with a consumed WCF service, change the URI of a consumed WCF service, and dynamically set the WCF for a consumed Web service.</span></span> <span data-ttu-id="882c6-109">WCF 发送适配器使用 WCF 服务和 WCF 接收位置发布 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="882c6-109">WCF send adapters consume WCF services and WCF receive locations publish WCF services.</span></span>  
  
 <span data-ttu-id="882c6-110">BizTalk WCF 发送适配器包括五个物理发送适配器，分别表示 WCF 预定义绑定**BasicHttpBinding**， **WsHttpBinding**， **NetTcpBinding**，**NetNamedPipeBinding**，并**NetMsmqBinding**。</span><span class="sxs-lookup"><span data-stu-id="882c6-110">The BizTalk WCF send adapters include five physical send adapters that represent the WCF predefined bindings **BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="882c6-111">BizTalk WCF 适配器还包括使您能够随意配置 WCF 绑定和行为信息的发送端口的自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="882c6-111">The BizTalk WCF adapters also include the custom adapters that enable you to freely configure WCF binding and behavior information for a send port.</span></span> <span data-ttu-id="882c6-112">有关如何配置 WCF 发送处理程序和发送端口的详细信息，请参阅中每个 WCF 适配器的操作指南主题[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="882c6-112">For more information about how to configure a WCF send handler and send port, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="882c6-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="882c6-113">In This Section</span></span>  
  
-   [<span data-ttu-id="882c6-114">通过 WCF 发送适配器使用 WCF 服务时的注意事项</span><span class="sxs-lookup"><span data-stu-id="882c6-114">Considerations When Consuming WCF Services with the WCF Send Adapters</span></span>](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)  
  
-   [<span data-ttu-id="882c6-115">SOAP 标头与使用的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="882c6-115">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)  
  
-   [<span data-ttu-id="882c6-116">使用 WCF 适配器上下文属性配置动态发送端口</span><span class="sxs-lookup"><span data-stu-id="882c6-116">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [<span data-ttu-id="882c6-117">如何使用 BizTalk WCF 服务使用向导来使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="882c6-117">How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service</span></span>](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)  
  
-   [<span data-ttu-id="882c6-118">如何处理业务流程中的类型化的错误协定</span><span class="sxs-lookup"><span data-stu-id="882c6-118">How to Handle Typed Fault Contracts in Orchestrations</span></span>](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)  
  
-   [<span data-ttu-id="882c6-119">为 WCF 发送适配器指定 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="882c6-119">Specifying SOAP Actions for WCF Send Adapters</span></span>](../core/specifying-soap-actions-for-wcf-send-adapters.md)