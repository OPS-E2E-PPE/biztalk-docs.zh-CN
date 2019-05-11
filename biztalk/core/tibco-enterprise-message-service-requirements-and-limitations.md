---
title: TIBCO Enterprise Message Service 要求和限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e4c022c-e6a8-4ac5-b998-b0465002a31e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94a0adbc67dfb78eef97876d65b4da50a343efce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379844"
---
# <a name="tibco-enterprise-message-service-requirements-and-limitations"></a><span data-ttu-id="75bab-102">TIBCO Enterprise Message Service 要求和限制</span><span class="sxs-lookup"><span data-stu-id="75bab-102">TIBCO Enterprise Message Service Requirements and Limitations</span></span>

## <a name="system-requirements"></a><span data-ttu-id="75bab-103">系统要求</span><span class="sxs-lookup"><span data-stu-id="75bab-103">System Requirements</span></span>  
<span data-ttu-id="75bab-104">包含与 TIBCO Enterprise Message Service 包括客户端 SDK （使用 TIBCO EMS C# API）。</span><span class="sxs-lookup"><span data-stu-id="75bab-104">Included with TIBCO Enterprise Message Service includes a client SDK (using the TIBCO EMS C# API).</span></span> <span data-ttu-id="75bab-105">用于 TIBCO EMS 的 BizTalk 适配器使用此 API 与 TIBCO EMS 进行通信。</span><span class="sxs-lookup"><span data-stu-id="75bab-105">BizTalk Adapter for TIBCO EMS uses this API to communicate with TIBCO EMS.</span></span>  
  
## <a name="add-the-api-to-the-gac"></a><span data-ttu-id="75bab-106">将 API 添加到 GAC</span><span class="sxs-lookup"><span data-stu-id="75bab-106">Add the API to the GAC</span></span>  
 <span data-ttu-id="75bab-107">用于 TIBCO EMS 的 BizTalk 适配器要求 TIBCO EMS C# API，TIBCO。EMS.dll，若要添加到全局程序集缓存 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="75bab-107">BizTalk Adapter for TIBCO EMS requires the TIBCO EMS C# API, TIBCO.EMS.dll, to be added to the global assembly cache (GAC).</span></span> <span data-ttu-id="75bab-108">适配器触发异常并记录相应的消息，如果未安装此程序集。</span><span class="sxs-lookup"><span data-stu-id="75bab-108">The adapter triggers an exception and logs an appropriate message if this assembly is not installed.</span></span>  
  
1. <span data-ttu-id="75bab-109">将复制到 TIBCO EMS C #API 你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="75bab-109">Copy the TIBCO EMS C#API to your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span>  
  
2. <span data-ttu-id="75bab-110">将目录更改为 C# API 文件，TIBCO 的位置。EMS。DLL。</span><span class="sxs-lookup"><span data-stu-id="75bab-110">Change directories to the location of the C# API file, TIBCO.EMS.DLL.</span></span>  
  
    <span data-ttu-id="75bab-111">在默认安装中，此 DLL 的路径是 c:\tibco\ems\clients\cs\TIBCO。EMS。DLL。</span><span class="sxs-lookup"><span data-stu-id="75bab-111">In the default installation, the path to this DLL is c:\tibco\ems\clients\cs\TIBCO.EMS.DLL.</span></span>  
  
3. <span data-ttu-id="75bab-112">在命令提示符下键入：</span><span class="sxs-lookup"><span data-stu-id="75bab-112">In a command prompt, type:</span></span>  
  
    `C:\bin> gacutil /i TIBCO.EMS.dll`  
  
    <span data-ttu-id="75bab-113">TIBCO。EMS.dll 现在显示 gac。</span><span class="sxs-lookup"><span data-stu-id="75bab-113">The TIBCO.EMS.dll now shows the GAC.</span></span>  
  
    <span data-ttu-id="75bab-114">若要查看 GAC 列表中，在控制面板中，打开**管理工具**，打开**Microsoft.NET Framework X.XConfiguration**，然后单击**程序集缓存**。</span><span class="sxs-lookup"><span data-stu-id="75bab-114">To view the GAC list, in Control Panel, open **Administrative Tools**, open **Microsoft .NET Framework X.XConfiguration**, and then click **Assembly Cache**.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="75bab-115">限制</span><span class="sxs-lookup"><span data-stu-id="75bab-115">Limitations</span></span>  
 <span data-ttu-id="75bab-116">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器使用 TIBCO。EMS.dll 与 TIBCO Enterprise Message Service 进行通信。</span><span class="sxs-lookup"><span data-stu-id="75bab-116">BizTalk Adapter for TIBCO Enterprise Message Service uses TIBCO.EMS.dll to communicate with TIBCO Enterprise Message Service.</span></span> <span data-ttu-id="75bab-117">使用 TIBCO EMS C# API 时，应考虑以下限制：</span><span class="sxs-lookup"><span data-stu-id="75bab-117">You should consider the following limitations when you use the TIBCO EMS C# API:</span></span>  
  
-   <span data-ttu-id="75bab-118">消息压缩，允许 TIBCO EMS 客户端将以压缩形式的消息发送到 EMS，不是可用于 C# API。</span><span class="sxs-lookup"><span data-stu-id="75bab-118">Message compression, which enables the TIBCO EMS client to send messages in a compressed form to EMS, is not available with the C# API.</span></span>  
  
-   <span data-ttu-id="75bab-119">适配器与服务器之间的消息加密不可用与 C# API。</span><span class="sxs-lookup"><span data-stu-id="75bab-119">Encryption of messages between the adapter and the server is not available with the C# API.</span></span> <span data-ttu-id="75bab-120">C# API 不允许 SSL 加密使用 OpenSSL 库。</span><span class="sxs-lookup"><span data-stu-id="75bab-120">The C# API does not allow for SSL encryption using the OpenSSL libraries.</span></span>  
  
-   <span data-ttu-id="75bab-121">C# API 不支持用于 EMS 的管理 API。</span><span class="sxs-lookup"><span data-stu-id="75bab-121">The C# API does not support the Administration API for EMS.</span></span>  
  
-   <span data-ttu-id="75bab-122">无法发送或接收使用 BizTalk TIBCO EMS 适配器的消息大于 50 MB 的大小。</span><span class="sxs-lookup"><span data-stu-id="75bab-122">Messages greater than 50MB in size cannot be sent or received using the BizTalk TIBCO EMS adapter.</span></span> <span data-ttu-id="75bab-123">超出此大小，在环境体验 System.OutOfMemoryException 异常。</span><span class="sxs-lookup"><span data-stu-id="75bab-123">Beyond this size, the environment experiences System.OutOfMemoryException exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75bab-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="75bab-124">See Also</span></span>  
 [<span data-ttu-id="75bab-125">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="75bab-125">Planning and Architecture</span></span>](../core/planning-and-architecture16.md)