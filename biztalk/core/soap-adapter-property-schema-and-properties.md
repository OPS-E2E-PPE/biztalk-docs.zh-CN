---
title: SOAP 适配器属性架构和属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ProxyUsername property [SOAP adapters]
- ClientConnectionTimeout property [SOAP adapters]
- SOAP adapters, properties
- ProxyAddress property [SOAP adapters]
- UserDefined property [SOAP adapters]
- AssemblyName property [SOAP adapters]
- ClientCertificate property [SOAP adapters]
- AffiliateApplicationName property [SOAP adapters]
- schemas, SOAP adapters
- AuthenticationScheme property [SOAP adapters]
- UserName property, SOAP adapters
- UseProxy property [SOAP adapters]
- Password property [SOAP adapters]
- configuring [SOAP adapters], schemas
- UnknownHeaders property [SOAP adapters]
- configuring [SOAP adapters], properties
- UseSoap12 property [SOAP adapters]
- UseHandlerSetting property [SOAP adapters]
- SOAP adapters, schemas
- ProxyPassword property [SOAP adapters]
- UseSSO property [SOAP adapters]
- MethodName property [SOAP adapters]
- ProxyPort property [SOAP adapters]
ms.assetid: b471cf4b-2d87-4aa2-ae4a-f48517fd4c94
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 681a7f529d1326b3301a5cc09dc31e94c8bfbb96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314055"
---
# <a name="soap-adapter-property-schema-and-properties"></a><span data-ttu-id="82135-102">SOAP 适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="82135-102">SOAP Adapter Property Schema and Properties</span></span>
<span data-ttu-id="82135-103">下表列出了 SOAP 适配器属性架构中的属性。</span><span class="sxs-lookup"><span data-stu-id="82135-103">The following table lists the properties in the SOAP adapter property schema.</span></span>  
  
 <span data-ttu-id="82135-104">**Namespace**： http://schemas.microsoft.com/BizTalk/2003/soap-properties</span><span class="sxs-lookup"><span data-stu-id="82135-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/soap-properties</span></span>  
  
