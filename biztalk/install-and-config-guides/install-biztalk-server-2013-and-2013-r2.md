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
ms.openlocfilehash: e3ce184bf0562ae9dd18291b37a75fc5360d9b5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266175"
---
# <a name="install-biztalk-server-2013-and-2013-r2"></a>安装 BizTalk Server 2013 和 2013 R2
列出了安装的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

## <a name="before-you-get-started"></a>准备工作

- **帐户名**– 使用默认帐户名，只要有可能。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序会自动输入默认帐户。 如果有多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组在域中更改帐户名，以避免冲突。 如果更改名称，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仅支持\< *NetBIOS 域名*\>\\<*用户*\>服务帐户和 Windows 组。  

- **带有 BAM 管理 Web 服务的帐户名称**–[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持内置帐户或无密码的帐户为 BAM 管理 Web 服务用户。 Web 服务会访问[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和这些帐户可能带来安全威胁。  

  > [!NOTE]
  >  配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与这些类型的帐户可能会成功，但是 BAM 管理 Web 服务失败。 内置帐户或无密码可用于 BAM 应用程序池。  

- **BizTalk 程序集查看器**– 在 64 位平台上不受支持。  

- **安装和卸载**– 卸载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]需要手动删除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 如果您正在安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为开发人员或评估师身份，使用虚拟机。 如果你需要重新安装，您可以轻松回滚虚拟机而无需卸载和删除数据库。  

- **32 位和 64 位计算机**– 有一些不同之处时安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位或 64 位计算机上。 安装和配置对 32 位和 64 位计算机。 任何对差异进行说明。  

- **工作组**-安装和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]单台计算机上的环境支持对工作组中。 SQL Server 和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能和组件安装和配置在同一计算机上。  

