---
title: 优化 WCF Web 服务性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93947cef-469c-4126-85a5-06456fa37443
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b0dc200135d65f179d565ba0fe03cc8df897eeb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999374"
---
# <a name="optimizing-wcf-web-service-performance"></a><span data-ttu-id="56120-102">优化 WCF Web 服务性能</span><span class="sxs-lookup"><span data-stu-id="56120-102">Optimizing WCF Web Service Performance</span></span>
<span data-ttu-id="56120-103">WCF 服务公开大量会影响性能的配置参数。</span><span class="sxs-lookup"><span data-stu-id="56120-103">WCF services expose numerous configuration parameters that affect performance.</span></span> <span data-ttu-id="56120-104">本主题提供有关设置这些配置参数，以提高性能的 WCF 服务的最佳值的一般指南。</span><span class="sxs-lookup"><span data-stu-id="56120-104">This topic provides general guidance for setting optimal values for these configuration parameters to improve performance of WCF services.</span></span>  
  
## <a name="implement-servicethrottling-behavior-for-backend-wcf-services"></a><span data-ttu-id="56120-105">实现 serviceThrottling 行为的后端 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="56120-105">Implement serviceThrottling behavior for backend WCF services</span></span>  
 <span data-ttu-id="56120-106">实现 serviceThrottling 行为的后端 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="56120-106">Implement serviceThrottling behavior for backend WCF services.</span></span> <span data-ttu-id="56120-107">服务限制，可以在后端 WCF 服务器上的负载均衡并实施资源分配。</span><span class="sxs-lookup"><span data-stu-id="56120-107">Service throttling allows you to even out the load on your backend WCF servers and to enforce resource allocation.</span></span> <span data-ttu-id="56120-108">通过修改的值配置的后端 WCF 服务的 serviceThrottling 行为**maxConcurrentCalls**， **maxConcurrentSessions**，和**maxConcurrentInstances** WCF 服务的配置文件中的参数。</span><span class="sxs-lookup"><span data-stu-id="56120-108">serviceThrottling behavior for backend WCF services is configured by modifying the values for the **maxConcurrentCalls**, **maxConcurrentSessions**, and **maxConcurrentInstances** parameters in the config file for the WCF service.</span></span> <span data-ttu-id="56120-109">设置**maxConcurrentCalls**， **maxConcurrentSessions**，和**maxConcurrentInstances**为值大于 16 \* 数的 Cpu 或 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="56120-109">Set **maxConcurrentCalls**, **maxConcurrentSessions**, and **maxConcurrentInstances** to a value greater than 16 \* the number of CPUs or CPU cores.</span></span> <span data-ttu-id="56120-110">例如，具有 8 个 CPU 内核的计算机上, 设置**maxConcurrentCalls**， **maxConcurrentSessions**，并**maxConcurrentInstances**为值大于 128 (16 \* 8 = 128)按如下所示：</span><span class="sxs-lookup"><span data-stu-id="56120-110">For example, on a computer with 8 CPU cores, set **maxConcurrentCalls**, **maxConcurrentSessions**, and **maxConcurrentInstances** to a value greater than 128 (16 \* 8 = 128) as follows:</span></span>  
  
```  
<serviceThrottling  
maxConcurrentCalls="200"  
maxConcurrentSessions="200"  
maxConcurrentInstances="200" />  
```  
  
