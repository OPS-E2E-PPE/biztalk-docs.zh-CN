---
title: 元数据错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccb60c91-5905-4852-813b-586b82de4825
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7699aa162044e13b5f3176e38cf858a5268e25f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324953"
---
# <a name="metadata-errors"></a><span data-ttu-id="b06c0-102">元数据错误</span><span class="sxs-lookup"><span data-stu-id="b06c0-102">Metadata Errors</span></span>
<span data-ttu-id="b06c0-103">诊断和解决 WCF 元数据错误的信息。</span><span class="sxs-lookup"><span data-stu-id="b06c0-103">Information for diagnosing and resolving WCF Metadata errors.</span></span>  
  
## <a name="error-consuming-wcf-service-metadata"></a><span data-ttu-id="b06c0-104">使用 WCF 服务元数据时出错</span><span class="sxs-lookup"><span data-stu-id="b06c0-104">Error consuming WCF service metadata</span></span>

|                 |                                   <span data-ttu-id="b06c0-105">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="b06c0-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="b06c0-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="b06c0-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="b06c0-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="b06c0-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="b06c0-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b06c0-108">Event ID</span></span>     |                                         <span data-ttu-id="b06c0-109">0</span><span class="sxs-lookup"><span data-stu-id="b06c0-109">0</span></span>                                          |
|  <span data-ttu-id="b06c0-110">事件源</span><span class="sxs-lookup"><span data-stu-id="b06c0-110">Event Source</span></span>   |                                         <span data-ttu-id="b06c0-111">0</span><span class="sxs-lookup"><span data-stu-id="b06c0-111">0</span></span>                                          |
|    <span data-ttu-id="b06c0-112">组件</span><span class="sxs-lookup"><span data-stu-id="b06c0-112">Component</span></span>    |                                         <span data-ttu-id="b06c0-113">0</span><span class="sxs-lookup"><span data-stu-id="b06c0-113">0</span></span>                                          |
|  <span data-ttu-id="b06c0-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="b06c0-114">Symbolic Name</span></span>  |                                         <span data-ttu-id="b06c0-115">0</span><span class="sxs-lookup"><span data-stu-id="b06c0-115">0</span></span>                                          |
|  <span data-ttu-id="b06c0-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="b06c0-116">Message Text</span></span>   |                        <span data-ttu-id="b06c0-117">使用 WCF 服务元数据时出错</span><span class="sxs-lookup"><span data-stu-id="b06c0-117">Error consuming WCF service metadata</span></span>                        |
  
### <a name="explanation"></a><span data-ttu-id="b06c0-118">解释</span><span class="sxs-lookup"><span data-stu-id="b06c0-118">Explanation</span></span>  
 <span data-ttu-id="b06c0-119">此错误表示元数据存储服务未提供或无效。</span><span class="sxs-lookup"><span data-stu-id="b06c0-119">This error indicates the metadata for the service is either not available or is not valid.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="b06c0-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="b06c0-120">User Action</span></span>  
 <span data-ttu-id="b06c0-121">更正服务元数据，然后尝试使用 （如果您拥有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="b06c0-121">Correct the service metadata and try to consume (if you own the WCF service you are trying to consume).</span></span> <span data-ttu-id="b06c0-122">转到服务配置编辑器 (**svcConfigEditor.exe**) 并对配置文件进行更改。</span><span class="sxs-lookup"><span data-stu-id="b06c0-122">Go to the Service Configuration Editor (**svcConfigEditor.exe**) and make changes to the configuration file.</span></span>  <span data-ttu-id="b06c0-123">否则，请联系服务提供程序</span><span class="sxs-lookup"><span data-stu-id="b06c0-123">Otherwise, contact the service provider</span></span>

## <a name="failed-to-get-metadata"></a><span data-ttu-id="b06c0-124">无法获取元数据</span><span class="sxs-lookup"><span data-stu-id="b06c0-124">Failed to get metadata</span></span>

|                 |                                   <span data-ttu-id="b06c0-125">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="b06c0-125">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="b06c0-126">产品名称</span><span class="sxs-lookup"><span data-stu-id="b06c0-126">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="b06c0-127">产品版本</span><span class="sxs-lookup"><span data-stu-id="b06c0-127">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="b06c0-128">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b06c0-128">Event ID</span></span>     |                                         <span data-ttu-id="b06c0-129">0</span><span class="sxs-lookup"><span data-stu-id="b06c0-129">0</span></span>                                          |
|  <span data-ttu-id="b06c0-130">事件源</span><span class="sxs-lookup"><span data-stu-id="b06c0-130">Event Source</span></span>   |                                         <span data-ttu-id="b06c0-131">0</span><span class="sxs-lookup"><span data-stu-id="b06c0-131">0</span></span>                                          |
|    <span data-ttu-id="b06c0-132">组件</span><span class="sxs-lookup"><span data-stu-id="b06c0-132">Component</span></span>    |                                         <span data-ttu-id="b06c0-133">0</span><span class="sxs-lookup"><span data-stu-id="b06c0-133">0</span></span>                                          |
|  <span data-ttu-id="b06c0-134">符号名称</span><span class="sxs-lookup"><span data-stu-id="b06c0-134">Symbolic Name</span></span>  |                                         <span data-ttu-id="b06c0-135">0</span><span class="sxs-lookup"><span data-stu-id="b06c0-135">0</span></span>                                          |
|  <span data-ttu-id="b06c0-136">消息正文</span><span class="sxs-lookup"><span data-stu-id="b06c0-136">Message Text</span></span>   |                          <span data-ttu-id="b06c0-137">未能获取从元数据"{0}</span><span class="sxs-lookup"><span data-stu-id="b06c0-137">Failed to get metadata from "{0}</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="b06c0-138">解释</span><span class="sxs-lookup"><span data-stu-id="b06c0-138">Explanation</span></span>  
 <span data-ttu-id="b06c0-139">此错误表明该服务的元数据不可用。</span><span class="sxs-lookup"><span data-stu-id="b06c0-139">This error indicates the metadata is not available for that service.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b06c0-140">用户操作</span><span class="sxs-lookup"><span data-stu-id="b06c0-140">User Action</span></span>  
 <span data-ttu-id="b06c0-141">启用服务的元数据并再次运行使用向导（如果您具有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="b06c0-141">Enable metadata for the service and run the consuming wizard again (if you own the WCF service you are trying to consume).</span></span> <span data-ttu-id="b06c0-142">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="b06c0-142">Otherwise, contact the service provider.</span></span>