- **终端服务器**– 安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持使用在应用程序模式下运行的终端服务器。 请参阅[KB 832027](http://support.microsoft.com/kb/832027)。  

- **BAM 门户**-如果使用的应用程序运行的.NET Framework 2.0，然后创建新的 BAM 门户网站的网站上配置 BAM 门户：  

   [创建 IIS 7 网站](http://technet.microsoft.com/library/cc772350\(WS.10\).aspx)  

   [创建 IIS 8 网站](http://technet.microsoft.com/library/hh831515.aspx)  

   在创建新网站：  

  1. 打开**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置**。  

  2. 配置 BAM 门户，并选择从新的网站**BAM 门户网站**列表。  

- **社区补充内容**:读取：  

   [BizTalk Server 中的主动性](http://msdn.microsoft.com/library/dn393929\(v=bts.10\).aspx)  

   [BizTalk Server 2013 R2:安装和配置 – 设置服务器 (第 1 部分) 前的重要注意事项](http://sandroaspbiztalkblog.wordpress.com/2015/01/04/biztalk-server-2013-r2-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)  

##  <a name="BKMK_Install"></a> 安装 BizTalk Server  

1. 关闭任何打开的程序。 运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以管理员身份安装程序。  

2. 在中**启动**，选择**安装 Microsoft BizTalk Server**。  

3. 在中**客户信息**，输入用户名、 组织、 产品密钥，然后选择**下一步**。  

4. 在中**许可协议**，接受许可协议，然后选择**下一步**。  

5. 在中**客户体验改善计划**，选择您希望参与，并选择**下一步**。  

    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 参与客户体验改善计划。 选择就功能使用情况报告功能向 Microsoft 提供有用的反馈[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 收集的数据是匿名的不能用于确定您的身份。 Microsoft 会收集功能使用情况统计信息作为此计划的一部分。 通过参与此计划，可以帮助提高可靠性和性能的各种功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关此计划及其隐私策略的详细信息，请参阅[Microsoft BizTalk Server CEIP 隐私策略](http://go.microsoft.com/fwlink/p/?LinkId=188553)。  

6. 在中**组件安装**，查看可用组件，然后选择你想要安装的：  


   |                             功能                             |                                                                                                                                                                                                                                                                                                                                                                                                               Description                                                                                                                                                                                                                                                                                                                                                                                                                |
   |-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                        **文档**                        |                                                                                                                                                                                                                                                                                                                                                 核心文档、 教程、 用户界面参考 （F1 帮助）、 程序员参考和 SDK 示例和实用程序的使用说明。                                                                                                                                                                                                                                                                                                                                                 |
   |                       **服务器运行时**                        |                                                                                                                                                                                                                                                                                                                                                          基本运行时服务为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。                                                                                                                                                                                                                                                                                                                                                          |
   |                   **BizTalk EDI/AS2 运行时**                   |                                                                                                                                                                                                                                                                                      运行时服务提供本机支持电子数据交换 (EDI) 数据交换和 Applicability Statement 2 (AS2) 数据传输消息传送功能。 **注意：** 仅当你选择才能选择此**Server 运行时**功能。                                                                                                                                                                                                                                                                                       |
   |   **Windows Communication Foundation (WCF) 适配器运行时**    |                                                                                                                                                                                                                                                                                                   启用适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与基于 WCF 的应用程序进行通信。 **注意：** 仅当你选择才能选择此**Server 运行时**功能。                                                                                                                                                                                                                                                                                                   |
   |                      **门户组件**                      |                                                                                                                                                                                                                                                                                                                                               门户组件是一套业务分析师用来进行通信、 协作并达成决定使用业务数据的功能。                                                                                                                                                                                                                                                                                                                                                |
   |                **业务活动监视**                 |                                                                                                                                                                                                                                                                         也称为 BAM，这些是一套功能，为业务用户提供其异构业务流程，从而使他们能够做出重要业务决策的实时视图。 **注意：** 仅当你选择才能选择此**门户组件**功能。                                                                                                                                                                                                                                                                          |
   |             **管理工具和监视**             |                                                                                                                                                                                                                                                                                                                            管理和监视所必需的组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在本地计算机和远程服务器上。                                                                                                                                                                                                                                                                                                                             |
   | **Windows Communication Foundation (WCF) 管理工具** |                                                                                                                                                                                                                                                                                                                         选择此功能将安装用于 WCF 组件的管理服务。 **注意：** 仅当你选择才能选择此**管理工具和监视**功能。                                                                                                                                                                                                                                                                                                                         |
   |                   **开发人员工具和 SDK**                   |                                                                                                                                   示例和实用程序，用于快速创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。 这包括 SDK 示例和支持文档、 架构和映射设计器和 Visual Studio 项目模板。 **重要提示：** 如果你打算进行任何开发工作，则必须安装此组件。 使用 Visual Studio 扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将无法正常**开发人员工具和 SDK**安装组件。                                                                                                                                    |
   |                    ***其他软件***                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   |    **企业单一登录 (SSO) 管理模块**    |                                                                                                                                                                                                                                                                                                                                                                                用于管理 SSO 关联应用程序及其映射的接口。                                                                                                                                                                                                                                                                                                                                                                                 |
   |       **企业单一登录主密钥服务器**        |                                                                                                                                                                                                                                                                                   存储主密钥的 SSO 服务器。 在系统中的所有其他 SSO 服务器从此服务器获取主密钥。 中需要主密钥服务器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。                                                                                                                                                                                                                                                                                    |
   |                  **业务规则组件**                  |                                                                                                                                                                                                                                                                                                                                                                                 用于撰写策略可供业务规则引擎。                                                                                                                                                                                                                                                                                                                                                                                 |
   |                       **MQSeries 代理**                        |                                                                                                                                                                                                                                                                                                                                                                     提供用于 MQSeries 的 BizTalk 适配器和 MQSeries Server for Windows 之间的通信。                                                                                                                                                                                                                                                                                                                                                                     |
   |       **Windows SharePoint Services 适配器 Web Services**       | **已弃用**。 使用 IIS web 服务上安装[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]计算机，[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]适配器处理通过 Microsoft SharePoint 传入和传出的文档。<br /><br /> **建议**：不要**不**安装。 默认情况下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用自动安装的 SharePoint 客户端对象模型 (CSOM) 可再发行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]; 中所述[附录 b:安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)。 |
   |                     **BAM 警报提供程序**                      |                                                                                                                                                                                                                                                                        配置 BAM 警报。<br /><br /> 使用 BAM 警报时[!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]或[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]SP1，你必须配置数据库邮件功能。 不能使用 SQL Server Notification Services。                                                                                                                                                                                                                                                                        |
   |                         **BAM Client**                          |                                                                                                                                                                                                                                                                                                                                                                                      使业务用户能够使用 BAM 客户端软件。                                                                                                                                                                                                                                                                                                                                                                                      |
   |                        **BAM 事件**                         |                                                                                                                                                                                                                                                                                                                           用于 Windows Workflow Foundation 和 Windows Communication Foundation 的侦听器。 此外包括 BAM Event API，它将事件发送到 BAM 数据库中，从自定义应用程序。                                                                                                                                                                                                                                                                                                                           |
   |                   **项目生成组件**                   |                                                                                                                                                                                                                                                                                                                                        一种工具，使您能够构建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]而无需使用 Visual Studio 的解决方案。                                                                                                                                                                                                                                                                                                                                        |


7. 接受默认安装位置，或选择**浏览**输入其他位置，以安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 选择“**下一步**”。  

8. 如果计算机缺少必备组件，例如 ADOMD.NET，安装程序可以安装可再发行的必备组件。 您可以：  

   -   选择**自动从 web 安装可再发行的必备组件**  

        或  

   -   选择**自动从 CAB 文件安装可再发行的必备组件**如果你已下载 CAB 文件。 如果选择此选项，然后可以浏览到 CAB 文件的位置。  

9. 在中**摘要**，验证组件是否正确。 若要使系统重新启动后自动登录，请选择**设置**，并输入您的登录信息。 自动登录，仅为重新启动安装过程中，并安装完成后禁用。  

10. 选择**安装**启动安装过程。  

11. 在中**Microsoft Update 安装**，选择你的偏好，然后选择**下一步**。  

12. 在中**安装已完成**，取消选中**启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置**，然后选择**完成**。  

## <a name="additional"></a>其他  

- 安装 SQL Server，SQL Server 安装程序将授予你已登录的帐户系统管理员权限。 由于这些权限，则还需要安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您必须执行下列操作之一：  

  -   使用安装 SQL Server 时所用的相同帐户。  

  -   授予登录帐户的系统管理员权限。  

- 下载自解压 EXE 后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，会打开安装指南。 Setup.exe[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]位于相同位置和安装指南。  

- 而不是安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]物理计算机上可以 o 配置[!INCLUDE[winazure](../includes/winazure-md.md)]虚拟机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]映像。 请参阅[在 Azure VM 上配置 BizTalk Server](http://msdn.microsoft.com/library/azure/jj248689.aspx)。  

- 有关安装步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用命令提示符，请参阅[附录 a:无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)。  


## <a name="see-also"></a>请参阅  

 [附录 a:无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)   
 [附录 b:安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)   
 [附录 c:可再发行 CAB 文件](../install-and-config-guides/appendix-c-redistributable-cab-files.md)   
 [附录 d:创建 SMTP 服务器](../install-and-config-guides/appendix-d-create-the-smtp-server.md)