|<span data-ttu-id="82135-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="82135-105">Name</span></span>|<span data-ttu-id="82135-106">类型</span><span class="sxs-lookup"><span data-stu-id="82135-106">Type</span></span>|<span data-ttu-id="82135-107">Description</span><span class="sxs-lookup"><span data-stu-id="82135-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="82135-108">**AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="82135-108">**AssemblyName**</span></span>|<span data-ttu-id="82135-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="82135-109">xs:string</span></span>|<span data-ttu-id="82135-110">标识的.NET 类型和程序集加载和执行。</span><span class="sxs-lookup"><span data-stu-id="82135-110">Identifies the .NET type and assembly to be loaded and executed.</span></span>|  
|<span data-ttu-id="82135-111">**MethodName**</span><span class="sxs-lookup"><span data-stu-id="82135-111">**MethodName**</span></span>|<span data-ttu-id="82135-112">xs:string</span><span class="sxs-lookup"><span data-stu-id="82135-112">xs:string</span></span>|<span data-ttu-id="82135-113">标识要调用的.NET 程序集的目标方法。</span><span class="sxs-lookup"><span data-stu-id="82135-113">Identifies the target method on the .NET assembly that is to be invoked.</span></span>|  
|<span data-ttu-id="82135-114">**用户名**</span><span class="sxs-lookup"><span data-stu-id="82135-114">**Username**</span></span>|<span data-ttu-id="82135-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="82135-115">xs:string</span></span>|<span data-ttu-id="82135-116">要用于服务器的身份验证的用户名称。</span><span class="sxs-lookup"><span data-stu-id="82135-116">User name to use for authentication with the server.</span></span>|  
|<span data-ttu-id="82135-117">**密码**</span><span class="sxs-lookup"><span data-stu-id="82135-117">**Password**</span></span>|<span data-ttu-id="82135-118">xs:string</span><span class="sxs-lookup"><span data-stu-id="82135-118">xs:string</span></span>|<span data-ttu-id="82135-119">要用于服务器的身份验证的用户密码。</span><span class="sxs-lookup"><span data-stu-id="82135-119">User password to use for authentication with the server.</span></span>|  
|<span data-ttu-id="82135-120">**ClientCertificate**</span><span class="sxs-lookup"><span data-stu-id="82135-120">**ClientCertificate**</span></span>|<span data-ttu-id="82135-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="82135-121">xs:string</span></span>|<span data-ttu-id="82135-122">客户端 SSL 证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="82135-122">Thumbprint of the client SSL certificate.</span></span>|  
|<span data-ttu-id="82135-123">**UseProxy**</span><span class="sxs-lookup"><span data-stu-id="82135-123">**UseProxy**</span></span>|<span data-ttu-id="82135-124">xs:Boolean</span><span class="sxs-lookup"><span data-stu-id="82135-124">xs:Boolean</span></span>|<span data-ttu-id="82135-125">指定 SOAP 适配器是否使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="82135-125">Specifies whether the SOAP adapter uses a proxy server.</span></span>|  
|<span data-ttu-id="82135-126">**ProxyAddress**</span><span class="sxs-lookup"><span data-stu-id="82135-126">**ProxyAddress**</span></span>|<span data-ttu-id="82135-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="82135-127">xs:string</span></span>|<span data-ttu-id="82135-128">指定代理服务器地址。</span><span class="sxs-lookup"><span data-stu-id="82135-128">Specifies the proxy server address.</span></span>|  
|<span data-ttu-id="82135-129">**ProxyPort**</span><span class="sxs-lookup"><span data-stu-id="82135-129">**ProxyPort**</span></span>|<span data-ttu-id="82135-130">xs:int</span><span class="sxs-lookup"><span data-stu-id="82135-130">xs:int</span></span>|<span data-ttu-id="82135-131">指定代理服务器端口。</span><span class="sxs-lookup"><span data-stu-id="82135-131">Specifies the proxy server port.</span></span>|  
|<span data-ttu-id="82135-132">**ProxyUsername**</span><span class="sxs-lookup"><span data-stu-id="82135-132">**ProxyUsername**</span></span>|<span data-ttu-id="82135-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="82135-133">xs:string</span></span>|<span data-ttu-id="82135-134">指定与代理服务器进行身份验证的用户名。</span><span class="sxs-lookup"><span data-stu-id="82135-134">Specifies the user name for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="82135-135">**ProxyPassword**</span><span class="sxs-lookup"><span data-stu-id="82135-135">**ProxyPassword**</span></span>|<span data-ttu-id="82135-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="82135-136">xs:string</span></span>|<span data-ttu-id="82135-137">指定与代理服务器进行身份验证的用户密码。</span><span class="sxs-lookup"><span data-stu-id="82135-137">Specifies the user password for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="82135-138">**UnknownHeaders**</span><span class="sxs-lookup"><span data-stu-id="82135-138">**UnknownHeaders**</span></span>|<span data-ttu-id="82135-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="82135-139">xs:string</span></span>|<span data-ttu-id="82135-140">指定未知 SOAP 标头的序列化的列表。</span><span class="sxs-lookup"><span data-stu-id="82135-140">Specifies the serialized list of unknown SOAP headers.</span></span>|  
|<span data-ttu-id="82135-141">**AffiliateApplicationName**</span><span class="sxs-lookup"><span data-stu-id="82135-141">**AffiliateApplicationName**</span></span>|<span data-ttu-id="82135-142">xs:string</span><span class="sxs-lookup"><span data-stu-id="82135-142">xs:string</span></span>|<span data-ttu-id="82135-143">定义要使用的 SSO 关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="82135-143">Defines the name of the affiliate application to use for SSO.</span></span>|  
|<span data-ttu-id="82135-144">**AuthenticationScheme**</span><span class="sxs-lookup"><span data-stu-id="82135-144">**AuthenticationScheme**</span></span>|<span data-ttu-id="82135-145">xs:string</span><span class="sxs-lookup"><span data-stu-id="82135-145">xs:string</span></span>|<span data-ttu-id="82135-146">指定要对目标服务器使用身份验证的类型。</span><span class="sxs-lookup"><span data-stu-id="82135-146">Specifies the type of authentication to use with the destination server.</span></span>|  
|<span data-ttu-id="82135-147">**UseSSO**</span><span class="sxs-lookup"><span data-stu-id="82135-147">**UseSSO**</span></span>|<span data-ttu-id="82135-148">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="82135-148">xs:boolean</span></span>|<span data-ttu-id="82135-149">指定 SOAP 适配器是否为发送端口使用 SSO。</span><span class="sxs-lookup"><span data-stu-id="82135-149">Specifies whether the SOAP adapter uses SSO for the send port.</span></span>|  
|<span data-ttu-id="82135-150">**UseHandlerSetting**</span><span class="sxs-lookup"><span data-stu-id="82135-150">**UseHandlerSetting**</span></span>|<span data-ttu-id="82135-151">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="82135-151">xs:boolean</span></span>|<span data-ttu-id="82135-152">指定 SOAP 发送端口是否使用处理程序的代理配置。</span><span class="sxs-lookup"><span data-stu-id="82135-152">Specifies whether the SOAP send port uses the proxy configuration for the handler.</span></span>|  
|<span data-ttu-id="82135-153">**ClientConnectionTimeout**</span><span class="sxs-lookup"><span data-stu-id="82135-153">**ClientConnectionTimeout**</span></span>|<span data-ttu-id="82135-154">xs:int</span><span class="sxs-lookup"><span data-stu-id="82135-154">xs:int</span></span>|<span data-ttu-id="82135-155">指定等待来自服务器的响应的超时时间。</span><span class="sxs-lookup"><span data-stu-id="82135-155">Specifies the time-out period of waiting for a response from the server.</span></span> <span data-ttu-id="82135-156">如果设置为零 (0)，系统将计算基于请求消息的大小的超时值。</span><span class="sxs-lookup"><span data-stu-id="82135-156">If set to zero (0), the system will calculate the time-out based on the request message size.</span></span>|  
|<span data-ttu-id="82135-157">**UserDefined**</span><span class="sxs-lookup"><span data-stu-id="82135-157">**UserDefined**</span></span>|<span data-ttu-id="82135-158">xs:string</span><span class="sxs-lookup"><span data-stu-id="82135-158">xs:string</span></span>|<span data-ttu-id="82135-159">定义用户定义的类。</span><span class="sxs-lookup"><span data-stu-id="82135-159">Defines user-defined classes.</span></span>|  
|<span data-ttu-id="82135-160">**UseSoap12**</span><span class="sxs-lookup"><span data-stu-id="82135-160">**UseSoap12**</span></span>|<span data-ttu-id="82135-161">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="82135-161">xs:boolean</span></span>|<span data-ttu-id="82135-162">指定是否生成支持 SOAP 1.2 协议的代理代码。</span><span class="sxs-lookup"><span data-stu-id="82135-162">Specifies whether to generate proxy code that supports the SOAP 1.2 protocol.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82135-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="82135-163">See Also</span></span>  
 [<span data-ttu-id="82135-164">配置 SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="82135-164">Configuring the SOAP Adapter</span></span>](../core/configuring-the-soap-adapter.md)