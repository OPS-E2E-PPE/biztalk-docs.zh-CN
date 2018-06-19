---
title: 故障排除 SharePoint 服务适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f88174-118d-4ed6-8449-c89ca195ce5c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f9885696df24cd5c5f8321ad3c6dd79d444559a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280229"
---
# <a name="troubleshooting-sharepoint-services-adapter"></a>SharePoint Services 适配器故障排除
本主题主要介绍 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) 适配器的疑难解答。  
  
## <a name="installation"></a>安装  
 当使用 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) 适配器时，有以下两个选项：  
  
|||  
|-|-|  
|**使用客户端 OM**设置为**是**。|**推荐**。 如果设置为“是”，则使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 客户端对象模型 (CSOM)。 此适配器将随 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起安装。 没有其他安装步骤。 **注意：** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装还将自动安装 SharePoint 客户端对象模型可再发行组件在[http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482)。|  
|**使用客户端 OM**设置为**否**。|**已弃用**。 使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 服务端对象模型 (SSOM)。<br /><br /> 该 Web 服务安装在 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 计算机上，既可以和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在同一计算机上，也可以在单独的计算机上。<br /><br /> 若要安装 web 服务，运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的安装[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]计算机并检查**Windows SharePoint Services Adapter**。 请参阅[附录 b： 安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)有关特定的安装步骤。|  
  
 **使用客户端 OM**设置为**是**建议。 当设置为**是**，SharePoint 计算机上未安装 web 服务。 如果想要使用的 web 服务选项，则必须设置**使用客户端 OM**到**否**上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="iis"></a>IIS  
 **BTSharePointAdapterWS.asmx web 服务**  
  
 在 SharePoint 计算机上安装 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] 适配器后，将在该 SharePoint 计算机上的 IIS 中创建 BTSharePointAdapterWS.asmx Web 服务。 通常，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 SharePoint 安装在不同计算机上。 当安装 SharePoint 时，内容 SQL 数据库可以位于 SharePoint 计算机本地，也可以位于远程 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 上。  
  
 **应用程序池使用域帐户**  
  
 当 BizTalk 和 SharePoint 位于不同计算机上时，运行 BTSharePointAdapterWS.asmx Web 服务的 IIS 应用程序池必须使用域帐户。 如果全部在同一计算机上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、BizTalk 数据库、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SharePoint 数据库，则可以使用本地帐户。  
  
 **双跃点方案**  
  
 当涉及三台计算机（[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]）时，可以使用一个需要 Kerberos 身份验证的双跃点方案。 BizTalk 计算机上的 SharePoint 适配器向 SharePoint 计算机上的 BTSharePointAdapterWS.asmx Web 服务提出一个 POST 请求。 然后，SharePoint 计算机查询其在 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 计算机上的数据库。  
  
 这个来自 BizTalk 适配器的 POST 请求必须成功完成。 如果你怀疑某个身份验证失败，请查阅 IIS 日志。 默认情况下，IIS 日志处于 c:\inetpub\logs\LogFiles\W3SVC*x*。 该 POST 请求应显示 200（成功）状态码。 如果返回失败的状态代码，如跟 401.1，由另一个 4 以下 401.2*xx*错误，然后身份验证可能会失败。  
  
 当使用 Kerberos 身份验证时，将需要服务主体名称 (SPN)，并且必须启用委派。  
  
## <a name="enable-kerberos-authentication"></a>启用 Kerberos 身份验证  
 在双跃点方案中，需要 Kerberos 身份验证并启用委派。 相关步骤包括：  
  
1.  启用**Negotiate** IIS/SharePoint 服务器上。 [215383： 如何将 IIS 配置为支持 Kerberos 协议和 NTLM 协议的网络身份验证](http://support.microsoft.com/kb/215383)列出的步骤。  
  
2.  执行 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 服务的域帐户和 IIS/SharePoint 计算机上的应用程序池需要服务主体名称 (SPN)。 若要创建 SPN，请使用 SetSPN.exe 命令行工具：  
  
     [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]:[有可用的 Windows Server 2003 中的 Setspn.exe 的更新](http://support.microsoft.com/kb/970536)  
  
     [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]8， [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]和[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]: [SetSPN](http://technet.microsoft.com/library/cc731241.aspx)  
  
    > [!IMPORTANT]
    >  SetSPN 需要域管理员权限，并且可以从域中的任何计算机上执行。  
  
     若要返回注册到某个域帐户的所有 SPN 的列表，请执行以下操作：  
  
    ```  
    setspn.exe -l Domain\UserAccount  
    ```  
  
     创建 SPN：  
  
    1.  为 IIS/SharePoint 计算机的 FQDN 创建 SPN：  
  
        ```  
        setspn.exe -s http/IISSharePointComputerName.domain.com domain\IISApplicationPoolDomainAccount  
        ```  
  
    2.  为 IIS/SharePoint 计算机的 NETBIOS 名称创建 SPN：  
  
        ```  
        setspn.exe -s http/IISSharePointComputerNamedomain\IISApplicationPoolDomainAccount  
        ```  
  
    3.  为 IIS/SharePoint 计算机使用的 SQL Server 计算机的 FQDN 创建 SPN：  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerName.domain.com domain\SQLServerServiceDomainAccount  
        ```  
  
    4.  为 IIS/SharePoint 计算机使用的 SQL Server 计算机的 FQDN 和 TCP 端口创建 SPN：  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerName.domain.com:1433 domain\SQLServerServiceDomainAccount  
        ```  
  
    5.  为 IIS/SharePoint 计算机使用的 SQL Server 计算机的 NETBIOS 名称创建 SPN：  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerNamedomain\SQLServerServiceDomainAccount  
        ```  
  
    6.  为 IIS/SharePoint 计算机使用的 SQL Server 计算机的 NETBIOS 名称:TCP 端口创建 SPN：  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerName:1433 domain\SQLServerServiceDomainAccount  
        ```  
  
3.  在域控制器上，转到**Active Directory 用户和计算机**和执行以下操作：  
  
    1.  检查**信任此计算机来委派任何服务**以下计算机：  
  
        -   SharePoint/IIS 服务器  
  
        -   由 SharePoint 使用的 SQL Server  
  
    2.  检查**帐户信任其委派**并取消选中**敏感帐户，不能被委派**以下的域帐户：  
  
        -   SQL Server 服务域帐户  
  
        -   IIS 应用程序池域帐户  
  
 有关其他故障排除，请转到[疑难解答 Windows SharePoint Services Adapter](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)  
  
## <a name="see-also"></a>另请参阅  
 [配置 SharePoint 服务接收位置](../core/configure-sharepoint-services-receive-location.md)   
 [配置 SharePoint Services 发送端口](../core/configure-sharepoint-services-send-port.md)   
 [CSOM: SharePoint Services Adapter](../core/csom-sharepoint-services-adapter.md)