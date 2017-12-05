---
title: "清单： 规划的安全环境中的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d6464df-6736-46e2-a0c7-cc2a256c5144
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c99c14f16df3f6b98555a4006706eb7804f24a34
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="checklist-planning-for-operations-in-a-secure-environment"></a>清单： 规划的安全环境中的操作
运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的安全环境中部署和配置需要额外的步骤。 虽然默认操作系统安装不需要考虑这些帐户，但方案其中已应用严格的安全策略，你应考虑到此部分中的帐户信息。 限制应用到服务器的级别可能不同，但以下信息应涵盖大多数情况下，并且会很好的起点。  
  
-   [有关运行 BizTalk Server 的计算机的安全注意事项](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_BTSSec)  
  
-   [有关运行 SQL Server 的计算机的安全注意事项](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_SQLServSec)  
  
-   [其他安全注意事项](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_AddSec)  
  
<a name="BKMK_BTSSec"></a>   
## <a name="security-considerations-for-computers-running-biztalk-server"></a>有关运行 BizTalk Server 的计算机的安全注意事项  
 下表提供的建议运行的计算机上与安全相关的设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
### <a name="user-rights-assignment"></a>用户权限分配  
 若要启动用户权限分配 MMC 管理单元中，单击**启动**，单击**管理工具**，然后单击**本地安全策略**。 在**本地安全策略**MMC 管理单元中，展开**安全设置**，展开**本地策略**，然后单击**用户权限分配**.  
  
