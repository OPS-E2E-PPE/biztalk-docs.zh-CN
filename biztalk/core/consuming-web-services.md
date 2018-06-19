---
title: 使用 Web 服务 |Microsoft 文档
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
ms.openlocfilehash: 528f61910dfc5e2d24a40b0ed29a23fcf85a72bb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237821"
---
# <a name="consuming-web-services"></a><span data-ttu-id="0dd8d-102">使用 Web Services</span><span class="sxs-lookup"><span data-stu-id="0dd8d-102">Consuming Web Services</span></span>
<span data-ttu-id="0dd8d-103">通过使用 Web Services，可以将现有的 Web Services 添加到业务流程中。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-103">Consuming Web services enables you to add existing Web services to your business process.</span></span> <span data-ttu-id="0dd8d-104">可以将若干 Web Services 聚合成单个业务流程。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-104">You can aggregate several Web services into a single orchestration.</span></span>  
  
 <span data-ttu-id="0dd8d-105">可以借助 Web 端口来从业务流程中使用（调用）Web Services。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-105">You can consume (call) a Web service from your orchestration by using Web ports.</span></span> <span data-ttu-id="0dd8d-106">若要从业务流程中使用 Web Services，需创建一个 Web 端口并构造 Web 消息。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-106">To consume a Web service from an orchestration, you create a Web port and construct Web messages.</span></span>  
  
 <span data-ttu-id="0dd8d-107">可以将 SOAP 标头与所使用的 Web Services 一起使用，更改所使用的 Web Services 的 URI，并动态设置所使用的 Web Services 的 URI。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-107">You can use SOAP headers with the consumed Web service, change the URI of a consumed Web service, and dynamically set the URI for a consumed Web service.</span></span>  
  
 <span data-ttu-id="0dd8d-108">璝惠砞 SOAP 接收处理程序，请参阅[如何配置一个 SOAP 接收处理程序](../core/how-to-configure-a-soap-receive-handler.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-108">For information about configuring a SOAP receive handler, see [How to Configure a SOAP Receive Handler](../core/how-to-configure-a-soap-receive-handler.md).</span></span> <span data-ttu-id="0dd8d-109">璝惠砞 SOAP 接收位置，请参阅[如何配置 SOAP 接收位置](../core/how-to-configure-a-soap-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-109">For information about configuring a SOAP receive location, see [How to Configure a SOAP Receive Location](../core/how-to-configure-a-soap-receive-location.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0dd8d-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="0dd8d-110">In This Section</span></span>  
  
-   [<span data-ttu-id="0dd8d-111">添加 Web 引用</span><span class="sxs-lookup"><span data-stu-id="0dd8d-111">Adding Web References</span></span>](../core/adding-web-references.md)  
  
-   [<span data-ttu-id="0dd8d-112">构造 Web 消息</span><span class="sxs-lookup"><span data-stu-id="0dd8d-112">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)  
  
-   [<span data-ttu-id="0dd8d-113">创建 Web 端口</span><span class="sxs-lookup"><span data-stu-id="0dd8d-113">Creating Web Ports</span></span>](../core/creating-web-ports.md)  
  
-   [<span data-ttu-id="0dd8d-114">使用 Web 服务时的注意事项</span><span class="sxs-lookup"><span data-stu-id="0dd8d-114">Considerations When Consuming Web Services</span></span>](../core/considerations-when-consuming-web-services.md)