---
title: "WCF 适配器安全建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF adapters, security
- security, WCF adapters
ms.assetid: bbaaca56-9ad5-4122-a8e9-6e975d308230
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ea0334e2d6164091e54321de8e1dccab5c07bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapters-security-recommendations"></a><span data-ttu-id="bbcfd-102">WCF 适配器的安全建议</span><span class="sxs-lookup"><span data-stu-id="bbcfd-102">WCF Adapters Security Recommendations</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bbcfd-103"> 使用 WCF 适配器来发布（接收）和使用（发送）WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-103"> uses the WCF adapters to publish (receive) and consume (send) WCF services.</span></span> <span data-ttu-id="bbcfd-104">我们建议您按照这些准则来确保您环境中的 WCF 适配器的安全以及部署它们。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-104">We recommend that you follow these guidelines for securing and deploying the WCF adapters in your environment.</span></span>  
  
 <span data-ttu-id="bbcfd-105">有关 WCF 适配器的详细信息，请参阅[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-105">For more information about the WCF adapters, see [WCF Adapters](../core/wcf-adapters.md).</span></span> <span data-ttu-id="bbcfd-106">有关 WCF 服务的详细信息，请参阅[使用 WCF 服务](../core/using-wcf-services.md)s。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-106">For more information about WCF services, see [Using WCF Services](../core/using-wcf-services.md)s.</span></span>  
  
## <a name="security-recommendations-for-all-wcf-adapters"></a><span data-ttu-id="bbcfd-107">针对所有 WCF 适配器的安全建议</span><span class="sxs-lookup"><span data-stu-id="bbcfd-107">Security Recommendations for All WCF Adapters</span></span>  
  
-   <span data-ttu-id="bbcfd-108">如果需要将前端用户的内容映射到后端系统中的凭据，则可以使用企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-108">You can use Enterprise Single Sign-On (SSO) in scenarios where you need to map the content of the front-end user to credentials in a back-end system.</span></span>  
  
-   <span data-ttu-id="bbcfd-109">并不是所有的服务都必须发布元数据。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-109">Not all services must publish metadata.</span></span> <span data-ttu-id="bbcfd-110">使元数据发布功能保留为禁用状态可减少服务遭受攻击的可能性，同时降低无意中泄露信息的危险。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-110">Leaving metadata publishing disabled reduces the attack surface for your service and lowers the risk of unintentional information disclosure.</span></span> <span data-ttu-id="bbcfd-111">与元数据相关的安全问题的详细信息，请参阅"安全注意事项与元数据"在[http://go.microsoft.com/fwlink/?LinkId=196671](http://go.microsoft.com/fwlink/?LinkId=196671)。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-111">For more information about security issues related to metadata, see "Security Considerations with Metadata" at [http://go.microsoft.com/fwlink/?LinkId=196671](http://go.microsoft.com/fwlink/?LinkId=196671).</span></span>  
  
-   <span data-ttu-id="bbcfd-112">并非所有的元数据终结点绑定和服务终结点绑定的组合都是有效的。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-112">Not all combinations of metadata endpoint bindings and service endpoint bindings are valid.</span></span> <span data-ttu-id="bbcfd-113">在某些情况下，元数据终结点的绑定配置必须与其服务终结点的绑定配置一致。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-113">In some cases, the binding configurations for a metadata endpoint must be in agreement with the binding configurations of its service endpoint.</span></span> <span data-ttu-id="bbcfd-114">例如，从与接收位置相同的位置提供元数据时，如果接收位置使用依赖于 HTTPS 的安全模式，则元数据终结点不能配置为需要 HTTP 传输的安全模式。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-114">For example, when metadata is served from the same location as the receive location, the metadata endpoint cannot be configured with a security mode requiring the HTTP transport if the receive location uses a security mode that relies on HTTPS.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bbcfd-115">发布通过具有相同的位置，但要求依赖于 HTTPS 传输，BizTalk WCF 发布向导生成时，Web.config 文件中的安全模式的服务终结点的 HTTP 传输的元数据时必须设置这两个**httpsGetEnabled**和**httpGetEnabled**特性以**true**。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-115">When publishing metadata through the HTTP transport for a service endpoint with the same location but requiring a security mode that relies on the HTTPS transport, in the Web.config file that the BizTalk WCF Publishing Wizard generates, you must set both of the **httpsGetEnabled** and **httpGetEnabled** attributes to **true**.</span></span>  
  
-   <span data-ttu-id="bbcfd-116">WCF 适配器利用 Windows Communication Foundation (WCF) 的安全功能进行通信。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-116">The WCF adapters leverage the security features of Windows Communication Foundation (WCF) to communicate.</span></span> <span data-ttu-id="bbcfd-117">了解 WCF 在安全方面的功能和限制很重要。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-117">It is important to understand the capabilities and limitations of WCF in terms of security.</span></span> <span data-ttu-id="bbcfd-118">WCF 的安全功能的详细信息，请参阅"Windows Communication Foundation 安全性"网址[http://go.microsoft.com/fwlink/?LinkId=87806](http://go.microsoft.com/fwlink/?LinkId=87806)。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-118">For more information about the security features of WCF, see "Windows Communication Foundation Security" at [http://go.microsoft.com/fwlink/?LinkId=87806](http://go.microsoft.com/fwlink/?LinkId=87806).</span></span>  
  
## <a name="security-recommendations-for-the-isolated-wcf-adapters"></a><span data-ttu-id="bbcfd-119">针对独立 WCF 适配器的安全建议</span><span class="sxs-lookup"><span data-stu-id="bbcfd-119">Security Recommendations for the Isolated WCF Adapters</span></span>  
  
-   <span data-ttu-id="bbcfd-120">有关用于发布 Web 服务的安全建议，请参阅[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-120">For security recommendations for publishing Web services, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
-   <span data-ttu-id="bbcfd-121">如 WCF CustomIsolated、 WCF-BasicHttp 和 WCF WSHttp 适配器的隔离的 WCF 适配器利用超文本传输协议 (HTTP) 发送和接收消息，并从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-121">The isolated WCF adapters such as the WCF-CustomIsolated, WCF-BasicHttp, and WCF-WSHttp adapters leverage the Hypertext Transfer Protocol (HTTP) to send and receive messages to and from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="bbcfd-122">因此，你必须遵循安全建议以确保 Internet 信息服务 (IIS) 的安全。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-122">Therefore, you must follow the security recommendations for securing Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="bbcfd-123">为独立的 WCF 接收位置创建应用程序池，你必须将它配置为是的成员的帐户下运行[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]组的独立主机运行 WCF 接收适配器和 Internet 信息服务工作线程进程组 （IIS_WPG 组）。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-123">When you create an application pool for an isolated WCF receive location, you must configure it to run under an account that is a member of the [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] group for the isolated host running the WCF receive adapter and the Internet Information Services Worker Process group (IIS_WPG group).</span></span> <span data-ttu-id="bbcfd-124">随后，必须将 WCF 接收适配器的主机实例配置为使用此帐户。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-124">You must then configure the host instance for the WCF receive adapter to use this account.</span></span> <span data-ttu-id="bbcfd-125">如果更改了 IIS_WPG 组的帐户，则必须确保将主机实例也更新为使用该新帐户运行。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-125">If you change the account for the IIS_WPG group, you must ensure that you also update the host instance to run under the new account.</span></span>  
  
## <a name="security-recommendations-for-the-wcf-custom-adapter"></a><span data-ttu-id="bbcfd-126">针对 WCF-Custom 适配器的安全建议</span><span class="sxs-lookup"><span data-stu-id="bbcfd-126">Security Recommendations for the WCF-Custom Adapter</span></span>  
  
-   <span data-ttu-id="bbcfd-127">如果 WCF 自定义接收位置碰巧使用 HTTP 内核模式驱动程序 (HTTP.sys)，如**httpsTransport**对于安全套接字层 (SSL) 通信，接收位置的绑定元素必须具有证书注册为每个套接字 （IP 地址/端口组合）。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-127">If a WCF-Custom receive location happens to use the HTTP kernel-mode driver (HTTP.sys) such as the **httpsTransport** binding element for Secure Sockets Layer (SSL) communications, the receive location must have a certificate registered for each socket (IP address/port combination).</span></span> <span data-ttu-id="bbcfd-128">使用 HttpCfg.exe 工具可将 SSL 证书绑定到计算机上的端口。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-128">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the computer.</span></span> <span data-ttu-id="bbcfd-129">有关详细信息，请参阅"如何为:: 配置端口使用 SSL 证书" [http://go.microsoft.com/fwlink/?LinkId=86384](http://go.microsoft.com/fwlink/?LinkId=86384)。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-129">For more information, see "How To: Configure a Port with An SSL Certificate" at [http://go.microsoft.com/fwlink/?LinkId=86384](http://go.microsoft.com/fwlink/?LinkId=86384).</span></span>  
  
## <a name="security-recommendations-for-the-wcf-netmsmq-adapter"></a><span data-ttu-id="bbcfd-130">针对 WCF-NetMsmq 适配器的安全建议</span><span class="sxs-lookup"><span data-stu-id="bbcfd-130">Security Recommendations for the WCF-NetMsmq Adapter</span></span>  
  
-   <span data-ttu-id="bbcfd-131">若要使用 WCF NetMsmq 适配器，你必须配置 WCF NetMsmq 适配器的 MSMQ 安全设置同样适用于相同的方式[netMsmqBinding](http://go.microsoft.com/fwlink/?LinkId=87813)。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-131">To use the WCF-NetMsmq adapter, you have to configure MSMQ security settings for the WCF-NetMsmq adapter in the same way as for the [netMsmqBinding](http://go.microsoft.com/fwlink/?LinkId=87813).</span></span> <span data-ttu-id="bbcfd-132">有关如何配置 MSMQ 安全设置的详细信息**netMsmqBinding**，请参阅"故障排除排队消息传递"在[http://go.microsoft.com/fwlink/?LinkId=87816](http://go.microsoft.com/fwlink/?LinkId=87816)。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-132">For more information about how to configure MSMQ security settings for the **netMsmqBinding**, see "Troubleshooting Queued Messaging" at [http://go.microsoft.com/fwlink/?LinkId=87816](http://go.microsoft.com/fwlink/?LinkId=87816).</span></span>  
  
## <a name="wcf-adapters-use-the-chaintrust-mode-to-validate-certificates"></a><span data-ttu-id="bbcfd-133">WCF 适配器使用 ChainTrust 模式来验证证书。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-133">WCF Adapters Use the ChainTrust Mode to Validate Certificates.</span></span>  
  
-   <span data-ttu-id="bbcfd-134">由于标准 WCF 收到适配器使用[ChainTrust](http://go.microsoft.com/fwlink/?LinkId=88960)模式下，若要验证客户端和服务证书中，你必须安装用于验证的 X.509 证书的 CA 证书链。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-134">Because the standard WCF receive adapters use the [ChainTrust](http://go.microsoft.com/fwlink/?LinkId=88960) mode to validate the client and service certificates, you must install the CA certificate chain to validate the X.509 certificates.</span></span> <span data-ttu-id="bbcfd-135">你可以使用 WCF 自定义或 WCF CustomIsolated 适配器若要更改此默认行为。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-135">You can use the WCF-Custom or the WCF-CustomIsolated adapter to change this default behavior.</span></span>  
  
## <a name="security-auditing-for-the-wcf-adapters"></a><span data-ttu-id="bbcfd-136">WCF 适配器的安全审核</span><span class="sxs-lookup"><span data-stu-id="bbcfd-136">Security Auditing for the WCF Adapters</span></span>  
  
-   <span data-ttu-id="bbcfd-137">默认情况下，WCF 适配器不使用 WCF 安全审核功能。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-137">The WCF adapters do not use the WCF security auditing features by default.</span></span> <span data-ttu-id="bbcfd-138">为 WCF 适配器启用 WCF 安全审核功能有多种方式。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-138">There are several ways to enable the WCF security auditing features for the WCF adapters.</span></span> <span data-ttu-id="bbcfd-139">有关 WCF 安全审核功能的详细信息，请参阅"审核安全事件"在[http://go.microsoft.com/fwlink/?LinkId=88975](http://go.microsoft.com/fwlink/?LinkId=88975)。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-139">For more information about the WCF security auditing features, see "Auditing Security Events" at [http://go.microsoft.com/fwlink/?LinkId=88975](http://go.microsoft.com/fwlink/?LinkId=88975).</span></span>  
  
-   <span data-ttu-id="bbcfd-140">若要使用的 WCF 安全，与 WCF 自定义接收适配器审核功能，你可以配置**ServiceSecurityAuditBehavior**接收位置。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-140">To use the WCF security auditing features with the WCF-Custom receive adapter, you can configure the **ServiceSecurityAuditBehavior** for the receive locations.</span></span>  
  
-   <span data-ttu-id="bbcfd-141">对于进程内 WCF 适配器，可以通过 BTSNTSvc.exe.config 文件启用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-141">For the in-process WCF adapters, you can enable the performance counters through the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="bbcfd-142">对于独立的 WCF 适配器，请通过修改 BizTalk WCF 服务发布向导创建的 Web 应用程序文件夹中的 Web.config 文件来启用 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-142">For the isolated WCF adapters, you can enable WCF tracing by modifying the Web.config file that the BizTalk WCF Service Publishing Wizard creates in the Web application folder.</span></span> <span data-ttu-id="bbcfd-143">若要修改 BTSNtSvc.exe.config 或 Web.config，请打开相应配置文件，然后配置 WCF 跟踪，如下面的配置示例所示：</span><span class="sxs-lookup"><span data-stu-id="bbcfd-143">To modify BTSNtSvc.exe.config or Web.config, open the configuration file, and then configure WCF tracing, as indicated in the following configuration example:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bbcfd-144">BTSNTSvc.exe.config 文件始终与 BTSNTSvc.exe 文件位于同一目录中，所在目录通常为 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-144">The BTSNTSvc.exe.config file is always located in the same directory as the BTSNTSvc.exe file, which is usually [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bbcfd-145">修改 BTSNTSvc.exe.config 文件之后，必须重新启动运行进程内 WCF 接收位置的主机实例。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-145">After modifying the BTSNTSvc.exe.config file, you must restart the host instances running the in-process WCF receive locations.</span></span>  
  
    ```  
    <configuration>  
        <system.serviceModel>  
          <diagnostics performanceCounters="All" />  
          <behaviors>  
            <serviceBehaviors>  
              <behavior name="ServiceBehaviorConfiguration">  
                <serviceSecurityAudit  
                          auditLogLocation="Application"  
                          suppressAuditFailure="true"  
                          serviceAuthorizationAuditLevel="SuccessOrFailure"  
    messageAuthenticationAuditLevel="SuccessOrFailure" />  
              </behavior>  
            </serviceBehaviors>  
          </behaviors>  
          <services>  
            <service name="Microsoft.BizTalk.Adapter.Wcf.Runtime.BizTalkServiceInstance" behaviorConfiguration="ServiceBehaviorConfiguration">  
            </service>  
          </services>        
        </system.serviceModel>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="bbcfd-146">您还可以使用与安全相关的性能计数器（如 Security Calls Not Authorized）来监视 WCF 适配器。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-146">You can also use a security-related performance counter such as Security Calls Not Authorized to monitor the WCF adapters.</span></span> <span data-ttu-id="bbcfd-147">有关如何启用对 WCF 性能计数器的详细信息，请参阅[WCF 适配器性能计数器](../core/wcf-adapters-performance-counters.md)。</span><span class="sxs-lookup"><span data-stu-id="bbcfd-147">For more information about how to enable the WCF performance counters, see [WCF Adapters Performance Counters](../core/wcf-adapters-performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbcfd-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbcfd-148">See Also</span></span>  
 [<span data-ttu-id="bbcfd-149">Planning for Security</span><span class="sxs-lookup"><span data-stu-id="bbcfd-149">Planning for Security</span></span>](../core/planning-for-security.md)