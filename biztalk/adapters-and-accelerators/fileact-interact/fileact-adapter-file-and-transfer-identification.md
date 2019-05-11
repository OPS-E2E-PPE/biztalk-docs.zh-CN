---
title: FileAct 适配器文件和传输标识 |Microsoft Docs
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
ms.openlocfilehash: 4530a524518c96db0b42cbae456ba6705e2e9b0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367201"
---
# <a name="fileact-adapter-file-and-transfer-identification"></a><span data-ttu-id="d7098-102">FileAct 适配器文件和传输标识</span><span class="sxs-lookup"><span data-stu-id="d7098-102">FileAct Adapter File and Transfer Identification</span></span>
<span data-ttu-id="d7098-103">A4SWIFT FileAct 适配器允许开发人员提供在运行时的文件和传输标识详细信息。</span><span class="sxs-lookup"><span data-stu-id="d7098-103">The A4SWIFT FileAct adapter permits the developer to supply file and transfer identification specifics at runtime.</span></span> <span data-ttu-id="d7098-104">这些参数包括：</span><span class="sxs-lookup"><span data-stu-id="d7098-104">These parameters include the following:</span></span>  
  
-   <span data-ttu-id="d7098-105">**物理文件名**– 的完整路径和要读取或写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d7098-105">**Physical file name** – the full path and name of the file to be read or written.</span></span> <span data-ttu-id="d7098-106">此参数永远不会传递，并且是本地的文件处理程序组件。</span><span class="sxs-lookup"><span data-stu-id="d7098-106">This parameter is never passed, and is local to the file handler component.</span></span>  
  
-   <span data-ttu-id="d7098-107">**逻辑文件名**– 跨 SWIFTNet，发送应用程序中对接收应用程序传递的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d7098-107">**Logical file name** – the file name passed from the sending application to the receiving application across SWIFTNet.</span></span> <span data-ttu-id="d7098-108">这是可选的并且如果未提供，则使用不带路径的物理文件名。</span><span class="sxs-lookup"><span data-stu-id="d7098-108">This is optional, and, if not supplied, the physical file name without the path is used.</span></span>  
  
-   <span data-ttu-id="d7098-109">**文件传输事件的终结点**– 指定订阅事件基元中处理文件传输事件的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="d7098-109">**File transfer event endpoint** – the name specified in the Subscribe Event primitive by the application handling the file transfer events.</span></span> <span data-ttu-id="d7098-110">此参数链接到应用程序接收事件报告的文件传输。</span><span class="sxs-lookup"><span data-stu-id="d7098-110">This parameter links the file transfer to the application which receives the event reports.</span></span>  
  
-   <span data-ttu-id="d7098-111">**文件传输引用**– 标记字符串创建和使用的传输中的句柄作为 FileAct 子系统本身。</span><span class="sxs-lookup"><span data-stu-id="d7098-111">**File Transfer Reference** – a token string created and used by the FileAct subsystem as a handle on the transfer, itself.</span></span> <span data-ttu-id="d7098-112">FileAct 适配器而言，这是只需对此传输，唯一的字符串。</span><span class="sxs-lookup"><span data-stu-id="d7098-112">This is simply a string unique to this transfer, as far as the FileAct adapter is concerned.</span></span>  
  
-   <span data-ttu-id="d7098-113">**将密钥传送**– 字符串分配的应用程序以标识为传输中止目的。</span><span class="sxs-lookup"><span data-stu-id="d7098-113">**Transfer Key** – a string assigned by the application to identify the transfer for abort purposes.</span></span> <span data-ttu-id="d7098-114">如果未提供应用程序，这是与文件关联的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d7098-114">If not provided by the application, this is the GUID associated with the file.</span></span>  
  
-   <span data-ttu-id="d7098-115">**传输分区**– 用于与多个传输的字符串。</span><span class="sxs-lookup"><span data-stu-id="d7098-115">**Transfer Partition** – a string used to relate multiple transfers.</span></span> <span data-ttu-id="d7098-116">如果未在调用中提供的开发人员，这将指定定义相关发送时的"应用程序名称"或接收位置。</span><span class="sxs-lookup"><span data-stu-id="d7098-116">If not supplied in the calls by the developer, this will be the “Application Name” specified when defining the relevant send or receive location.</span></span>  
  
-   <span data-ttu-id="d7098-117">**用户参考**– 应用程序以唯一标识对不可否认传输定义的字符串。</span><span class="sxs-lookup"><span data-stu-id="d7098-117">**User Reference** – a string defined by the application to uniquely identify the transfer for non-repudiation.</span></span> <span data-ttu-id="d7098-118">如果未提供应用程序，这将是与文件关联的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d7098-118">If not provided by the application, this will be the GUID associated with the file.</span></span>  
  
-   <span data-ttu-id="d7098-119">**消息 ID** – 唯一定义的初始请求或响应的标识符。</span><span class="sxs-lookup"><span data-stu-id="d7098-119">**Message ID** – the identifier uniquely defining the initial request or response.</span></span> <span data-ttu-id="d7098-120">这是由发送适配器生成与相应的请求或响应消息关联的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d7098-120">This is the GUID associated with the appropriate request or response message, as generated by the sending adapter.</span></span> <span data-ttu-id="d7098-121">因此，客户端生成的请求消息的 ID，该服务器将执行操作的响应。</span><span class="sxs-lookup"><span data-stu-id="d7098-121">Thus, the client generates the Message ID for requests and the server does so for responses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7098-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7098-122">See Also</span></span>  
 <span data-ttu-id="d7098-123">[FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d7098-123">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="d7098-124">[FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="d7098-124">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="d7098-125">[FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="d7098-125">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="d7098-126">[FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="d7098-126">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="d7098-127">[FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d7098-127">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="d7098-128">[FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="d7098-128">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="d7098-129">[FileAct 适配器送达通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="d7098-129">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="d7098-130">FileAct 适配器状态监视</span><span class="sxs-lookup"><span data-stu-id="d7098-130">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)