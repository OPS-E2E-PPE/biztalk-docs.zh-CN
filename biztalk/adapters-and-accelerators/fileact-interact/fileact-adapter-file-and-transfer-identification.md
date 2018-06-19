---
title: FileAct 适配器文件和传输标识 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a9aaff1-8816-42cf-b100-fedf964caaf5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5340f9ad739009ff1cb1257365ceeeb7459511a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223149"
---
# <a name="fileact-adapter-file-and-transfer-identification"></a><span data-ttu-id="10fde-102">FileAct 适配器文件和传输标识</span><span class="sxs-lookup"><span data-stu-id="10fde-102">FileAct Adapter File and Transfer Identification</span></span>
<span data-ttu-id="10fde-103">A4SWIFT FileAct 适配器允许开发人员提供在运行时的文件和传输标识详细信息。</span><span class="sxs-lookup"><span data-stu-id="10fde-103">The A4SWIFT FileAct adapter permits the developer to supply file and transfer identification specifics at runtime.</span></span> <span data-ttu-id="10fde-104">这些参数包括：</span><span class="sxs-lookup"><span data-stu-id="10fde-104">These parameters include the following:</span></span>  
  
-   <span data-ttu-id="10fde-105">**物理文件的名称**– 的完整路径和要读取或写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="10fde-105">**Physical file name** – the full path and name of the file to be read or written.</span></span> <span data-ttu-id="10fde-106">此参数绝对不传递和本地文件处理程序组件。</span><span class="sxs-lookup"><span data-stu-id="10fde-106">This parameter is never passed, and is local to the file handler component.</span></span>  
  
-   <span data-ttu-id="10fde-107">**逻辑文件名**– 跨 SWIFTNet，发送应用程序中对接收应用程序传递的文件名称。</span><span class="sxs-lookup"><span data-stu-id="10fde-107">**Logical file name** – the file name passed from the sending application to the receiving application across SWIFTNet.</span></span> <span data-ttu-id="10fde-108">这是可选的并且，如果未提供，不含路径的物理文件名称适用。</span><span class="sxs-lookup"><span data-stu-id="10fde-108">This is optional, and, if not supplied, the physical file name without the path is used.</span></span>  
  
-   <span data-ttu-id="10fde-109">**文件传输事件终结点**– 订阅事件基元中应用程序处理文件传输事件所指定的名称。</span><span class="sxs-lookup"><span data-stu-id="10fde-109">**File transfer event endpoint** – the name specified in the Subscribe Event primitive by the application handling the file transfer events.</span></span> <span data-ttu-id="10fde-110">此参数链接到应用程序接收事件报告的文件传输。</span><span class="sxs-lookup"><span data-stu-id="10fde-110">This parameter links the file transfer to the application which receives the event reports.</span></span>  
  
-   <span data-ttu-id="10fde-111">**文件传输引用**– 标记字符串创建和使用的传输中的句柄为 FileAct 子系统本身。</span><span class="sxs-lookup"><span data-stu-id="10fde-111">**File Transfer Reference** – a token string created and used by the FileAct subsystem as a handle on the transfer, itself.</span></span> <span data-ttu-id="10fde-112">就而言 FileAct 适配器，这是只需一个唯一的此传输的字符串。</span><span class="sxs-lookup"><span data-stu-id="10fde-112">This is simply a string unique to this transfer, as far as the FileAct adapter is concerned.</span></span>  
  
-   <span data-ttu-id="10fde-113">**将密钥传送**– 由应用程序标识的传输，分配的字符串中止目的。</span><span class="sxs-lookup"><span data-stu-id="10fde-113">**Transfer Key** – a string assigned by the application to identify the transfer for abort purposes.</span></span> <span data-ttu-id="10fde-114">如果不是由应用程序，这是与文件关联的 GUID。</span><span class="sxs-lookup"><span data-stu-id="10fde-114">If not provided by the application, this is the GUID associated with the file.</span></span>  
  
-   <span data-ttu-id="10fde-115">**传输分区**– 用于与多个传输的字符串。</span><span class="sxs-lookup"><span data-stu-id="10fde-115">**Transfer Partition** – a string used to relate multiple transfers.</span></span> <span data-ttu-id="10fde-116">如果未在调用中提供的开发人员，这将是指定定义相关发送时的"应用程序名称"或接收位置。</span><span class="sxs-lookup"><span data-stu-id="10fde-116">If not supplied in the calls by the developer, this will be the “Application Name” specified when defining the relevant send or receive location.</span></span>  
  
-   <span data-ttu-id="10fde-117">**用户参考**– 应用程序以唯一标识为不可否认性传输定义的字符串。</span><span class="sxs-lookup"><span data-stu-id="10fde-117">**User Reference** – a string defined by the application to uniquely identify the transfer for non-repudiation.</span></span> <span data-ttu-id="10fde-118">如果不是由应用程序，这将是与文件关联的 GUID。</span><span class="sxs-lookup"><span data-stu-id="10fde-118">If not provided by the application, this will be the GUID associated with the file.</span></span>  
  
-   <span data-ttu-id="10fde-119">**消息 ID** – 唯一定义的初始请求或响应的标识符。</span><span class="sxs-lookup"><span data-stu-id="10fde-119">**Message ID** – the identifier uniquely defining the initial request or response.</span></span> <span data-ttu-id="10fde-120">这是与相应的请求或响应消息关联的 GUID，因为生成的发送的适配器。</span><span class="sxs-lookup"><span data-stu-id="10fde-120">This is the GUID associated with the appropriate request or response message, as generated by the sending adapter.</span></span> <span data-ttu-id="10fde-121">因此，客户端生成的请求消息 ID，服务器所执行操作的响应。</span><span class="sxs-lookup"><span data-stu-id="10fde-121">Thus, the client generates the Message ID for requests and the server does so for responses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10fde-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10fde-122">See Also</span></span>  
 <span data-ttu-id="10fde-123">[FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="10fde-123">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="10fde-124">[FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="10fde-124">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="10fde-125">[FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="10fde-125">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="10fde-126">[FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="10fde-126">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="10fde-127">[FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="10fde-127">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="10fde-128">[FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="10fde-128">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="10fde-129">[FileAct 适配器传递通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="10fde-129">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="10fde-130">FileAct 适配器状态监视</span><span class="sxs-lookup"><span data-stu-id="10fde-130">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)