## <a name="increase-the-default-values-for-the-nettcpbindinglistenbacklog-and-nettcpbindingmaxconnections-properties-in-the-backend-wcf-service-webconfig-file"></a><span data-ttu-id="56120-111">增加后端 WCF 服务的 web.config 文件中的 NetTcpBinding.ListenBacklog 和 NetTcpBinding.MaxConnections 属性的默认值</span><span class="sxs-lookup"><span data-stu-id="56120-111">Increase the default values for the NetTcpBinding.ListenBacklog and NetTcpBinding.MaxConnections properties in the backend WCF service web.config file</span></span>  
 <span data-ttu-id="56120-112">**NetTcpBinding.ListenBacklog**属性控制的最大排队的连接请求可为挂起状态数为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="56120-112">The **NetTcpBinding.ListenBacklog** property controls the maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="56120-113">**NetTcpBinding.MaxConnections**属性控制的最大可存入池中以备后续重复使用在客户端上的连接数和最大可挂起调度的服务器上的连接数。</span><span class="sxs-lookup"><span data-stu-id="56120-113">The **NetTcpBinding.MaxConnections** property controls the maximum number of connections to be pooled for subsequent reuse on the client and the maximum number of connections allowed to be pending dispatch on the server.</span></span> <span data-ttu-id="56120-114">每个属性使用默认值为 10，这可能是不理想，尤其是对于需要高吞吐量的情况下处理的文档。</span><span class="sxs-lookup"><span data-stu-id="56120-114">Each of these properties uses a default value of 10 which may be suboptimal, especially for document processing scenarios that require high throughput.</span></span>  
  
 <span data-ttu-id="56120-115">请考虑增加针对高吞吐量、 文档处理的方案使用 WCF 服务实现的这些属性的默认值**netTcpBinding**绑定类。</span><span class="sxs-lookup"><span data-stu-id="56120-115">Consider increasing the default value of these properties for high-throughput, document-processing scenarios that use WCF services which implement the **netTcpBinding** binding class.</span></span>  
  
 <span data-ttu-id="56120-116">在以下示例中，同时**listenBacklog**并**maxConnections**参数设置为"200"的值。</span><span class="sxs-lookup"><span data-stu-id="56120-116">In the following example, both the **listenBacklog** and **maxConnections** parameters are set to a value of “200”.</span></span>  
  
