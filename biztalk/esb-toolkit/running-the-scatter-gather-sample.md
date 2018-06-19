---
title: 运行散播-聚集示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53676974-ea1f-4c95-9dbb-98fff92286fa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dcafa519aac074ccb339373a591b590846c9341
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294653"
---
# <a name="running-the-scatter-gather-sample"></a><span data-ttu-id="f4188-102">运行散播-聚集示例</span><span class="sxs-lookup"><span data-stu-id="f4188-102">Running the Scatter-Gather Sample</span></span>
<span data-ttu-id="f4188-103">散播-聚集示例使用 Windows 窗体测试客户端应用程序的路线入口示例来演示此模式将路线服务的功能的应用。</span><span class="sxs-lookup"><span data-stu-id="f4188-103">The Scatter-Gather sample uses a the Windows Forms test client application provided with the Itinerary On-Ramp sample to demonstrate how this pattern applies the features of the Itinerary service.</span></span>  
  
 <span data-ttu-id="f4188-104">**若要运行散播-聚集示例**</span><span class="sxs-lookup"><span data-stu-id="f4188-104">**To run the Scatter-Gather sample**</span></span>  
  
1.  <span data-ttu-id="f4188-105">如果 GlobalBank.ESB 应用程序尚未运行，使用 Microsoft BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="f4188-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="f4188-106">在 Windows 资源管理器，打开文件夹 \Source\Samples\Itinerary\Source\ESB。你的安装位置的 Itinerary.Test[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后启动指定 Esb.Itinerary.Test.exe 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f4188-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3.  <span data-ttu-id="f4188-107">单击**LoadItinerary**按钮，，然后选择名为 ScatterGatherItinerary.xml \Source\Samples\ScatterGather\Itineraries 文件夹中的示例路线。</span><span class="sxs-lookup"><span data-stu-id="f4188-107">Click the **LoadItinerary** button, and then select the sample itinerary named ScatterGatherItinerary.xml from the \Source\Samples\ScatterGather\Itineraries folder.</span></span>  
  
4.  <span data-ttu-id="f4188-108">清除**是请求响应**复选框，这样应用程序将执行单向路线服务操作。</span><span class="sxs-lookup"><span data-stu-id="f4188-108">Clear the **Is Request Response** check box so the application will perform a one-way itinerary services operation.</span></span>  
  
5.  <span data-ttu-id="f4188-109">（可选）设置**使用 WCF 服务**复选框，如果你想要使用 OnRamp.Itinerary.Response.WCF 的应用程序接收位置而非默认 OnRamp.Itinerary.Response.SOAP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="f4188-109">(Optional) Set the **Use WCF Service** check box if you want the application to use the OnRamp.Itinerary.Response.WCF receive location instead of the default OnRamp.Itinerary.Response.SOAP receive location.</span></span>  
  
6.  <span data-ttu-id="f4188-110">单击**LoadMessage**按钮，然后从 \Source\Samples\Itinerary\Test\Data 文件夹然后选择 NAOrderDoc.xml 示例消息。</span><span class="sxs-lookup"><span data-stu-id="f4188-110">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7.  <span data-ttu-id="f4188-111">单击**SubmitRequest**按钮以将请求发送到路线提升服务。</span><span class="sxs-lookup"><span data-stu-id="f4188-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="f4188-112">打开文件夹 \Source\Samples\DynamicResolution\Test\FileDrop\Out 若要查看响应消息。</span><span class="sxs-lookup"><span data-stu-id="f4188-112">Open the folder \Source\Samples\DynamicResolution\Test\FileDrop\Out to see the response message.</span></span>  
  
 <span data-ttu-id="f4188-113">有关如何散点图收集示例使用 ESB 路线服务的信息，请参阅[散播-聚集示例的工作原理](../esb-toolkit/how-the-scatter-gather-sample-works.md)。</span><span class="sxs-lookup"><span data-stu-id="f4188-113">For information about how the Scatter Gather sample uses the ESB Itinerary service, see [How the Scatter-Gather Sample Works](../esb-toolkit/how-the-scatter-gather-sample-works.md).</span></span>