---
title: 通信方向 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- port types, communication direction
- communication direction [port types]
ms.assetid: b278325e-a1da-49a6-8332-80a5f640cc22
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 307c8bae32aa7be0fee74f2f25c1bf4a2252ed0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357091"
---
# <a name="communication-direction"></a><span data-ttu-id="00eff-102">通信方向</span><span class="sxs-lookup"><span data-stu-id="00eff-102">Communication Direction</span></span>
<span data-ttu-id="00eff-103">每个*端口*都有其自己的通信方向。</span><span class="sxs-lookup"><span data-stu-id="00eff-103">Each *port* has its own communication direction.</span></span> <span data-ttu-id="00eff-104">通信方向结合使用的端口类型的通信模式与用于完成如何可以使用一个端口的定义。</span><span class="sxs-lookup"><span data-stu-id="00eff-104">The communication direction is used in combination with the communication pattern of the port's type to complete the definition of how a port can be used.</span></span> <span data-ttu-id="00eff-105">通信方向或极性，确定通过该端口将哪个方向传输消息。</span><span class="sxs-lookup"><span data-stu-id="00eff-105">The communication direction, or polarity, determines in which direction messages will be transmitted over that port.</span></span>  
  
 <span data-ttu-id="00eff-106">如果端口的类型具有一种单向通信模式，其通信方向可以发送或接收。</span><span class="sxs-lookup"><span data-stu-id="00eff-106">If the port's type has a one-way communication pattern, its communication direction can be either Send or Receive.</span></span> <span data-ttu-id="00eff-107">如果端口的类型具有双向 （请求-响应） 通信模式，其通信方向可以发送接收，在其中将请求发送和接收的响应或接收的发送，在其中收到的请求和发送响应。</span><span class="sxs-lookup"><span data-stu-id="00eff-107">If the port's type has a two-way (request-response) communication pattern, its communication direction can be Send-Receive, in which a request is sent and a response is received, or Receive-Send, in which a request is received and a response is sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00eff-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="00eff-108">See Also</span></span>  
 [<span data-ttu-id="00eff-109">通信模式</span><span class="sxs-lookup"><span data-stu-id="00eff-109">Communication Pattern</span></span>](../core/communication-pattern.md)  
 <span data-ttu-id="00eff-110">[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="00eff-110">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="00eff-111">在业务流程中使用端口</span><span class="sxs-lookup"><span data-stu-id="00eff-111">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)