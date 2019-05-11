---
title: 使用 SOAP 标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers
- SOAP headers, about SOAP headers
- Web services, SOAP headers
ms.assetid: 816618ff-ecd8-4f12-b9a9-dbe4203411d8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfc28000b6a1028ad97403b9c8ae17e0a047dd98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321692"
---
# <a name="using-soap-headers"></a><span data-ttu-id="1b6d5-102">使用 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="1b6d5-102">Using SOAP Headers</span></span>
<span data-ttu-id="1b6d5-103">Microsoft BizTalk Server 定义的和未知的 SOAP 标头提供支持。</span><span class="sxs-lookup"><span data-stu-id="1b6d5-103">Microsoft BizTalk Server provides support for defined and unknown SOAP headers.</span></span> <span data-ttu-id="1b6d5-104">定义的 SOAP 标头是 Web 服务描述语言 (WSDL) 中显式声明 Web 服务中。</span><span class="sxs-lookup"><span data-stu-id="1b6d5-104">Defined SOAP headers are headers in the Web Service Description Language (WSDL) that are explicity stated in the Web service.</span></span> <span data-ttu-id="1b6d5-105">未知的 SOAP 标头是，在 WSDL 中的不是显式声明 Web 服务中的标头。</span><span class="sxs-lookup"><span data-stu-id="1b6d5-105">Unknown SOAP headers are headers that in the WSDL that are not explicity stated in the Web service.</span></span> <span data-ttu-id="1b6d5-106">有关使用 SOAP 标头的详细信息，请参阅"使用 SOAP 标头"Microsoft.NET Framework 文档中在[ http://go.microsoft.com/fwlink/?LinkId=25363 ](http://go.microsoft.com/fwlink/?LinkId=25363)。</span><span class="sxs-lookup"><span data-stu-id="1b6d5-106">For more information about using SOAP headers, see "Using SOAP Headers" in the Microsoft .NET Framework documentation at [http://go.microsoft.com/fwlink/?LinkId=25363](http://go.microsoft.com/fwlink/?LinkId=25363).</span></span>  
  
 <span data-ttu-id="1b6d5-107">BizTalk Server Web 服务中创建每个定义的 SOAP 标头上下文属性。</span><span class="sxs-lookup"><span data-stu-id="1b6d5-107">BizTalk Server creates a context property for each defined SOAP header in the Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b6d5-108">仅已使用的 Web 服务支持已定义的 SOAP 标头。使用 Web services 时，不能设置未知标头。</span><span class="sxs-lookup"><span data-stu-id="1b6d5-108">Consumed Web services support only defined SOAP headers.You cannot set unknown headers when consuming Web services.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b6d5-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="1b6d5-109">In This Section</span></span>  
  
-   [<span data-ttu-id="1b6d5-110">与使用的 Web 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="1b6d5-110">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)  
  
-   [<span data-ttu-id="1b6d5-111">与发布的 Web 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="1b6d5-111">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)