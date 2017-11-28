---
title: "配置 MSMQ 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, configuring
- configuring [MSMQ adapters]
ms.assetid: 8f873ee1-4eaa-43d2-948d-aecc406a0bfb
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74e2cac70171a22dad391addc81daa696e204fd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-msmq-adapter"></a><span data-ttu-id="f529c-102">配置 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="f529c-102">Configuring the MSMQ Adapter</span></span>
<span data-ttu-id="f529c-103">本部分介绍有关配置 MSMQ 适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="f529c-103">This section includes information about configuring the MSMQ adapter.</span></span> <span data-ttu-id="f529c-104">对接收位置和发送端口均可配置 MSMQ 适配器。</span><span class="sxs-lookup"><span data-stu-id="f529c-104">You can configure the MSMQ adapter for both receive locations and send ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f529c-105">若要清除某些字段在属性表中，如**用户名**和**密码**，右键单击属性名称 （不是值），然后单击**Nullify**。</span><span class="sxs-lookup"><span data-stu-id="f529c-105">To clear certain fields in the property sheet, such as **User Name** and **Password**, right-click the property name (not the value), and then click **Nullify**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f529c-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="f529c-106">In This Section</span></span>  
  
-   [<span data-ttu-id="f529c-107">如何配置 MSMQ 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="f529c-107">How to Configure an MSMQ Receive Handler</span></span>](../core/how-to-configure-an-msmq-receive-handler.md)  
  
-   [<span data-ttu-id="f529c-108">如何配置 MSMQ 接收位置</span><span class="sxs-lookup"><span data-stu-id="f529c-108">How to Configure an MSMQ Receive Location</span></span>](../core/how-to-configure-an-msmq-receive-location.md)  
  
-   [<span data-ttu-id="f529c-109">如何配置 MSMQ 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="f529c-109">How to Configure an MSMQ Send Handler</span></span>](../core/how-to-configure-an-msmq-send-handler.md)  
  
-   [<span data-ttu-id="f529c-110">如何配置 MSMQ 发送端口</span><span class="sxs-lookup"><span data-stu-id="f529c-110">How to Configure an MSMQ Send Port</span></span>](../core/how-to-configure-an-msmq-send-port.md)  
  
-   [<span data-ttu-id="f529c-111">如何配置 MSMQ 发送端口</span><span class="sxs-lookup"><span data-stu-id="f529c-111">How to Configure an MSMQ Send Port</span></span>](../core/how-to-configure-an-msmq-send-port.md)  
  
-   [<span data-ttu-id="f529c-112">如何管理多个接收位置使用 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="f529c-112">How to Manage Multiple Receive Locations Using the MSMQ Adapter</span></span>](../core/how-to-manage-multiple-receive-locations-using-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="f529c-113">消息队列的队列</span><span class="sxs-lookup"><span data-stu-id="f529c-113">Message Queuing Queues</span></span>](../core/message-queuing-queues.md)  
  
-   [<span data-ttu-id="f529c-114">优化性能的 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="f529c-114">Optimizing Performance of the MSMQ Adapter</span></span>](../core/optimizing-performance-of-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="f529c-115">发送和接收使用 MSMQ 适配器的大型消息</span><span class="sxs-lookup"><span data-stu-id="f529c-115">Sending and Receiving Large Messages Using the MSMQ Adapter</span></span>](../core/sending-and-receiving-large-messages-using-the-msmq-adapter.md)