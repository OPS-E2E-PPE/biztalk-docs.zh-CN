---
title: 将错误发送 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3cf61c82-ad48-4555-af53-fb841fd0f503
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67741af0520d990be9a552685c8319aa6a5ae881
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269813"
---
# <a name="send-errors"></a><span data-ttu-id="18d8a-102">发送错误</span><span class="sxs-lookup"><span data-stu-id="18d8a-102">Send Errors</span></span>
<span data-ttu-id="18d8a-103">用于诊断和解决 WCF 发送错误的信息。</span><span class="sxs-lookup"><span data-stu-id="18d8a-103">Information for diagnosing and resolving WCF Send errors.</span></span>  
  
## <a name="failed-to-generate-odx-file"></a><span data-ttu-id="18d8a-104">生成 ODX 文件失败</span><span class="sxs-lookup"><span data-stu-id="18d8a-104">Failed to generate ODX file</span></span>

||<span data-ttu-id="18d8a-105">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="18d8a-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="18d8a-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="18d8a-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="18d8a-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="18d8a-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="18d8a-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="18d8a-108">Event ID</span></span>|<span data-ttu-id="18d8a-109">0</span><span class="sxs-lookup"><span data-stu-id="18d8a-109">0</span></span>|  
|<span data-ttu-id="18d8a-110">事件源</span><span class="sxs-lookup"><span data-stu-id="18d8a-110">Event Source</span></span>|<span data-ttu-id="18d8a-111">0</span><span class="sxs-lookup"><span data-stu-id="18d8a-111">0</span></span>|  
|<span data-ttu-id="18d8a-112">组件</span><span class="sxs-lookup"><span data-stu-id="18d8a-112">Component</span></span>|<span data-ttu-id="18d8a-113">0</span><span class="sxs-lookup"><span data-stu-id="18d8a-113">0</span></span>|  
|<span data-ttu-id="18d8a-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="18d8a-114">Symbolic Name</span></span>|<span data-ttu-id="18d8a-115">0</span><span class="sxs-lookup"><span data-stu-id="18d8a-115">0</span></span>|  
|<span data-ttu-id="18d8a-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="18d8a-116">Message Text</span></span>|<span data-ttu-id="18d8a-117">生成 ODX 文件失败</span><span class="sxs-lookup"><span data-stu-id="18d8a-117">Failed to generate ODX file</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="18d8a-118">解释</span><span class="sxs-lookup"><span data-stu-id="18d8a-118">Explanation</span></span>  
 <span data-ttu-id="18d8a-119">此错误指示在使用服务时出错。</span><span class="sxs-lookup"><span data-stu-id="18d8a-119">This error indicates there was an error in consuming the service.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="18d8a-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="18d8a-120">User Action</span></span>  
 <span data-ttu-id="18d8a-121">检查服务具有有效的 Web 方法，以及 （如果你拥有的 WCF 服务） 承载该元数据。</span><span class="sxs-lookup"><span data-stu-id="18d8a-121">Check that the service has valid Web Method and that metadata is hosted (if you own the WCF services).</span></span> <span data-ttu-id="18d8a-122">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="18d8a-122">Otherwise, contact the service provider.</span></span>  
  
 <span data-ttu-id="18d8a-123">有关使用 WCF 服务的其他信息，请参阅[注意事项时使用 WCF 服务与 WCF 发送适配器](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="18d8a-123">For additional information on consuming WCF services, see [Considerations When Consuming WCF Services with the WCF Send Adapters](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md).</span></span>
 
## <a name="response-message-body-was-not-read"></a><span data-ttu-id="18d8a-124">无法读取响应消息正文</span><span class="sxs-lookup"><span data-stu-id="18d8a-124">Response message body was not read</span></span>
  
||<span data-ttu-id="18d8a-125">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="18d8a-125">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="18d8a-126">产品名称</span><span class="sxs-lookup"><span data-stu-id="18d8a-126">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="18d8a-127">产品版本</span><span class="sxs-lookup"><span data-stu-id="18d8a-127">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="18d8a-128">事件 ID</span><span class="sxs-lookup"><span data-stu-id="18d8a-128">Event ID</span></span>|<span data-ttu-id="18d8a-129">0</span><span class="sxs-lookup"><span data-stu-id="18d8a-129">0</span></span>|  
|<span data-ttu-id="18d8a-130">事件源</span><span class="sxs-lookup"><span data-stu-id="18d8a-130">Event Source</span></span>|<span data-ttu-id="18d8a-131">0</span><span class="sxs-lookup"><span data-stu-id="18d8a-131">0</span></span>|  
|<span data-ttu-id="18d8a-132">组件</span><span class="sxs-lookup"><span data-stu-id="18d8a-132">Component</span></span>|<span data-ttu-id="18d8a-133">0</span><span class="sxs-lookup"><span data-stu-id="18d8a-133">0</span></span>|  
|<span data-ttu-id="18d8a-134">符号名称</span><span class="sxs-lookup"><span data-stu-id="18d8a-134">Symbolic Name</span></span>|<span data-ttu-id="18d8a-135">0</span><span class="sxs-lookup"><span data-stu-id="18d8a-135">0</span></span>|  
|<span data-ttu-id="18d8a-136">消息正文</span><span class="sxs-lookup"><span data-stu-id="18d8a-136">Message Text</span></span>|<span data-ttu-id="18d8a-137">未读取响应消息正文（这可能表示连接已关闭）。</span><span class="sxs-lookup"><span data-stu-id="18d8a-137">The response message body was not read  (This may indicate the connection has been closed.)</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="18d8a-138">解释</span><span class="sxs-lookup"><span data-stu-id="18d8a-138">Explanation</span></span>  
 <span data-ttu-id="18d8a-139">发回响应消息之前，客户端可能已断开连接。</span><span class="sxs-lookup"><span data-stu-id="18d8a-139">The client may be disconnected before the response message is sent back.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="18d8a-140">用户操作</span><span class="sxs-lookup"><span data-stu-id="18d8a-140">User Action</span></span>  
 <span data-ttu-id="18d8a-141">检查客户端连接。</span><span class="sxs-lookup"><span data-stu-id="18d8a-141">Check the client connectivity.</span></span> <span data-ttu-id="18d8a-142">所采取的步骤和操作的范围取决于端口类型。</span><span class="sxs-lookup"><span data-stu-id="18d8a-142">The steps taken, and the extent of the action, will depend on the port type.</span></span>   
<span data-ttu-id="18d8a-143">有关详细信息，请参阅[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="18d8a-143">For further information, see [Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md).</span></span>