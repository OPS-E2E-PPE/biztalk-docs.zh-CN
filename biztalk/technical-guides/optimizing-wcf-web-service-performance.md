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
# <a name="optimizing-wcf-web-service-performance"></a>优化 WCF Web 服务性能
WCF 服务公开大量会影响性能的配置参数。 本主题提供有关设置这些配置参数，以提高性能的 WCF 服务的最佳值的一般指南。  
  
## <a name="implement-servicethrottling-behavior-for-backend-wcf-services"></a>实现 serviceThrottling 行为的后端 WCF 服务  
 实现 serviceThrottling 行为的后端 WCF 服务。 服务限制，可以在后端 WCF 服务器上的负载均衡并实施资源分配。 通过修改的值配置的后端 WCF 服务的 serviceThrottling 行为**maxConcurrentCalls**， **maxConcurrentSessions**，和**maxConcurrentInstances** WCF 服务的配置文件中的参数。 设置**maxConcurrentCalls**， **maxConcurrentSessions**，和**maxConcurrentInstances**为值大于 16 * 数的 Cpu 或 CPU 内核数。 例如，具有 8 个 CPU 内核的计算机上, 设置**maxConcurrentCalls**， **maxConcurrentSessions**，并**maxConcurrentInstances**为值大于 128 (16 * 8 = 128)按如下所示：  
  
```  
<serviceThrottling  
maxConcurrentCalls="200"  
maxConcurrentSessions="200"  
maxConcurrentInstances="200" />  
```  
  
## <a name="increase-the-default-values-for-the-nettcpbindinglistenbacklog-and-nettcpbindingmaxconnections-properties-in-the-backend-wcf-service-webconfig-file"></a>增加后端 WCF 服务的 web.config 文件中的 NetTcpBinding.ListenBacklog 和 NetTcpBinding.MaxConnections 属性的默认值  
 **NetTcpBinding.ListenBacklog**属性控制的最大排队的连接请求可为挂起状态数为 Web 服务。 **NetTcpBinding.MaxConnections**属性控制的最大可存入池中以备后续重复使用在客户端上的连接数和最大可挂起调度的服务器上的连接数。 每个属性使用默认值为 10，这可能是不理想，尤其是对于需要高吞吐量的情况下处理的文档。  
  
 请考虑增加针对高吞吐量、 文档处理的方案使用 WCF 服务实现的这些属性的默认值**netTcpBinding**绑定类。  
  
 在以下示例中，同时**listenBacklog**并**maxConnections**参数设置为"200"的值。  
  
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
  
 有关 NetTcpBinding.ListenBacklog 属性的详细信息，请参阅[NetTcpBinding.ListenBacklog 属性](http://go.microsoft.com/fwlink/?LinkId=157752)(http://go.microsoft.com/fwlink/?LinkId=157752) MSDN 上。  
  
 有关 NetTcpBinding.MaxConnections 属性的详细信息，请参阅[NetTcpBinding.MaxConnections 属性](http://go.microsoft.com/fwlink/?LinkID=157751)(http://go.microsoft.com/fwlink/?LinkID=157751) MSDN 上。  
  
## <a name="eliminate-aspnet-httpmodules-that-are-not-required-to-run-wcf-web-services"></a>消除不需要运行 WCF Web 服务的 ASP.NET httpModules  
 默认情况下，多个 ASP.NET httpModules 中请求管道在 IIS 6.0 和经典或 IIS 7.5/7.0 集成管道中定义。 这些组件拦截和处理所有传入的请求。 包含在 %windir%\Microsoft.NET\Framework\v2.0.50727\CONFIG 文件夹中的 32 位 ASP.NET 应用程序并在 64 位 ASP %windir%\Microsoft.NET\Framework64\v2.0.50727\CONFIG 文件夹中的 web.config 文件中定义的默认模块。NET 应用程序，如通过以下代码片段所示。  
  
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
  
 在大多数情况下不需要加载所有这些模块。 因此，就可以通过消除以下 httpModules 运行 WCF Web 服务时提高性能：  
  
-   Session  
  
-   WindowsAuthentication  
  
-   FormsAuthentication  
  
-   PassportAuthentication  
  
-   RoleManager  
  
-   AnonymousIdentification  
  
-   配置文件  
  
## <a name="use-the-wcf-modulehandler-registration-tool-to-configure-wcf-moduleshandlers-and-improve-scalability-of-iis-7570-hosted-wcf-services"></a>使用 WCF 模块/处理程序注册工具来配置 WCF 模块/处理程序并提高可伸缩性的 IIS 7.5/7.0 中承载的 WCF 服务  
 WCF 模块/处理程序注册工具是可在下载[ http://go.microsoft.com/fwlink/?LinkId=157593 ](http://go.microsoft.com/fwlink/?LinkId=157593) (http://go.microsoft.com/fwlink/?LinkId=157593)。 此实用工具可以用于安装列表中，或配置以下 WCF 模块：  
  
- WCF 同步 HTTP 模块和处理程序  
  
- WCF 异步 HTTP 模块和处理程序  
  
- WCF HTTP 模块和处理程序  
  
  详细了解使用异步的 WCF HTTP 模块/处理程序中以提高可伸缩性的 IIS 7.5/7.0 中承载 WCF 服务，请参阅 Wenlong 盾博客[Orcas SP1 改善： 异步 WCF HTTP 模块/处理程序的更好的 IIS7服务器的可伸缩性](http://go.microsoft.com/fwlink/?LinkId=157428)(http://go.microsoft.com/fwlink/?LinkId=157428)。  
  
## <a name="see-also"></a>请参阅  
 [优化 BizTalk Server WCF 适配器性能](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)