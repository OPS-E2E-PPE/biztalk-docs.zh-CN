---
title: "FileAct 适配器安全体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5faeebd6-5287-4ac4-a1db-e3c055d323d2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ed8352b788af12fd3c38f489e9ddb65d8375f2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fileact-adapter-security-architecture"></a><span data-ttu-id="48c6e-102">FileAct 适配器安全体系结构</span><span class="sxs-lookup"><span data-stu-id="48c6e-102">FileAct Adapter Security Architecture</span></span>
<span data-ttu-id="48c6e-103">使用 SNL 和压降中固有的证书和加密功能实现的文件发送和接收的安全性。</span><span class="sxs-lookup"><span data-stu-id="48c6e-103">Security for the file transmission and receipt is implemented using the certificate and crypto features inherent in SNL and the SAG.</span></span>  <span data-ttu-id="48c6e-104">管理证书、 等，完全是 FileAct 适配器的范围之外。</span><span class="sxs-lookup"><span data-stu-id="48c6e-104">The management of certificates, etc., is completely outside of the scope of the FileAct Adapter.</span></span> <span data-ttu-id="48c6e-105">只要 SWIFT 和 SNL/压降上正确安装的软件的 FileAct 服务注册时与之关联的 SNL/压降实例，该适配器将使用设施到 SNL Api。</span><span class="sxs-lookup"><span data-stu-id="48c6e-105">As long as the associated SNL/SAG instance is registered for the FileAct service with SWIFT and the software properly installed on SNL/SAG, the adapter makes use of the facilities throught the SNL APIs.</span></span> <span data-ttu-id="48c6e-106">FileAct 适配器将始终设置为"高级"（最佳做法） FACryptoMode。</span><span class="sxs-lookup"><span data-stu-id="48c6e-106">The FileAct Adapter will always set the FACryptoMode to “Advanced” (best practice).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48c6e-107">对于适配器，你可以创建每个发送端口的单独的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="48c6e-107">For the adapter, you can create a separate security context for  each send port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c6e-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48c6e-108">See Also</span></span>  
 <span data-ttu-id="48c6e-109">[FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="48c6e-109">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="48c6e-110">[FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="48c6e-110">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="48c6e-111">[FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="48c6e-111">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="48c6e-112">[FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="48c6e-112">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="48c6e-113">[FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="48c6e-113">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="48c6e-114">[FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="48c6e-114">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="48c6e-115">[FileAct 适配器传递通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="48c6e-115">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="48c6e-116">FileAct 适配器状态监视</span><span class="sxs-lookup"><span data-stu-id="48c6e-116">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)