---
title: InterAct 适配器服务器应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c50b239-0480-449f-aa6d-50bbb892e8a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28af1e636d00b3a1d7b8cd9afead5dbc3285aabf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366636"
---
# <a name="interact-adapter-server-application"></a><span data-ttu-id="6afe6-102">InterAct 适配器服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="6afe6-102">InterAct Adapter Server Application</span></span>
<span data-ttu-id="6afe6-103">本部分介绍服务器应用程序请求消息的组合的一般说明。</span><span class="sxs-lookup"><span data-stu-id="6afe6-103">This section presents a general description of the composition of server application Request messages.</span></span> <span data-ttu-id="6afe6-104">这些是从服务器端 SNL 传递到服务器应用程序的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="6afe6-104">These are the XML documents passed from the server-side SNL to the server application.</span></span> <span data-ttu-id="6afe6-105">在这种情况下，这些消息是在服务器端执行的 SWIFTNet 基元的第一部分的特征。</span><span class="sxs-lookup"><span data-stu-id="6afe6-105">As such, these messages are characteristic of the first part of the SWIFTNet primitives exercised on the server side.</span></span>  
  
 <span data-ttu-id="6afe6-106">下图显示服务器请求消息。</span><span class="sxs-lookup"><span data-stu-id="6afe6-106">The following figure shows the server request message.</span></span>  
  
 <span data-ttu-id="6afe6-107">![服务器请求消息](../../adapters-and-accelerators/fileact-interact/media/05bf7d1b-199c-4806-be91-32ca013e9af8.gif "05bf7d1b-199c-4806-be91-32ca013e9af8")</span><span class="sxs-lookup"><span data-stu-id="6afe6-107">![Server request message](../../adapters-and-accelerators/fileact-interact/media/05bf7d1b-199c-4806-be91-32ca013e9af8.gif "05bf7d1b-199c-4806-be91-32ca013e9af8")</span></span>  
  
 <span data-ttu-id="6afe6-108">下图显示了 SNL 和 InterAct 服务器应用程序之间交换的消息的序列。</span><span class="sxs-lookup"><span data-stu-id="6afe6-108">The following figure shows the sequence of messages exchanged between SNL and the InterAct server application.</span></span>  
  
 <span data-ttu-id="6afe6-109">![InterAct 适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/media/33edb889-edfa-4e55-842a-e238950327e6.gif "33edb889-edfa-4e55-842a-e238950327e6")</span><span class="sxs-lookup"><span data-stu-id="6afe6-109">![InterAct adapter server application](../../adapters-and-accelerators/fileact-interact/media/33edb889-edfa-4e55-842a-e238950327e6.gif "33edb889-edfa-4e55-842a-e238950327e6")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6afe6-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="6afe6-110">See Also</span></span>  
 <span data-ttu-id="6afe6-111">[InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="6afe6-111">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="6afe6-112">[InterAct 适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="6afe6-112">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="6afe6-113">[Business Exchange 的 interAct 适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="6afe6-113">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="6afe6-114">[InterAct 适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="6afe6-114">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="6afe6-115">[InterAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="6afe6-115">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="6afe6-116">[InterAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="6afe6-116">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="6afe6-117">[交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="6afe6-117">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="6afe6-118">[InterAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="6afe6-118">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="6afe6-119">InterAct 适配器不可否认性</span><span class="sxs-lookup"><span data-stu-id="6afe6-119">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)