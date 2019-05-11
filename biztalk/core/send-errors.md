---
title: 将错误发送 |Microsoft Docs
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
ms.openlocfilehash: 5b469e319c1e93fcdfa7a330fe29a1dcde55a4a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250995"
---
# <a name="send-errors"></a><span data-ttu-id="efa94-102">将错误发送</span><span class="sxs-lookup"><span data-stu-id="efa94-102">Send Errors</span></span>
<span data-ttu-id="efa94-103">诊断和解决 WCF 发送错误的信息。</span><span class="sxs-lookup"><span data-stu-id="efa94-103">Information for diagnosing and resolving WCF Send errors.</span></span>  
  
## <a name="failed-to-generate-odx-file"></a><span data-ttu-id="efa94-104">生成 ODX 文件失败</span><span class="sxs-lookup"><span data-stu-id="efa94-104">Failed to generate ODX file</span></span>

|                 |                                   <span data-ttu-id="efa94-105">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="efa94-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="efa94-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="efa94-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="efa94-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="efa94-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="efa94-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="efa94-108">Event ID</span></span>     |                                         <span data-ttu-id="efa94-109">0</span><span class="sxs-lookup"><span data-stu-id="efa94-109">0</span></span>                                          |
|  <span data-ttu-id="efa94-110">事件源</span><span class="sxs-lookup"><span data-stu-id="efa94-110">Event Source</span></span>   |                                         <span data-ttu-id="efa94-111">0</span><span class="sxs-lookup"><span data-stu-id="efa94-111">0</span></span>                                          |
|    <span data-ttu-id="efa94-112">组件</span><span class="sxs-lookup"><span data-stu-id="efa94-112">Component</span></span>    |                                         <span data-ttu-id="efa94-113">0</span><span class="sxs-lookup"><span data-stu-id="efa94-113">0</span></span>                                          |
|  <span data-ttu-id="efa94-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="efa94-114">Symbolic Name</span></span>  |                                         <span data-ttu-id="efa94-115">0</span><span class="sxs-lookup"><span data-stu-id="efa94-115">0</span></span>                                          |
|  <span data-ttu-id="efa94-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="efa94-116">Message Text</span></span>   |                            <span data-ttu-id="efa94-117">生成 ODX 文件失败</span><span class="sxs-lookup"><span data-stu-id="efa94-117">Failed to generate ODX file</span></span>                             |
  
### <a name="explanation"></a><span data-ttu-id="efa94-118">解释</span><span class="sxs-lookup"><span data-stu-id="efa94-118">Explanation</span></span>  
 <span data-ttu-id="efa94-119">此错误表示在使用该服务时出错。</span><span class="sxs-lookup"><span data-stu-id="efa94-119">This error indicates there was an error in consuming the service.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="efa94-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="efa94-120">User Action</span></span>  
 <span data-ttu-id="efa94-121">（如果你拥有的 WCF 服务） 托管的服务具有有效的 Web 方法和该元数据的检查。</span><span class="sxs-lookup"><span data-stu-id="efa94-121">Check that the service has valid Web Method and that metadata is hosted (if you own the WCF services).</span></span> <span data-ttu-id="efa94-122">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="efa94-122">Otherwise, contact the service provider.</span></span>  
  
 <span data-ttu-id="efa94-123">使用 WCF 服务的其他信息，请参阅[注意事项时使用 WCF 服务与 WCF 发送适配器](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="efa94-123">For additional information on consuming WCF services, see [Considerations When Consuming WCF Services with the WCF Send Adapters](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md).</span></span>
 
## <a name="response-message-body-was-not-read"></a><span data-ttu-id="efa94-124">无法读取响应消息正文</span><span class="sxs-lookup"><span data-stu-id="efa94-124">Response message body was not read</span></span>
  
|                 |                                        <span data-ttu-id="efa94-125">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="efa94-125">Error details</span></span>                                        |
|-----------------|---------------------------------------------------------------------------------------------|
|  <span data-ttu-id="efa94-126">产品名称</span><span class="sxs-lookup"><span data-stu-id="efa94-126">Product Name</span></span>   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]      |
| <span data-ttu-id="efa94-127">产品版本</span><span class="sxs-lookup"><span data-stu-id="efa94-127">Product Version</span></span> |                 [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                  |
|    <span data-ttu-id="efa94-128">事件 ID</span><span class="sxs-lookup"><span data-stu-id="efa94-128">Event ID</span></span>     |                                              <span data-ttu-id="efa94-129">0</span><span class="sxs-lookup"><span data-stu-id="efa94-129">0</span></span>                                              |
|  <span data-ttu-id="efa94-130">事件源</span><span class="sxs-lookup"><span data-stu-id="efa94-130">Event Source</span></span>   |                                              <span data-ttu-id="efa94-131">0</span><span class="sxs-lookup"><span data-stu-id="efa94-131">0</span></span>                                              |
|    <span data-ttu-id="efa94-132">组件</span><span class="sxs-lookup"><span data-stu-id="efa94-132">Component</span></span>    |                                              <span data-ttu-id="efa94-133">0</span><span class="sxs-lookup"><span data-stu-id="efa94-133">0</span></span>                                              |
|  <span data-ttu-id="efa94-134">符号名称</span><span class="sxs-lookup"><span data-stu-id="efa94-134">Symbolic Name</span></span>  |                                              <span data-ttu-id="efa94-135">0</span><span class="sxs-lookup"><span data-stu-id="efa94-135">0</span></span>                                              |
|  <span data-ttu-id="efa94-136">消息正文</span><span class="sxs-lookup"><span data-stu-id="efa94-136">Message Text</span></span>   | <span data-ttu-id="efa94-137">未读取响应消息正文 （这可能表示连接已关闭。）</span><span class="sxs-lookup"><span data-stu-id="efa94-137">The response message body was not read  (This may indicate the connection has been closed.)</span></span> |
  
### <a name="explanation"></a><span data-ttu-id="efa94-138">解释</span><span class="sxs-lookup"><span data-stu-id="efa94-138">Explanation</span></span>  
 <span data-ttu-id="efa94-139">响应消息发回之前，客户端可能会断开连接。</span><span class="sxs-lookup"><span data-stu-id="efa94-139">The client may be disconnected before the response message is sent back.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="efa94-140">用户操作</span><span class="sxs-lookup"><span data-stu-id="efa94-140">User Action</span></span>  
 <span data-ttu-id="efa94-141">检查客户端连接。</span><span class="sxs-lookup"><span data-stu-id="efa94-141">Check the client connectivity.</span></span> <span data-ttu-id="efa94-142">所执行的步骤和操作的范围将取决于端口类型。</span><span class="sxs-lookup"><span data-stu-id="efa94-142">The steps taken, and the extent of the action, will depend on the port type.</span></span>   
<span data-ttu-id="efa94-143">有关详细信息，请参阅[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="efa94-143">For further information, see [Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md).</span></span>