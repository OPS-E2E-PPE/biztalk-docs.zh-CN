---
title: 点到点解析终结点以及转换要求 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4c570bf-8274-4779-ae83-2aef2bf57ded
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8899c5f713f1c9ebfe299d3e431754dd8b9794d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294461"
---
# <a name="point-to-point-resolution-of-endpoints-and-transformation-requirements"></a><span data-ttu-id="f01fd-102">点到点解析终结点以及转换要求</span><span class="sxs-lookup"><span data-stu-id="f01fd-102">Point-to-Point Resolution of Endpoints and Transformation Requirements</span></span>
<span data-ttu-id="f01fd-103">在使用这种情况下，Web 服务客户端调用 Web 服务，而无需通过 ESB。</span><span class="sxs-lookup"><span data-stu-id="f01fd-103">In this use case, a Web service client calls a Web service without going through the ESB.</span></span> <span data-ttu-id="f01fd-104">两个点进行直接通信，但客户端进行的调用之前，它必须解析 Web 服务的终结点。</span><span class="sxs-lookup"><span data-stu-id="f01fd-104">The two points communicate directly, but before the client makes the call, it must resolve the endpoint of the Web service.</span></span> <span data-ttu-id="f01fd-105">对 Web 服务的调用可以是单向或请求-响应。</span><span class="sxs-lookup"><span data-stu-id="f01fd-105">The call to the Web service can be either a one-way or a request-response.</span></span> <span data-ttu-id="f01fd-106">实现此目的的一种方法是使用 ESB，动态解析功能，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="f01fd-106">One way of achieving this is to use the dynamic resolution features of the ESB, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="f01fd-107">![点 &#45; 到 &#45;终结点解析点](../esb-toolkit/media/ch3-pointtopoint.gif "Ch3 PointToPoint")</span><span class="sxs-lookup"><span data-stu-id="f01fd-107">![Point&#45;to&#45;Point Resolution of Endpoints](../esb-toolkit/media/ch3-pointtopoint.gif "Ch3-PointToPoint")</span></span>  
  
 <span data-ttu-id="f01fd-108">**图 1**</span><span class="sxs-lookup"><span data-stu-id="f01fd-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="f01fd-109">**解决使用 UDDI 终结点**</span><span class="sxs-lookup"><span data-stu-id="f01fd-109">**Resolving endpoints using UDDI**</span></span>  
  
 <span data-ttu-id="f01fd-110">附带的解析程序服务示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="f01fd-110">The Resolver Service sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="f01fd-111">此示例演示如何调用 ESB 解析程序服务，以执行解析，使你可以测试解决方法，如你正在开发的后端存储，例如通用、 描述、 发现和集成 (UDDI)，XML 路径语言 (XPath) 的内容静态的或 BizTalk Server 业务规则引擎中的策略。</span><span class="sxs-lookup"><span data-stu-id="f01fd-111">The sample shows how to call the ESB Resolver Service to perform resolution, which enables you to test resolution as you are developing the contents of the back-end stores, such as Universal Description, Discovery, and Integration (UDDI), XML Path Language (XPath), Static, or policies in the BizTalk Server Business Rules Engine.</span></span>  
  
 <span data-ttu-id="f01fd-112">有关详细信息，请参阅[安装和运行解析程序服务示例](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="f01fd-112">For more information, see [Installing and Running the Resolver Service Sample](../esb-toolkit/installing-and-running-the-resolver-service-sample.md).</span></span>