---
title: 将转换以及消息路由到磁盘文件夹、 队列或 FTP 文件夹 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bfdbc38-6663-4d95-a0ed-57fec0245b9f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcbc9d42fbed5dfd73aee910ba2e1a40da595658
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009838"
---
# <a name="transforming-and-routing-a-message-to-disk-folder-queue-or-ftp-folder"></a><span data-ttu-id="0b6d5-102">将转换以及消息路由到磁盘文件夹、 队列或 FTP 文件夹</span><span class="sxs-lookup"><span data-stu-id="0b6d5-102">Transforming and Routing a Message to Disk Folder, Queue, or FTP Folder</span></span>
<span data-ttu-id="0b6d5-103">在此用例，ESB 转换消息提交通过路线 Web 服务或任何在负载增加。</span><span class="sxs-lookup"><span data-stu-id="0b6d5-103">In this use case, the ESB transforms a message submitted through the Itinerary Web service or any on-ramp.</span></span> <span data-ttu-id="0b6d5-104">动态解析的文件类型的查找、 FTP 或队列位置确定 （适用于转换） 将映射名称和目标终结点的消息，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="0b6d5-104">A dynamic resolution lookup of type FILE, FTP, or queue location determines the map name (for transformation) and the target endpoint for the message, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="0b6d5-105">![转换磁盘文件夹](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3 TransformingDiskFolder")</span><span class="sxs-lookup"><span data-stu-id="0b6d5-105">![Transforming Disk Folder](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3-TransformingDiskFolder")</span></span>  
  
 <span data-ttu-id="0b6d5-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="0b6d5-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="0b6d5-107">**将转换以及将消息路由到磁盘文件夹**</span><span class="sxs-lookup"><span data-stu-id="0b6d5-107">**Transforming and routing a message to a disk folder**</span></span>  
  
 <span data-ttu-id="0b6d5-108">包含动态解析示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="0b6d5-108">The Dynamic Resolution sample included with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="0b6d5-109">它演示如何使用组件来动态解析终结点的位置、 设置路由的属性，并解决，并执行 BizTalk Server 映射在消息级别，而无需使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="0b6d5-109">It shows how to use the components to dynamically resolve endpoint location, set routing properties, and resolve and execute BizTalk Server maps at the messaging level, without using an orchestration.</span></span> <span data-ttu-id="0b6d5-110">它还演示了单向和双向消息模式。</span><span class="sxs-lookup"><span data-stu-id="0b6d5-110">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
 <span data-ttu-id="0b6d5-111">此用例的扩展是转换的一种简单的路由解决方案，将传入消息路由到文件、 FTP 或队列的位置而无需额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="0b6d5-111">An extension of this use case is a simple routing solution that routes an incoming message to a file, FTP, or queue location without the additional step of transformation.</span></span>  
  
 <span data-ttu-id="0b6d5-112">有关详细信息，请参阅[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0b6d5-112">For more information, see [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).</span></span>