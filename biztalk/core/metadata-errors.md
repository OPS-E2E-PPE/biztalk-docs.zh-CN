---
title: 元数据错误 |Microsoft 文档
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
ms.openlocfilehash: 4dce5fc9eb944eccbeed57073c2546f81825ec6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262941"
---
# <a name="metadata-errors"></a><span data-ttu-id="5d40d-102">元数据错误</span><span class="sxs-lookup"><span data-stu-id="5d40d-102">Metadata Errors</span></span>
<span data-ttu-id="5d40d-103">用于诊断和解决 WCF 元数据错误的信息。</span><span class="sxs-lookup"><span data-stu-id="5d40d-103">Information for diagnosing and resolving WCF Metadata errors.</span></span>  
  
## <a name="error-consuming-wcf-service-metadata"></a><span data-ttu-id="5d40d-104">使用 WCF 服务元数据时出错</span><span class="sxs-lookup"><span data-stu-id="5d40d-104">Error consuming WCF service metadata</span></span>

||<span data-ttu-id="5d40d-105">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="5d40d-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="5d40d-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="5d40d-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5d40d-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="5d40d-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="5d40d-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5d40d-108">Event ID</span></span>|<span data-ttu-id="5d40d-109">0</span><span class="sxs-lookup"><span data-stu-id="5d40d-109">0</span></span>|  
|<span data-ttu-id="5d40d-110">事件源</span><span class="sxs-lookup"><span data-stu-id="5d40d-110">Event Source</span></span>|<span data-ttu-id="5d40d-111">0</span><span class="sxs-lookup"><span data-stu-id="5d40d-111">0</span></span>|  
|<span data-ttu-id="5d40d-112">组件</span><span class="sxs-lookup"><span data-stu-id="5d40d-112">Component</span></span>|<span data-ttu-id="5d40d-113">0</span><span class="sxs-lookup"><span data-stu-id="5d40d-113">0</span></span>|  
|<span data-ttu-id="5d40d-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="5d40d-114">Symbolic Name</span></span>|<span data-ttu-id="5d40d-115">0</span><span class="sxs-lookup"><span data-stu-id="5d40d-115">0</span></span>|  
|<span data-ttu-id="5d40d-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="5d40d-116">Message Text</span></span>|<span data-ttu-id="5d40d-117">使用 WCF 服务元数据时出错</span><span class="sxs-lookup"><span data-stu-id="5d40d-117">Error consuming WCF service metadata</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="5d40d-118">解释</span><span class="sxs-lookup"><span data-stu-id="5d40d-118">Explanation</span></span>  
 <span data-ttu-id="5d40d-119">此错误表示元数据，有关该服务不提供或无效。</span><span class="sxs-lookup"><span data-stu-id="5d40d-119">This error indicates the metadata for the service is either not available or is not valid.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="5d40d-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="5d40d-120">User Action</span></span>  
 <span data-ttu-id="5d40d-121">如果您拥有要尝试使用的 WCF 服务，则更正服务元数据，然后尝试使用该服务。</span><span class="sxs-lookup"><span data-stu-id="5d40d-121">Correct the service metadata and try to consume (if you own the WCF service you are trying to consume).</span></span> <span data-ttu-id="5d40d-122">转到服务配置编辑器 (**svcConfigEditor.exe**) 以及对配置文件进行更改。</span><span class="sxs-lookup"><span data-stu-id="5d40d-122">Go to the Service Configuration Editor (**svcConfigEditor.exe**) and make changes to the configuration file.</span></span>  <span data-ttu-id="5d40d-123">否则，请联系服务提供商</span><span class="sxs-lookup"><span data-stu-id="5d40d-123">Otherwise, contact the service provider</span></span>

## <a name="failed-to-get-metadata"></a><span data-ttu-id="5d40d-124">无法获取元数据</span><span class="sxs-lookup"><span data-stu-id="5d40d-124">Failed to get metadata</span></span>

||<span data-ttu-id="5d40d-125">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="5d40d-125">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="5d40d-126">产品名称</span><span class="sxs-lookup"><span data-stu-id="5d40d-126">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5d40d-127">产品版本</span><span class="sxs-lookup"><span data-stu-id="5d40d-127">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="5d40d-128">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5d40d-128">Event ID</span></span>|<span data-ttu-id="5d40d-129">0</span><span class="sxs-lookup"><span data-stu-id="5d40d-129">0</span></span>|  
|<span data-ttu-id="5d40d-130">事件源</span><span class="sxs-lookup"><span data-stu-id="5d40d-130">Event Source</span></span>|<span data-ttu-id="5d40d-131">0</span><span class="sxs-lookup"><span data-stu-id="5d40d-131">0</span></span>|  
|<span data-ttu-id="5d40d-132">组件</span><span class="sxs-lookup"><span data-stu-id="5d40d-132">Component</span></span>|<span data-ttu-id="5d40d-133">0</span><span class="sxs-lookup"><span data-stu-id="5d40d-133">0</span></span>|  
|<span data-ttu-id="5d40d-134">符号名称</span><span class="sxs-lookup"><span data-stu-id="5d40d-134">Symbolic Name</span></span>|<span data-ttu-id="5d40d-135">0</span><span class="sxs-lookup"><span data-stu-id="5d40d-135">0</span></span>|  
|<span data-ttu-id="5d40d-136">消息正文</span><span class="sxs-lookup"><span data-stu-id="5d40d-136">Message Text</span></span>|<span data-ttu-id="5d40d-137">无法从“{0}”获取元数据</span><span class="sxs-lookup"><span data-stu-id="5d40d-137">Failed to get metadata from "{0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5d40d-138">解释</span><span class="sxs-lookup"><span data-stu-id="5d40d-138">Explanation</span></span>  
 <span data-ttu-id="5d40d-139">此错误表明该服务的元数据不可用。</span><span class="sxs-lookup"><span data-stu-id="5d40d-139">This error indicates the metadata is not available for that service.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5d40d-140">用户操作</span><span class="sxs-lookup"><span data-stu-id="5d40d-140">User Action</span></span>  
 <span data-ttu-id="5d40d-141">启用服务的元数据并再次运行使用向导（如果您具有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="5d40d-141">Enable metadata for the service and run the consuming wizard again (if you own the WCF service you are trying to consume).</span></span> <span data-ttu-id="5d40d-142">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="5d40d-142">Otherwise, contact the service provider.</span></span>