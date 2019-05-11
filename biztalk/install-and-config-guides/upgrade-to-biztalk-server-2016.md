---
title: 升级到 BizTalk Server 2016 |Microsoft Docs
ms.custom: ''
ms.prod: biztalk-server
ms.date: 06/08/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 975ec82b-ed27-4545-8e4a-0e567507c9ba
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a545f03f480a2cade3d609feb085449ab9a2f726
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401442"
---
# <a name="upgrade-to-biztalk-server-2016"></a>升级到 BizTalk Server 2016
升级到[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]从[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]，或 BizTalk Server 2013。

本主题概述的[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]升级过程中，密钥信息和从 BizTalk Server 2013 R2 或 BizTalk Server 2013 升级的分步说明。


## <a name="upgrade-overview"></a>升级概述

- 在升级之前，请阅读整篇文档。 BizTalk Server 将很多不同的组件，内部和外部，连接到你的企业。 大多数实际的部署方案都会进一步扩展以包括多个服务器，最终包括物理和虚拟计算机群集。

- 没有两个 BizTalk Server 部署是相同的。 在升级之前，您企业的需求，收集信息并讨论使用 IT 专业人员、 系统管理员和开发人员使用 BizTalk Server 部署的作用域。 通过学习此升级指南，并确定企业的具体需求，您将创建自己的部署指南。

- 使用 BizTalk Server 最佳做法分析器 (BPA) 来检查 BizTalk Server 部署，并生成一系列最佳实践。 BPA 只，通过读取和报告方式执行配置级别验证，并使用收集到的数据来确定是否遵循最佳实践。

### <a name="planning-your-upgrade"></a>规划升级

下面是升级过程的高级视图。 必须按照所示顺序运行每个列出的步骤。

- 操作系统升级路径
- Microsoft SQL Server® 的升级路径
- Windows® SharePoint® Services 升级
- 安装 Visual Studio 并行
- 安装 Microsoft Office 2016、office 2013年并行

