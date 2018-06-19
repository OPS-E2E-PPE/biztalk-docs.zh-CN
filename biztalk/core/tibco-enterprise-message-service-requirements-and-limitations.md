---
title: TIBCO 企业消息服务要求和限制 |Microsoft 文档
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
ms.openlocfilehash: fcd386245ba06c2e3b5a5b92df7b7a7f01a1a749
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013668"
---
# <a name="tibco-enterprise-message-service-requirements-and-limitations"></a><span data-ttu-id="c44c2-102">TIBCO Enterprise Message Service 要求和限制</span><span class="sxs-lookup"><span data-stu-id="c44c2-102">TIBCO Enterprise Message Service Requirements and Limitations</span></span>

## <a name="system-requirements"></a><span data-ttu-id="c44c2-103">系统要求</span><span class="sxs-lookup"><span data-stu-id="c44c2-103">System Requirements</span></span>  
<span data-ttu-id="c44c2-104">附带 TIBCO 企业消息服务包括客户端 SDK （使用 TIBCO EMS C# API）。</span><span class="sxs-lookup"><span data-stu-id="c44c2-104">Included with TIBCO Enterprise Message Service includes a client SDK (using the TIBCO EMS C# API).</span></span> <span data-ttu-id="c44c2-105">用于 TIBCO EMS 的 BizTalk 适配器使用此 API 与 TIBCO EMS 通信。</span><span class="sxs-lookup"><span data-stu-id="c44c2-105">BizTalk Adapter for TIBCO EMS uses this API to communicate with TIBCO EMS.</span></span>  
  
## <a name="add-the-api-to-the-gac"></a><span data-ttu-id="c44c2-106">将 API 添加到 gac 中</span><span class="sxs-lookup"><span data-stu-id="c44c2-106">Add the API to the GAC</span></span>  
 <span data-ttu-id="c44c2-107">用于 TIBCO EMS 的 BizTalk 适配器要求将 TIBCO EMS C# API TIBCO.EMS.dll 添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="c44c2-107">BizTalk Adapter for TIBCO EMS requires the TIBCO EMS C# API, TIBCO.EMS.dll, to be added to the global assembly cache (GAC).</span></span> <span data-ttu-id="c44c2-108">如果未安装此程序集，则适配器会触发异常并记录相应的消息。</span><span class="sxs-lookup"><span data-stu-id="c44c2-108">The adapter triggers an exception and logs an appropriate message if this assembly is not installed.</span></span>  
  
1.  <span data-ttu-id="c44c2-109">将复制到 TIBCO EMS C #API 你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="c44c2-109">Copy the TIBCO EMS C#API to your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span>  
  
2.  <span data-ttu-id="c44c2-110">将目录更改为 C# API 文件，TIBCO 的位置。EMS。DLL。</span><span class="sxs-lookup"><span data-stu-id="c44c2-110">Change directories to the location of the C# API file, TIBCO.EMS.DLL.</span></span>  
  
     <span data-ttu-id="c44c2-111">在默认安装中，此 DLL 的路径是 c:\tibco\ems\clients\cs\TIBCO。EMS。DLL。</span><span class="sxs-lookup"><span data-stu-id="c44c2-111">In the default installation, the path to this DLL is c:\tibco\ems\clients\cs\TIBCO.EMS.DLL.</span></span>  
  
3.  <span data-ttu-id="c44c2-112">在命令提示符下键入：</span><span class="sxs-lookup"><span data-stu-id="c44c2-112">In a command prompt, type:</span></span>  
  
     `C:\bin> gacutil /i TIBCO.EMS.dll`  
  
     <span data-ttu-id="c44c2-113">TIBCO。EMS.dll 现在显示 gac。</span><span class="sxs-lookup"><span data-stu-id="c44c2-113">The TIBCO.EMS.dll now shows the GAC.</span></span>  
  
     <span data-ttu-id="c44c2-114">若要查看 GAC 列表中，在控制面板中，打开**管理工具**，打开**Microsoft.NET Framework X.XConfiguration**，然后单击**程序集缓存**。</span><span class="sxs-lookup"><span data-stu-id="c44c2-114">To view the GAC list, in Control Panel, open **Administrative Tools**, open **Microsoft .NET Framework X.XConfiguration**, and then click **Assembly Cache**.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="c44c2-115">限制</span><span class="sxs-lookup"><span data-stu-id="c44c2-115">Limitations</span></span>  
 <span data-ttu-id="c44c2-116">BizTalk 适配器 TIBCO 企业消息服务使用 TIBCO。EMS.dll 与 TIBCO 企业消息服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="c44c2-116">BizTalk Adapter for TIBCO Enterprise Message Service uses TIBCO.EMS.dll to communicate with TIBCO Enterprise Message Service.</span></span> <span data-ttu-id="c44c2-117">当你使用 TIBCO EMS C# API 时，应考虑以下限制：</span><span class="sxs-lookup"><span data-stu-id="c44c2-117">You should consider the following limitations when you use the TIBCO EMS C# API:</span></span>  
  
-   <span data-ttu-id="c44c2-118">使 TIBCO EMS 客户端将消息以压缩形式发送到 EMS 的消息压缩时无法使用 C# API。</span><span class="sxs-lookup"><span data-stu-id="c44c2-118">Message compression, which enables the TIBCO EMS client to send messages in a compressed form to EMS, is not available with the C# API.</span></span>  
  
-   <span data-ttu-id="c44c2-119">加密的适配器和服务器之间的消息时无法使用 C# API。</span><span class="sxs-lookup"><span data-stu-id="c44c2-119">Encryption of messages between the adapter and the server is not available with the C# API.</span></span> <span data-ttu-id="c44c2-120">C# API 不允许使用 OpenSSL 库的 SSL 加密。</span><span class="sxs-lookup"><span data-stu-id="c44c2-120">The C# API does not allow for SSL encryption using the OpenSSL libraries.</span></span>  
  
-   <span data-ttu-id="c44c2-121">C# API 不支持进行 ems 相关的管理 API。</span><span class="sxs-lookup"><span data-stu-id="c44c2-121">The C# API does not support the Administration API for EMS.</span></span>  
  
-   <span data-ttu-id="c44c2-122">无法发送或接收使用 BizTalk TIBCO EMS 适配器大于 50 MB 的大小的消息。</span><span class="sxs-lookup"><span data-stu-id="c44c2-122">Messages greater than 50MB in size cannot be sent or received using the BizTalk TIBCO EMS adapter.</span></span> <span data-ttu-id="c44c2-123">超出此大小，环境遇到 System.OutOfMemoryException 异常。</span><span class="sxs-lookup"><span data-stu-id="c44c2-123">Beyond this size, the environment experiences System.OutOfMemoryException exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44c2-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c44c2-124">See Also</span></span>  
 [<span data-ttu-id="c44c2-125">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="c44c2-125">Planning and Architecture</span></span>](../core/planning-and-architecture16.md)