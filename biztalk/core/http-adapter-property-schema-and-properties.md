---
title: HTTP 适配器属性架构和属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- AffiliateApplicationName property [HTTP adapters]
- Certificate property [HTTP adapters]
- Password property [HTTP adapters]
- HTTP adapters, properties
- InboundHttpHeaders property [HTTP adapters]
- UseHandlerProxySettings property [HTTP adapters]
- configuring [HTTP adapters], properties
- schemas, HTTP adapters
- RequestTimeout property [HTTP adapters]
- ProxyPassword property [HTTP adapters]
- UseSSO property [HTTP adapters]
- HTTP adapters, schemas
- AuthenticationScheme property [HTTP adapters]
- ProxyName property [HTTP adapters]
- ProxyPort property [HTTP adapters]
- UseProxy property [HTTP adapters]
- configuring [HTTP adapters], schemas
- ContentType property [HTTP adapters]
- MaxRedirects property [HTTP adapters]
- ProxyUsername property [HTTP adapters]
- UserName property, HTTP adapters
ms.assetid: c9b50a82-8cb1-4521-9cf3-5fd77a3531e1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2f4fdfbd082bb9bbb8e3a37355068b3c8d29c63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332893"
---
# <a name="http-adapter-property-schema-and-properties"></a><span data-ttu-id="30080-102">HTTP 适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="30080-102">HTTP Adapter Property Schema and Properties</span></span>
<span data-ttu-id="30080-103">下表列出了 HTTP 适配器属性架构中的属性。</span><span class="sxs-lookup"><span data-stu-id="30080-103">The following table lists the properties in the HTTP adapter property schema.</span></span>  
  
 <span data-ttu-id="30080-104">**Namespace**： http://schemas.microsoft.com/BizTalk/2003/http-properties</span><span class="sxs-lookup"><span data-stu-id="30080-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/http-properties</span></span>  
  
