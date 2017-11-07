---
title: "SAP 适配器示例 |Microsoft 文档"
description: "为 SAP 使用 BizTalk Server、 WCF 服务模型，WCF 通道模型和数据提供程序使用的 mySAP WCF 适配器示例"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4654c458-83be-417f-ae54-5c3a8f6ab81f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d163c573003f40b2049f7e921e5edc4997b4e115
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="samples-for-the-sap-adapter"></a><span data-ttu-id="56017-103">SAP 适配器的示例</span><span class="sxs-lookup"><span data-stu-id="56017-103">Samples for the SAP adapter</span></span>
<span data-ttu-id="56017-104">示例[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]分为：</span><span class="sxs-lookup"><span data-stu-id="56017-104">Samples for [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] are categorized into:</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="56017-105"> 示例</span><span class="sxs-lookup"><span data-stu-id="56017-105"> samples</span></span>  
  
-   <span data-ttu-id="56017-106">WCF 服务模型示例</span><span class="sxs-lookup"><span data-stu-id="56017-106">WCF service model samples</span></span>  
  
-   <span data-ttu-id="56017-107">WCF 通道模型示例</span><span class="sxs-lookup"><span data-stu-id="56017-107">WCF channel model samples</span></span>  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="56017-108"> 示例</span><span class="sxs-lookup"><span data-stu-id="56017-108"> samples</span></span>  

  
 <span data-ttu-id="56017-109">这些示例位于[BizTalk 适配器包 2010年: SAP 适配器示例](https://www.microsoft.com/download/details.aspx?id=1314)。</span><span class="sxs-lookup"><span data-stu-id="56017-109">The samples are available at [BizTalk Adapter Pack 2010: SAP adapter samples](https://www.microsoft.com/download/details.aspx?id=1314).</span></span> 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
 <span data-ttu-id="56017-110">以下列表介绍这些示例。</span><span class="sxs-lookup"><span data-stu-id="56017-110">The following list describes the samples.</span></span>
  
## <a name="biztalk-server-samples"></a><span data-ttu-id="56017-111">BizTalk Server 示例</span><span class="sxs-lookup"><span data-stu-id="56017-111">BizTalk Server samples</span></span>  
  
|<span data-ttu-id="56017-112">示例目录名称</span><span class="sxs-lookup"><span data-stu-id="56017-112">Sample Directory Name</span></span>|<span data-ttu-id="56017-113">Description</span><span class="sxs-lookup"><span data-stu-id="56017-113">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="56017-114">IDOCSend</span><span class="sxs-lookup"><span data-stu-id="56017-114">IDOCSend</span></span>|<span data-ttu-id="56017-115">演示如何将 IDOC 发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="56017-115">Demonstrates how to send an IDOC to an SAP system.</span></span>|  
|<span data-ttu-id="56017-116">ReceiveIDOC</span><span class="sxs-lookup"><span data-stu-id="56017-116">ReceiveIDOC</span></span>|<span data-ttu-id="56017-117">演示如何从某个 SAP 系统接收 IDOC。</span><span class="sxs-lookup"><span data-stu-id="56017-117">Demonstrates how to receive an IDOC from an SAP system.</span></span>|  
|<span data-ttu-id="56017-118">ReceiveIDOC_SYSREL</span><span class="sxs-lookup"><span data-stu-id="56017-118">ReceiveIDOC_SYSREL</span></span>|<span data-ttu-id="56017-119">演示如何从某个 SAP 系统接收 IDOC。</span><span class="sxs-lookup"><span data-stu-id="56017-119">Demonstrates how to receive an IDOC from an SAP system.</span></span> <span data-ttu-id="56017-120">所收到的 IDOC 的版本号小于 SAP SYSREL。</span><span class="sxs-lookup"><span data-stu-id="56017-120">The IDOC being received has the version number less than the SAP SYSREL.</span></span>|  
|<span data-ttu-id="56017-121">RFCServer</span><span class="sxs-lookup"><span data-stu-id="56017-121">RFCServer</span></span>|<span data-ttu-id="56017-122">演示如何从 SAP 系统接收的 RFC 服务器调用。</span><span class="sxs-lookup"><span data-stu-id="56017-122">Demonstrates how to receive an RFC server call from the SAP system.</span></span>|  
|<span data-ttu-id="56017-123">SAPTransaction</span><span class="sxs-lookup"><span data-stu-id="56017-123">SAPTransaction</span></span>|<span data-ttu-id="56017-124">演示如何在 SAP 系统使用中执行事务。</span><span class="sxs-lookup"><span data-stu-id="56017-124">Demonstrates how to perform transactions in an SAP system using.</span></span>|  
|<span data-ttu-id="56017-125">tRFCClient</span><span class="sxs-lookup"><span data-stu-id="56017-125">tRFCClient</span></span>|<span data-ttu-id="56017-126">演示如何在 SAP 系统上进行 tRFC 客户端调用。</span><span class="sxs-lookup"><span data-stu-id="56017-126">Demonstrates how to make tRFC client calls on an SAP system.</span></span>|  
  
## <a name="wcf-service-model-samples"></a><span data-ttu-id="56017-127">WCF 服务模型示例</span><span class="sxs-lookup"><span data-stu-id="56017-127">WCF service model samples</span></span>   
  
|<span data-ttu-id="56017-128">示例目录名称</span><span class="sxs-lookup"><span data-stu-id="56017-128">Sample Directory Name</span></span>|<span data-ttu-id="56017-129">Description</span><span class="sxs-lookup"><span data-stu-id="56017-129">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="56017-130">SapIdocStringClientSM</span><span class="sxs-lookup"><span data-stu-id="56017-130">SapIdocStringClientSM</span></span>|<span data-ttu-id="56017-131">演示如何将 IDOC 发送到 SAP 系统，通过调用 SendIdoc 操作。</span><span class="sxs-lookup"><span data-stu-id="56017-131">Demonstrates how to send an IDOC to an SAP system by invoking the SendIdoc operation.</span></span>|  
|<span data-ttu-id="56017-132">SapRfcServerSM</span><span class="sxs-lookup"><span data-stu-id="56017-132">SapRfcServerSM</span></span>|<span data-ttu-id="56017-133">演示如何从某个 SAP 系统接收的 RFC 服务器调用。</span><span class="sxs-lookup"><span data-stu-id="56017-133">Demonstrates how to receive an RFC server call from an SAP system.</span></span>|  
|<span data-ttu-id="56017-134">SapBapiTxClientSM</span><span class="sxs-lookup"><span data-stu-id="56017-134">SapBapiTxClientSM</span></span>|<span data-ttu-id="56017-135">演示如何在 SAP 系统上事务内调用 BAPIs。</span><span class="sxs-lookup"><span data-stu-id="56017-135">Demonstrates how to invoke BAPIs inside a transaction on an SAP system.</span></span>|  
|<span data-ttu-id="56017-136">SapTrfcClientSM</span><span class="sxs-lookup"><span data-stu-id="56017-136">SapTrfcClientSM</span></span>|<span data-ttu-id="56017-137">演示如何调用 tRFC SAP 系统上的客户端调用。</span><span class="sxs-lookup"><span data-stu-id="56017-137">Demonstrates how to invoke tRFC client calls on an SAP system.</span></span>|  
  
## <a name="wcf-channel-model-samples"></a><span data-ttu-id="56017-138">WCF 通道模型示例</span><span class="sxs-lookup"><span data-stu-id="56017-138">WCF channel model samples</span></span>  
  
|<span data-ttu-id="56017-139">示例目录名称</span><span class="sxs-lookup"><span data-stu-id="56017-139">Sample Directory Name</span></span>|<span data-ttu-id="56017-140">Description</span><span class="sxs-lookup"><span data-stu-id="56017-140">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="56017-141">SapIdocReceiveCM</span><span class="sxs-lookup"><span data-stu-id="56017-141">SapIdocReceiveCM</span></span>|<span data-ttu-id="56017-142">演示如何从某个 SAP 系统接收到的 Idoc</span><span class="sxs-lookup"><span data-stu-id="56017-142">Demonstrates how to receive IDOCs from an SAP system</span></span>|  
|<span data-ttu-id="56017-143">SapRfcServerCM</span><span class="sxs-lookup"><span data-stu-id="56017-143">SapRfcServerCM</span></span>|<span data-ttu-id="56017-144">演示如何从 SAP 系统接收的 RFC 服务器调用。</span><span class="sxs-lookup"><span data-stu-id="56017-144">Demonstrates how to receive an RFC server call from the SAP system.</span></span>|  
  
## <a name="data-provider-for-sap-samples"></a><span data-ttu-id="56017-145">用于 SAP 示例数据提供程序</span><span class="sxs-lookup"><span data-stu-id="56017-145">Data Provider for SAP samples</span></span>  
  
|<span data-ttu-id="56017-146">示例目录名称</span><span class="sxs-lookup"><span data-stu-id="56017-146">Sample Directory Name</span></span>|<span data-ttu-id="56017-147">Description</span><span class="sxs-lookup"><span data-stu-id="56017-147">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="56017-148">sap ado</span><span class="sxs-lookup"><span data-stu-id="56017-148">sap ado</span></span>|<span data-ttu-id="56017-149">演示如何使用[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="56017-149">Demonstrates how to use the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>|  
  
 
## <a name="see-also"></a><span data-ttu-id="56017-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56017-150">See Also</span></span>  
[<span data-ttu-id="56017-151">开发 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="56017-151">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)