```  
<netTcpBinding>  
   <binding name="netTcpBinding"  
      closeTimeout="00:10:00"  
      openTimeout="00:10:00"  
      receiveTimeout="00:10:00"  
      sendTimeout="00:10:00"  
      transactionFlow="false"  
      transferMode="Buffered"  
      transactionProtocol="OleTransactions"  
      hostNameComparisonMode="StrongWildcard"  
      listenBacklog="200"  
      maxBufferPoolSize="1048576"  
      maxBufferSize="10485760"  
      maxConnections="200"  
      maxReceivedMessageSize="10485760">  
      <readerQuotas  
         maxDepth="32"  
         maxStringContentLength="8192"  
         maxArrayLength="16384"  
         maxBytesPerRead="4096"  
         maxNameTableCharCount="16384" />  
      <reliableSession  
         ordered="true"  
         inactivityTimeout="00:10:00"  
         enabled="false" />  
      <security mode="None">  
         <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />  
         <message clientCredentialType="Windows" />  
      </security>  
   </binding>  
</netTcpBinding>  
```  
  
 <span data-ttu-id="56120-117">有关 NetTcpBinding.ListenBacklog 属性的详细信息，请参阅[NetTcpBinding.ListenBacklog 属性](http://go.microsoft.com/fwlink/?LinkId=157752)(http://go.microsoft.com/fwlink/?LinkId=157752) MSDN 上。</span><span class="sxs-lookup"><span data-stu-id="56120-117">For more information about the NetTcpBinding.ListenBacklog property, see [NetTcpBinding.ListenBacklog Property](http://go.microsoft.com/fwlink/?LinkId=157752) (http://go.microsoft.com/fwlink/?LinkId=157752) on MSDN.</span></span>  
  
 <span data-ttu-id="56120-118">有关 NetTcpBinding.MaxConnections 属性的详细信息，请参阅[NetTcpBinding.MaxConnections 属性](http://go.microsoft.com/fwlink/?LinkID=157751)(http://go.microsoft.com/fwlink/?LinkID=157751) MSDN 上。</span><span class="sxs-lookup"><span data-stu-id="56120-118">For more information about the NetTcpBinding.MaxConnections property, see [NetTcpBinding.MaxConnections Property](http://go.microsoft.com/fwlink/?LinkID=157751) (http://go.microsoft.com/fwlink/?LinkID=157751) on MSDN.</span></span>  
  
## <a name="eliminate-aspnet-httpmodules-that-are-not-required-to-run-wcf-web-services"></a><span data-ttu-id="56120-119">消除不需要运行 WCF Web 服务的 ASP.NET httpModules</span><span class="sxs-lookup"><span data-stu-id="56120-119">Eliminate ASP.NET httpModules that are not required to run WCF Web services</span></span>  
 <span data-ttu-id="56120-120">默认情况下，多个 ASP.NET httpModules 中请求管道在 IIS 6.0 和经典或 IIS 7.5/7.0 集成管道中定义。</span><span class="sxs-lookup"><span data-stu-id="56120-120">By default, several ASP.NET httpModules are defined in the Request Pipeline in IIS 6.0 and in the Classic or Integrated Pipeline in IIS 7.5/7.0.</span></span> <span data-ttu-id="56120-121">这些组件拦截和处理所有传入的请求。</span><span class="sxs-lookup"><span data-stu-id="56120-121">These components intercept and process all incoming requests.</span></span> <span data-ttu-id="56120-122">包含在 %windir%\Microsoft.NET\Framework\v2.0.50727\CONFIG 文件夹中的 32 位 ASP.NET 应用程序并在 64 位 ASP %windir%\Microsoft.NET\Framework64\v2.0.50727\CONFIG 文件夹中的 web.config 文件中定义的默认模块。NET 应用程序，如通过以下代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="56120-122">The default modules are defined in the web.config file contained in the %windir%\Microsoft.NET\Framework\v2.0.50727\CONFIG folder for 32-bit ASP.NET applications and in the %windir%\Microsoft.NET\Framework64\v2.0.50727\CONFIG folder for 64-bit ASP.NET applications, as shown by the following snippet.</span></span>  
  
```  
<httpModules>  
<add name="OutputCache" type="System.Web.Caching.OutputCacheModule"/>  
<add name="Session" type="System.Web.SessionState.SessionStateModule"/>  
<add name="WindowsAuthentication" type="System.Web.Security.WindowsAuthenticationModule"/>  
<add name="FormsAuthentication" type="System.Web.Security.FormsAuthenticationModule"/>  
<add name="PassportAuthentication" type="System.Web.Security.PassportAuthenticationModule"/>  
<add name="RoleManager" type="System.Web.Security.RoleManagerModule"/>  
<add name="UrlAuthorization" type="System.Web.Security.UrlAuthorizationModule"/>  
<add name="FileAuthorization" type="System.Web.Security.FileAuthorizationModule"/>  
<add name="AnonymousIdentification" type="System.Web.Security.AnonymousIdentificationModule"/>  
<add name="Profile" type="System.Web.Profile.ProfileModule"/>  
<add name="ErrorHandlerModule" type="System.Web.Mobile.ErrorHandlerModule, System.Web.Mobile, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"/>  
<add name="ServiceModel" type="System.ServiceModel.Activation.HttpModule, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
</httpModules>  
```  
  
 <span data-ttu-id="56120-123">在大多数情况下不需要加载所有这些模块。</span><span class="sxs-lookup"><span data-stu-id="56120-123">In most scenarios it is not necessary to load all of these modules.</span></span> <span data-ttu-id="56120-124">因此，就可以通过消除以下 httpModules 运行 WCF Web 服务时提高性能：</span><span class="sxs-lookup"><span data-stu-id="56120-124">Therefore, it is possible to improve performance by eliminating the following httpModules when running WCF Web services:</span></span>  
  
-   <span data-ttu-id="56120-125">Session</span><span class="sxs-lookup"><span data-stu-id="56120-125">Session</span></span>  
  
-   <span data-ttu-id="56120-126">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="56120-126">WindowsAuthentication</span></span>  
  
-   <span data-ttu-id="56120-127">FormsAuthentication</span><span class="sxs-lookup"><span data-stu-id="56120-127">FormsAuthentication</span></span>  
  
-   <span data-ttu-id="56120-128">PassportAuthentication</span><span class="sxs-lookup"><span data-stu-id="56120-128">PassportAuthentication</span></span>  
  
-   <span data-ttu-id="56120-129">RoleManager</span><span class="sxs-lookup"><span data-stu-id="56120-129">RoleManager</span></span>  
  
-   <span data-ttu-id="56120-130">AnonymousIdentification</span><span class="sxs-lookup"><span data-stu-id="56120-130">AnonymousIdentification</span></span>  
  
-   <span data-ttu-id="56120-131">配置文件</span><span class="sxs-lookup"><span data-stu-id="56120-131">Profile</span></span>  
  
## <a name="use-the-wcf-modulehandler-registration-tool-to-configure-wcf-moduleshandlers-and-improve-scalability-of-iis-7570-hosted-wcf-services"></a><span data-ttu-id="56120-132">使用 WCF 模块/处理程序注册工具来配置 WCF 模块/处理程序并提高可伸缩性的 IIS 7.5/7.0 中承载的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="56120-132">Use the WCF Module/Handler Registration tool to configure WCF modules/handlers and improve scalability of IIS 7.5/7.0 hosted WCF services</span></span>  
 <span data-ttu-id="56120-133">WCF 模块/处理程序注册工具是可在下载[ http://go.microsoft.com/fwlink/?LinkId=157593 ](http://go.microsoft.com/fwlink/?LinkId=157593) (http://go.microsoft.com/fwlink/?LinkId=157593)。</span><span class="sxs-lookup"><span data-stu-id="56120-133">The WCF Module/Handler Registration Tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=157593](http://go.microsoft.com/fwlink/?LinkId=157593) (http://go.microsoft.com/fwlink/?LinkId=157593).</span></span> <span data-ttu-id="56120-134">此实用工具可以用于安装列表中，或配置以下 WCF 模块：</span><span class="sxs-lookup"><span data-stu-id="56120-134">This utility can be used to install, list, or configure the following WCF modules:</span></span>  
  
- <span data-ttu-id="56120-135">WCF 同步 HTTP 模块和处理程序</span><span class="sxs-lookup"><span data-stu-id="56120-135">WCF Synchronous HTTP module and handler</span></span>  
  
- <span data-ttu-id="56120-136">WCF 异步 HTTP 模块和处理程序</span><span class="sxs-lookup"><span data-stu-id="56120-136">WCF Asynchronous HTTP module and handler</span></span>  
  
- <span data-ttu-id="56120-137">WCF HTTP 模块和处理程序</span><span class="sxs-lookup"><span data-stu-id="56120-137">WCF HTTP module and handler</span></span>  
  
  <span data-ttu-id="56120-138">详细了解使用异步的 WCF HTTP 模块/处理程序中以提高可伸缩性的 IIS 7.5/7.0 中承载 WCF 服务，请参阅 Wenlong 盾博客[Orcas SP1 改善： 异步 WCF HTTP 模块/处理程序的更好的 IIS7服务器的可伸缩性](http://go.microsoft.com/fwlink/?LinkId=157428)(http://go.microsoft.com/fwlink/?LinkId=157428)。</span><span class="sxs-lookup"><span data-stu-id="56120-138">For more information about using the asynchronous WCF HTTP modules/handlers to improve the scalability of IIS 7.5/7.0 hosted WCF services, see Wenlong Dong’s blog [Orcas SP1 Improvement: Asynchronous WCF HTTP Module/Handler for IIS7 for Better Server Scalability](http://go.microsoft.com/fwlink/?LinkId=157428) (http://go.microsoft.com/fwlink/?LinkId=157428).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56120-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="56120-139">See Also</span></span>  
 [<span data-ttu-id="56120-140">优化 BizTalk Server WCF 适配器性能</span><span class="sxs-lookup"><span data-stu-id="56120-140">Optimizing BizTalk Server WCF Adapter Performance</span></span>](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)