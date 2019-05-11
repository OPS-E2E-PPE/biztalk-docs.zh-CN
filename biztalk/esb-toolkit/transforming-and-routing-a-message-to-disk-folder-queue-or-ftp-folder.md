---
title: 转换和消息路由到磁盘文件夹、 队列或 FTP 文件夹 |Microsoft Docs
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
ms.openlocfilehash: cfed87c48e0e8dfc845163325319f77de1bc2dff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399638"
---
# <a name="transforming-and-routing-a-message-to-disk-folder-queue-or-ftp-folder"></a><span data-ttu-id="4f35f-102">转换和消息路由到磁盘文件夹、 队列或 FTP 文件夹</span><span class="sxs-lookup"><span data-stu-id="4f35f-102">Transforming and Routing a Message to Disk Folder, Queue, or FTP Folder</span></span>
<span data-ttu-id="4f35f-103">在此用例，ESB 转换提交通过路线 Web 服务或任何接入点的消息。</span><span class="sxs-lookup"><span data-stu-id="4f35f-103">In this use case, the ESB transforms a message submitted through the Itinerary Web service or any on-ramp.</span></span> <span data-ttu-id="4f35f-104">动态解析查找属于文件类型、 FTP 或队列位置确定的映射名称 （转换） 和目标终结点的消息，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="4f35f-104">A dynamic resolution lookup of type FILE, FTP, or queue location determines the map name (for transformation) and the target endpoint for the message, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="4f35f-105">![转换磁盘文件夹](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3-TransformingDiskFolder")</span><span class="sxs-lookup"><span data-stu-id="4f35f-105">![Transforming Disk Folder](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3-TransformingDiskFolder")</span></span>  
  
 <span data-ttu-id="4f35f-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="4f35f-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="4f35f-107">**转换和一条消息路由到磁盘文件夹**</span><span class="sxs-lookup"><span data-stu-id="4f35f-107">**Transforming and routing a message to a disk folder**</span></span>  
  
 <span data-ttu-id="4f35f-108">动态解析示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="4f35f-108">The Dynamic Resolution sample included with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="4f35f-109">它演示如何为使用组件动态解析终结点位置、 设置路由属性和解析和执行级别的消息传送的 BizTalk Server 映射而无需使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="4f35f-109">It shows how to use the components to dynamically resolve endpoint location, set routing properties, and resolve and execute BizTalk Server maps at the messaging level, without using an orchestration.</span></span> <span data-ttu-id="4f35f-110">它还演示了单向和双向消息传送模式。</span><span class="sxs-lookup"><span data-stu-id="4f35f-110">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
 <span data-ttu-id="4f35f-111">此用例的扩展是转换的一种简单的路由解决方案，将传入消息路由到文件、 FTP 或队列的位置而无需额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="4f35f-111">An extension of this use case is a simple routing solution that routes an incoming message to a file, FTP, or queue location without the additional step of transformation.</span></span>  
  
 <span data-ttu-id="4f35f-112">有关详细信息，请参阅[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="4f35f-112">For more information, see [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).</span></span>