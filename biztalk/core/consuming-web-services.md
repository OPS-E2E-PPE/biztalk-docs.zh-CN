---
title: 使用 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, Web services
- orchestrations, Web services
- Web services, consuming
- Web services, orchestrations
ms.assetid: 803ba623-86e7-479a-a4b6-5b576fee8825
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1239f54d3bd0ce71db1c77875e5b1bc852ec8bc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354549"
---
# <a name="consuming-web-services"></a><span data-ttu-id="9913a-102">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="9913a-102">Consuming Web Services</span></span>
<span data-ttu-id="9913a-103">使用 Web 服务，可以将现有的 Web 服务添加到您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="9913a-103">Consuming Web services enables you to add existing Web services to your business process.</span></span> <span data-ttu-id="9913a-104">可以将若干 Web services 聚合成单个业务流程。</span><span class="sxs-lookup"><span data-stu-id="9913a-104">You can aggregate several Web services into a single orchestration.</span></span>  
  
 <span data-ttu-id="9913a-105">通过使用 Web 端口，可以从您的业务流程使用 （调用） Web 服务。</span><span class="sxs-lookup"><span data-stu-id="9913a-105">You can consume (call) a Web service from your orchestration by using Web ports.</span></span> <span data-ttu-id="9913a-106">若要使用业务流程中的 Web 服务，创建一个 Web 端口并构造 Web 消息。</span><span class="sxs-lookup"><span data-stu-id="9913a-106">To consume a Web service from an orchestration, you create a Web port and construct Web messages.</span></span>  
  
 <span data-ttu-id="9913a-107">可以使用 SOAP 标头与已使用的 Web 服务、 更改使用的 Web 服务的 URI 和动态设置已使用的 Web 服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="9913a-107">You can use SOAP headers with the consumed Web service, change the URI of a consumed Web service, and dynamically set the URI for a consumed Web service.</span></span>  
  
 <span data-ttu-id="9913a-108">了解如何配置 SOAP 接收处理程序，请参阅[如何配置 SOAP 接收处理程序](../core/how-to-configure-a-soap-receive-handler.md)。</span><span class="sxs-lookup"><span data-stu-id="9913a-108">For information about configuring a SOAP receive handler, see [How to Configure a SOAP Receive Handler](../core/how-to-configure-a-soap-receive-handler.md).</span></span> <span data-ttu-id="9913a-109">了解如何配置 SOAP 接收位置，请参阅[如何配置 SOAP 接收位置](../core/how-to-configure-a-soap-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="9913a-109">For information about configuring a SOAP receive location, see [How to Configure a SOAP Receive Location](../core/how-to-configure-a-soap-receive-location.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9913a-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="9913a-110">In This Section</span></span>  
  
-   [<span data-ttu-id="9913a-111">添加 Web 引用</span><span class="sxs-lookup"><span data-stu-id="9913a-111">Adding Web References</span></span>](../core/adding-web-references.md)  
  
-   [<span data-ttu-id="9913a-112">构造 Web 消息</span><span class="sxs-lookup"><span data-stu-id="9913a-112">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)  
  
-   [<span data-ttu-id="9913a-113">创建 Web 端口</span><span class="sxs-lookup"><span data-stu-id="9913a-113">Creating Web Ports</span></span>](../core/creating-web-ports.md)  
  
-   [<span data-ttu-id="9913a-114">使用 Web 服务时的注意事项</span><span class="sxs-lookup"><span data-stu-id="9913a-114">Considerations When Consuming Web Services</span></span>](../core/considerations-when-consuming-web-services.md)