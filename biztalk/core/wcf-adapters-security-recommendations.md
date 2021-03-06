---
title: WCF 适配器的安全建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF adapters, security
- security, WCF adapters
ms.assetid: bbaaca56-9ad5-4122-a8e9-6e975d308230
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 617d573dba56cfae8f95c6d847813f50e57f3b48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279090"
---
# <a name="wcf-adapters-security-recommendations"></a>WCF 适配器的安全建议
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用 WCF 适配器来发布 （接收） 和使用 （发送） WCF 服务。 我们建议您遵循这些准则以保护和部署你的环境中的 WCF 适配器。  
  
 有关 WCF 适配器的详细信息，请参阅[WCF 适配器](../core/wcf-adapters.md)。 有关 WCF 服务的详细信息，请参阅[使用 WCF 服务](../core/using-wcf-services.md)s。  
  
## <a name="security-recommendations-for-all-wcf-adapters"></a>针对所有 WCF 适配器的安全建议  
  
-   在方案中可以使用企业单一登录 (SSO) 需要在后端系统中将前端用户的内容映射到凭据。  
  
-   并非所有服务都必须都发布元数据。 禁用元数据发布可以减少您的服务的攻击面并降低意外泄漏信息的风险。 有关与元数据相关的安全问题的详细信息，请参阅"安全注意事项与元数据"网址[ http://go.microsoft.com/fwlink/?LinkId=196671 ](http://go.microsoft.com/fwlink/?LinkId=196671)。  
  
-   并非所有组合的元数据终结点绑定和服务终结点绑定都都有效。 在某些情况下，元数据终结点的绑定配置必须与其服务终结点的绑定配置一致。 例如，从接收位置所在的同一位置提供元数据时, 不能要求使用 HTTP 传输，如果接收位置使用依赖于 HTTPS 的安全模式下在安全模式下配置元数据终结点。  
  
    > [!NOTE]
    >  通过具有相同的位置，但需依赖于 HTTPS 传输，BizTalk WCF 发布向导生成，在 Web.config 文件中的安全模式的服务终结点的 HTTP 传输发布元数据时必须设置这两个**httpsGetEnabled**并**httpGetEnabled**向属性**true**。  
  
-   WCF 适配器利用的安全功能的 Windows Communication Foundation (WCF) 进行通信。 请务必了解的功能和 WCF 的在安全性方面的限制。 WCF 的安全功能的详细信息，请参阅"Windows Communication Foundation 安全"网址[ http://go.microsoft.com/fwlink/?LinkId=87806 ](http://go.microsoft.com/fwlink/?LinkId=87806)。  
  
## <a name="security-recommendations-for-the-isolated-wcf-adapters"></a>针对独立的 WCF 适配器的安全建议  
  
- 有关针对发布 Web 服务的安全建议，请参阅[启用 Web 服务](../core/enabling-web-services.md)。  
  
- 如 Wcf-customisolated、 Wcf-basichttp 和 Wcf-wshttp 适配器的独立的 WCF 适配器利用超文本传输协议 (HTTP) 来发送和接收消息与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 因此，必须遵循安全建议以确保 Internet 信息服务 (IIS)。  
  
- 当为独立的 WCF 接收位置创建应用程序池时，必须将其成员的帐户下运行配置[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]独立主机运行 WCF 接收适配器和 Internet 信息服务工作进程组进程组 （IIS_WPG 组）。 为 WCF 接收适配器以使用此帐户，然后必须配置的主机实例。 如果你更改了 IIS_WPG 组帐户，则必须确保也更新为新帐户下运行的主机实例。  
  
## <a name="security-recommendations-for-the-wcf-custom-adapter"></a>WCF 自定义适配器的安全建议  
  
-   如果 WCF 自定义接收位置正好在使用 HTTP 内核模式驱动程序 (HTTP.sys)，如**httpsTransport**安全套接字层 (SSL) 通信，接收位置的绑定元素必须具有证书为每个套接字 （IP 地址/端口组合） 注册。 使用 HttpCfg.exe 工具将 SSL 证书绑定到的计算机上的端口。 有关详细信息，请参阅"如何为：配置使用 SSL 证书的端口"处[ http://go.microsoft.com/fwlink/?LinkId=86384 ](http://go.microsoft.com/fwlink/?LinkId=86384)。  
  
## <a name="security-recommendations-for-the-wcf-netmsmq-adapter"></a>针对 Wcf-netmsmq 适配器的安全建议  
  
-   若要使用 Wcf-netmsmq 适配器，您必须在相同的方式作为对中配置 Wcf-netmsmq 适配器的 MSMQ 安全设置[netMsmqBinding](http://go.microsoft.com/fwlink/?LinkId=87813)。 有关如何配置 MSMQ 安全设置的详细信息**netMsmqBinding**，请参阅"故障排除已排队消息传递"处[ http://go.microsoft.com/fwlink/?LinkId=87816 ](http://go.microsoft.com/fwlink/?LinkId=87816)。  
  
## <a name="wcf-adapters-use-the-chaintrust-mode-to-validate-certificates"></a>WCF 适配器使用 ChainTrust 模式来验证证书。  
  
-   由于标准 WCF 接收适配器使用[ChainTrust](http://go.microsoft.com/fwlink/?LinkId=88960)模式来验证客户端和服务证书，必须安装 CA 证书链来验证 X.509 证书。 可以使用 Wcf-custom 或 Wcf-customisolated 适配器来更改此默认行为。  
  
## <a name="security-auditing-for-the-wcf-adapters"></a>WCF 适配器的安全审核  
  
- 默认情况下，WCF 适配器不使用 WCF 安全审核功能。 有几种方法来启用 WCF 适配器的 WCF 安全审核功能。 有关 WCF 安全审核功能的详细信息，请参阅"审核安全事件"处[ http://go.microsoft.com/fwlink/?LinkId=88975 ](http://go.microsoft.com/fwlink/?LinkId=88975)。  
  
- 若要使用 WCF 安全审核使用 Wcf-custom 接收适配器的功能，可以配置**ServiceSecurityAuditBehavior**为接收位置。  
  
- 对于进程内 WCF 适配器，可以通过 BTSNTSvc.exe.config 文件启用性能计数器。 对于独立 WCF 适配器，可以通过修改 BizTalk WCF 服务发布向导创建 Web 应用程序文件夹中的 Web.config 文件来启用 WCF 跟踪。 若要修改 BTSNtSvc.exe.config 或 Web.config，请打开配置文件，然后配置 WCF 跟踪，如下面的配置示例中所示：  
  
  > [!NOTE]
  >  BTSNTSvc.exe.config 文件始终与 BTSNTSvc.exe 文件，这通常是相同的目录中位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。  
  > 
  > [!NOTE]
  >  修改后的 BTSNTSvc.exe.config 文件，您必须重新启动主机实例运行的进程内 WCF 接收位置。  
  
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
  
- 此外可以使用如 Security Calls Not Authorized 的与安全相关的性能计数器来监视 WCF 适配器。 有关如何启用 WCF 性能计数器的详细信息，请参阅[WCF 适配器性能计数器](../core/wcf-adapters-performance-counters.md)。  
  
## <a name="see-also"></a>请参阅  
 [规划安全性](../core/planning-for-security.md)