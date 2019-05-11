---
title: 发布 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- BizTalk Server Web Services Publishing Wizard
ms.assetid: eed0717c-b390-492a-a3b9-ae31024805a2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76c699ff7fec169064b446e0e83b9eaae1160bfd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398354"
---
# <a name="publishing-web-services"></a><span data-ttu-id="7f011-102">发布 Web Services</span><span class="sxs-lookup"><span data-stu-id="7f011-102">Publishing Web Services</span></span>
<span data-ttu-id="7f011-103">发布 Web 服务，可创建一个 Web 服务，可将消息提交到 Microsoft BizTalk Server 用于业务流程和其他发送适配器。</span><span class="sxs-lookup"><span data-stu-id="7f011-103">Publishing Web services enables you to create a Web service that can submit messages to Microsoft BizTalk Server for use by orchestrations and other send adapters.</span></span> <span data-ttu-id="7f011-104">创建使用 BizTalk Web Services 发布向导发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="7f011-104">You create published Web services using the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="7f011-105">有关配置 SOAP 发送处理程序的信息，请参阅[如何配置 SOAP 发送处理程序](../core/how-to-configure-a-soap-send-handler.md)。</span><span class="sxs-lookup"><span data-stu-id="7f011-105">For information about configuring a SOAP send handler, see [How to Configure a SOAP Send Handler](../core/how-to-configure-a-soap-send-handler.md).</span></span> <span data-ttu-id="7f011-106">有关配置 SOAP 发送端口的信息，请参阅[如何配置 SOAP 发送端口](../core/how-to-configure-a-soap-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="7f011-106">For information about configuring a SOAP send port, see [How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md).</span></span>  
  
 <span data-ttu-id="7f011-107">BizTalk Web Services 发布向导提供了两个方法，用于发布 Web services： 业务流程发布为 Web 服务和将架构发布为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="7f011-107">The BizTalk Web Services Publishing Wizard provides you with two methods to publish Web services: publishing an orchestration as a Web service and publishing schemas as a Web service.</span></span>  
  
 <span data-ttu-id="7f011-108">必须安装并启用 Microsoft Internet 信息服务 (IIS) 和 ASP.NET，然后才能发布 Microsoft BizTalk Server 业务流程和架构作为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="7f011-108">You must install and enable Microsoft Internet Information Services (IIS) and ASP.NET before you can publish Microsoft BizTalk Server orchestrations and schemas as Web services.</span></span> <span data-ttu-id="7f011-109">有关安装 IIS 和 ASP.NET 的信息，请参阅安装 Internet 信息服务 (IIS) 中位于 BizTalk Server 安装指南[超链接"http://go.microsoft.com/fwlink/?LinkID=191321" http://go.microsoft.com/fwlink/?LinkID=191321 ](http://go.microsoft.com/fwlink/?LinkID=191321)。</span><span class="sxs-lookup"><span data-stu-id="7f011-109">For information about installing IIS and ASP.NET, see Installing Internet Information Services (IIS) in the BizTalk Server Installation Guide located at [HYPERLINK "http://go.microsoft.com/fwlink/?LinkID=191321" http://go.microsoft.com/fwlink/?LinkID=191321](http://go.microsoft.com/fwlink/?LinkID=191321).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7f011-110">运行 BizTalk Web 服务发布向导之前，必须启用 Web services。</span><span class="sxs-lookup"><span data-stu-id="7f011-110">Before running the BizTalk Web Services Publishing Wizard, you must enable Web services.</span></span> <span data-ttu-id="7f011-111">有关启用 Web services 为您的系统的详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="7f011-111">For more information about enabling Web services for your system, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f011-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="7f011-112">In This Section</span></span>  
  
-   [<span data-ttu-id="7f011-113">规划发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="7f011-113">Planning for Publishing Web Services</span></span>](../core/planning-for-publishing-web-services2.md)  
  
-   [<span data-ttu-id="7f011-114">启用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="7f011-114">Enabling Web Services</span></span>](../core/enabling-web-services.md)  
  
-   [<span data-ttu-id="7f011-115">将业务流程发布为 Web 服务</span><span class="sxs-lookup"><span data-stu-id="7f011-115">Publishing an Orchestration as a Web Service</span></span>](../core/publishing-an-orchestration-as-a-web-service.md)  
  
-   [<span data-ttu-id="7f011-116">将架构发布为 Web 服务</span><span class="sxs-lookup"><span data-stu-id="7f011-116">Publishing Schemas as a Web Service</span></span>](../core/publishing-schemas-as-a-web-service.md)  
  
-   [<span data-ttu-id="7f011-117">发布 Web 服务时的注意事项</span><span class="sxs-lookup"><span data-stu-id="7f011-117">Considerations When Publishing Web Services</span></span>](../core/considerations-when-publishing-web-services.md)  
  
-   [<span data-ttu-id="7f011-118">调试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="7f011-118">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)  
  
-   [<span data-ttu-id="7f011-119">测试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="7f011-119">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)  
  
-   [<span data-ttu-id="7f011-120">在无 Visual Studio 的计算机上部署已发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="7f011-120">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)