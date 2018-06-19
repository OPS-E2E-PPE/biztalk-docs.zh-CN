---
title: 运行 JMS MQRFH2 组件示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44f4b48c-398a-4ec1-a033-1fc4a76a305c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fcea4bca324f73ee37b63e78673140eae250692
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294261"
---
# <a name="running-the-jms-mqrfh2-component-sample"></a><span data-ttu-id="ae0c3-102">运行 JMS MQRFH2 组件示例</span><span class="sxs-lookup"><span data-stu-id="ae0c3-102">Running the JMS MQRFH2 Component Sample</span></span>
<span data-ttu-id="ae0c3-103">JMS MQRFH2 组件示例由三部分组成：</span><span class="sxs-lookup"><span data-stu-id="ae0c3-103">The JMS MQRFH2 Component sample consists of three parts:</span></span>  
  
-   <span data-ttu-id="ae0c3-104">[运行 JMS MQRFH2 标头保留示例](../esb-toolkit/running-the-jms-mqrfh2-header-preservation-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0c3-104">[Running the JMS MQRFH2 Header Preservation Sample](../esb-toolkit/running-the-jms-mqrfh2-header-preservation-sample.md).</span></span> <span data-ttu-id="ae0c3-105">本部分演示了完全保真的标头保留，因为从 IBM WebSphere MQ，通过 ESB 和 Microsoft BizTalk Server 中，并返回到 IBM WebSphere MQ 传输一条消息。</span><span class="sxs-lookup"><span data-stu-id="ae0c3-105">This part demonstrates full-fidelity header preservation as a message travels from IBM WebSphere MQ, through ESB and Microsoft BizTalk Server, and back to IBM WebSphere MQ.</span></span>  
  
-   <span data-ttu-id="ae0c3-106">[从业务流程示例运行标头属性访问](../esb-toolkit/running-the-header-property-access-from-an-orchestration-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0c3-106">[Running the Header Property Access from an Orchestration Sample](../esb-toolkit/running-the-header-property-access-from-an-orchestration-sample.md).</span></span> <span data-ttu-id="ae0c3-107">本部分演示了如何 ESB 业务流程中的代码可以访问 MQRFH2 标头属性。</span><span class="sxs-lookup"><span data-stu-id="ae0c3-107">This part demonstrates how code within an ESB orchestration can access MQRFH2 header properties.</span></span> <span data-ttu-id="ae0c3-108">在这种情况下，代码使用标头属性以指定的目标队列名称。</span><span class="sxs-lookup"><span data-stu-id="ae0c3-108">In this case, the code uses a header property to specify the destination queue name.</span></span>  
  
-   <span data-ttu-id="ae0c3-109">[运行大容量加载基于内容的路由示例](../esb-toolkit/running-the-bulk-load-content-based-routing-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0c3-109">[Running the Bulk Load Content-Based Routing Sample](../esb-toolkit/running-the-bulk-load-content-based-routing-sample.md).</span></span> <span data-ttu-id="ae0c3-110">本部分演示了大容量加载的队列消息，并显示应用程序将消息路由到指定的消息内容一部分的目标队列的方式。</span><span class="sxs-lookup"><span data-stu-id="ae0c3-110">This part demonstrates bulk loading a queue with messages, and it shows how the application routes messages to the destination queues specified as part of the message content.</span></span>