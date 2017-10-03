---
title: "通信方向 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port types, communication direction
- communication direction [port types]
ms.assetid: b278325e-a1da-49a6-8332-80a5f640cc22
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d6c664643629971366805d08600677d22d7c419
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="communication-direction"></a><span data-ttu-id="c7d27-102">通信方向</span><span class="sxs-lookup"><span data-stu-id="c7d27-102">Communication Direction</span></span>
<span data-ttu-id="c7d27-103">每个*端口*都有其自己的通信的方向。</span><span class="sxs-lookup"><span data-stu-id="c7d27-103">Each *port* has its own communication direction.</span></span> <span data-ttu-id="c7d27-104">通信方向端口的类型的通信模式与结合使用，以完成如何使用一个端口的定义。</span><span class="sxs-lookup"><span data-stu-id="c7d27-104">The communication direction is used in combination with the communication pattern of the port's type to complete the definition of how a port can be used.</span></span> <span data-ttu-id="c7d27-105">通信方向或极性，确定通过该端口将的方向传输消息。</span><span class="sxs-lookup"><span data-stu-id="c7d27-105">The communication direction, or polarity, determines in which direction messages will be transmitted over that port.</span></span>  
  
 <span data-ttu-id="c7d27-106">如果端口的类型具有一种单向通信模式，其通信方向可以发送或接收。</span><span class="sxs-lookup"><span data-stu-id="c7d27-106">If the port's type has a one-way communication pattern, its communication direction can be either Send or Receive.</span></span> <span data-ttu-id="c7d27-107">如果端口的类型具有双向 （请求-响应） 通信模式，其通信方向可以发送-接收，在其中将请求发送和接收的响应或接收发送，在其中接收到的请求和发送响应。</span><span class="sxs-lookup"><span data-stu-id="c7d27-107">If the port's type has a two-way (request-response) communication pattern, its communication direction can be Send-Receive, in which a request is sent and a response is received, or Receive-Send, in which a request is received and a response is sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7d27-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7d27-108">See Also</span></span>  
 [<span data-ttu-id="c7d27-109">通信模式</span><span class="sxs-lookup"><span data-stu-id="c7d27-109">Communication Pattern</span></span>](../core/communication-pattern.md)  
 <span data-ttu-id="c7d27-110">[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="c7d27-110">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="c7d27-111">使用在业务流程中的端口</span><span class="sxs-lookup"><span data-stu-id="c7d27-111">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)