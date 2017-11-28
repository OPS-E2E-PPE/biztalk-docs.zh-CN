---
title: "保持到 BizTalk 消息框中数据库的情况下转换 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f5b4caf-88e9-41dd-a644-e229e411a4a7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 407725509121948619e4eb05b583f6c8c1362f9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transformation-without-persisting-to-the-biztalk-message-box-database"></a><span data-ttu-id="6acd8-102">保持到 BizTalk 消息框中数据库的情况下转换</span><span class="sxs-lookup"><span data-stu-id="6acd8-102">Transformation Without Persisting to the BizTalk Message Box Database</span></span>
<span data-ttu-id="6acd8-103">在使用这种情况下，对 Web 服务的调用执行实时转换的一条消息，根据运行时的适当的映射的分辨率若要应用，并返回转换后的结果。</span><span class="sxs-lookup"><span data-stu-id="6acd8-103">In this use case, a call to a Web service performs real-time transformation of a message, based on run-time resolution of the appropriate map to apply, and returns the transformed result.</span></span> <span data-ttu-id="6acd8-104">图 1 说明的过程的示意图。</span><span class="sxs-lookup"><span data-stu-id="6acd8-104">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="6acd8-105">![保持的情况下转换](../esb-toolkit/media/ch3-transformationwithout.gif "Ch3 TransformationWithout")</span><span class="sxs-lookup"><span data-stu-id="6acd8-105">![Transformation Without Persisting](../esb-toolkit/media/ch3-transformationwithout.gif "Ch3-TransformationWithout")</span></span>  
  
 <span data-ttu-id="6acd8-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="6acd8-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="6acd8-107">**保持到 Microsoft BizTalk Server 消息框数据库的情况下转换消息**</span><span class="sxs-lookup"><span data-stu-id="6acd8-107">**Transforming a message without persisting to the Microsoft BizTalk Server Message Box database**</span></span>  
  
 <span data-ttu-id="6acd8-108">包含转换服务示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="6acd8-108">The Transformation Service sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="6acd8-109">通过使用它，您可以调用 ESB 转换服务;这使你可以在开发组件和 BizTalk Server 业务规则引擎中的策略时，测试转换和映射。</span><span class="sxs-lookup"><span data-stu-id="6acd8-109">By using it, you can call the ESB Transformation Service; this enables you to test transformations and mappings as you are developing components and policies in the BizTalk Server Business Rules Engine.</span></span>  
  
 <span data-ttu-id="6acd8-110">有关详细信息，请参阅[安装和运行转换服务示例](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="6acd8-110">For more information, see [Installing and Running the Transformation Service Sample](../esb-toolkit/installing-and-running-the-transformation-service-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6acd8-111">不要混淆通过 BizTalk Server 转换代理执行的动态转换操作此处所称为转换服务。</span><span class="sxs-lookup"><span data-stu-id="6acd8-111">Do not confuse the Transformation Service referred to here with the dynamic transformation operations performed by the BizTalk Server Transformation Agent.</span></span> <span data-ttu-id="6acd8-112">转换服务是高性能 Web 服务，可通过直接调入 BizTalk Server 大幅减少延迟，而无需通过消息框数据库。</span><span class="sxs-lookup"><span data-stu-id="6acd8-112">The Transformation Service is a high-performance Web service that significantly reduces latency by calling directly into BizTalk Server without going through the Message Box database.</span></span>