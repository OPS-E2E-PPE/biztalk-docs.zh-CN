---
title: "发布 Web 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- BizTalk Server Web Services Publishing Wizard
ms.assetid: eed0717c-b390-492a-a3b9-ae31024805a2
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aca08c1e4fabd833bd6de924e04e6052cd99890b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-web-services"></a><span data-ttu-id="11934-102">发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="11934-102">Publishing Web Services</span></span>
<span data-ttu-id="11934-103">通过发布 Web Services，您可以创建一个可将消息提交给 Microsoft BizTalk Server 以供业务流程和其他发送适配器使用的 Web Services。</span><span class="sxs-lookup"><span data-stu-id="11934-103">Publishing Web services enables you to create a Web service that can submit messages to Microsoft BizTalk Server for use by orchestrations and other send adapters.</span></span> <span data-ttu-id="11934-104">创建使用 BizTalk Web 服务发布向导的已发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="11934-104">You create published Web services using the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="11934-105">有关配置 SOAP 发送处理程序的信息，请参阅[如何配置 SOAP 发送处理程序](../core/how-to-configure-a-soap-send-handler.md)。</span><span class="sxs-lookup"><span data-stu-id="11934-105">For information about configuring a SOAP send handler, see [How to Configure a SOAP Send Handler](../core/how-to-configure-a-soap-send-handler.md).</span></span> <span data-ttu-id="11934-106">有关配置 SOAP 发送端口的信息，请参阅[如何配置 SOAP 发送端口](../core/how-to-configure-a-soap-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="11934-106">For information about configuring a SOAP send port, see [How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md).</span></span>  
  
 <span data-ttu-id="11934-107">BizTalk Web 服务发布向导为你提供两种方法来发布 Web 服务： 发布作为 Web 服务业务流程和作为 Web 服务中发布的架构。</span><span class="sxs-lookup"><span data-stu-id="11934-107">The BizTalk Web Services Publishing Wizard provides you with two methods to publish Web services: publishing an orchestration as a Web service and publishing schemas as a Web service.</span></span>  
  
 <span data-ttu-id="11934-108">必须先安装和启用 Microsoft Internet 信息服务 (IIS) 和 ASP.NET，然后才能将 Microsoft BizTalk Server 业务流程和架构发布为 Web Services。</span><span class="sxs-lookup"><span data-stu-id="11934-108">You must install and enable Microsoft Internet Information Services (IIS) and ASP.NET before you can publish Microsoft BizTalk Server orchestrations and schemas as Web services.</span></span> <span data-ttu-id="11934-109">有关安装 IIS 和 ASP.NET 的信息，请参阅安装 Internet 信息服务 (IIS) 位于 BizTalk Server 安装指南中[超链接"http://go.microsoft.com/fwlink/?LinkID = 191321"http://go.microsoft.com/fwlink/?LinkID = 191321](http://go.microsoft.com/fwlink/?LinkID=191321)。</span><span class="sxs-lookup"><span data-stu-id="11934-109">For information about installing IIS and ASP.NET, see Installing Internet Information Services (IIS) in the BizTalk Server Installation Guide located at [HYPERLINK "http://go.microsoft.com/fwlink/?LinkID=191321" http://go.microsoft.com/fwlink/?LinkID=191321](http://go.microsoft.com/fwlink/?LinkID=191321).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="11934-110">在运行 BizTalk Web Services 发布向导之前，必须启用 Web Services。</span><span class="sxs-lookup"><span data-stu-id="11934-110">Before running the BizTalk Web Services Publishing Wizard, you must enable Web services.</span></span> <span data-ttu-id="11934-111">有关启用你的系统的 Web 服务的详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="11934-111">For more information about enabling Web services for your system, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11934-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="11934-112">In This Section</span></span>  
  
-   [<span data-ttu-id="11934-113">规划发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="11934-113">Planning for Publishing Web Services</span></span>](../core/planning-for-publishing-web-services2.md)  
  
-   [<span data-ttu-id="11934-114">启用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="11934-114">Enabling Web Services</span></span>](../core/enabling-web-services.md)  
  
-   [<span data-ttu-id="11934-115">发布作为 Web 服务业务流程</span><span class="sxs-lookup"><span data-stu-id="11934-115">Publishing an Orchestration as a Web Service</span></span>](../core/publishing-an-orchestration-as-a-web-service.md)  
  
-   [<span data-ttu-id="11934-116">发布架构作为 Web 服务</span><span class="sxs-lookup"><span data-stu-id="11934-116">Publishing Schemas as a Web Service</span></span>](../core/publishing-schemas-as-a-web-service.md)  
  
-   [<span data-ttu-id="11934-117">发布 Web 服务时的注意事项</span><span class="sxs-lookup"><span data-stu-id="11934-117">Considerations When Publishing Web Services</span></span>](../core/considerations-when-publishing-web-services.md)  
  
-   [<span data-ttu-id="11934-118">调试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="11934-118">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)  
  
-   [<span data-ttu-id="11934-119">测试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="11934-119">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)  
  
-   [<span data-ttu-id="11934-120">部署非 Visual Studio 计算机上的发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="11934-120">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)