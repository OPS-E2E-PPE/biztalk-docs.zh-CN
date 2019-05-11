---
title: FileAct 适配器支持信息传输 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fc27561-9abb-4496-9db7-f221a6c90738
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49966bac71f9bdd2c825da2869ec81907b90c8c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367157"
---
# <a name="fileact-adapter-supporting-information-transfer"></a><span data-ttu-id="661cf-102">FileAct 适配器支持信息传输</span><span class="sxs-lookup"><span data-stu-id="661cf-102">FileAct Adapter Supporting Information Transfer</span></span>
<span data-ttu-id="661cf-103">FileAct 适配器允许可选传输的文件的支持信息。</span><span class="sxs-lookup"><span data-stu-id="661cf-103">The FileAct adapter permits the optional transfer of supporting information with files.</span></span> <span data-ttu-id="661cf-104">应用程序自行传输此信息。</span><span class="sxs-lookup"><span data-stu-id="661cf-104">This information is transferred at the discretion of the application.</span></span> <span data-ttu-id="661cf-105">适配器不执行除以验证它以正确的格式在原始端此信息的任何特殊处理。</span><span class="sxs-lookup"><span data-stu-id="661cf-105">The adapter does not do any special processing of this information on the originating side except to validate that it is in the correct format.</span></span> <span data-ttu-id="661cf-106">元素组成的支持信息包括：</span><span class="sxs-lookup"><span data-stu-id="661cf-106">The elements which comprise supporting information include:</span></span>  
  
-   <span data-ttu-id="661cf-107">文件说明和文件信息</span><span class="sxs-lookup"><span data-stu-id="661cf-107">File description and file information</span></span>  
  
-   <span data-ttu-id="661cf-108">说明传输和传输信息</span><span class="sxs-lookup"><span data-stu-id="661cf-108">Transfer description and transfer information</span></span>  
  
-   <span data-ttu-id="661cf-109">确认说明和确认信息</span><span class="sxs-lookup"><span data-stu-id="661cf-109">Acknowledgement description and acknowledgement information</span></span>  
  
-   <span data-ttu-id="661cf-110">拒绝说明和拒绝信息</span><span class="sxs-lookup"><span data-stu-id="661cf-110">Rejection description and reject information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="661cf-111">文件信息的组件之一定义压缩和解压缩。</span><span class="sxs-lookup"><span data-stu-id="661cf-111">One of the components of file information defines compression and decompression.</span></span> <span data-ttu-id="661cf-112">应用程序不是适配器负责压缩和解压缩。</span><span class="sxs-lookup"><span data-stu-id="661cf-112">Compression and decompression are the responsibility of the application, not the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="661cf-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="661cf-113">See Also</span></span>  
 <span data-ttu-id="661cf-114">[FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="661cf-114">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="661cf-115">[FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="661cf-115">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="661cf-116">[FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="661cf-116">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="661cf-117">[FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="661cf-117">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="661cf-118">[FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="661cf-118">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="661cf-119">[FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="661cf-119">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="661cf-120">[FileAct 适配器送达通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="661cf-120">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="661cf-121">FileAct 适配器状态监视</span><span class="sxs-lookup"><span data-stu-id="661cf-121">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)