### <a name="supported-upgrade-paths"></a>支持的升级路径
下表列出了支持的操作系统可以升级到[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 "是"表示在该操作系统上运行的 BizTalk Server 版本可以升级。 "否"表示不能升级在该操作系统上运行的 BizTalk Server 版本。 如果是"否"，必须在受支持的操作系统上重新创建 BizTalk 环境。  [硬件和软件要求 BizTalk Server 2016 的](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)列出了支持的操作系统。

| 操作系统 | BizTalk Server 2013 R2 |BizTalk Server 2013 |
| --- | --- | --- |
| Windows Server 2012 R2 | 是 | 否 |
| Windows Server 2012 | 否 | 否 |
| Windows 8.1 | 是 | 否 |
| Windows 8 | 否 | 否
| Windows 7 SP1 | 否 | 否 |

下表列出了支持的 SQL Server 版本，可以升级到[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 SQL Server 可承载 BizTalk Server 使用的数据库。 "是"表示 BizTalk Server 使用该 SQL Server 版本可以升级。 "否"表示使用该 SQL Server 版本的 BizTalk Server 不可升级。 如果是"否"，必须支持的 SQL Server 版本上重新创建 BizTalk 环境。 [硬件和软件要求 BizTalk Server 2016 的](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)列出了受支持的 SQL Server 版本。 

> [!TIP]
> 如果您是 SQL Server 版本不受支持，或不在以下列表中，请查看 SQL Server 升级文档。 SQL 升级所适用的更多版本比 BizTalk 支持。 例如，如果您使用 SQL Server 2008，您可能能够升级 SQL Server 2016。 然后，你可以升级到[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 [升级到 SQL Server 2016](https://msdn.microsoft.com/library/bb677622.aspx)并[升级到 SQL Server 2014](https://msdn.microsoft.com/library/bb677622(v=sql.120).aspx)列出了可以升级的 SQL Server 版本。

| SQL Server | BizTalk Server 2013 R2 |BizTalk Server 2013 |
| --- | --- | --- |
| SQL Server 2014 | 是 | 否 |
| SQL Server 2012 SP1| 否 | 否 |
| SQL Server 2012 | 否 | 否 |
| SQL Server 2008 R2 SP1 | 否 | 否 |


下表列出了从受支持的版本升级路径[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 到[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 "是"表示 [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] /2013年版本可以升级到版本。 "否"表示 [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] /2013年版本无法升级到版本。 如果是"否"，则必须重新创建 BizTalk 环境。

| BizTalk Server 2013 R2/2013 | BizTalk Server 2016 评估版 | BizTalk Server 2016 分支版 | BizTalk Server 2016 开发人员版 | BizTalk Server 2016 标准版 | BizTalk Server 2016 企业版 |
| --- | --- | --- | --- | --- | --- |
| Evaluation | 否 | 否 | 否 | 否 | 是 | 
| 分支 | 否 | 是 | 否 | 否 | 是 | 
| 开发人员 | 否 | 否 | 是 | 否 | 是 | 
| 标准 | 否 | 否 | 否 | 是 | 是 | 
| Enterprise | 否 | 否 | 否 | 否 | 是 | 

## <a name="before-the-upgrade--what-you-need-to-know"></a>升级之前 – 需要知道


- **权限**:执行升级的用户必须是以下用户组的成员或具有同等权限：

    - 在本地计算机上的 administrators 组
    - SQL Server 上的 SQL Server 系统管理员组
    - BizTalk Server Administrators 组
    - 单一登录 (SSO) 管理员组

- **SSO**:单一登录主密钥服务器和 SSO 数据库的宿主 SQL Server 必须运行在升级过程。

- **网络服务帐户**:必须具有对 windir%\temp 的写访问权限。

- **证书**:备份 Windows 证书存储：  

    [Windows 7 和 Windows Server 2008 R2:导入证书](http://technet.microsoft.com/library/cc754489.aspx)  
    [Windows 7 和 Windows Server 2008 R2:导出证书](http://technet.microsoft.com/library/cc730988.aspx)  

- **DTC**:启用 Microsoft 分布式事务处理协调器 (MSDTC) ([用于优化环境的配置后步骤](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md))，然后启用入站/出站 DTC 规则：

    1. 在服务器管理器中，选择**工具**，然后打开**高级安全 Windows 防火墙**。
    2. 选择**入站规则**。
    3. 在中**入站规则**，右键单击**分布式事务处理协调器*** （根据需要），然后**启用规则**。
    4.  在高级安全 Windows 防火墙中，选择**出站规则**。
    5.  在中**出站规则**，右键单击**分布式事务处理协调器*** （根据需要），然后**启用规则**。

- **SharePoint**:客户端对象模型 (CSOM) 用于连接到 SharePoint 服务。 服务器端对象模型 (SSOM) （web 服务） 中已删除[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。

    如果使用不支持 CSOM 的 SharePoint 版本，你可以升级到受支持 SharePoint 版本：

    [升级到 SharePoint 2016](https://technet.microsoft.com/library/cc303420(v=office.16).aspx)  
    [升级到 SharePoint 2013](https://technet.microsoft.com/library/cc303420(v=office.15).aspx)

- **.NET framework**:没有通过并行安装.NET Framework 4.5 和.NET Framework 4.6 之间的概念。 .NET Framework 4.6 二进制文件会覆盖.NET Framework 4.5 二进制文件。 .NET framework 4.6 是[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]要求，并不支持 （和不应安装） 在 BizTalk Server 早期版本中。

- **Office 2016 和 Office 2013**:[安装和使用不同版本的 Office](https://support.office.com/article/Install-and-use-different-versions-of-Office-on-the-same-PC-6EBB44CE-18A3-43F9-A187-B78C513788BF)同一台计算机上。 此外，请查看[这些问题](https://support.microsoft.com/kb/3094527)。

- **BizTalkServerApplication 主机**:升级需要存在默认主机。 如果与 SQL 适配器关联的默认主机实例发送端口和接收位置删除，将默认主机与 SQL 适配器相关联，然后再升级。 升级完成后，你可以从列表中删除默认主机。

- **自定义绑定**:在升级后，用户定义的自定义绑定与早期版本的.NET Framework 生成不可用。 若要使用自定义绑定，手动在.NET Framework 4.6 machine.config 文件中添加自定义绑定。

- **配置文件**:备份 BizTalk Server 2013 R2/2013年中的所有自定义配置文件。 BizTalk Server 支持的更改迁移仅在`btsntsvc.exe.config`和`bm.exe.config`文件。



### <a name="bam-alerts"></a>BAM 警报

使用 BAM 警报需要 SQL Server Database Mail。 如果正在从与通知服务结合使用现有 BAM 警报定义的 SQL 版本升级 SQL Server，然后可以备份 BAM 警报定义，并在升级后部署它们。 使用 BM.exe 命令行工具 (`\Program Files (x86)\Microsoft BizTalk Server <your version>\Tracking`)。 具体步骤包括：

1. 打开命令提示符并转到`\Program Files (x86)\Microsoft BizTalk Server <your version>\Tracking`。
2. 在命令提示符处创建一个定义文件： `bm.exe get-defxml -FileName:YourBAMDefinition.xml`
3. 在[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 配置中，取消对 BAM 警报。
4. 升级到 SQL Server 2016 或 SQL Server 2014 SP1。
5. 配置 SQL Server Database Mail。
6. 升级到[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。
7. 在[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]配置中，配置 BAM 警报。
8. 部署在命令提示符中保存的定义文件： `bm.exe update-all -DefinitionFile:YourBAMDefinition.xml`

> [!IMPORTANT]
> 如果没有中列出的顺序执行以下步骤或创建一个定义文件，必须在 BizTalk Server 升级后重新定义文件。
> 
> 若要查看 BM.exe 帮助，请键入： `bm.exe help`。


### <a name="bam"></a>BAM 

- **BAM DTS 包**:停止所有 BAM 数据转换服务 (DTS) 包。 否则为可能会丢失数据或联机分析处理 (OLAP) 多维数据集可能会损坏。 

- **磁盘空间**:可用磁盘空间应至少是现有 BAM 数据库的大小。

- **实时聚合**:如果当前版本的 BizTalk Server 中使用的 BAM 实时聚合且要升级 SQL Server，安装或升级到 SQL Server Enterprise Edition。 否则，升级将失败。

- **maxTimeout 值**:如果拥有大型 BAM 数据库，更新`maxTimeout`为分布式事务到 machine.config 文件中的值：  

    ```
    <system.transactions>
       <machineSettings maxTimeout="23:59:59" />
    </system.transactions>
    ```

- **使用跟踪配置文件编辑器 (TPE) 启用 BAM 跟踪**:在升级后，升级以前部署的跟踪配置文件;但是，不升级相应的侦听器配置。 任何新截获的 BAM 消息可能仍具有 BizTalk Server 2013 R2/2013年引用。 若要升级相应的侦听器配置，使用跟踪配置文件编辑器检索活动的配置文件并重新应用该配置文件。

- **实时数据工作簿**:如果在升级后，要在 BizTalk Server 2013 R2/2013 中，使用 BAM，您必须手动重新生成实时数据工作簿。 若要重新生成实时数据工作簿：

  1. 通过运行以下命令来检索 BAM 定义：  
     `BM get-defxml MyDef.xml`
  2. 重新创建数据透视表打开 Microsoft Office Excel，然后选择 BAM 外接程序。导入*MyDef.xml*文件中创建的步骤 (1)，并重新创建数据透视表报表。 保存为新的 BAM 工作簿*MyNewBook.xls*。
  3. 通过查找中的数据透视表名称重命名数据透视表报告*MyDef.xml*下`<Caption>`中`<BAMDefinition>\<Extension>\<OWC>\<PivotTableView>\<PivotTable>\<PivotView>\<Label>`路径。 使用这些名称重命名数据透视表的报表中*MyNewBook.xls*。
  4. 通过运行以下命令重新生成实时数据工作簿：  
     `BM regenerate-livedataworkbook MyNewBook.xls`

     > [!NOTE]
     > 不会重新生成实时数据工作簿重新 Excel 项目 （例如，图表） 创建原始实时数据工作簿中。 手动重新创建项目。


### <a name="enterprise-single-sign-on-esso"></a>企业单一登录 (ESSO)

|                            应用场景                            |                                                                                                                                                                                                                                                                                                                                          详细信息                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 从企业单一登录的早期版本升级 | BizTalk Server 包含企业单一登录 (ESSO) 的更新的版本。 如果使用早期版本的 BizTalk 的计算机上安装此版本中，则 ESSO 自动更新在安装过程。 我们建议你在升级之前执行以下步骤： <br/><br/> 1.验证单一登录数据库 (SSODB) 的当前版本备份到安全位置。 <br/>2.验证当前的主密钥备份到安全位置。<br/>3.知道主密钥的密码。<br/><br/>在 BizTalk 组中的所有服务器都升级到同一版本。 此要求也适用于独立主密钥服务器。 |
|  使用企业单一登录独立安装程序升级  |             使用以下步骤来安装，如专用主密钥服务器的独立企业单一登录的计算机上执行升级。<br/><br/>1.验证当前的主密钥备份到安全位置。<br/>2.验证当前版本的 SSODB 备份到安全位置。<br/>3.运行 ESSO **Setup.exe**从[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]安装介质。 默认安装文件夹是`\Platform\SSO`。<br/>4.在中**自动运行**对话框中，选择**Microsoft 企业单一登录**。<br/>5.在摘要对话框，选择**升级**。              |

### <a name="multicomputer-environment"></a>多计算机环境
在多计算机环境中，升级 SSO 主密钥服务器计算机。 然后，升级其他 BizTalk Server 计算机。 不支持同时升级一个组中的 BizTalk 计算机。 按以下顺序一次升级一台计算机：

1. 单一登录主密钥服务器
2. 在运行 BizTalk Server 运行时计算机
3. 管理工具和监视计算机
4. 开发和运行 BizTalk Server 的任何其他剩余的计算机

**其他**  
使用设置仪表板，可以广泛地调整 BizTalk Server 设置以优化性能。 此外可以修改 BizTalk 组、 BizTalk 主机和 BizTalk 主机实例设置。 请参阅[使用设置仪表板进行 BizTalk Server 性能调优](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。

### <a name="general-information"></a>常规信息

- **帐户名**:使用默认帐户名，只要有可能。 BizTalk Server 安装程序会自动配置已安装的组件要使用的默认帐户。 如果在 Active Directory 林中有多个 BizTalk Server 组，更改帐户名，以避免冲突。 BizTalk Server 仅支持`<NetBIOS domain name>\<user>`名称格式的服务帐户和 Windows 组。

- **带有 BAM 管理 Web 服务的帐户名称**:BizTalk Server 不支持 BAM 管理 Web 服务用户的内置帐户或无密码的帐户。 

  通过此类帐户配置 BizTalk Server 似乎会成功，但 BAM 管理 Web 服务会失败。 

  支持将此类帐户用于 BAM 应用程序池。

- **BizTalk 程序集查看器**不支持在 64 位操作系统上。

- **安装和卸载**:当你卸载 BizTalk Server 后时，手动删除 BizTalk Server 数据库。 如果以开发人员或评估师身份安装 BizTalk Server，请考虑在虚拟机上安装。 这样一来，如果你必须重新安装，您可以轻松回滚到预设检查点而无需完成整个卸载过程。

- **32 位和 64 位计算机**:在 32 位 Windows 或 64 位 Windows 上安装 BizTalk Server 时，有一些不同之处。 本文档介绍如何同时在 32 位和 64 位安装。 说明了它们之间的差异。

- **工作组**:支持安装和配置 BizTalk Server 在一台计算机上的工作组环境中。 在此方案中，SQL Server 和 BizTalk Server 功能和组件将安装并配置在同一计算机上。

- **终端服务器**:安装 BizTalk Server 使用在应用程序模式下运行的终端服务器不支持。 请参阅[KB 832027](https://support.microsoft.com/kb/832027)。

- **无提示升级**不受支持。

- **不受支持的应用程序**:BizTalk Server 不支持基于不支持的 Api，例如 PAM Api、 存储的过程或直接数据库访问的自定义应用程序。 在升级生产环境之前，请运行至少一个测试升级。

- **SQL Server 实例**:最好在升级平台前先升级任何 SQL Server 实例。

## <a name="prepare-your-computer-for-upgrade"></a>为升级准备您的计算机

|                 任务                  |                                                                                                                                                                                                                                        T:System.Diagnostics.Switch                                                                                                                                                                                                                                         |
|---------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   安装重要 Windows 更新    |                                                                                                                                                                                                从程序菜单中选择 Windows 更新。 您可能需要重新启动计算机。                                                                                                                                                                                                 |
|      保存 BAM 警报定义       |                                    仅适用于当前使用现有 BAM 警报定义和 SQL Server Notification Services。 创建使用 BM.exe 定义文件并取消配置 BAM 警报[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 配置。<br/><br/>**在升级之前**（在本主题中） 列出了特定步骤。<br/><br/>否则，在升级后重新创建 BAM 警报定义。                                    |
|          升级 SQL Server           |                                         升级到支持的 SQL Server 版本。 请参阅：<br/><br/>[硬件和软件要求适用于 BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)<br/>[升级到 SQL Server 2016](https://msdn.microsoft.com/library/bb677622.aspx)<br/>[升级到 SQL Server 2014](https://msdn.microsoft.com/library/bb677622(v=sql.120).aspx)                                          |
|    升级 SQL Server 客户端工具    |                                                                                                                                                在多计算机环境中，可能在单独的计算机上安装管理工具。 升级 SQL Server 管理客户端工具，包括管理工具。                                                                                                                                                |
|         安装 Visual Studio         |                         请参阅[硬件和软件要求 BizTalk Server 2016 的](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)有关受支持的版本。 可以为不同 Visual Studio 版本已安装的并排方案。 请参阅[Visual Studio 2015](https://msdn.microsoft.com/library/ms246609(v=vs.140).aspx)并[Visual Studio 2013](https://msdn.microsoft.com/library/ms246609(v=vs.120).aspx)。                         |
|            安装 Office             |                                     请参阅[安装和使用不同版本的 Office](https://support.office.com/article/Install-and-use-different-versions-of-Office-on-the-same-PC-6EBB44CE-18A3-43F9-A187-B78C513788BF)同一台计算机上。 [硬件和软件要求 BizTalk Server 2016 的](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)列出了支持的 Office 版本。                                     |
| 停止 BizTalk 和 Windows 服务 |                                                                                                      -BizTalk 服务 BizTalk 组： *< 名称 >*<br/>-BizTalk 基本 EDI 服务<br/>-规则引擎更新服务<br/>-万维网发布服务<br/><br/>**请注意**<br/>如果您安装了任何 BizTalk Server 加速器，停止 HL7 日志记录服务。                                                                                                      |
|         将数据库备份         | 主机<br/>- MSDB<br/>-BAMArchive<br/>- BAMPrimaryImport<br/>- BAMStarSchema<br/>- BizTalkDTADb<br/>- BizTalkEDIDb<br/>- BizTalkHwsDb<br/>- BizTalkMgmtDb<br/>- BizTalkMsgBoxDb<br/>- BizTalkRuleEngineDb<br/>- TPM<br/>- BizTalkAnalysisDb<br/>- BAMAnalysis<br/><br/>[SQL Server 2014:备份概述](https://technet.microsoft.com/library/ms175477(v=sql.120).aspx)<br/>[SQL Server 2012:备份概述](https://technet.microsoft.com/library/ms175477(v=sql.110).aspx) |
|  配置 SQL Server 数据库邮件   |                                                                                                                      仅适用于您使用 BAM 警报定义和 SQL Server Notification Services。<br/><br/>**在升级之前**（在本主题中） 列出了特定步骤。<br/><br/>否则，在升级后重新创建 BAM 警报定义。                                                                                                                       |

## <a name="do-the-upgrade"></a>执行升级

> [!IMPORTANT]
> 安装 SQL Server，则安装程序授予系统管理员权限登录的帐户。 安装 BizTalk Server 时，还需要执行系统管理员权限。 执行以下操作之一：
> 
> - 使用相同的帐户安装 SQL Server 时使用  
> **OR**  
> - 请确保当前登录的帐户具有系统管理员权限

### <a name="upgrade-steps"></a>升级步骤

1. 关闭任何打开的程序。
2. 运行**Setup.exe**从安装媒体。
3. 在入门中，选择**安装 Microsoft BizTalk Server**。
4. 在中**客户信息**，输入用户名称、 组织和产品密钥。 选择“**下一步**”。
5. 接受许可协议，然后选择**下一步**。
6. 在客户体验改善计划，输入首选项。 请参阅**附录 A** （在本主题中） 有关详细信息。
7. 在中**组件安装**，查看可用组件，然后选择**下一步**。
8. 如果您的计算机缺少的必备软件，安装程序可以安装可再发行的必备组件。 您可以：

    - 选择自动从 web 安装可再发行的必备组件  

      或  

    - 选择自动安装可再发行的必备组件 CAB 文件中如果你已下载 CAB 文件。 浏览到 CAB 文件的位置并选择它。

9. 在中**摘要**，查看可升级的组件。
10. 选择**升级**启动。
11. 可选：选择**使用 Microsoft Update 检查更新 （推荐） 时**。
12. 在中**升级已完成**，清除**启动 BizTalk Server 配置**复选框，并选择**完成**。

**ADDITIONAL**  
BizTalk Server 中，升级期间会发生很多并不少见在过程中遇到错误。 但是，大多数错误可轻松纠正如果做好准备。 我们建议阅读**附录 B** （本主题中有关如何避免升级错误，以及要执行的操作如果发生这种错误的提示。

升级过程仅升级属于你的 BizTalk Server 的以前版本的功能。 在升级过程不会安装新的功能。 若要安装这些功能，在升级后重新运行安装程序中，选择**修改**，并选择你想要安装的功能。 安装后，配置这些使用**BizTalk Server 配置管理器**。

若要验证升级是否成功，请打开**程序和功能**并查找[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 如果已列出，则安装成功。

## <a name="post-upgrade"></a>升级后
您无法回滚到 [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] /2013年。

- **如果创建了 BAM 警报定义 XML 文件**:在[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]配置中，配置 BAM 警报。 然后，部署已保存的定义。

    **在升级之前**（在本主题中） 列出了特定步骤。 否则，在升级后重新创建 BAM 警报定义。

- **安装 MQSAgent**:如果 MQSAgent.dll 文件安装在远程 WebSphere MQ Server 上，安装新版 MQ 代理[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]远程 WebSphere MQ Server 上。

- **启动 MSMQ**:如果使用 MSMQ 适配器，启动消息队列服务。

- **自定义 EXE 和 BRE**:如果必须引用 BizTalk Server 2010 中的业务规则引擎程序集的自定义托管可执行文件，以下代码添加到应用程序配置文件以.NET Framework 2.0 中运行此进程。

    ```
    <?xml version="1.0" encoding="Windows-1252"?>
    <configuration> 
     <startup>
      <supportedRuntime version="v2.0.50727" />
     </startup>   
    </configuration>
    ```

- **SQL 代理作业**:重新配置以下 SQL Server 代理作业：

    -   DTA 清除和存档 (BizTalkDTADb):请参阅[如何配置 DTA 清除和存档作业](../core/how-to-configure-the-dta-purge-and-archive-job.md)
    -   备份 BizTalk Server (BizTalkMgmtDb):请参阅[如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)

- **重新启动应用程序**:重新启动升级的所有已部署应用程序。

- **BAM 门户错误**:当您打开 BAM 门户时，可能会收到以下错误消息： 

    `The server encountered a critical failure while trying to access the list of Views. The Business Management Web Service requires Administrator's attention.` 

    如果运行的.NET Framework 2.0 的应用程序使用的网站上配置 BAM 门户，可以发生此错误。 在此方案中，托管新的网站上的 BAM 门户。 若要添加的网站，请参阅[创建的 Web 站点](http://go.microsoft.com/fwlink/p/?LinkID=196470)。 创建网站后, 重新配置 BAM 门户：

    1. 打开**BizTalk Server 配置**。
    2. 选择**取消对功能**。 在中**取消对功能**，选择**BAM 门户**复选框，然后选择**确定**。
    3. 通过选择从新网站来重新配置 BAM 门户**BAM 门户网站**列表。

- **BizTalk 2016 Accelerator for SWIFT**:BizTalk Server 升级过程不会更新已编辑*BREDeployment.exe.config*文件。 手动更改中的路径*BREDeployment.exe.config*文件位于`\Program Files\Microsoft BizTalk 2016 Accelerator for SWIFT\SDK\Tools`文件夹。

    另外，A4SWIFT Web Services 和 Message Pack 配置也将丢失。 BizTalk Server 升级后重新配置这些设置。

## <a name="appendix-a-customer-experience-improvement-program"></a>附录 A：客户体验改善计划
作为 BizTalk Server 中的客户体验改善计划的一部分，可以向 Microsoft 提供有用的反馈，就功能使用情况的 BizTalk Server。 收集的数据是匿名的不能用于确定您的身份。 Microsoft 会收集功能使用情况统计信息作为此计划的一部分。

通过参与此计划，可以帮助提高可靠性和性能的各种功能的 BizTalk Server。 有关此计划及其隐私策略的详细信息，请参阅[Microsoft BizTalk Server CEIP 隐私策略](http://go.microsoft.com/fwlink/p/?LinkId=188553)。

## <a name="appendix-b-known-issues"></a>附录 B：已知问题

- **管理计算机上配置 BAM 警报**:没有单独的计算机上安装的管理、 运行时和 SQL Server 组件的多计算机环境。 当使用 BAM 工具或 BAM 警报时，可能会出现以下问题：

    **问题**:在 BizTalk 管理计算机上配置 BAM 工具时，会发生以下错误：

    `Service BAMAlerts was not found on computer ‘.’.The specified service does not exist as an installed service.`

    **问题**:在部署 BAM 活动定义从运行时计算机时，会发生以下错误：

    `A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)`

    如果在运行时计算机上配置 BAM 警报，将发生这种情况。 若要解决，请在 BizTalk 管理控制台的同一计算机上配置 BAM 警报。 不要在运行时计算机上配置 BAM 警报。

- **从失败的升级中恢复**:在升级过程中随时可能发生升级失败。 如何恢复失败的升级确定哪个点发生失败的每个阶段。

  - 如果升级失败时安装系统必备组件，安装程序停止进一步安装系统必备组件，并返回错误消息。 然后可以更正问题并重新运行安装程序。

  - 如果升级失败时升级数据库，删除现有 BizTalk Server 版本中的功能或安装最新版本，安装程序停止进一步安装，并返回错误消息。 将回滚任何更改。 无法回滚到 BizTalk Server 数据库所做的更改。

      如果在升级过程中删除以前的 BizTalk Server 安装的组件，您的计算机可能会处于一种状态无 BizTalk Server 组件。 可能会保留先前安装中的功能配置信息。 并且根据升级过程失败的位置，BizTalk Server 数据库可能已升级。 可能需要还原的数据库，再次运行安装程序之前备份。

  - 如果升级失败时重新配置 BizTalk Server 功能，安装程序将返回完成比例消息。 如果配置升级失败或部分成功，运行 BizTalk Server 配置来完成升级。

    如果升级继续失败并且需要回退到以前版本的 BizTalk Server，必须还原您备份的数据库，然后重新安装先前的 BizTalk Server 版本。

- **使用相同的版本**:在 BizTalk 应用程序组中，无法运行具有不同版本的 BizTalk Server 的计算机。 例如，在 BizTalk 管理控制台中，不能绑定到不同版本的 BizTalk Server 上运行的接收位置的 BizTalk Server 的一个版本上运行的发送端口。 

- **重新启动 SSO 服务**:如果您有以前的 Visual Studio 版本或在计算机上安装.NET Framework 4.5，BizTalk Server 的早期版本中的 SSO 服务将停止工作。 若要解决此问题，请运行`regasm SSOSQL.dll`命令从 Visual Studio 命令提示符。 此命令重新启动 SSO 服务。

    > [!NOTE]
    > 64 位计算机上，运行 32 位和 64 位版本的 regasm 命令。

- **无法使用 SOAP**:平台升级之后，你可能无法发送 SOAP 消息，因为权限。 若要解决此问题，请编辑 Web.config 文件在`C:\inetpub\wwwroot\<SOAPExternalAppName>\`具有以下文本：

    ```
    <securityPolicy>
    <trustLevel name="Full" policyFile="internal" />
    <trustLevel name="High" policyFile="web_hightrust.config" />
    <trustLevel name="Medium" policyFile="web_mediumtrust.config" />
    <trustLevel name="Low" policyFile="web_lowtrust.config" />
    <trustLevel name="Minimal" policyFile="web_minimaltrust.config"/>
    </securityPolicy>
    <trust level="Full" originUrl="" processRequestInApplicationTrust="true"/>
    ```

    您可能还需要更改自定义错误模式从**仅远程**到**关闭**。

- **证书存储区**:升级后，打开发送端口或接收位置从 BizTalk Server 管理控制台中，并出现错误： `Could not open certificate store, the system cannot find the file specified (System).`

    缺少的证书存储区时，将发生此错误。

- **BAM 门户**:在 64 位计算机上，不能在升级后访问 BAM 门户。 可能的解决方法：

  1. 创建在 web.config 文件的备份副本`%BizTalkInstallDir%\BAMPortal\web.config`。

  2. 使用 bm.exe 在 BizTalk Server Tracking 文件夹中，在命令提示符处运行以下命令： `bm.exe get-config –FileName:<filepath> -Server:MyServer -Database:MyDB`

     从配置 XML 文件获取的值*BAMVRoot* (xpath:BAMConfiguration\ GlobalProperty\Name="BAMVRoot").

  3. 打开列为 BAMVRoot 值的计算机上的 BizTalk Server 配置，并取消配置 BAM 门户。

  4. 打开 BizTalk Server 配置，然后配置 BAM 门户。

  5. 从步骤 (1) 中提到的位置打开新的 web.config 文件。

  6. 使用 web.config 文件中，备份副本设置以下值 (在`configuration\appSettings`):

      - key="MainPageContentUrl"
      - key="AlertNotificationOptions"

     > [!NOTE] 
     > 在 64 位计算机上升级操作系统之后, 我们建议重新配置 BAM 门户。

- **部署 EDI BAM 活动**:升级时，可能会部分成功升级。 这可以升级 SQL Server （与已配置 EDI)。 可能未正确升级 EDI BAM 活动。 若要解决此问题，请使用管理凭据在命令提示符处运行以下命令部署 BAM 活动：

    `"<BizTalk Installation Folder>\Tracking\bm.exe" deploy-all -DefinitionFile:"<BizTalk Installation Folder>\AS2ResendActivityDefs.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

    `"<BizTalk Installation Folder>\Tracking\bm.exe" update-all -DefinitionFile:"<BizTalk Installation Folder>\Microsoft.BizTalk.Configuration.EdiAS2.UpgradeR2toR3.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

    `"<BizTalk Installation Folder>\Tracking\bm.exe" update-all -DefinitionFile:"<BizTalk Installation Folder>\Microsoft.BizTalk.Configuration.Batching.UpgradeR2toR3.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

- **群集上的 SSO 错误**:在 BizTalk Server 运行时群集环境中，当您尝试升级，可能会收到一条错误消息：

    `SSO Master Secret Server service is not running on <Cluster name>.Please start the service to continue the upgrade.` 

    若要解决此问题，请刷新 SSO 服务 SSO 和 BizTalk Server 运行时群集中。

    **若要刷新 SSO 群集中的 SSO 服务**:

  1. 在群集管理器中，**使联机**包含群集的企业 SSO 服务资源的群集组。 这应启动的所有资源的群集组中。

  2. **执行脱机**企业 SSO 服务的群集的实例。 然后，将其置于重新**Online**。

  3. **移动**群集组。 此步骤应将包含群集的企业 SSO 服务资源的第一个节点到第二个节点的群集组移。

  4. **执行脱机**企业 SSO 服务的群集的实例。 然后，将其置于重新**Online**。

     **若要刷新 BizTalk Server 运行时群集中的 SSO 服务**:

  5. 在群集管理器中，**使联机**包含群集的 BizTalk Server 运行时资源的群集组。 这应启动的所有资源的群集组中。

  6. **执行脱机**企业 SSO 服务的群集的实例。 然后，将其置于重新**Online**。

  7. **移动**群集组。 此步骤应将包含群集的 BizTalk Server 运行时资源的第一个节点到第二个节点的群集组移。

  8. **执行脱机**企业 SSO 服务的群集的实例。 然后，将其置于重新**Online**。
