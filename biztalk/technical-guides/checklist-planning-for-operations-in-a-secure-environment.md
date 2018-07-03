---
title: 清单： 规划在安全环境中的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d6464df-6736-46e2-a0c7-cc2a256c5144
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9caa74fbd3e9ac06728a9e2ee332bb3277f8a240
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995918"
---
# <a name="checklist-planning-for-operations-in-a-secure-environment"></a>清单： 规划在安全环境中的操作
运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在安全环境中部署和配置需要额外的步骤。 虽然默认的操作系统安装不需要考虑这些帐户，但方案已在其中应用严格的安全策略，您应考虑到本部分中的帐户信息。 限制应用到的服务器上的级别可能不同，但以下信息应涵盖大多数情况下，并且会很好的起点。  

-   [运行 BizTalk Server 的计算机的安全注意事项](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_BTSSec)  

-   [有关运行 SQL Server 的计算机的安全注意事项](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_SQLServSec)  

-   [其他安全注意事项](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_AddSec)  

<a name="BKMK_BTSSec"></a>   
## <a name="security-considerations-for-computers-running-biztalk-server"></a>运行 BizTalk Server 的计算机的安全注意事项  
 下表所示运行的计算机上与安全相关的设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

### <a name="user-rights-assignment"></a>用户权限分配  
 若要启动用户权限分配 MMC 管理单元中，单击**启动**，单击**管理工具**，然后单击**本地安全策略**。 在中**本地安全策略**MMC 管理单元中，展开**安全设置**，展开**本地策略**，然后单击**用户权限分配**.  

