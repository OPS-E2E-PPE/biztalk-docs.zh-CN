---
title: SOAP 适配器属性架构和属性 |Microsoft 文档
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
ms.openlocfilehash: 7a24a9ccfc3a07abe925761fe2d6886646981be9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277509"
---
# <a name="soap-adapter-property-schema-and-properties"></a><span data-ttu-id="7c779-102">SOAP 适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="7c779-102">SOAP Adapter Property Schema and Properties</span></span>
<span data-ttu-id="7c779-103">下表列出了 SOAP 适配器属性架构中的属性：</span><span class="sxs-lookup"><span data-stu-id="7c779-103">The following table lists the properties in the SOAP adapter property schema.</span></span>  
  
 <span data-ttu-id="7c779-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/soap-properties</span><span class="sxs-lookup"><span data-stu-id="7c779-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/soap-properties</span></span>  
  
|<span data-ttu-id="7c779-105">Name</span><span class="sxs-lookup"><span data-stu-id="7c779-105">Name</span></span>|<span data-ttu-id="7c779-106">类型</span><span class="sxs-lookup"><span data-stu-id="7c779-106">Type</span></span>|<span data-ttu-id="7c779-107">Description</span><span class="sxs-lookup"><span data-stu-id="7c779-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="7c779-108">**程序集名称**</span><span class="sxs-lookup"><span data-stu-id="7c779-108">**AssemblyName**</span></span>|<span data-ttu-id="7c779-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c779-109">xs:string</span></span>|<span data-ttu-id="7c779-110">标识要加载和执行的 .NET 类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="7c779-110">Identifies the .NET type and assembly to be loaded and executed.</span></span>|  
|<span data-ttu-id="7c779-111">**MethodName**</span><span class="sxs-lookup"><span data-stu-id="7c779-111">**MethodName**</span></span>|<span data-ttu-id="7c779-112">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c779-112">xs:string</span></span>|<span data-ttu-id="7c779-113">标识 .NET 程序集中要调用的目标方法。</span><span class="sxs-lookup"><span data-stu-id="7c779-113">Identifies the target method on the .NET assembly that is to be invoked.</span></span>|  
|<span data-ttu-id="7c779-114">**用户名**</span><span class="sxs-lookup"><span data-stu-id="7c779-114">**Username**</span></span>|<span data-ttu-id="7c779-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c779-115">xs:string</span></span>|<span data-ttu-id="7c779-116">要使用服务器的身份验证的用户名称。</span><span class="sxs-lookup"><span data-stu-id="7c779-116">User name to use for authentication with the server.</span></span>|  
|<span data-ttu-id="7c779-117">**密码**</span><span class="sxs-lookup"><span data-stu-id="7c779-117">**Password**</span></span>|<span data-ttu-id="7c779-118">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c779-118">xs:string</span></span>|<span data-ttu-id="7c779-119">要用于服务器的身份验证的用户密码。</span><span class="sxs-lookup"><span data-stu-id="7c779-119">User password to use for authentication with the server.</span></span>|  
|<span data-ttu-id="7c779-120">**ClientCertificate**</span><span class="sxs-lookup"><span data-stu-id="7c779-120">**ClientCertificate**</span></span>|<span data-ttu-id="7c779-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c779-121">xs:string</span></span>|<span data-ttu-id="7c779-122">客户端 SSL 证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="7c779-122">Thumbprint of the client SSL certificate.</span></span>|  
|<span data-ttu-id="7c779-123">**UseProxy**</span><span class="sxs-lookup"><span data-stu-id="7c779-123">**UseProxy**</span></span>|<span data-ttu-id="7c779-124">xs:Boolean</span><span class="sxs-lookup"><span data-stu-id="7c779-124">xs:Boolean</span></span>|<span data-ttu-id="7c779-125">指定 SOAP 适配器是否使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="7c779-125">Specifies whether the SOAP adapter uses a proxy server.</span></span>|  
|<span data-ttu-id="7c779-126">**ProxyAddress**</span><span class="sxs-lookup"><span data-stu-id="7c779-126">**ProxyAddress**</span></span>|<span data-ttu-id="7c779-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c779-127">xs:string</span></span>|<span data-ttu-id="7c779-128">指定代理服务器地址。</span><span class="sxs-lookup"><span data-stu-id="7c779-128">Specifies the proxy server address.</span></span>|  
|<span data-ttu-id="7c779-129">**友好**</span><span class="sxs-lookup"><span data-stu-id="7c779-129">**ProxyPort**</span></span>|<span data-ttu-id="7c779-130">xs:int</span><span class="sxs-lookup"><span data-stu-id="7c779-130">xs:int</span></span>|<span data-ttu-id="7c779-131">指定代理服务器端口。</span><span class="sxs-lookup"><span data-stu-id="7c779-131">Specifies the proxy server port.</span></span>|  
|<span data-ttu-id="7c779-132">**ProxyUsername**</span><span class="sxs-lookup"><span data-stu-id="7c779-132">**ProxyUsername**</span></span>|<span data-ttu-id="7c779-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c779-133">xs:string</span></span>|<span data-ttu-id="7c779-134">指定与代理服务器的身份验证的用户名。</span><span class="sxs-lookup"><span data-stu-id="7c779-134">Specifies the user name for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="7c779-135">**代理**</span><span class="sxs-lookup"><span data-stu-id="7c779-135">**ProxyPassword**</span></span>|<span data-ttu-id="7c779-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c779-136">xs:string</span></span>|<span data-ttu-id="7c779-137">指定与代理服务器的身份验证的用户密码。</span><span class="sxs-lookup"><span data-stu-id="7c779-137">Specifies the user password for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="7c779-138">**UnknownHeaders**</span><span class="sxs-lookup"><span data-stu-id="7c779-138">**UnknownHeaders**</span></span>|<span data-ttu-id="7c779-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c779-139">xs:string</span></span>|<span data-ttu-id="7c779-140">指定未知 SOAP 标头的序列化列表。</span><span class="sxs-lookup"><span data-stu-id="7c779-140">Specifies the serialized list of unknown SOAP headers.</span></span>|  
|<span data-ttu-id="7c779-141">**AffiliateApplicationName**</span><span class="sxs-lookup"><span data-stu-id="7c779-141">**AffiliateApplicationName**</span></span>|<span data-ttu-id="7c779-142">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c779-142">xs:string</span></span>|<span data-ttu-id="7c779-143">定义用于 SSO 的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="7c779-143">Defines the name of the affiliate application to use for SSO.</span></span>|  
|<span data-ttu-id="7c779-144">**AuthenticationScheme**</span><span class="sxs-lookup"><span data-stu-id="7c779-144">**AuthenticationScheme**</span></span>|<span data-ttu-id="7c779-145">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c779-145">xs:string</span></span>|<span data-ttu-id="7c779-146">指定对目标服务器使用的验证类型。</span><span class="sxs-lookup"><span data-stu-id="7c779-146">Specifies the type of authentication to use with the destination server.</span></span>|  
|<span data-ttu-id="7c779-147">**UseSSO**</span><span class="sxs-lookup"><span data-stu-id="7c779-147">**UseSSO**</span></span>|<span data-ttu-id="7c779-148">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="7c779-148">xs:boolean</span></span>|<span data-ttu-id="7c779-149">指定 SOAP 适配器是否对发送端口使用 SSO。</span><span class="sxs-lookup"><span data-stu-id="7c779-149">Specifies whether the SOAP adapter uses SSO for the send port.</span></span>|  
|<span data-ttu-id="7c779-150">**UseHandlerSetting**</span><span class="sxs-lookup"><span data-stu-id="7c779-150">**UseHandlerSetting**</span></span>|<span data-ttu-id="7c779-151">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="7c779-151">xs:boolean</span></span>|<span data-ttu-id="7c779-152">指定 SOAP 发送端口是否使用处理程序的代理配置。</span><span class="sxs-lookup"><span data-stu-id="7c779-152">Specifies whether the SOAP send port uses the proxy configuration for the handler.</span></span>|  
|<span data-ttu-id="7c779-153">**ClientConnectionTimeout**</span><span class="sxs-lookup"><span data-stu-id="7c779-153">**ClientConnectionTimeout**</span></span>|<span data-ttu-id="7c779-154">xs:int</span><span class="sxs-lookup"><span data-stu-id="7c779-154">xs:int</span></span>|<span data-ttu-id="7c779-155">指定等待服务器响应的超时期限。</span><span class="sxs-lookup"><span data-stu-id="7c779-155">Specifies the time-out period of waiting for a response from the server.</span></span> <span data-ttu-id="7c779-156">如果设置为零 (0)，系统将计算基于对请求消息大小的超时值。</span><span class="sxs-lookup"><span data-stu-id="7c779-156">If set to zero (0), the system will calculate the time-out based on the request message size.</span></span>|  
|<span data-ttu-id="7c779-157">**用户定义**</span><span class="sxs-lookup"><span data-stu-id="7c779-157">**UserDefined**</span></span>|<span data-ttu-id="7c779-158">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c779-158">xs:string</span></span>|<span data-ttu-id="7c779-159">定义用户定义的类。</span><span class="sxs-lookup"><span data-stu-id="7c779-159">Defines user-defined classes.</span></span>|  
|<span data-ttu-id="7c779-160">**UseSoap12**</span><span class="sxs-lookup"><span data-stu-id="7c779-160">**UseSoap12**</span></span>|<span data-ttu-id="7c779-161">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="7c779-161">xs:boolean</span></span>|<span data-ttu-id="7c779-162">指定是否生成支持 SOAP 1.2 协议的代理代码。</span><span class="sxs-lookup"><span data-stu-id="7c779-162">Specifies whether to generate proxy code that supports the SOAP 1.2 protocol.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c779-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c779-163">See Also</span></span>  
 [<span data-ttu-id="7c779-164">配置 SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="7c779-164">Configuring the SOAP Adapter</span></span>](../core/configuring-the-soap-adapter.md)