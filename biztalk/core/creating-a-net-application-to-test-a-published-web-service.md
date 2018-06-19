---
title: 创建.NET 应用程序的已发布的 Web 服务测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, Web services
- Web services, testing
ms.assetid: 94b2223b-45d7-4b86-b4ec-87cc027d7e2a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d13c69a471d546fe8d2b70363dad5cced8bbe62f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237949"
---
# <a name="creating-a-net-application-to-test-a-published-web-service"></a><span data-ttu-id="d3a9d-102">创建.NET 应用程序的已发布的 Web 服务测试</span><span class="sxs-lookup"><span data-stu-id="d3a9d-102">Creating a .NET Application to Test a Published Web Service</span></span>
<span data-ttu-id="d3a9d-103">若要测试已发布 Web Services，请创建一个使用已发布 Web Services 的 ASP.NET Web 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3a9d-103">To test your published Web service, you can create an ASP.NET Web client application that consumes your published Web service.</span></span> <span data-ttu-id="d3a9d-104">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 帮助集合包含创建 ASP.NET Web 客户端应用程序的重要演练。</span><span class="sxs-lookup"><span data-stu-id="d3a9d-104">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection contains a valuable walkthrough for creating an ASP.NET Web client application.</span></span> <span data-ttu-id="d3a9d-105">您可以使用此演练测试已发布 Web Services。</span><span class="sxs-lookup"><span data-stu-id="d3a9d-105">You can use the walkthrough to test your published Web service.</span></span>  
  
 <span data-ttu-id="d3a9d-106">本演练创建 ASP.NET Web 客户端应用程序、添加 Web 引用，并提供了显示如何访问已发布 Web Services 的示例代码。</span><span class="sxs-lookup"><span data-stu-id="d3a9d-106">The walkthrough creates an ASP.NET Web client application, adds a Web reference, and provides sample code to show you how to access your published Web service.</span></span> <span data-ttu-id="d3a9d-107">本演练将指导您在调试模式下运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3a9d-107">The walkthrough takes you through running the application in debug mode.</span></span>  
  
 <span data-ttu-id="d3a9d-108">有关信息和有关创建 XML Web 服务客户端项目中的过程，请参阅"演练:: 访问 XML Web 服务使用 Visual Basic 或 Visual C#"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]在帮助集合[http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263)。</span><span class="sxs-lookup"><span data-stu-id="d3a9d-108">For information and procedures about creating an XML Web service client project, see "Walkthrough: Accessing an XML Web Service Using Visual Basic or Visual C#" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263).</span></span> <span data-ttu-id="d3a9d-109">您可以使用已发布 BizTalk Web Services 替换本示例中使用的 Web Services，即 TempConvert1。</span><span class="sxs-lookup"><span data-stu-id="d3a9d-109">You can replace the Web service used in this example, TempConvert1, with a BizTalk published Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3a9d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3a9d-110">See Also</span></span>  
 [<span data-ttu-id="d3a9d-111">测试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="d3a9d-111">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)