|策略设置|值|引用和详细信息|  
|--------------------|------------|---------------------------|  
|作为服务登录|BizTalk Application Users|运行 BizTalk 主机实例所必需。 有关不同的用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](http://go.microsoft.com/fwlink/?LinkID=155755)(http://go.microsoft.com/fwlink/?LinkID=155755)。|  
|作为服务登录|RuleEngine 更新服务帐户|需要运行 RuleEngine 更新服务。 有关不同的用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](http://go.microsoft.com/fwlink/?LinkID=155755)(http://go.microsoft.com/fwlink/?LinkID=155755)。|  
|作为服务登录|SSO 服务帐户|需要运行企业单一登录服务。 有关不同的用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](http://go.microsoft.com/fwlink/?LinkID=155755)(http://go.microsoft.com/fwlink/?LinkID=155755)。|  

### <a name="system-services"></a>系统服务  
 若要启动服务 MMC 管理单元中，单击**启动**，单击**运行**，然后在**运行**对话框中，键入`services.msc`然后按 ENTER。  


|                Service name                 | 启动类型<sup>1</sup> |                                                              详细信息                                                               |       用户<sup>2</sup>        | 权限  |             详细信息             |
|---------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------------------------------|-------------------------------|--------------|---------------------------------|
|           COM+ System Application           |        自动         |                                                BizTalk 要求才能正常运行                                                 |           （默认值）           |              |                                 |
|                 DHCP 客户端                 |        自动         |                                              如果即使是静态的 IP 地址被必需的                                              |           （默认值）           |              |                                 |
|     分布式事务处理协调器     |        自动         |                                                BizTalk 要求才能正常运行                                                 |      SSO 服务帐户      | 完全控制 |  需启动 SSO 服务  |
|                                             |                          |                                                                                                                                    | BizTalk 主机服务帐户 | 完全控制 | 启动 BizTalk 主机所需 |
|                                             |                          |                                                                                                                                    |        Network Service        | 完全控制 |         所需的 IIS         |
|            HTTP SSL<sup>3</sup>             |        自动         |                                                          所需的 IIS                                                           |           （默认值）           |              |                                 |
|         IPSEC 服务<sup>3</sup>          |        自动         |                                              IPSEC 可提高网络安全性，如果使用                                              |           （默认值）           |              |                                 |
|                  Netlogon                   |        （默认值）         |                                                                                                                                    |         Local Service         | 完全控制 |                                 |
| NT LM 安全支持提供商<sup>3</sup> |        自动         | 有关 Kerberos 身份验证所需[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL 中 |           （默认值）           |              |                                 |
|      远程访问连接管理器       |        （默认值）         |                                                                                                                                    |      SSO 服务帐户      | 完全控制 |  需启动 SSO 服务  |
|                                             |                          |                                                                                                                                    | BizTalk 主机服务帐户 | 完全控制 | 启动 BizTalk 主机所需 |
|                                             |                          |                                                                                                                                    |        Network Service        | 完全控制 |         所需的 IIS         |
|     远程过程调用 (RPC) 定位符     |        自动         |                                                        所需的 BizTalk                                                         |           （默认值）           |              |                                 |
|  WinHTTP Web 代理自动发现服务   |        （默认值）         |                                                                                                                                    |      SSO 服务帐户      | 完全控制 |  需启动 SSO 服务  |
|                                             |                          |                                                                                                                                    | BizTalk 主机服务帐户 | 完全控制 | 启动 BizTalk 主机所需 |

 <sup>1</sup> （默认值） 的值表示不更改应用的安全策略的默认设置  

 <sup>2</sup> （默认值） 的值表示尚未更改该服务的默认用户权限  

### <a name="registry-settings"></a>注册表设置  
 若要启动注册表编辑器，请单击**启动**，单击**运行**，然后在**运行**对话框中，键入`regedit`然后按 ENTER。  

|Key|用户|权限|详细信息|  
|---------|----------|-----------------|-------------|  
|HKLM\ SYSTEM\CurrentControlSet\Services\DHCP|Network Service|完全控制|DHCP 客户端服务所必需的|  
|HKLM\ SYSTEM\CurrentControlSet\Services\TCPIP|Network Service|完全控制|DHCP 客户端服务所必需的|  

<a name="BKMK_SQLServSec"></a>   
## <a name="security-considerations-for-computers-running-sql-server"></a>有关运行 SQL Server 的计算机的安全注意事项  
 下表所示运行的计算机上与安全相关的设置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  

### <a name="user-rights-assignment"></a>用户权限分配  
 若要启动用户权限分配 MMC 管理单元中，单击**启动**，单击**管理工具**，然后单击**本地安全策略**。 在中**本地安全策略**MMC 管理单元中，展开**安全设置**，展开**本地策略**，然后单击**用户权限分配**.  


|                         策略设置                         |                                             值                                              |                                                                                                                             引用和详细信息                                                                                                                             |
|----------------------------------------------------------------|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              以操作系统方式操作               |                  SQL Server 代理服务帐户，SQL Server 服务帐户                   |         运行所需[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。          |
|               调整进程的内存配额               |                   SQL Server 代理服务帐户，SQL Server 服务帐户                   |         运行所需[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。          |
|                    跳过遍历检查                    |                   SQL Server 代理服务帐户，SQL Server 服务帐户                   |         运行所需[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。          |
|                     创建全局对象                      |                                   SQL Server 服务帐户                                    |                                          所需的 SSIS 服务。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。                                           |
| 使计算机和用户帐户以进行受信任可以进行委派 | SQL Server 服务帐户，SQL Server 服务器，BizTalk Server 服务器，SQL Server 群集名称 | BizTalk Server 所需。 服务器名称是在窗体\<servername\>$。 有关详细信息，请参阅[如何： 在 SQL Server 故障转移群集上启用 Kerberos 身份验证](http://go.microsoft.com/fwlink/?LinkId=157417)(<http://go.microsoft.com/fwlink/?LinkId=157417>)。 |
|                      作为服务登录                       |                   SQL Server 代理服务帐户，SQL Server 服务帐户                   |         运行所需[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。          |
|                      作为服务登录                       |                                       SSO 服务帐户                                       |       需要运行企业单一登录服务。 有关不同的用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](http://go.microsoft.com/fwlink/?LinkID=155755)(<http://go.microsoft.com/fwlink/?LinkID=155755>)。       |
|                      作为批处理作业登录                       |                   SQL Server 代理服务帐户，SQL Server 服务帐户                   |         运行所需[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。          |
|                 替换进程级记号                  |                   SQL Server 代理服务帐户，SQL Server 服务帐户                   |         运行所需[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。          |

### <a name="system-services"></a>系统服务  
 若要启动服务 MMC 管理单元中，单击**启动**，单击**运行**，然后在**运行**对话框中，键入`services.msc`然后按 ENTER。  


|                Service name                 |     启动类型<sup>1</sup>      |                                                              详细信息                                                               |             用户<sup>2</sup>              | 权限  |            详细信息            |
|---------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|--------------|-------------------------------|
|                 DHCP 客户端                 |             自动             |                                              如果即使是静态的 IP 地址被必需的                                              |                 （默认值）                 |              |                               |
|     分布式事务处理协调器     |              Manual               |                                             服务启动群集服务管理                                             |            SSO 服务帐户            | 完全控制 | 需启动 SSO 服务 |
|                                             |                                   |                                                                                                                                    |              Network Service              | 完全控制 |        所需的 IIS        |
|            HTTP SSL<sup>3</sup>             |             自动             |                                                          所需的 IIS                                                           |                 （默认值）                 |              |                               |
|         IPSEC 服务<sup>3</sup>          |             自动             |                                              IPSEC 可提高网络安全性，如果使用                                              |                 （默认值）                 |              |                               |
|                  Netlogon                   |             （默认值）             |                                                                                                                                    |               Local Service               | 完全控制 |                               |
| NT LM 安全支持提供商<sup>3</sup> |             自动             | 有关 Kerberos 身份验证所需[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL 中 |                 （默认值）                 |              |                               |
|      远程访问连接管理器       |             （默认值）             |                                                                                                                                    |            SSO 服务帐户            | 完全控制 | 需启动 SSO 服务 |
|                                             |                                   |                                                                                                                                    |              Network Service              | 完全控制 |        所需的 IIS        |
|                   “服务器”                    |             自动             |                                              用于群集文件共享资源                                               |              Network Service              | 完全控制 |                               |
|  WinHTTP Web 代理自动发现服务   |             （默认值）             |                                                                                                                                    |            SSO 服务帐户            | 完全控制 | 需启动 SSO 服务 |
|                                             | 万维网发布服务 |                                                             自动                                                              | 所需的 SQL Server Reporting Services |  （默认值）   |                               |

 <sup>1</sup> （默认值） 的值表示不更改应用的安全策略的默认设置  

 <sup>2</sup> （默认值） 的值表示尚未更改该服务的默认用户权限  

### <a name="registry-settings"></a>注册表设置  
 若要启动注册表编辑器，请单击**启动**，单击**运行**，然后在**运行**对话框中，键入`regedit`然后按 ENTER。  

|Key|用户|权限|详细信息|  
|---------|----------|-----------------|-------------|  
|HKLM\ SYSTEM\CurrentControlSet\Services\DHCP|Network Service|完全控制|DHCP 客户端服务所必需的|  
|HKLM\ SYSTEM\CurrentControlSet\Services\TCPIP|Network Service|完全控制|DHCP 客户端服务所必需的|  

<a name="BKMK_AddSec"></a>   
## <a name="additional-security-considerations"></a>其他安全注意事项  
 下表所示的其他重要的安全性设置为你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  


|                                        受影响的项目                                        |                                 更改                                  |                                                                                                               引用和详细信息                                                                                                                |
|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                       SSO 服务帐户                                       |       在群集管理器中群集上的完全控制权限授予       |                                                                                             此更改才能正常工作是所必需的 SSO                                                                                              |
| SQL Server 服务帐户，SQL Server 服务器，BizTalk Server 服务器，SQL Server 群集名称 |                在 Active Directory 中委派信任                 | 所需的适当的 Kerberos 身份验证。 有关详细信息，请参阅[如何： 在 SQL Server 故障转移群集上启用 Kerberos 身份验证](http://go.microsoft.com/fwlink/?LinkId=157417)(<http://go.microsoft.com/fwlink/?LinkId=157417>)。 |
|                                   SQL Server 服务帐户                                    |                 授予创建 SPN 条目的权限                  |            所需的适当的 Kerberos 身份验证。 有关详细信息，请参阅[如何在 SQL Server 中使用 Kerberos 身份验证](http://go.microsoft.com/fwlink/?LinkId=157420)(<http://go.microsoft.com/fwlink/?LinkId=157420>)。             |
|                               SQL Server 节点，SQL 群集名称                                |         创建用户 SQL Server 服务帐户的 SPN 条目          |            所需的适当的 Kerberos 身份验证。 有关详细信息，请参阅[如何在 SQL Server 中使用 Kerberos 身份验证](http://go.microsoft.com/fwlink/?LinkId=157420)(<http://go.microsoft.com/fwlink/?LinkId=157420>)。             |
|                               SQL 网络名称群集资源                                |     DNS 注册必须成功，启用 Kerberos 身份验证      |                                                                                                    所需的适当的 Kerberos 身份验证                                                                                                     |
|                                SQL Server 应用配置                                 |              启用远程管理员直接连接              |                                           所需的 SQL Browser 服务才能正常运行所必需的 SQL 客户端 (BizTalk/ASP.NET) 才能正确地找到 SQL Server 命名实例                                           |
|                                 BizTalk 应用程序用户组                                 | 授予 Execute 权限**sp_help_jobhistory**中**msdb**数据库 |                                                                           所需的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                           |

## <a name="see-also"></a>请参阅  
 [其他重要任务清单](~/technical-guides/checklists-for-other-important-tasks.md)