|策略设置|值|引用和详细信息|  
|--------------------|------------|---------------------------|  
|作为服务登录|BizTalk Application Users|需要运行 BizTalk 主机实例。 有关不同的用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](http://go.microsoft.com/fwlink/?LinkID=155755)(http://go.microsoft.com/fwlink/?LinkID=155755)。|  
|作为服务登录|RuleEngine 更新服务帐户|需要运行 RuleEngine 更新服务。 有关不同的用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](http://go.microsoft.com/fwlink/?LinkID=155755)(http://go.microsoft.com/fwlink/?LinkID=155755)。|  
|作为服务登录|SSO 服务帐户|需要运行企业单一登录服务。 有关不同的用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](http://go.microsoft.com/fwlink/?LinkID=155755)(http://go.microsoft.com/fwlink/?LinkID=155755)。|  
  
### <a name="system-services"></a>系统服务  
 若要启动服务 MMC 管理单元中，单击**启动**，单击**运行**，然后在**运行**对话框中，键入`services.msc`，然后按 enter 键。  
  
|Service name|启动类型<sup>1</sup>|详细信息|用户<sup>2</sup>|Permissions|详细信息|  
|------------------|------------------------------|-------------|----------------------|-----------------|-------------|  
|COM+ System Application|自动|正常运行所需的 BizTalk|（默认值）|||  
|DHCP 客户端|自动|所需即使静态 IP 地址|（默认值）|||  
|分布式事务处理协调器|自动|正常运行所需的 BizTalk|SSO 服务帐户|完全控制|启动 SSO 服务所需|  
||||BizTalk 主机服务帐户|完全控制|启动 BizTalk 主机所需|  
||||Network Service|完全控制|所需的 IIS|  
|HTTP SSL<sup>3</sup>|自动|所需的 IIS|（默认值）|||  
|IPSEC 服务<sup>3</sup>|自动|如果使用 IPSEC 将增加网络安全|（默认值）|||  
|Netlogon|（默认值）||Local Service|完全控制||  
|NT LM 安全支持提供程序<sup>3</sup>|自动|所需的 Kerberos 身份验证以[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL 中|（默认值）|||  
|远程访问连接管理器|（默认值）||SSO 服务帐户|完全控制|启动 SSO 服务所需|  
||||BizTalk 主机服务帐户|完全控制|启动 BizTalk 主机所需|  
||||Network Service|完全控制|所需的 IIS|  
|远程过程调用 (RPC) 定位符|自动|所需的 BizTalk|（默认值）|||  
|WinHTTP Web 代理自动发现服务|（默认值）||SSO 服务帐户|完全控制|启动 SSO 服务所需|  
||||BizTalk 主机服务帐户|完全控制|启动 BizTalk 主机所需|  
  
 <sup>1</sup>值为 （默认值） 表示，由安全策略应用的默认设置未发生更改  
  
 <sup>2</sup> （默认值） 的值表示未更改服务的默认用户权限  
  
### <a name="registry-settings"></a>注册表设置  
 若要启动注册表编辑器，请单击**启动**，单击**运行**，然后在**运行**对话框中，键入`regedit`，然后按 enter 键。  
  
|Key|用户|Permissions|详细信息|  
|---------|----------|-----------------|-------------|  
|HKLM\ SYSTEM\CurrentControlSet\Services\DHCP|Network Service|完全控制|DHCP 客户端服务所需的|  
|HKLM\ SYSTEM\CurrentControlSet\Services\TCPIP|Network Service|完全控制|DHCP 客户端服务所需的|  
  
<a name="BKMK_SQLServSec"></a>   
## <a name="security-considerations-for-computers-running-sql-server"></a>有关运行 SQL Server 的计算机的安全注意事项  
 下表提供的建议运行的计算机上与安全相关的设置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
### <a name="user-rights-assignment"></a>用户权限分配  
 若要启动用户权限分配 MMC 管理单元中，单击**启动**，单击**管理工具**，然后单击**本地安全策略**。 在**本地安全策略**MMC 管理单元中，展开**安全设置**，展开**本地策略**，然后单击**用户权限分配**.  
  
|策略设置|值|引用和详细信息|  
|--------------------|------------|---------------------------|  
|以操作系统方式操作|SQL Server 代理服务帐户，SQL Server 服务帐户|运行所需[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(http://go.microsoft.com/fwlink/?LinkId=157415)。|  
|调整进程的内存配额|SQL Server 代理服务帐户，SQL Server 服务帐户|运行所需[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(http://go.microsoft.com/fwlink/?LinkId=157415)。|  
|跳过遍历检查|SQL Server 代理服务帐户，SQL Server 服务帐户|运行所需[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(http://go.microsoft.com/fwlink/?LinkId=157415)。|  
|创建全局对象|SQL Server 服务帐户|所需的 SSIS 服务。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(http://go.microsoft.com/fwlink/?LinkId=157415)。|  
|使计算机和用户帐户可以委派其他|SQL Server 服务帐户，SQL Server 服务器，BizTalk Server 服务器，SQL Server 群集名称|所需的 BizTalk Server。 服务器名称采用的形式\<servername\>$。 有关详细信息，请参阅[如何： 在 SQL Server 故障转移群集上启用 Kerberos 身份验证](http://go.microsoft.com/fwlink/?LinkId=157417)(http://go.microsoft.com/fwlink/?LinkId=157417)。|  
|作为服务登录|SQL Server 代理服务帐户，SQL Server 服务帐户|运行所需[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(http://go.microsoft.com/fwlink/?LinkId=157415)。|  
|作为服务登录|SSO 服务帐户|需要运行企业单一登录服务。 有关不同的用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](http://go.microsoft.com/fwlink/?LinkID=155755)(http://go.microsoft.com/fwlink/?LinkID=155755)。|  
|作为批处理作业登录|SQL Server 代理服务帐户，SQL Server 服务帐户|运行所需[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(http://go.microsoft.com/fwlink/?LinkId=157415)。|  
|替换进程级记号|SQL Server 代理服务帐户，SQL Server 服务帐户|运行所需[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息请参阅[设置 Windows 服务帐户](http://go.microsoft.com/fwlink/?LinkId=157415)(http://go.microsoft.com/fwlink/?LinkId=157415)。|  
  
### <a name="system-services"></a>系统服务  
 若要启动服务 MMC 管理单元中，单击**启动**，单击**运行**，然后在**运行**对话框中，键入`services.msc`，然后按 enter 键。  
  
|Service name|启动类型<sup>1</sup>|详细信息|用户<sup>2</sup>|Permissions|详细信息|  
|------------------|------------------------------|-------------|----------------------|-----------------|-------------|  
|DHCP 客户端|自动|所需即使静态 IP 地址|（默认值）|||  
|分布式事务处理协调器|Manual|服务启动后由群集服务|SSO 服务帐户|完全控制|启动 SSO 服务所需|  
||||Network Service|完全控制|所需的 IIS|  
|HTTP SSL<sup>3</sup>|自动|所需的 IIS|（默认值）|||  
|IPSEC 服务<sup>3</sup>|自动|如果使用 IPSEC 将增加网络安全|（默认值）|||  
|Netlogon|（默认值）||Local Service|完全控制||  
|NT LM 安全支持提供程序<sup>3</sup>|自动|所需的 Kerberos 身份验证以[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL 中|（默认值）|||  
|远程访问连接管理器|（默认值）||SSO 服务帐户|完全控制|启动 SSO 服务所需|  
||||Network Service|完全控制|所需的 IIS|  
|Server|自动|用于群集文件共享资源|Network Service|完全控制||  
|WinHTTP Web 代理自动发现服务|（默认值）||SSO 服务帐户|完全控制|启动 SSO 服务所需|  
||万维网发布服务|自动|所需的 SQL Server Reporting Services|（默认值）||  
  
 <sup>1</sup>值为 （默认值） 表示，由安全策略应用的默认设置未发生更改  
  
 <sup>2</sup> （默认值） 的值表示未更改服务的默认用户权限  
  
### <a name="registry-settings"></a>注册表设置  
 若要启动注册表编辑器，请单击**启动**，单击**运行**，然后在**运行**对话框中，键入`regedit`，然后按 enter 键。  
  
|Key|用户|Permissions|详细信息|  
|---------|----------|-----------------|-------------|  
|HKLM\ SYSTEM\CurrentControlSet\Services\DHCP|Network Service|完全控制|DHCP 客户端服务所需的|  
|HKLM\ SYSTEM\CurrentControlSet\Services\TCPIP|Network Service|完全控制|DHCP 客户端服务所需的|  
  
<a name="BKMK_AddSec"></a>   
## <a name="additional-security-considerations"></a>其他安全注意事项  
 下表提供的其他重要安全相关设置的建议你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
|受影响的项目|更改|引用和详细信息|  
|-----------------------|------------|---------------------------|  
|SSO 服务帐户|授予群集在群集管理器上的完全控制权限|此更改是必需的 SSO 才能正常工作|  
|SQL Server 服务帐户，SQL Server 服务器，BizTalk Server 服务器，SQL Server 群集名称|在 Active Directory 中的委派信任|所需的正确的 Kerberos 身份验证。 有关详细信息，请参阅[如何： 在 SQL Server 故障转移群集上启用 Kerberos 身份验证](http://go.microsoft.com/fwlink/?LinkId=157417)(http://go.microsoft.com/fwlink/?LinkId=157417)。|  
|SQL Server 服务帐户|授予权限来创建 SPN 条目|所需的正确的 Kerberos 身份验证。 有关详细信息，请参阅[如何在 SQL Server 中使用 Kerberos 身份验证](http://go.microsoft.com/fwlink/?LinkId=157420)(http://go.microsoft.com/fwlink/?LinkId=157420)。|  
|SQL Server 节点，SQL 群集名称|创建用户 SQL Server 服务帐户的 SPN 条目|所需的正确的 Kerberos 身份验证。 有关详细信息，请参阅[如何在 SQL Server 中使用 Kerberos 身份验证](http://go.microsoft.com/fwlink/?LinkId=157420)(http://go.microsoft.com/fwlink/?LinkId=157420)。|  
|SQL 网络名称群集资源|DNS 注册必须成功，启用 Kerberos 身份验证|所需的正确的 Kerberos 身份验证|  
|SQL Server 外围配置|启用远程直接管理员连接|所需的 SQL Browser 服务才能正常工作所需的 SQL 客户端 (BizTalk/ASP.NET) 以便正确地找到了 SQL Server 命名实例|  
|BizTalk 应用程序用户组|授予执行权限**sp_help_jobhistory**中**msdb**数据库|所需的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
  
## <a name="see-also"></a>另请参阅  
 [其他重要任务清单](~/technical-guides/checklists-for-other-important-tasks.md)