|<span data-ttu-id="30080-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="30080-105">Name</span></span>|<span data-ttu-id="30080-106">类型</span><span class="sxs-lookup"><span data-stu-id="30080-106">Type</span></span>|<span data-ttu-id="30080-107">Description</span><span class="sxs-lookup"><span data-stu-id="30080-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="30080-108">**ProxyName**</span><span class="sxs-lookup"><span data-stu-id="30080-108">**ProxyName**</span></span>|<span data-ttu-id="30080-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="30080-109">xs:string</span></span>|<span data-ttu-id="30080-110">指定代理服务器名称。</span><span class="sxs-lookup"><span data-stu-id="30080-110">Specifies the proxy server name.</span></span>|  
|<span data-ttu-id="30080-111">**ProxyPort**</span><span class="sxs-lookup"><span data-stu-id="30080-111">**ProxyPort**</span></span>|<span data-ttu-id="30080-112">xs:int</span><span class="sxs-lookup"><span data-stu-id="30080-112">xs:int</span></span>|<span data-ttu-id="30080-113">指定代理服务器端口。</span><span class="sxs-lookup"><span data-stu-id="30080-113">Specifies the proxy server port.</span></span>|  
|<span data-ttu-id="30080-114">**UseHandlerProxySettings**</span><span class="sxs-lookup"><span data-stu-id="30080-114">**UseHandlerProxySettings**</span></span>|<span data-ttu-id="30080-115">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="30080-115">xs:boolean</span></span>|<span data-ttu-id="30080-116">指定 HTTP 发送端口是否使用处理程序的代理配置。</span><span class="sxs-lookup"><span data-stu-id="30080-116">Specifies whether the HTTP send port uses the proxy configuration for the handler.</span></span>|  
|<span data-ttu-id="30080-117">**UseProxy**</span><span class="sxs-lookup"><span data-stu-id="30080-117">**UseProxy**</span></span>|<span data-ttu-id="30080-118">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="30080-118">xs:boolean</span></span>|<span data-ttu-id="30080-119">指定 HTTP 适配器是否使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="30080-119">Specifies whether HTTP adapter uses the proxy server.</span></span>|  
|<span data-ttu-id="30080-120">**RequestTimeout**</span><span class="sxs-lookup"><span data-stu-id="30080-120">**RequestTimeout**</span></span>|<span data-ttu-id="30080-121">xs:int</span><span class="sxs-lookup"><span data-stu-id="30080-121">xs:int</span></span>|<span data-ttu-id="30080-122">超时期限的等待来自服务器的响应。</span><span class="sxs-lookup"><span data-stu-id="30080-122">Time-out period of waiting for a response from the server.</span></span> <span data-ttu-id="30080-123">如果此属性设置为零 (0)，系统会计算请求消息的大小的超时值。</span><span class="sxs-lookup"><span data-stu-id="30080-123">If this property is set to zero (0), the system calculates the time-out on the request message size.</span></span>|  
|<span data-ttu-id="30080-124">**用户名**</span><span class="sxs-lookup"><span data-stu-id="30080-124">**Username**</span></span>|<span data-ttu-id="30080-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="30080-125">xs:string</span></span>|<span data-ttu-id="30080-126">要用于服务器的身份验证的用户名称。</span><span class="sxs-lookup"><span data-stu-id="30080-126">The user name to use for authentication with the server.</span></span>|  
|<span data-ttu-id="30080-127">**密码**</span><span class="sxs-lookup"><span data-stu-id="30080-127">**Password**</span></span>|<span data-ttu-id="30080-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="30080-128">xs:string</span></span>|<span data-ttu-id="30080-129">要使用的服务器的身份验证的用户密码。</span><span class="sxs-lookup"><span data-stu-id="30080-129">The user password to use for authentication with the server.</span></span>|  
|<span data-ttu-id="30080-130">**ProxyUsername**</span><span class="sxs-lookup"><span data-stu-id="30080-130">**ProxyUsername**</span></span>|<span data-ttu-id="30080-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="30080-131">xs:string</span></span>|<span data-ttu-id="30080-132">指定与代理服务器进行身份验证的用户名。</span><span class="sxs-lookup"><span data-stu-id="30080-132">Specifies the user name for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="30080-133">**ProxyPassword**</span><span class="sxs-lookup"><span data-stu-id="30080-133">**ProxyPassword**</span></span>|<span data-ttu-id="30080-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="30080-134">xs:string</span></span>|<span data-ttu-id="30080-135">指定与代理服务器进行身份验证的用户密码。</span><span class="sxs-lookup"><span data-stu-id="30080-135">Specifies the user password for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="30080-136">**MaxRedirects**</span><span class="sxs-lookup"><span data-stu-id="30080-136">**MaxRedirects**</span></span>|<span data-ttu-id="30080-137">xs:int</span><span class="sxs-lookup"><span data-stu-id="30080-137">xs:int</span></span>|<span data-ttu-id="30080-138">HTTP 适配器将重定向请求最大次数。</span><span class="sxs-lookup"><span data-stu-id="30080-138">The maximum number of times that the HTTP adapter will redirect the request.</span></span>|  
|<span data-ttu-id="30080-139">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="30080-139">**ContentType**</span></span>|<span data-ttu-id="30080-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="30080-140">xs:string</span></span>|<span data-ttu-id="30080-141">请求消息的内容类型。</span><span class="sxs-lookup"><span data-stu-id="30080-141">Content type of the request messages.</span></span>|  
|<span data-ttu-id="30080-142">**AuthenticationScheme**</span><span class="sxs-lookup"><span data-stu-id="30080-142">**AuthenticationScheme**</span></span>|<span data-ttu-id="30080-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="30080-143">xs:string</span></span>|<span data-ttu-id="30080-144">要对目标服务器使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="30080-144">Type of authentication to use with the destination server.</span></span>|  
|<span data-ttu-id="30080-145">**证书**</span><span class="sxs-lookup"><span data-stu-id="30080-145">**Certificate**</span></span>|<span data-ttu-id="30080-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="30080-146">xs:string</span></span>|<span data-ttu-id="30080-147">客户端 SSL 证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="30080-147">Thumbprint of client SSL certificate.</span></span>|  
|<span data-ttu-id="30080-148">**UseSSO**</span><span class="sxs-lookup"><span data-stu-id="30080-148">**UseSSO**</span></span>|<span data-ttu-id="30080-149">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="30080-149">xs:boolean</span></span>|<span data-ttu-id="30080-150">指定 HTTP 发送端口是否将使用 SSO。</span><span class="sxs-lookup"><span data-stu-id="30080-150">Specifies whether the HTTP send port will use SSO.</span></span>|  
|<span data-ttu-id="30080-151">**AffiliateApplicationName**</span><span class="sxs-lookup"><span data-stu-id="30080-151">**AffiliateApplicationName**</span></span>|<span data-ttu-id="30080-152">xs:string</span><span class="sxs-lookup"><span data-stu-id="30080-152">xs:string</span></span>|<span data-ttu-id="30080-153">要使用的 SSO 关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="30080-153">Name of affiliate application to use for SSO.</span></span>|  
|<span data-ttu-id="30080-154">**InboundHttpHeaders**</span><span class="sxs-lookup"><span data-stu-id="30080-154">**InboundHttpHeaders**</span></span>|<span data-ttu-id="30080-155">xs:string</span><span class="sxs-lookup"><span data-stu-id="30080-155">xs:string</span></span>|<span data-ttu-id="30080-156">包含从入站 HTTP 请求的 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="30080-156">Contains the HTTP headers from the inbound HTTP request.</span></span>|  
|<span data-ttu-id="30080-157">**SubmissionHandle**</span><span class="sxs-lookup"><span data-stu-id="30080-157">**SubmissionHandle**</span></span>|<span data-ttu-id="30080-158">xs:string</span><span class="sxs-lookup"><span data-stu-id="30080-158">xs:string</span></span>|<span data-ttu-id="30080-159">包含请求消息的 BizTalk Server 相关标记 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="30080-159">Contains the BizTalk Server correlation token (GUID) for the request message.</span></span>|  
|<span data-ttu-id="30080-160">**EnableChunkedEncoding**</span><span class="sxs-lookup"><span data-stu-id="30080-160">**EnableChunkedEncoding**</span></span>|<span data-ttu-id="30080-161">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="30080-161">xs:boolean</span></span>|<span data-ttu-id="30080-162">指定 chunked 编码使用的 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="30080-162">Specifies whether or not chunked encoding is used by the HTTP adapter.</span></span>|  
|<span data-ttu-id="30080-163">**UserHttpHeaders**</span><span class="sxs-lookup"><span data-stu-id="30080-163">**UserHttpHeaders**</span></span>|<span data-ttu-id="30080-164">xs:string</span><span class="sxs-lookup"><span data-stu-id="30080-164">xs:string</span></span>|<span data-ttu-id="30080-165">包含 HTTP 请求或响应消息中包含的自定义标头</span><span class="sxs-lookup"><span data-stu-id="30080-165">Contains the customized headers contained in the HTTP request or response message</span></span><br /><br /> <span data-ttu-id="30080-166">值**UserHttpHeaders**属性必须具有以下格式：</span><span class="sxs-lookup"><span data-stu-id="30080-166">The value of the **UserHttpHeaders** property must have the following format:</span></span><br /><br /> `Header1: value\r\nHeader2: value\r\n`<br /><br /> <span data-ttu-id="30080-167">**请注意**放置冒号 （:）和标头和值之间的空格字符 （）。</span><span class="sxs-lookup"><span data-stu-id="30080-167">**Note** Put a colon (:) and a SPACE character ( ) between the header and the value.</span></span> <span data-ttu-id="30080-168">标头为空将导致要筛选出的项。空值是可行的。</span><span class="sxs-lookup"><span data-stu-id="30080-168">An empty header will cause the entry to be filtered out. An empty value is okay.</span></span><br /><br /> <span data-ttu-id="30080-169">可以通过使用修改下面的五个标准 HTTP 标头**UserHttpHeaders**属性：</span><span class="sxs-lookup"><span data-stu-id="30080-169">You can modify the following five standard HTTP headers by using the **UserHttpHeaders** property:</span></span><br /><br /> <span data-ttu-id="30080-170">-接受</span><span class="sxs-lookup"><span data-stu-id="30080-170">- Accept</span></span><br /><br /> <span data-ttu-id="30080-171">-引用网站</span><span class="sxs-lookup"><span data-stu-id="30080-171">- Referrer</span></span><br /><br /> <span data-ttu-id="30080-172">-预期</span><span class="sxs-lookup"><span data-stu-id="30080-172">- Expect</span></span><br /><br /> <span data-ttu-id="30080-173">-如果-修改-自</span><span class="sxs-lookup"><span data-stu-id="30080-173">- If-Modified-Since</span></span><br /><br /> <span data-ttu-id="30080-174">-用户代理</span><span class="sxs-lookup"><span data-stu-id="30080-174">- User-Agent</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30080-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="30080-175">See Also</span></span>  
 [<span data-ttu-id="30080-176">配置 HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="30080-176">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)