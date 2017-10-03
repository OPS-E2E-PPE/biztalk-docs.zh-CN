---
title: "升级到 BizTalk Server 2016 |Microsoft 文档"
ms.custom: 
ms.prod: biztalk-server
ms.date: 06/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 975ec82b-ed27-4545-8e4a-0e567507c9ba
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a139b625ff1c31fb0dce71c08779856f0dc8b685
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="upgrade-to-biztalk-server-2016"></a>升级到 BizTalk Server 2016
从 [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] 或 BizTalk Server 2013 升级到 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。

本主题简要介绍 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 升级过程、重要信息，以及从 BizTalk Server 2013 R2 或 BizTalk Server 2013 进行升级的分步说明。


## <a name="upgrade-overview"></a>升级概述

- 升级之前，请阅读整篇文档。 BizTalk Server 可以将很多不同的组件（内部和外部）连接到你的企业。 大多数实际的部署方案都会进一步扩展，以包括多台服务器，最终包括物理和虚拟计算机群集。

- 没有任何两个 BizTalk Server 的部署是相同的。 在升级之前，请先根据企业需要收集信息，并与将使用 BizTalk Server 的 IT 专家、系统管理员及开发人员讨论部署范围。 通过学习此升级指南并确定企业的具体需求，可创建出属于自己的部署指南。

- 使用 BizTalk Server 最佳实践分析工具 (BPA)，检查 BizTalk Server 部署，并生成最佳实践列表。 BPA 只通过读取和报告的方式执行配置级别验证，它使用收集到的数据来确定是否符合最佳实践。

### <a name="planning-your-upgrade"></a>规划升级

以下是升级过程的高级视图。 必须按所示顺序完成所列的每个步骤。

- 操作系统升级路径
- Microsoft SQL Server® 升级路径
- Windows® SharePoint® Services 升级
- 并行安装 Visual Studio
- 并行安装 Microsoft Office 2016/2013

### <a name="supported-upgrade-paths"></a>受支持的升级路径
下表列出了可以升级到 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 的受支持操作系统。 “是”表示在该操作系统上运行的 BizTalk Server 版本可升级。 “否”表示在该操作系统上运行的 BizTalk Server 版本不可升级。 如果是“否”，则必须在受支持的操作系统上重新创建 BizTalk 环境。  [BizTalk Server 2016 的硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)列出了受支持的操作系统。

| 操作系统 | BizTalk Server 2013 R2 |BizTalk Server 2013 |
| --- | --- | --- |
| Windows Server 2012 R2 | 是 | 是 |
| Windows Server 2012 | 是 | 是 |
| Windows 8.1 | 是 | 是 |
| Windows 8 | 是 | 是
| Windows 7 SP1 | 是 | 是 |

下表列出了可以升级到 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 的受支持 SQL Server 版本。 SQL Server 可承载 BizTalk Server 所使用的数据库。 “是”表示使用该 SQL Server 版本的 BizTalk Server 可以升级。 “否”表示使用该 SQL Server 版本的 BizTalk Server 不可升级。 如果是“否”，则必须在受支持的 SQL Server 版本上重新创建 BizTalk 环境。 [BizTalk Server 2016 的硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)列出了受支持的 SQL Server 版本。 

