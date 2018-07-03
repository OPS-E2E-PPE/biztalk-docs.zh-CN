---
title: 安装 BizTalk Server 2013 和 2013 R2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b4665ea-6f2c-477f-98ec-1cebef05ad4a
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 849106d0a64df6520e25ccf35b50c78a60ea9749
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970590"
---
# <a name="install-biztalk-server-2013-and-2013-r2"></a>安装 BizTalk Server 2013 和 2013 R2
列出安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的步骤。  

## <a name="before-you-get-started"></a>开始操作之前

- **帐户名** – 应尽可能使用默认帐户名。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序会自动输入默认帐户。 如果域中存在多个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组，应更改帐户名，以避免冲突。 如果更改名称，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仅支持\< *NetBIOS 域名*\>\\<*用户*\>服务帐户和 Windows 组。  

- **带有 BAM 管理 Web Service 的帐户名称** – [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持 BAM 管理 Web Service 用户使用内置帐户或无密码的帐户。 Web 服务会访问 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库，而此类帐户可能带来安全威胁。  

  > [!NOTE]
  >  为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置此类帐户可能会成功，但是 BAM 管理 Web Service 会发生故障。 可以对 BAM 应用程序池使用内置帐户或无密码的帐户。  

- **BizTalk 程序集查看器** – 在 64 位平台上不受支持。  

- **安装和卸载** – 卸载 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 需要手动删除 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库。 如果你是以开发人员或评估师身份安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请使用虚拟机。 如果需要进行重新安装，可以轻松回滚虚拟机，而无需卸载和删除数据库。  

- **32 位和 64 位计算机** – 在 32 位与 64 位计算机上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 之间的差异较少。 安装和配置对 32 位和 64 位计算机均适用。 将介绍两者之间的差别。  

- **工作组** - 支持在单台计算机上的工作组环境中安装和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 SQL Server 和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的功能和组件在同一计算机上安装和配置。  

- **终端服务器** – 不支持使用在应用程序模式下运行的终端服务器安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 请参阅 [KB 832027](http://support.microsoft.com/kb/832027)。  

- **BAM 门户** - 如果 BAM 门户配置在某个网站上，而该网站由运行 .NET Framework 2.0 的应用程序使用，则应为 BAM 门户新建一个网站：  

   [创建 IIS 7 网站](http://technet.microsoft.com/library/cc772350\(WS.10\).aspx)  

   [创建 IIS 8 网站](http://technet.microsoft.com/library/hh831515.aspx)  

   在创建新网站之后，请执行以下操作：  

  1. 打开“[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置”。  

  2. 配置 BAM 门户并从“BAM 门户网站”列表中选择新网站。  

- **社区补充内容**：阅读：  

   [BizTalk Server 中的主动性](http://msdn.microsoft.com/library/dn393929\(v=bts.10\).aspx)  

   [BizTalk Server 2013 R2：安装和配置 – 设置服务器前的重要注意事项（第 1 部分）](http://sandroaspbiztalkblog.wordpress.com/2015/01/04/biztalk-server-2013-r2-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)  

##  <a name="BKMK_Install"></a> 安装 BizTalk Server  

1. 关闭所有打开的程序。 以管理员身份运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序。  

2. 在“开始”中，选择“安装 Microsoft BizTalk Server”。  

3. 在“客户信息”中，输入用户名、组织、产品密钥，然后选择“下一步”。  

4. 在“许可协议”中，接受许可协议，然后选择“下一步”。  

5. 在“客户体验改善计划”中，选择你是否希望参与该计划，然后选择“下一步”。  

    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 参与了客户体验改善计划。 你可以选择就 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的功能使用情况报告功能向 Microsoft 提供有用的反馈。 收集的数据是匿名的，不能用来识别您的身份。 Microsoft 会作为此计划的一部分来收集功能使用情况统计信息。 通过参与此计划，你可以帮助提高 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的各种功能的可靠性和性能。 若要深入了解此计划及其隐私策略，请参阅 [Microsoft BizTalk Server CEIP 隐私策略](http://go.microsoft.com/fwlink/p/?LinkId=188553)。  

6. 在“组件安装”中，查看可用组件，然后选择要安装的组件：  


   |                             功能                             |                                                                                                                                                                                                                                                                                                                                                                                                               Description                                                                                                                                                                                                                                                                                                                                                                                                                |
   |-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                        **文档**                        |                                                                                                                                                                                                                                                                                                                                                 核心文档、教程、用户界面参考（F1 帮助）、程序员参考，以及 SDK 示例和实用程序的使用说明。                                                                                                                                                                                                                                                                                                                                                 |
   |                       **服务器运行时**                        |                                                                                                                                                                                                                                                                                                                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的基本运行时服务。                                                                                                                                                                                                                                                                                                                                                          |
   |                   **BizTalk EDI/AS2 运行时**                   |                                                                                                                                                                                                                                                                                      运行时服务为电子数据交换 (EDI) 数据交换和 Applicability Statement 2 (AS2) 数据传输消息传送功能提供本机支持。 **注意：** 只有选择了“服务器运行时”功能时，才能选择此功能。                                                                                                                                                                                                                                                                                       |
   |   **Windows Communication Foundation (WCF) 适配器运行时**    |                                                                                                                                                                                                                                                                                                   允许 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与基于 WCF 的应用程序进行通信的适配器。 **注意：** 只有选择了“服务器运行时”功能时，才能选择此功能。                                                                                                                                                                                                                                                                                                   |
   |                      **门户组件**                      |                                                                                                                                                                                                                                                                                                                                               “门户”组件是一组功能，业务分析师使用业务数据通过这些功能进行通信、协作并达成决定。                                                                                                                                                                                                                                                                                                                                                |
   |                **业务活动监视**                 |                                                                                                                                                                                                                                                                         也称为 BAM，这组功能可为业务用户提供其异构业务流程的实时视图，帮助其做出重要的业务决策。 **注意：** 只有选择了“门户组件”功能时，才能选择此功能。                                                                                                                                                                                                                                                                          |
   |             **管理工具和监视**             |                                                                                                                                                                                                                                                                                                                            在本地计算机和远程服务器上管理和监视 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 所必需的组件。                                                                                                                                                                                                                                                                                                                             |
   | **Windows Communication Foundation (WCF) 管理工具** |                                                                                                                                                                                                                                                                                                                         选择此功能将安装用于 WCF 组件的管理服务。 **注意：** 只有选择了“管理工具和监视”功能时，才能选择此功能。                                                                                                                                                                                                                                                                                                                         |
   |                   **开发人员工具和 SDK**                   |                                                                                                                                   用于快速创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 解决方案的示例和实用程序。 其中包括：SDK 示例和支持文档、架构和映射设计器，以及 Visual Studio 项目模板。 **重要提示：** 如果计划进行任何开发工作，则必须安装此组件。 若未安装**开发人员工具和 SDK** 组件，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用的 Visual Studio 扩展将无法正常工作。                                                                                                                                    |
   |                    ***其他软件***                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   |    **企业单一登录 (SSO) 管理模块**    |                                                                                                                                                                                                                                                                                                                                                                                管理 SSO 关联应用程序及其映射的界面。                                                                                                                                                                                                                                                                                                                                                                                 |
   |       **企业单一登录主密钥服务器**        |                                                                                                                                                                                                                                                                                   存储主密钥的 SSO 服务器。 系统中的所有其他 SSO 服务器均从此服务器获取该主密钥。 主密钥服务器在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中是必需的。                                                                                                                                                                                                                                                                                    |
   |                  **业务规则组件**                  |                                                                                                                                                                                                                                                                                                                                                                                 用于撰写策略以备业务规则引擎使用。                                                                                                                                                                                                                                                                                                                                                                                 |
   |                       **MQSeries 代理**                        |                                                                                                                                                                                                                                                                                                                                                                     为用于 MQSeries 的 BizTalk 适配器和用于 Windows 的 MQSeries 服务器之间提供了通信。                                                                                                                                                                                                                                                                                                                                                                     |
   |       **Windows SharePoint Services 适配器 Web Service**       | **已弃用**。 使用在 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 计算机上安装的 IIS Web 服务，[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 适配器可处理通过 Microsoft SharePoint 传入和传出的文档。<br /><br /> **建议**：**不要**安装。 默认情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中自动安装的可再发行的 SharePoint 客户端对象模型 (CSOM)；如[附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)中所述。 |
   |                     **BAM 警报提供程序**                      |                                                                                                                                                                                                                                                                        配置 BAM 警报。<br /><br /> 将 BAM 警报与 [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)] 或 [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] SP1 一起使用时，你必须配置数据库邮件功能。 不能使用 SQL Server Notification Services。                                                                                                                                                                                                                                                                        |
   |                         **BAM 客户端**                          |                                                                                                                                                                                                                                                                                                                                                                                      使业务用户能够使用 BAM 的客户端软件。                                                                                                                                                                                                                                                                                                                                                                                      |
   |                        **BAM 事件**                         |                                                                                                                                                                                                                                                                                                                           适用于 Windows Workflow Foundation 和 Windows Communication Foundation 的侦听器。 还包含 BAM Event API，它可将事件从自定义应用程序发送到 BAM 数据库。                                                                                                                                                                                                                                                                                                                           |
   |                   **项目生成组件**                   |                                                                                                                                                                                                                                                                                                                                        一种让你无需使用 Visual Studio 就能生成 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 解决方案的工具。                                                                                                                                                                                                                                                                                                                                        |


7. 接受默认安装位置，或者选择“浏览”以进入其他要安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的位置。 选择“下一步” 。  

8. 如果计算机缺少必备组件，例如 ADOMD.NET，则安装程序可能会安装可再发行的必备组件。 您可以：  

   -   选择“自动从 Web 安装可再发行的必备组件”  

        或  

   -   如果已下载 CAB 文件，则选择“自动从 CAB 文件安装可再发行的必备组件”。 如果你选择此操作，之后可以浏览到 CAB 文件所在的位置。  

9. 在“摘要”中，验证选择安装的组件是否正确。 若要使系统在重新启动后自动登录，请选择“设置”并输入登录信息。 只能在安装期间为重新启动启用自动登录，安装完成后即禁用。  

10. 单击“安装”开始安装过程。  

11. 在“Microsoft Update 安装”中，选择你的偏好，然后选择“下一步”。  

12. 在“安装已完成”中，取消选中“启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置”，然后选择“完成”。  

## <a name="additional"></a>补充说明  

- 安装 SQL Server 时，安装程序即已将系统管理员权限授予你的登录帐户。 由于安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 也需要这些权限，因此必须执行下列操作之一：  

  -   使用在安装 SQL Server 时所用的同一帐户。  

  -   向登录帐户授予系统管理员权限。  

- 下载 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的自解压缩可执行文件 (EXE) 后，会打开安装指南。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 Setup.exe 和安装指南位于同一位置。  

- 你可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 映像来配置 [!INCLUDE[winazure](../includes/winazure-md.md)] 虚拟机，而无需在物理计算机上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 请参阅[在 Azure VM 上配置 BizTalk Server](http://msdn.microsoft.com/library/azure/jj248689.aspx)。  

- 有关使用命令提示符安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的步骤，请参阅[附录 A：无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)。  


## <a name="see-also"></a>请参阅  

 [附录 A：无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)   
 [附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)   
 [附录 C：可再发行的 CAB 文件](../install-and-config-guides/appendix-c-redistributable-cab-files.md)   
 [附录 D：创建 SMTP 服务器](../install-and-config-guides/appendix-d-create-the-smtp-server.md)