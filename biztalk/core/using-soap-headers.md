---
title: "使用 SOAP 标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP headers
- SOAP headers, about SOAP headers
- Web services, SOAP headers
ms.assetid: 816618ff-ecd8-4f12-b9a9-dbe4203411d8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0671dabe7547d3f55b937a1de58241a35cb70b39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers"></a><span data-ttu-id="65bb6-102">使用 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="65bb6-102">Using SOAP Headers</span></span>
<span data-ttu-id="65bb6-103">Microsoft BizTalk Server 支持已定义的和未知的 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="65bb6-103">Microsoft BizTalk Server provides support for defined and unknown SOAP headers.</span></span> <span data-ttu-id="65bb6-104">已定义的 SOAP 标头是 Web Services 中以 Web 服务描述语言 (WSDL) 显式声明的标头。</span><span class="sxs-lookup"><span data-stu-id="65bb6-104">Defined SOAP headers are headers in the Web Service Description Language (WSDL) that are explicity stated in the Web service.</span></span> <span data-ttu-id="65bb6-105">未知的 SOAP 标头是 Web Services 中未以 WSDL 显式声明的标头。</span><span class="sxs-lookup"><span data-stu-id="65bb6-105">Unknown SOAP headers are headers that in the WSDL that are not explicity stated in the Web service.</span></span> <span data-ttu-id="65bb6-106">有关使用 SOAP 标头的详细信息，请参阅"使用 SOAP 标头"Microsoft.NET Framework 文档中在[http://go.microsoft.com/fwlink/?LinkId=25363](http://go.microsoft.com/fwlink/?LinkId=25363)。</span><span class="sxs-lookup"><span data-stu-id="65bb6-106">For more information about using SOAP headers, see "Using SOAP Headers" in the Microsoft .NET Framework documentation at [http://go.microsoft.com/fwlink/?LinkId=25363](http://go.microsoft.com/fwlink/?LinkId=25363).</span></span>  
  
 <span data-ttu-id="65bb6-107">BizTalk Server 为 Web Services 中的每个已定义的 SOAP 标头创建一个上下文属性。</span><span class="sxs-lookup"><span data-stu-id="65bb6-107">BizTalk Server creates a context property for each defined SOAP header in the Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65bb6-108">使用的 Web Services 仅支持已定义的 SOAP 标头。你不能在使用 Web Services 时设置未知标头。</span><span class="sxs-lookup"><span data-stu-id="65bb6-108">Consumed Web services support only defined SOAP headers.You cannot set unknown headers when consuming Web services.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65bb6-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="65bb6-109">In This Section</span></span>  
  
-   [<span data-ttu-id="65bb6-110">与使用的 Web 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="65bb6-110">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)  
  
-   [<span data-ttu-id="65bb6-111">与发布的 Web 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="65bb6-111">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)