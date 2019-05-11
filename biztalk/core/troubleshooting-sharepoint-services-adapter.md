---
title: 故障排除 SharePoint Services 适配器 |Microsoft Docs
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
ms.openlocfilehash: d1f3c4e3740d2fb73cde2cc71426e109f7534fa7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306482"
---
# <a name="troubleshooting-sharepoint-services-adapter"></a>SharePoint Services 适配器故障排除
本主题重点介绍故障排除[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)](WSS) 适配器。  

## <a name="installation"></a>安装  
 当使用[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)](WSS) 适配器，有两个选项：  


|                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **使用客户端 OM**设置为**是**。 |                                                                                                                                     **建议**。 当设置为 Yes，[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]使用客户端对象模型 (CSOM)。 此适配器将随 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起安装。 没有其他安装步骤。 **注意：** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装还会自动安装 SharePoint 客户端对象模型可再发行的网址[ http://go.microsoft.com/fwlink/p/?LinkId=263482 ](http://go.microsoft.com/fwlink/p/?LinkId=263482)。                                                                                                                                     |
| **使用客户端 OM**设置为**否**。  | **已弃用**。 使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 服务端对象模型 (SSOM)。<br /><br /> Web 服务安装在[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]可以是同一台计算机的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或在单独的计算机。<br /><br /> 若要安装该 Web 服务，请在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上运行 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 安装，然后检查 **Windows SharePoint Services 适配器**。 请参阅[附录 b:安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)了解特定安装步骤。 |

 **使用客户端 OM**设置为**是**建议。 如果设置为**是**，SharePoint 计算机上未安装 web 服务。 如果想要使用的 web 服务选项，则必须设置**使用客户端 OM**到**否**上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

## <a name="iis"></a>IIS  
 **BTSharePointAdapterWS.asmx web 服务**  

 当[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]适配器安装在 SharePoint 计算机上，在 SharePoint 计算机上在 IIS 中创建 BTSharePointAdapterWS.asmx web 服务。 通常情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SharePoint 安装在不同计算机上。 安装 SharePoint 时，内容 SQL 数据库可以是 SharePoint 计算机或远程计算机上本地[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  

 **应用程序池使用域帐户**  

 当 BizTalk 和 SharePoint 位于不同的计算机上时，运行 BTSharePointAdapterWS.asmx web 服务的 IIS 应用程序池必须使用域帐户。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，BizTalk 数据库[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]SharePoint 数据库所有安装在同一台计算机上，则可以使用本地帐户。  

 **双跃点方案**  

 当涉及三台计算机 ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)])，没有需要 Kerberos 身份验证的双跃点方案。 BizTalk 计算机上的 SharePoint 适配器会对 SharePoint 计算机上的 BTSharePointAdapterWS.asmx web 服务的 POST 请求。 SharePoint 计算机然后查询它的数据库上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  

 这样的 BizTalk 适配器的 POST 请求必须成功完成。 如果你怀疑身份验证失败，请查看 IIS 日志。 默认情况下，IIS 日志位于 c:\inetpub\logs\LogFiles\W3SVC*x*。 POST 请求应显示 200 （成功） 状态代码。 如果返回失败的状态代码，如 401.2，跟以下由另一个 4 401.1*xx*错误，则身份验证可能会失败。  

 当使用 Kerberos 身份验证时，服务主体名称 (SPN) 需要并且必须启用委派。  

## <a name="enable-kerberos-authentication"></a>启用 Kerberos 身份验证  
 在双跃点方案中，则需要 Kerberos 身份验证和启用委派。 步骤包括：  

1. 启用**Negotiate** IIS/SharePoint 服务器上。 [215383:如何配置 IIS 以用于网络身份验证支持 Kerberos 协议和 NTLM 协议](http://support.microsoft.com/kb/215383)列出的步骤。  

2. 服务主体名称 (Spn) 所需执行的域帐户[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]服务和 IIS/SharePoint 计算机上的应用程序池。 若要创建 SPN，请使用 SetSPN.exe 命令行工具：  

    [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]设置用户帐户 ：[有可用的 Windows Server 2003 中的 Setspn.exe 更新](http://support.microsoft.com/kb/970536)  

    [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] 8 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]和[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]:[SetSPN](http://technet.microsoft.com/library/cc731241.aspx)  

   > [!IMPORTANT]
   >  SetSPN 需要域管理员权限，并且可以从域中的任何计算机执行。  

    若要返回的所有注册到域帐户的 Spn 的列表：  

   ```  
   setspn.exe -l Domain\UserAccount  
   ```  

    创建 Spn:  

   1.  为 IIS/SharePoint 计算机的 fqdn 创建 SPN:  

       ```  
       setspn.exe -s http/IISSharePointComputerName.domain.com domain\IISApplicationPoolDomainAccount  
       ```  

   2.  创建 IIS/SharePoint 计算机的 NETBIOS 名称的 SPN:  

       ```  
       setspn.exe -s http/IISSharePointComputerNamedomain\IISApplicationPoolDomainAccount  
       ```  

   3.  为 IIS/SharePoint 计算机使用的 SQL Server 计算机的 FQDN 创建 SPN:  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerName.domain.com domain\SQLServerServiceDomainAccount  
       ```  

   4.  FQDN 和 IIS/SharePoint 计算机使用的 SQL Server 计算机的 TCP 端口创建 SPN:  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerName.domain.com:1433 domain\SQLServerServiceDomainAccount  
       ```  

   5.  创建 IIS/SharePoint 计算机使用的 SQL Server 计算机的 NETBIOS 名称的 SPN:  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerNamedomain\SQLServerServiceDomainAccount  
       ```  

   6.  创建 IIS/SharePoint 计算机使用的 SQL Server 计算机的 NETBIOS 名称： TCP 端口的 SPN:  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerName:1433 domain\SQLServerServiceDomainAccount  
       ```  

3. 在域控制器上转到**Active Directory 用户和计算机**并执行以下操作：  

   1.  检查**信任此计算机来委派任何服务**以下计算机：  

       -   SharePoint/IIS 服务器  

       -   使用 SharePoint 的 SQL Server  

   2.  检查**帐户受信任为委派**并取消选中**敏感帐户，不能被委派**对于以下域帐户：  

       -   SQL Server 服务域帐户  

       -   IIS 应用程序池域帐户  

   有关其他故障排除，请转到[Windows SharePoint Services 适配器故障排除](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)  

## <a name="see-also"></a>请参阅  
 [配置 SharePoint Services 接收位置](../core/configure-sharepoint-services-receive-location.md)   
 [配置 SharePoint Services 发送端口](../core/configure-sharepoint-services-send-port.md)   
 [CSOM:SharePoint Services Adapter](../core/csom-sharepoint-services-adapter.md)