---
title: "支持信息传输的 FileAct 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fc27561-9abb-4496-9db7-f221a6c90738
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5aefba5fe85a8a275d3b2050d8c08cc98f74d06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fileact-adapter-supporting-information-transfer"></a><span data-ttu-id="a2b1a-102">FileAct 适配器支持信息传输</span><span class="sxs-lookup"><span data-stu-id="a2b1a-102">FileAct Adapter Supporting Information Transfer</span></span>
<span data-ttu-id="a2b1a-103">FileAct 适配器允许可选传输的文件的支持信息。</span><span class="sxs-lookup"><span data-stu-id="a2b1a-103">The FileAct adapter permits the optional transfer of supporting information with files.</span></span> <span data-ttu-id="a2b1a-104">应用程序自行传输此信息。</span><span class="sxs-lookup"><span data-stu-id="a2b1a-104">This information is transferred at the discretion of the application.</span></span> <span data-ttu-id="a2b1a-105">适配器不会执行操作 （验证它正在正确的格式除外） 的起始端上的此信息进行任何特殊处理。</span><span class="sxs-lookup"><span data-stu-id="a2b1a-105">The adapter does not do any special processing of this information on the originating side except to validate that it is in the correct format.</span></span> <span data-ttu-id="a2b1a-106">元素用于构成支持信息包括：</span><span class="sxs-lookup"><span data-stu-id="a2b1a-106">The elements which comprise supporting information include:</span></span>  
  
-   <span data-ttu-id="a2b1a-107">文件说明和文件信息</span><span class="sxs-lookup"><span data-stu-id="a2b1a-107">File description and file information</span></span>  
  
-   <span data-ttu-id="a2b1a-108">传输说明和传输信息</span><span class="sxs-lookup"><span data-stu-id="a2b1a-108">Transfer description and transfer information</span></span>  
  
-   <span data-ttu-id="a2b1a-109">确认说明和确认信息</span><span class="sxs-lookup"><span data-stu-id="a2b1a-109">Acknowledgement description and acknowledgement information</span></span>  
  
-   <span data-ttu-id="a2b1a-110">拒绝说明和拒绝信息</span><span class="sxs-lookup"><span data-stu-id="a2b1a-110">Rejection description and reject information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2b1a-111">文件信息的以下组件之一定义压缩和解压缩。</span><span class="sxs-lookup"><span data-stu-id="a2b1a-111">One of the components of file information defines compression and decompression.</span></span> <span data-ttu-id="a2b1a-112">压缩和解压缩负责管理的应用程序，不是适配器。</span><span class="sxs-lookup"><span data-stu-id="a2b1a-112">Compression and decompression are the responsibility of the application, not the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b1a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2b1a-113">See Also</span></span>  
 <span data-ttu-id="a2b1a-114">[FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="a2b1a-114">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="a2b1a-115">[FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="a2b1a-115">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="a2b1a-116">[FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="a2b1a-116">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="a2b1a-117">[FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="a2b1a-117">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="a2b1a-118">[FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="a2b1a-118">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="a2b1a-119">[FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="a2b1a-119">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="a2b1a-120">[FileAct 适配器传递通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="a2b1a-120">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="a2b1a-121">FileAct 适配器状态监视</span><span class="sxs-lookup"><span data-stu-id="a2b1a-121">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)