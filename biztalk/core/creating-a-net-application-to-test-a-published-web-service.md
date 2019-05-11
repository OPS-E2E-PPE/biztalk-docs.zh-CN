---
title: 创建.NET 应用程序以测试已发布的 Web 服务 |Microsoft Docs
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
ms.openlocfilehash: 323ba7b5cce1d7cd83c9031f51ca7944ae5f5bb1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390130"
---
# <a name="creating-a-net-application-to-test-a-published-web-service"></a><span data-ttu-id="b42d3-102">创建.NET 应用程序以测试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="b42d3-102">Creating a .NET Application to Test a Published Web Service</span></span>
<span data-ttu-id="b42d3-103">若要测试已发布的 Web 服务，可以创建使用已发布的 Web 服务的 ASP.NET Web 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="b42d3-103">To test your published Web service, you can create an ASP.NET Web client application that consumes your published Web service.</span></span> <span data-ttu-id="b42d3-104">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]帮助集合包含创建 ASP.NET Web 客户端应用程序的重要演练。</span><span class="sxs-lookup"><span data-stu-id="b42d3-104">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection contains a valuable walkthrough for creating an ASP.NET Web client application.</span></span> <span data-ttu-id="b42d3-105">可以使用本演练测试已发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="b42d3-105">You can use the walkthrough to test your published Web service.</span></span>  
  
 <span data-ttu-id="b42d3-106">本演练创建 ASP.NET Web 客户端应用程序、 添加 Web 引用，并且提供了示例代码演示如何访问已发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="b42d3-106">The walkthrough creates an ASP.NET Web client application, adds a Web reference, and provides sample code to show you how to access your published Web service.</span></span> <span data-ttu-id="b42d3-107">本演练将通过在调试模式下运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="b42d3-107">The walkthrough takes you through running the application in debug mode.</span></span>  
  
 <span data-ttu-id="b42d3-108">有关信息和有关创建 XML Web 服务客户端项目的过程，请参阅"演练：访问 XML Web 服务使用 Visual Basic 或 Visual C#"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]帮助集合中处[ http://go.microsoft.com/fwlink/?LinkId=62263 ](http://go.microsoft.com/fwlink/?LinkId=62263)。</span><span class="sxs-lookup"><span data-stu-id="b42d3-108">For information and procedures about creating an XML Web service client project, see "Walkthrough: Accessing an XML Web Service Using Visual Basic or Visual C#" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263).</span></span> <span data-ttu-id="b42d3-109">您可以替换在此示例中，即 TempConvert1 所使用的 Web 服务已发布 BizTalk Web 服务。</span><span class="sxs-lookup"><span data-stu-id="b42d3-109">You can replace the Web service used in this example, TempConvert1, with a BizTalk published Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b42d3-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="b42d3-110">See Also</span></span>  
 [<span data-ttu-id="b42d3-111">测试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="b42d3-111">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)