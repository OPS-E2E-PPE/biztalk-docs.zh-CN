---
title: "TIBCO 企业消息服务要求和限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption
- messages, compression
- EMS limitations
- message compression
- API, adding to GAC
- global assembly cache, adding API
- GAC, adding TIBCO EMS API
- system requirements
- TIBCO.EMS.dll
- EMS requirements
- messages, encryption
ms.assetid: 6e4c022c-e6a8-4ac5-b998-b0465002a31e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81e49f4a74cce4414fd9d0b069a382d9facb03d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-enterprise-message-service-requirements-and-limitations"></a><span data-ttu-id="6df0d-102">TIBCO Enterprise Message Service 要求和限制</span><span class="sxs-lookup"><span data-stu-id="6df0d-102">TIBCO Enterprise Message Service Requirements and Limitations</span></span>
## <a name="system-requirements"></a><span data-ttu-id="6df0d-103">系统要求</span><span class="sxs-lookup"><span data-stu-id="6df0d-103">System Requirements</span></span>  
 <span data-ttu-id="6df0d-104">用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器支持 TIBCO Enterprise Message Service (EMS) 版本 4.2。</span><span class="sxs-lookup"><span data-stu-id="6df0d-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service supports TIBCO Enterprise Message Service (EMS) version 4.2.</span></span> <span data-ttu-id="6df0d-105">TIBCO EMS 版本 4.2 随附有客户端 SDK（使用 TIBCO EMS C# API）。</span><span class="sxs-lookup"><span data-stu-id="6df0d-105">Included with TIBCO EMS version 4.2 is a client SDK (using the TIBCO EMS C# API).</span></span> <span data-ttu-id="6df0d-106">用于 TIBCO EMS 的 BizTalk 适配器使用此 API 与 TIBCO EMS 通信。</span><span class="sxs-lookup"><span data-stu-id="6df0d-106">BizTalk Adapter for TIBCO EMS uses this API to communicate with TIBCO EMS.</span></span>  
  
## <a name="adding-the-api-to-the-gac"></a><span data-ttu-id="6df0d-107">将 API 添加到 GAC</span><span class="sxs-lookup"><span data-stu-id="6df0d-107">Adding the API to the GAC</span></span>  
 <span data-ttu-id="6df0d-108">用于 TIBCO EMS 的 BizTalk 适配器要求将 TIBCO EMS C# API TIBCO.EMS.dll 添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="6df0d-108">BizTalk Adapter for TIBCO EMS requires the TIBCO EMS C# API, TIBCO.EMS.dll, to be added to the global assembly cache (GAC).</span></span> <span data-ttu-id="6df0d-109">如果未安装此程序集，则适配器会触发异常并记录相应的消息。</span><span class="sxs-lookup"><span data-stu-id="6df0d-109">The adapter triggers an exception and logs an appropriate message if this assembly is not installed.</span></span>  
  
#### <a name="to-add-the-tibco-ems-c-api-to-the-gac"></a><span data-ttu-id="6df0d-110">将 TIBCO EMS C# API 添加到 GAC</span><span class="sxs-lookup"><span data-stu-id="6df0d-110">To add the TIBCO EMS C# API to the GAC</span></span>  
  
1.  <span data-ttu-id="6df0d-111">将复制到 TIBCO EMS C #API 你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="6df0d-111">Copy the TIBCO EMS C#API to your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span>  
  
2.  <span data-ttu-id="6df0d-112">将目录更改为 C# API 文件，TIBCO 的位置。EMS。DLL。</span><span class="sxs-lookup"><span data-stu-id="6df0d-112">Change directories to the location of the C# API file, TIBCO.EMS.DLL.</span></span>  
  
     <span data-ttu-id="6df0d-113">在默认安装中，此 DLL 的路径是 c:\tibco\ems\clients\cs\TIBCO。EMS。DLL。</span><span class="sxs-lookup"><span data-stu-id="6df0d-113">In the default installation, the path to this DLL is c:\tibco\ems\clients\cs\TIBCO.EMS.DLL.</span></span>  
  
3.  <span data-ttu-id="6df0d-114">在命令提示符下键入：</span><span class="sxs-lookup"><span data-stu-id="6df0d-114">In a command prompt, type:</span></span>  
  
     `C:\bin> gacutil /i TIBCO.EMS.dll`  
  
     <span data-ttu-id="6df0d-115">TIBCO。EMS.dll 现在显示 gac。</span><span class="sxs-lookup"><span data-stu-id="6df0d-115">The TIBCO.EMS.dll now shows the GAC.</span></span>  
  
     <span data-ttu-id="6df0d-116">若要查看 GAC 列表中，在控制面板中，打开**管理工具**，打开**Microsoft.NET Framework X.XConfiguration**，然后单击**程序集缓存**。</span><span class="sxs-lookup"><span data-stu-id="6df0d-116">To view the GAC list, in Control Panel, open **Administrative Tools**, open **Microsoft .NET Framework X.XConfiguration**, and then click **Assembly Cache**.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="6df0d-117">限制</span><span class="sxs-lookup"><span data-stu-id="6df0d-117">Limitations</span></span>  
 <span data-ttu-id="6df0d-118">BizTalk 适配器 TIBCO 企业消息服务使用 TIBCO。EMS.dll 与 TIBCO 企业消息服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="6df0d-118">BizTalk Adapter for TIBCO Enterprise Message Service uses TIBCO.EMS.dll to communicate with TIBCO Enterprise Message Service.</span></span> <span data-ttu-id="6df0d-119">当你使用 TIBCO EMS C# API 时，应考虑以下限制：</span><span class="sxs-lookup"><span data-stu-id="6df0d-119">You should consider the following limitations when you use the TIBCO EMS C# API:</span></span>  
  
-   <span data-ttu-id="6df0d-120">使 TIBCO EMS 客户端将消息以压缩形式发送到 EMS 的消息压缩时无法使用 C# API。</span><span class="sxs-lookup"><span data-stu-id="6df0d-120">Message compression, which enables the TIBCO EMS client to send messages in a compressed form to EMS, is not available with the C# API.</span></span>  
  
-   <span data-ttu-id="6df0d-121">加密的适配器和服务器之间的消息时无法使用 C# API。</span><span class="sxs-lookup"><span data-stu-id="6df0d-121">Encryption of messages between the adapter and the server is not available with the C# API.</span></span> <span data-ttu-id="6df0d-122">C# API 不允许使用 OpenSSL 库的 SSL 加密。</span><span class="sxs-lookup"><span data-stu-id="6df0d-122">The C# API does not allow for SSL encryption using the OpenSSL libraries.</span></span>  
  
-   <span data-ttu-id="6df0d-123">C# API 不支持进行 ems 相关的管理 API。</span><span class="sxs-lookup"><span data-stu-id="6df0d-123">The C# API does not support the Administration API for EMS.</span></span>  
  
-   <span data-ttu-id="6df0d-124">无法发送或接收使用 BizTalk TIBCO EMS 适配器大于 50 MB 的大小的消息。</span><span class="sxs-lookup"><span data-stu-id="6df0d-124">Messages greater than 50MB in size cannot be sent or received using the BizTalk TIBCO EMS adapter.</span></span> <span data-ttu-id="6df0d-125">超出此大小，环境遇到 System.OutOfMemoryException 异常。</span><span class="sxs-lookup"><span data-stu-id="6df0d-125">Beyond this size, the environment experiences System.OutOfMemoryException exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6df0d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6df0d-126">See Also</span></span>  
 [<span data-ttu-id="6df0d-127">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="6df0d-127">Planning and Architecture</span></span>](../core/planning-and-architecture16.md)