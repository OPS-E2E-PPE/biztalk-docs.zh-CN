---
title: 配置 MSMQ 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, configuring
- configuring [MSMQ adapters]
ms.assetid: 8f873ee1-4eaa-43d2-948d-aecc406a0bfb
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5615178f5eb5248f74b0991075e159df70c89a09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355174"
---
# <a name="configuring-the-msmq-adapter"></a><span data-ttu-id="f0a91-102">配置 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="f0a91-102">Configuring the MSMQ Adapter</span></span>
<span data-ttu-id="f0a91-103">本部分包括有关配置 MSMQ 适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="f0a91-103">This section includes information about configuring the MSMQ adapter.</span></span> <span data-ttu-id="f0a91-104">对于接收位置和发送端口，可以配置 MSMQ 适配器。</span><span class="sxs-lookup"><span data-stu-id="f0a91-104">You can configure the MSMQ adapter for both receive locations and send ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0a91-105">若要清除属性表中的某些字段，如**用户名**并**密码**，右键单击属性名称 （不是值），并单击**Nullify**。</span><span class="sxs-lookup"><span data-stu-id="f0a91-105">To clear certain fields in the property sheet, such as **User Name** and **Password**, right-click the property name (not the value), and then click **Nullify**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f0a91-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="f0a91-106">In This Section</span></span>  
  
-   [<span data-ttu-id="f0a91-107">如何配置 MSMQ 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="f0a91-107">How to Configure an MSMQ Receive Handler</span></span>](../core/how-to-configure-an-msmq-receive-handler.md)  
  
-   [<span data-ttu-id="f0a91-108">如何配置 MSMQ 接收位置</span><span class="sxs-lookup"><span data-stu-id="f0a91-108">How to Configure an MSMQ Receive Location</span></span>](../core/how-to-configure-an-msmq-receive-location.md)  
  
-   [<span data-ttu-id="f0a91-109">如何配置 MSMQ 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="f0a91-109">How to Configure an MSMQ Send Handler</span></span>](../core/how-to-configure-an-msmq-send-handler.md)  
  
-   [<span data-ttu-id="f0a91-110">如何配置 MSMQ 发送端口</span><span class="sxs-lookup"><span data-stu-id="f0a91-110">How to Configure an MSMQ Send Port</span></span>](../core/how-to-configure-an-msmq-send-port.md)  
  
-   [<span data-ttu-id="f0a91-111">如何配置 MSMQ 发送端口</span><span class="sxs-lookup"><span data-stu-id="f0a91-111">How to Configure an MSMQ Send Port</span></span>](../core/how-to-configure-an-msmq-send-port.md)  
  
-   [<span data-ttu-id="f0a91-112">如何管理多个接收位置使用 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="f0a91-112">How to Manage Multiple Receive Locations Using the MSMQ Adapter</span></span>](../core/how-to-manage-multiple-receive-locations-using-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="f0a91-113">“消息队列”队列</span><span class="sxs-lookup"><span data-stu-id="f0a91-113">Message Queuing Queues</span></span>](../core/message-queuing-queues.md)  
  
-   [<span data-ttu-id="f0a91-114">优化 MSMQ 适配器的性能</span><span class="sxs-lookup"><span data-stu-id="f0a91-114">Optimizing Performance of the MSMQ Adapter</span></span>](../core/optimizing-performance-of-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="f0a91-115">使用 MSMQ 适配器发送和接收大型消息</span><span class="sxs-lookup"><span data-stu-id="f0a91-115">Sending and Receiving Large Messages Using the MSMQ Adapter</span></span>](../core/sending-and-receiving-large-messages-using-the-msmq-adapter.md)