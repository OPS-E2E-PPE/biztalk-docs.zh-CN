---
title: 优化 WCF Web 服务性能 |Microsoft 文档
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
ms.openlocfilehash: 413642931fcf9580ade280c2e7b3472599859d8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299413"
---
# <a name="optimizing-wcf-web-service-performance"></a>优化 WCF Web 服务性能
WCF 服务公开多个会影响性能的配置参数。 本主题提供有关这些配置参数，以提高性能的 WCF 服务的设置最佳值的常规指南。  
  
## <a name="implement-servicethrottling-behavior-for-backend-wcf-services"></a>实现后端 WCF 服务的 serviceThrottling 行为  
 实现后端 WCF 服务的 serviceThrottling 行为。 服务限制，可以在后端 WCF 服务器上的负载平衡和强制执行资源分配。 通过修改的值配置的后端 WCF 服务的 serviceThrottling 行为**maxConcurrentCalls**， **maxConcurrentSessions**，和**maxConcurrentInstances** WCF 服务的配置文件中的参数。 设置**maxConcurrentCalls**， **maxConcurrentSessions**，和**maxConcurrentInstances**为值大于 16 * 数 Cpu 或 CPU 内核。 例如，具有 8 个 CPU 内核的计算机上, 设置**maxConcurrentCalls**， **maxConcurrentSessions**，和**maxConcurrentInstances**到大于 128 (16 * 8 = 128) 的值如下所示：  
  
```  
<serviceThrottling  
maxConcurrentCalls="200"  
maxConcurrentSessions="200"  
maxConcurrentInstances="200" />  
```  
  
## <a name="increase-the-default-values-for-the-nettcpbindinglistenbacklog-and-nettcpbindingmaxconnections-properties-in-the-backend-wcf-service-webconfig-file"></a>增加在后端 WCF 服务的 web.config 文件中的 NetTcpBinding.ListenBacklog 和 NetTcpBinding.MaxConnections 属性的默认值  
 **NetTcpBinding.ListenBacklog**属性控制的最大可为挂起状态的排队的连接请求数的 Web 服务。 **NetTcpBinding.MaxConnections**属性控制的最大可存入池中以备后续重复使用客户端上的连接数和最大允许可挂起调度的服务器上的连接数。 上述每个属性使用默认值为 10 可能并非最佳，尤其是对于处理需要高吞吐量的方案的文档。  
  
 请考虑增加高吞吐量、 文档处理方案，它们使用 WCF 服务实现这些属性的默认值**netTcpBinding**绑定类。  
  
 在下面的示例中，同时**listenBacklog**和**maxConnections**参数设置为值为"200"。  
  
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
  
## <a name="eliminate-aspnet-httpmodules-that-are-not-required-to-run-wcf-web-services"></a>消除不需要运行 WCF Web 服务的 ASP.NET Httpmodule  
 默认情况下，多个 ASP.NET Httpmodule 请求管道在 IIS 6.0 中，然后在经典或集成管道 IIS 7.5/7.0 中定义。 这些组件拦截和处理所有传入的请求。 在 32 位 ASP.NET 应用程序的 %windir%\Microsoft.NET\Framework\v2.0.50727\CONFIG 文件夹和 64 位 ASP %windir%\Microsoft.NET\Framework64\v2.0.50727\CONFIG 文件夹中包含 web.config 文件中定义的默认模块。NET 应用程序，如以下片段所示。  
  
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
  
 在大多数情况下不需要加载所有这些模块。 因此，就可以通过消除以下 Httpmodule，运行 WCF Web 服务时提高性能：  
  
-   Session  
  
-   Windows 身份验证  
  
-   FormsAuthentication  
  
-   PassportAuthentication  
  
-   RoleManager  
  
-   AnonymousIdentification  
  
-   配置文件  
  
## <a name="use-the-wcf-modulehandler-registration-tool-to-configure-wcf-moduleshandlers-and-improve-scalability-of-iis-7570-hosted-wcf-services"></a>使用 WCF 模块/处理程序注册工具以配置 WCF 模块处理程序和提高可伸缩性的 IIS 7.5/7.0 中承载 WCF 服务  
 WCF 模块/处理程序注册工具是可在下载[http://go.microsoft.com/fwlink/?LinkId=157593](http://go.microsoft.com/fwlink/?LinkId=157593) (http://go.microsoft.com/fwlink/?LinkId=157593)。 可以使用此实用工具要安装列表中，或配置以下 WCF 模块：  
  
-   WCF 同步 HTTP 模块和处理程序  
  
-   WCF 异步 HTTP 模块和处理程序  
  
-   WCF HTTP 模块和处理程序  
  
 有关详细信息，有关使用异步的 WCF HTTP 模块/处理程序中以提高可缩放性的 IIS 7.5/7.0 中托管 WCF 服务，请参阅 Wenlong 盾博客[Orcas SP1 改善： 异步 WCF HTTP 模块/处理程序以更好的 IIS7服务器的可伸缩性](http://go.microsoft.com/fwlink/?LinkId=157428)(http://go.microsoft.com/fwlink/?LinkId=157428)。  
  
## <a name="see-also"></a>另请参阅  
 [优化 BizTalk Server WCF 适配器性能](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)