> [!TIP] 
> 如果 SQL Server 版本不受支持，或不在下面的列表中，请查看 SQL Server 升级文档。 SQL 升级所适用的版本比 BizTalk 支持的版本更多。 例如，如果使用的是 SQL Server 2008，则可以升级到 SQL Server 2016。 然后，可以升级到 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 [升级到 SQL Server 2016](https://msdn.microsoft.com/library/bb677622.aspx) 和[升级到 SQL Server 2014](https://msdn.microsoft.com/library/bb677622(v=sql.120).aspx) 列出了可升级的 SQL Server 版本。

| SQL Server | BizTalk Server 2013 R2 |BizTalk Server 2013 |
| --- | --- | --- |
| SQL Server 2014 | 是 | 是 |
| SQL Server 2012 SP1| 是 | 是 |
| SQL Server 2012 | 是 | 是 |
| SQL Server 2008 R2 SP1 | 是 | 是 |


下表列出了 [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 到 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 这些版本中支持的版本升级路径。 “是”表示 [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 版本可升级到该版本。 “否”表示 [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 版本不可升级到该版本。 如果是“否”，则必须重新创建 BizTalk 环境。

| BizTalk Server 2013 R2/2013 | BizTalk Server 2016 Evaluation Edition | BizTalk Server 2016 Branch Edition | BizTalk Server 2016 Developer Edition | BizTalk Server 2016 Standard Edition | BizTalk Server 2016 Enterprise Edition |
| --- | --- | --- | --- | --- | --- |
| Evaluation | 是 | “否” | “否” | 是 | 是 | 
| Branch | 是 | 是 | “否” | 是 | 是 | 
| Developer | 是 | 是 | 是 | “否” | 是 | 
| Standard | 是 | “否” | 是 | 是 | 是 | 
| Enterprise | 是 | “否” | “否” | 是 | 是 | 

## <a name="before-the-upgrade--what-you-need-to-know"></a>升级之前 – 需要知道的事项


- **权限**：执行升级的用户必须属于以下用户组或具有同等权限：

    - 本地计算机上的管理员组
    - SQL Server 上的 SQL Server 系统管理员组
    - BizTalk Server 管理员组
    - 单一登录 (SSO) 管理员组

- **SSO**：升级期间，托管 SSO 数据库的单一登录主密钥服务器和 SQL Server 必须处于运行状态。

- **网络服务帐户**：必须具有对 %windir%\temp 的写入权限。

- **证书**：备份 Windows 证书存储：  

    [Windows 7 和 Windows Server 2008 R2：导入证书](http://technet.microsoft.com/library/cc754489.aspx)  
    [Windows 7 和 Windows Server 2008 R2：导出证书](http://technet.microsoft.com/library/cc730988.aspx)  

- **DTC**：启用 Microsoft 分布式事务处理协调器 (MSDTC)（[用于优化环境的配置后步骤](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)），然后启用入站/出站 DTC 规则：

    1. 在“服务器管理器”中，选择“工具”，然后打开“高级安全 Windows 防火墙”。
    2. 选择“入站规则”。
    3. 在**入站规则**，右键单击**分布式事务处理协调器*** （根据需要），然后**启用规则**。
    4.  在“高级安全 Windows 防火墙”中，选择“出站规则”。
    5.  在**出站规则**，右键单击**分布式事务处理协调器*** （根据需要），然后**启用规则**。
    
- **SharePoint**：用于连接到 SharePoint 服务的客户端对象模型 (CSOM)。 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 中已删除客户端对象模型 (SSOM)（Web 服务）。

    如果使用的是不支持 CSOM 的 SharePoint 版本，则可升级到支持的 SharePoint 版本：
    
    [升级到 SharePoint 2016](https://technet.microsoft.com/library/cc303420(v=office.16).aspx)  
    [Upgrade to SharePoint 2013](https://technet.microsoft.com/library/cc303420(v=office.15).aspx)（升级到 SharePoint 2013）

- **.NET Framework**：.NET Framework 4.5 和 .NET Framework 4.6 之间不存在并行安装的概念。 .NET Framework 4.6 二进制文件会覆盖 .NET Framework 4.5 二进制文件。 .NET Framework 4.6 是一项 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 要求，并且在以前的 BizTalk Server 版本中不受支持，也不应安装。

- **Office 2016 和 Office 2013**：在同一台计算机上[安装和使用不同版本的 Office](https://support.office.com/article/Install-and-use-different-versions-of-Office-on-the-same-PC-6EBB44CE-18A3-43F9-A187-B78C513788BF)。 此外，请检查[这些问题](https://support.microsoft.com/kb/3094527)。

- **BizTalkServerApplication 主机**：升级需要默认主机。 如果已删除与 SQL 适配器发送端口和接收位置相关联的默认主机实例，请将默认主机与 SQL 适配器关联后再进行升级。 升级完成后，可从列表中删除默认主机。

- **自定义绑定**：升级后，通过 .NET Framework 早期版本生成的用户定义的自定义绑定不可用。 若要使用自定义绑定，请在 .NET Framework 4.6 machine.config 文件中手动添加自定义绑定。

- **配置文件**：备份 BizTalk Server 2013 R2/2013 中的所有自定义配置文件。 BizTalk Server 仅支持 `btsntsvc.exe.config` 和 `bm.exe.config` 文件中的更改迁移。



### <a name="bam-alerts"></a>BAM 警报

使用 BAM 警报需要 SQL Server Database Mail。 如果要从 SQL 版本升级 SQL Server，并且使用的是现有 BAM 警报定义和通知服务，那么可以备份 BAM 警报定义，并在升级后对其进行部署。 使用 BM.exe 命令行工具 (`\Program Files (x86)\Microsoft BizTalk Server <your version>\Tracking`)。 具体步骤包括：

1. 打开命令提示符，并转到 `\Program Files (x86)\Microsoft BizTalk Server <your version>\Tracking`。
2. 在命令提示符处创建一个定义文件：`bm.exe get-defxml -FileName:YourBAMDefinition.xml`
4. 在 [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 配置中，取消对 BAM 警报的配置。
5. 升级到 SQL Server 2016 或 SQL Server 2014 SP1。
6. 配置 SQL Server Database Mail。
7. 升级到 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。
8. 在 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 配置中，配置 BAM 警报。
9. 在命令提示符处部署保存的定义文件：`bm.exe update-all -DefinitionFile:YourBAMDefinition.xml`

> [!IMPORTANT]
> 如果不按所列顺序执行这些步骤或创建一个定义文件，则必须在升级 BizTalk Server 后重新创建定义文件。
> 
> 若要查看 BM.exe 帮助，请键入：`bm.exe help`。


### <a name="bam"></a>BAM 

- **BAM DTS 包**：停止所有 BAM 数据转换服务 (DTS) 包。 否则，可能会丢失数据或损坏联机分析处理 (OLAP) 多维数据集。 

- **磁盘空间**：可用磁盘空间应至少是现有 BAM 数据库的大小。

- **实时聚合**：如果当前版本的 BizTalk Server 中使用的是 BAM 实时聚合，且要升级 SQL Server，请安装或升级到 SQL Server Enterprise Edition。 否则升级将失败。

- **maxTimeout 值**：如果拥有大型 BAM 数据库，请将 machine.config 文件中的分布式事务的 `maxTimeout` 值更新到：  

    ```
    \<system.transactions>
       <machineSettings maxTimeout="23:59:59" />
    \</system.transactions>
    ```

- **使用跟踪配置文件编辑器 (TPE) 启用的 BAM 跟踪**：升级后，会发现之前部署的跟踪配置文件已升级，但相应的侦听器配置尚未升级。 任何新截获的 BAM 消息可能仍具有 BizTalk Server 2013 R2/2013 引用。 若要升级相应的侦听器配置，请使用“跟踪配置文件编辑器”检索活动的配置文件，然后重新应用此配置文件。

- **实时数据工作薄**：如果在 BizTalk Server 2013 R2/2013 中使用的是 BAM，升级后，必须手动重新生成实时数据工作簿。 重新生成实时数据工作簿：

    1. 运行以下命令来检索 BAM 定义：  
    `BM get-defxml MyDef.xml`
    2. 打开 Microsoft Office Excel，然后选择 BAM 外接程序，重新创建数据透视表。导入在步骤 (1) 中创建的 *MyDef.xml* 文件，并重新创建数据透视表。 将新的 BAM 工作簿保存为 *MyNewBook.xls*。
    3. 在 `<BAMDefinition>\<Extension>\<OWC>\<PivotTableView>\<PivotTable>\<PivotView>\<Label>` 路径中的 `<Caption>` 下的 *MyDef.xml* 中，找到数据透视表名，然后重命名数据透视表。 使用这些名称重命名 *MyNewBook.xls* 中的数据透视表。
    4. 运行以下命令，重新生成实时数据工作簿：  
    `BM regenerate-livedataworkbook MyNewBook.xls`

    > [!NOTE]
    > 重新生成的实时数据工作簿不会在原始实时数据工作簿中重新创建 Excel 项目（例如，图表）。 手动重新创建项目。


### <a name="enterprise-single-sign-on-esso"></a>企业单一登录 (ESSO)

| 应用场景 | 详细信息 |
| --- | --- |
| 从企业单一登录的早期版本进行升级 | BizTalk Server 包含企业单一登录 (ESSO) 的已更新版本。 如果您在安装了 BizTalk 早期版本的计算机上安装此发行版本，则 ESSO 在安装过程中自动更新。 建议您在升级前先执行以下步骤： <br/><br/> 1.验证是否已将当前版本的单一登录数据库 (SSODB) 备份到安全位置。 <br/>2.验证是否已将当前主密钥备份到安全位置。<br/>3.知道主密钥的密码。<br/><br/>将 BizTalk 组中的所有服务器升级到同一发行版本。 此要求同样适用于独立主密钥服务器。 |
| 使用企业单一登录独立安装程序进行升级 | 按照以下步骤，在安装有独立企业单一登录的计算机（如专用主密钥服务器）上执行升级。<br/><br/>1.验证是否已将当前主密钥备份到安全位置。<br/>2.验证是否已将当前版本的 SSODB 备份到安全位置。<br/>3.从 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 安装媒体运行 ESSO **Setup.exe**。 默认安装文件夹是 `\Platform\SSO`。<br/>4.在“自动运行”对话框中，选择“Microsoft 企业单一登录”。<br/>5.在“摘要”对话框中，选择“升级”。 |

### <a name="multicomputer-environment"></a>多计算机环境
在多计算机环境中，升级 SSO 主密钥服务器计算机。 之后再升级其他 BizTalk Server 计算机。 不支持同时升级一个组中的 BizTalk 计算机。 按以下顺序一次升级一台计算机：

1. 单一登录主密钥服务器
2. 运行 BizTalk Server 的运行时计算机
3. 管理工具和监视计算机
4. 开发计算机和运行 BizTalk Server 的所有其他剩余的计算机

**补充说明**  
使用设置仪表板，可以细致地调整 BizTalk Server 设置以优化性能。 还可以修改 BizTalk 组、BizTalk 主机和 BizTalk 主机实例的设置。 请参阅[使用 BizTalk Server 性能调整的设置仪表板](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。

### <a name="general-information"></a>一般信息

- **帐户名**：应尽可能使用默认帐户名。 BizTalk Server 安装程序会自动将已安装的组件配置为使用默认帐户。 如果 Active Directory 林中有多个 BizTalk Server 组，请更改帐户名，以避免冲突。 对于服务帐户和 Windows 组，BizTalk Server 仅支持 `<NetBIOS domain name>\<user>` 名称格式。

- **带有 BAM 管理 Web 服务的帐户名**：BizTalk Server 不支持 BAM 管理 Web 服务用户的内置帐户或无密码的帐户。 

  通过此类帐户配置 BizTalk Server 看起来似乎会成功，但是 BAM 管理 Web 服务会发生故障。 

  系统支持将此类帐户用于 BAM 应用程序池。

- 64 位操作系统不支持**BizTalk 程序集查看器**。

- **安装和卸载**：卸载 BizTalk Server 时，请手动删除 BizTalk Server 数据库。 如果是以开发人员或评估师身份安装 BizTalk Server，请考虑在虚拟机上进行安装。 这样，如果您必须进行重新安装，就可以轻松回滚到预设的检查点，而无需完成整个卸载过程。

- **32 位和 64 位计算机**：在 32 位 Windows 或 64 位 Windows 上安装 BizTalk Server 时有一些不同之处。 本文档同时介绍 32 位和 64 位安装。 以下是它们的不同之处。

- **工作组**：支持在单台计算机上的工作组环境中安装和配置 BizTalk Server。 在此方案中，SQL Server 和 BizTalk Server 的功能和组件在同一计算机上安装和配置。

- **终端服务器**：不支持使用在应用程序模式下运行的终端服务器安装 BizTalk Server。 请参阅 [KB 832027](https://support.microsoft.com/kb/832027)。

- 不支持**无提示升级**。

- **不支持的应用程序**：BizTalk Server 不支持在不受支持的 API（例如 PAM API）上生成的自定义应用程序、存储过程或直接数据库访问。 先运行至少一个测试升级，然后再升级生产环境。

- **SQL Server 实例**：良好的做法是在升级平台前先升级任何 SQL Server 实例。

## <a name="prepare-your-computer-for-upgrade"></a>准备计算机以进行升级

| 任务 | 信息 |
| --- | --- | 
| 安装 Windows 的关键更新 | 在“程序”菜单中，选择“Windows 更新”。 可能需要重启计算机。 |
| 保存 BAM 警报定义 | 仅在当前使用现有 BAM 警报定义和 SQL Server 通知服务时适用。 使用 BM.exe 创建定义文件并在 [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 配置中取消对 BAM 警报的配置。<br/><br/>本主题中的**升级之前**部分中列出了具体步骤。<br/><br/>否则，请在升级后重新创建 BAM 警报定义。 |
| 升级 SQL Server | 升级到受支持的 SQL Server 版本。 请参阅：<br/><br/>[BizTalk Server 2016 的硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)<br/>[升级到 SQL Server 2016](https://msdn.microsoft.com/library/bb677622.aspx)<br/>[升级到 SQL Server 2014](https://msdn.microsoft.com/library/bb677622(v=sql.120).aspx) |
| 升级 SQL Server 客户端工具 | 在多计算机环境中，可能会在单独的计算机上安装管理工具。 升级 SQL Server 管理客户端工具，包括管理工具。 |
| 安装 Visual Studio | 有关支持的版本，请参阅 [BizTalk Server 2016 的硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。 可以并行安装不同的 Visual Studio 版本。 请参阅 [Visual Studio 2015](https://msdn.microsoft.com/library/ms246609(v=vs.140).aspx) 和 [Visual Studio 2013](https://msdn.microsoft.com/library/ms246609(v=vs.120).aspx)。 |
| 安装 Office | 请参阅[在同一台计算机上安装和使用不同版本的 Office](https://support.office.com/article/Install-and-use-different-versions-of-Office-on-the-same-PC-6EBB44CE-18A3-43F9-A187-B78C513788BF)。 [BizTalk Server 2016 的硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)列出了支持的 Office 版本。 |
| 停止 BizTalk 和 Windows 服务 | - BizTalk 服务 BizTalk 组：*<Application_Name>*<br/>- BizTalk 基本 EDI 服务<br/>- 规则引擎更新服务<br/>- 万维网发布服务<br/><br/>**注意**<br/>如果安装了任何 BizTalk Server 加速器，请停止 HL7 日志记录服务。 |
| 备份数据库 | - Master<br/>- MSDB<br/>- BAMArchive<br/>- BAMPrimaryImport<br/>- BAMStarSchema<br/>- BizTalkDTADb<br/>- BizTalkEDIDb<br/>- BizTalkHwsDb<br/>- BizTalkMgmtDb<br/>- BizTalkMsgBoxDb<br/>- BizTalkRuleEngineDb<br/>- TPM<br/>- BizTalkAnalysisDb<br/>- BAMAnalysis<br/><br/>[SQL Server 2014：备份概述](https://technet.microsoft.com/library/ms175477(v=sql.120).aspx)<br/>[SQL Server 2012：备份概述](https://technet.microsoft.com/library/ms175477(v=sql.110).aspx) |
| 配置 SQL Server Database Mail | 仅在使用 BAM 警报定义和 SQL Server 通知服务时适用。<br/><br/>本主题中的**升级之前**部分中列出了具体步骤。<br/><br/>否则，请在升级后重新创建 BAM 警报定义。 |

## <a name="do-the-upgrade"></a>执行升级

> [!IMPORTANT]
> 安装 SQL Server 时，安装程序便将系统管理员权限授予你的登录帐户。 安装 BizTalk Server 时也需要系统管理员权限。 执行以下操作之一：
> 
> - 使用安装 SQL Server 时所用的同一帐户  
> **或**  
> - 确保当前的登录帐户具有系统管理员权限

### <a name="upgrade-steps"></a>升级步骤

1. 关闭所有打开的程序。
2. 从安装媒体中运行 **Setup.exe**。
3. 在“开始”中，选择“安装 Microsoft BizTalk Server”。
4. 在“客户信息”中，输入用户名、组织、产品密钥。 选择“下一步”。
5. 接受许可协议，然后选择“下一步”。
6. 在“客户体验改善计划”中，输入首选项。 有关详细信息，请参阅本主题中的**附录 A**。
7. 在“组件安装”中，查看可用组件，然后选择“下一步”。
8. 如果计算机缺少必备组件，则安装程序可能会安装可再发行的必备组件。 您可以：

    - 选择“自动从 Web 安装可再发行的必备组件”  
  
      或  
  
    - 如果已下载 CAB 文件，则选择“自动从 CAB 文件安装可再发行的必备组件”。 浏览到 CAB 文件的位置，然后选择该文件。

9. 在“摘要”中，查看可升级的组件。
10. 选择“升级”以开始升级。
11. 可选：选择“检查更新时使用 Microsoft 更新(推荐)”。
12. 在“升级已完成”中，清除“启动 BizTalk Server 配置”复选框，然后选择“完成”。

**补充说明**  
升级 BizTalk Server 期间会发生很多情况，在此过程中发生错误也就不足为奇了。 但是，如果您作了准备，大多数错误可轻松纠正。 建议阅读本主题中的**附录 B**，了解如何避免升级错误，以及发生错误时应采取的操作。

升级过程仅升级作为前一版本 BizTalk Server 一部分的功能。 升级过程中不安装新的功能。 若要安装这些功能，请在升级之后重新运行安装程序，选择“修改”，然后选择要安装的功能。 安装后，可使用 **BizTalk Server 配置管理器**对其进行配置。

若要验证升级是否成功，请打开“程序和功能”并查找 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 如果已列出，则安装成功。

## <a name="post-upgrade"></a>升级后
无法回退到 [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013。

- **如果创建了 BAM 警报定义 XML 文件**：在 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 配置中，配置 BAM 警报。 然后，部署已保存的定义。

    本主题中的**升级之前**部分中列出了具体步骤。 否则，请在升级后重新创建 BAM 警报定义。

- **安装 MQSAgent**：如果 MQSAgent.dll 文件安装在远程 WebSphere MQ Server 上，请在远程 WebSphere MQ Server 上安装 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 的新版 MQ 代理。

- **启动 MSMQ**：如果使用 MSMQ 适配器，请启动消息队列服务。

- **自定义 EXE 和 BRE**：如果在 BizTalk Server 2010 中具有引用业务规则引擎程序集的自定义托管可执行文件，请将以下内容添加到应用程序配置文件中，以在 .NET Framework 2.0 中运行此进程。

    ```
    \<?xml version="1.0" encoding="Windows-1252"?>
    <configuration> 
     <startup>
      <supportedRuntime version="v2.0.50727" />
     </startup>   
    </configuration>
    ```

- **SQL 代理作业**：重新配置以下 SQL Server 代理作业：

    -   配置 DTA 清除和存档 (BizTalkDTADb)：请参阅[如何配置 DTA 清除和存档作业](../core/how-to-configure-the-dta-purge-and-archive-job.md)
    -   备份 BizTalk Server (BizTalkMgmtDb)：请参阅[如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)

- **重启应用程序**：重启升级后的所有部署的应用程序。

- **BAM 门户错误**：打开 BAM 门户时，可能会收到以下错误消息： 

    `The server encountered a critical failure while trying to access the list of Views. The Business Management Web Service requires Administrator's attention.` 

    如果 BAM 门户是在运行 .NET Framework 2.0 的应用程序所用的网站上配置的，则可能发生此错误。 在这种情况下，应在一个新网站上托管 BAM 门户。 若要添加网站，请参阅[创建网站](http://go.microsoft.com/fwlink/p/?LinkID=196470)。 创建网站后，重新配置 BAM 门户：

    1. 打开“BizTalk Server 配置”。
    2. 选择“取消对功能的配置”。 在“取消对功能的配置”中，选中“BAM 门户”复选框，然后选择“确定”。
    3. 从“BAM 门户网站”列表中选择新网站，重新配置 BAM 门户。

- **用于 SWIFT 的 BizTalk 2016 加速器**：BizTalk Server 升级过程不会更新已编辑的 *BREDeployment.exe.config* 文件。 手动更改 *BREDeployment.exe.config* 文件中的路径，该文件位于 `\Program Files\Microsoft BizTalk 2016 Accelerator for SWIFT\SDK\Tools` 文件夹中。

    另外，A4SWIFT Web 服务和 Message Pack 配置也将丢失。 在 BizTalk Server 升级后，重新配置这些设置。

## <a name="appendix-a-customer-experience-improvement-program"></a>附录 A：客户体验改善计划
根据 BizTalk Server 中的客户体验改善计划，可就 BizTalk Server 的功能使用情况向 Microsoft 提供有用的反馈。 收集的数据是匿名的，不能用来识别你的身份。 Microsoft 会作为此计划的一部分来收集功能使用情况统计信息。

通过参与此计划，您可以帮助我们改进 BizTalk Server 各项功能的可靠性和性能。 若要深入了解此计划及其隐私策略，请参阅 [Microsoft BizTalk Server CEIP 隐私策略](http://go.microsoft.com/fwlink/p/?LinkId=188553)。

## <a name="appendix-b-known-issues"></a>附录 B：已知问题

- **在管理计算机上配置 BAM 警报**：在不同的计算机上安装了管理组件、运行时组件和 SQL Server 组件的多计算机环境。 在使用 BAM 工具或 BAM 警报时，可能会出现以下问题：

    **问题**：在 BizTalk 管理计算机上配置 BAM 工具时，将发生以下错误：
    
    `Service BAMAlerts was not found on computer ‘.’.The specified service does not exist as an installed service.`

    **问题**：从运行时计算机部署 BAM 活动定义时，将发生以下错误：
    
    `A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)`
    
    如果在运行时计算机上配置 BAM 警报，则会发生这种情况。 若要解决，请在 BizTalk 管理控制台的同一台计算机上配置 BAM 警报。 请勿在运行时计算机上配置 BAM 警报。

- **从失败的升级中恢复**：升级过程中随时可能发生升级失败。 如何从失败的升级中恢复将取决于升级失败发生在每个阶段中的哪个点。

    - 如果在安装必备组件时发生升级失败，安装程序将停止必备软件的进一步安装，并返回错误消息。 然后，可更正问题并重新运行安装程序。
    
    - 如果在升级数据库、删除现有 BizTalk Server 版本中的功能或安装新版本时升级失败，则安装程序将停止进一步安装，并返回错误消息。 将回退所做的任何更改。 无法回退对 BizTalk Server 数据库所做的更改。
    
        如果在升级过程中删除了先前安装的 BizTalk Server 的组件，那么计算机可能会保持无 BizTalk Server 组件的状态。 可能会保留先前安装中的功能配置信息。 并且根据升级过程失败的位置，可能已升级了 BizTalk Server 数据库。 可能需要还原之前备份的数据库，然后才能再次运行安装程序。
    
    - 如果在重新配置 BizTalk Server 功能时升级失败，则安装程序将返回完成比例消息。 如果配置升级失败或部分成功，请运行 BizTalk Server 配置来完成升级。
    
    如果升级继续失败并且需要回退到先前版本的 BizTalk Server，则必须还原已备份的数据库，然后再重新安装先前的 BizTalk Server 版本。

- **使用同一版本**：在 BizTalk 应用程序组中，无法运行具有不同版本 BizTalk Server 的计算机。 例如，在 BizTalk 管理控制台中，你无法将运行在一个 BizTalk Server 版本上的发送端口绑定到运行在其他 BizTalk Server 版本上的接收位置。 

- **重启 SSO 服务**：如果在计算机上安装了早期版本的 Visual Studio 或 .NET Framework 4.5，则早期版本的 BizTalk Server 中的 SSO 服务会停止工作。 若要解决此问题，请从 Visual Studio 命令提示符处运行 `regasm SSOSQL.dll` 命令。 该命令将重新启动 SSO 服务。

    > [!NOTE]
    > 在 64 位计算机上，运行 32 位和 64 位版本的 regasm 命令。

- **无法使用 SOAP**：平台升级完成之后，可能会由于没有权限而无法发送 SOAP 消息。 若要解决此问题，请使用下列文本在 `C:\inetpub\wwwroot\<SOAPExternalAppName>\` 处编辑 Web.config 文件：

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

    可能还必须将自定义错误模式从“仅远程”更改为“禁用”。

- **证书存储**：升级后，从 BizTalk Server 管理控制台打开发送端口或接收位置，会出现错误：`Could not open certificate store, the system cannot find the file specified (System).`

    缺少证书存储时会出现此错误。

- **BAM 门户**：在 64 位计算机上，升级后无法访问 BAM 门户。 可能的解决方法：

    1. 创建位于 `%BizTalkInstallDir%\BAMPortal\web.config` 处的 web.config 文件的备份副本。

    2. 使用 BizTalk Server Tracking 文件夹中的 bm.exe，在命令提示符处运行以下命令：`bm.exe get-config –FileName:<filepath> -Server:MyServer -Database:MyDB`

    在 Config XML 文件中，获取 *BAMVRoot* 的值 (xpath: BAMConfiguration\ GlobalProperty\Name="BAMVRoot")。

    3. 打开列为 BAMVRoot 值的计算机上的 BizTalk Server 配置，然后取消对 BAM 门户的配置。

    4. 打开 BizTalk Server 配置，然后配置 BAM 门户。

    5. 从步骤 (1) 中提到的位置打开新的 web.config 文件。

    6. 使用 web.config 文件的备份副本，设置以下值（`configuration\appSettings` 下）：

        - key="MainPageContentUrl"
        - key="AlertNotificationOptions"

    > [!NOTE] 
    > 在 64 位计算机上，升级操作系统之后，建议重新配置 BAM 门户。

- **部署 EDI BAM 活动**：升级时，升级可能会部分成功。 升级已配置 EDI 的 SQL Server 时可能发生这种情况。 可能未正确升级 EDI BAM 活动。 若要解决此问题，请通过使用管理凭据在命令提示符处运行以下命令来部署 BAM 活动：

    `"<BizTalk Installation Folder>\Tracking\bm.exe" deploy-all -DefinitionFile:"<BizTalk Installation Folder>\AS2ResendActivityDefs.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

    `"<BizTalk Installation Folder>\Tracking\bm.exe" update-all -DefinitionFile:"<BizTalk Installation Folder>\Microsoft.BizTalk.Configuration.EdiAS2.UpgradeR2toR3.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

    `"<BizTalk Installation Folder>\Tracking\bm.exe" update-all -DefinitionFile:"<BizTalk Installation Folder>\Microsoft.BizTalk.Configuration.Batching.UpgradeR2toR3.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

- **群集上的 SSO 错误**：在 BizTalk Server 运行时群集环境中，尝试升级时，可能会收到错误消息：

    `SSO Master Secret Server service is not running on <Cluster name>.Please start the service to continue the upgrade.` 

    若要解决此问题，请刷新 SSO 和 BizTalk Server 运行时群集中的 SSO 服务。

    **刷新 SSO 群集中的 SSO 服务**：

    1. 在群集管理器中，对包含群集企业 SSO 服务资源的群集组执行**联机**操作。 这应启动群集组中的所有资源。

    2. 对企业 SSO 服务的群集实例执行**脱机**操作。 然后，让其返回到**联机**状态。

    3. **移动**群集组。 此步骤应将第一个节点上包含群集企业 SSO 服务资源的群集组移到第二个节点上。

    4. 对企业 SSO 服务的群集实例执行**脱机**操作。 然后，让其返回到**联机**状态。

    **刷新 BizTalk Server 运行时群集中的 SSO 服务**：

    1. 在群集管理器中，对包含群集 BizTalk Server 运行时资源的群集组执行**联机**操作。 这应启动群集组中的所有资源。

    2. 对企业 SSO 服务的群集实例执行**脱机**操作。 然后，让其返回到**联机**状态。

    3. **移动**群集组。 此步骤应将第一个节点上包含群集 BizTalk Server 运行时资源的群集组移到第二个节点上。

    4. 对企业 SSO 服务的群集实例执行**脱机**操作。 然后，让其返回到**联机**状态。