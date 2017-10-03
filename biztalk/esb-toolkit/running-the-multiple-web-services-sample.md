---
title: "运行多个 Web 服务示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b201c7c3-213a-4009-8872-5a4c1cbb8195
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ec54fabb7ed140fd88b5a2d5a07d788805c741e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-multiple-web-services-sample"></a><span data-ttu-id="d286c-102">运行多个 Web 服务示例</span><span class="sxs-lookup"><span data-stu-id="d286c-102">Running the Multiple Web Services Sample</span></span>
<span data-ttu-id="d286c-103">多个 Web 服务示例使用 Windows 窗体测试客户端应用程序的入口路线示例。</span><span class="sxs-lookup"><span data-stu-id="d286c-103">The Multiple Web Services sample uses the Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="d286c-104">**若要运行多个 Web 服务示例**</span><span class="sxs-lookup"><span data-stu-id="d286c-104">**To run the Multiple Web Services sample**</span></span>  
  
1.  <span data-ttu-id="d286c-105">如果 GlobalBank.ESB 应用程序尚未运行，使用 Microsoft BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="d286c-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="d286c-106">在 Windows 资源管理器，打开文件夹 \Source\Samples\Itinerary\Source\ESB。你的安装位置的 Itinerary.Test[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后启动指定 Esb.Itinerary.Test.exe 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d286c-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3.  <span data-ttu-id="d286c-107">清除**使用 WCF 服务**复选框，以便可以利用客户端路线。</span><span class="sxs-lookup"><span data-stu-id="d286c-107">Clear the **Use WCF Service** check box, so that a client-side itinerary can be utilized.</span></span>  
  
4.  <span data-ttu-id="d286c-108">单击**负载路线**按钮，，然后选择一个位于 \Source\Samples\MultipleWebServices\Itineraries 文件夹示例路线。</span><span class="sxs-lookup"><span data-stu-id="d286c-108">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the \Source\Samples\MultipleWebServices\Itineraries folder.</span></span>  
  
5.  <span data-ttu-id="d286c-109">选择**两个方式服务**复选框，这样应用程序将执行双向路线服务操作。</span><span class="sxs-lookup"><span data-stu-id="d286c-109">Select the **Two Way Service** check box so the application will perform a two-way itinerary services operation.</span></span>  
  
6.  <span data-ttu-id="d286c-110">单击**LoadMessage**按钮，然后从 \Source\Samples\Itinerary\Test\Data 文件夹然后选择 NAOrderDoc.xml 示例消息。</span><span class="sxs-lookup"><span data-stu-id="d286c-110">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7.  <span data-ttu-id="d286c-111">单击**SubmitRequest**按钮以将请求发送到路线提升服务。</span><span class="sxs-lookup"><span data-stu-id="d286c-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="d286c-112">等待响应消息显示在**结果**框。</span><span class="sxs-lookup"><span data-stu-id="d286c-112">Wait for a response message to appear in the **Result** box.</span></span>  
  
 <span data-ttu-id="d286c-113">有关如何在多个 Web 服务示例使用 ESB 路线服务的信息，请参阅[多个 Web 服务示例的工作原理](../esb-toolkit/how-the-multiple-web-services-sample-works.md)。</span><span class="sxs-lookup"><span data-stu-id="d286c-113">For information about how the Multiple Web Services sample uses the ESB Itinerary service, see [How the Multiple Web Services Sample Works](../esb-toolkit/how-the-multiple-web-services-sample-works.md).</span></span>