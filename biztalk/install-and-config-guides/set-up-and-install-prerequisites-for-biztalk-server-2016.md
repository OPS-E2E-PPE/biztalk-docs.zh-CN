---
title: 设置和安装 BizTalk Server 2016 的必备组件 |Microsoft Docs
description: 安装和配置所需的软件和设置 BizTalk Server 2016 的分步说明
author: MandiOhlinger
manager: anneta
ms.prod: biztalk-server
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa70b621-903a-4cfa-9cb0-c6a82ed8f733
caps.latest.revision: 11
ms.author: mandia
ms.openlocfilehash: aab7bb1fa22a249eb287f01b2050d10d9f0042ac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018050"
---
# <a name="set-up-and-install-prerequisites-for-biztalk-server-2016"></a>设置和安装 BizTalk Server 2016 的必备组件
设置服务器，然后安装和配置软件必备组件。

## <a name="join-the-administrators-group"></a>加入管理员组
若要安装并配置 BizTalk Server，在本地计算机上使用管理员帐户登录到服务器。 向本地管理员组添加任何管理 BizTalk Server 的用户帐户：

1.  在开始菜单中，打开“计算机管理”。

    * 或者，打开“管理工具”，然后选择“计算机管理”。
    * 或者，打开“服务器管理器”，选择“工具”，然后选择“计算机管理”。
  
2.  展开“本地用户和组”，然后选择“组”。
3.  右键单击“管理员”组，然后选择“添加到组”。 **添加**帐户，然后选择“确定”以保存更改。 

## <a name="change-the-computer-name-optional"></a>更改计算机名称 （可选）
如果您的计算机名称的长度超过 15 个字符，则 BizTalk Server 配置失败。 将计算机名称更改为少于 15 个字符：

1.  在“服务器管理器” > “仪表板”中，选择“本地服务器”。 
2.  在“属性”中，选择“计算机名称”属性以对其进行更改。
3. 重新启动计算机。 

**另请参阅**：Windows PowerShell [Rename-Computer](https://technet.microsoft.com/library/hh849792.aspx)

## <a name="enable-network-dtc-access"></a>启用网络 DTC 访问
如果 BizTalk 和 SQL Server 安装在不同的计算机上，则对 BizTalk Server 和 SQL Server启用网络 DTC 访问。 

1. 在“开始”菜单中，打开 "dcomcnfg"。

    * 或者，打开“管理工具”，然后选择“组件服务”。
    * 或者，打开“服务器管理器”，选择“工具”，然后选择“组件服务”。
  
2. 依次展开“组件服务”、“计算机”、“我的电脑”和“分布式事务处理协调器”。
3. 右键单击“本地 DTC”，再选择“属性”。
4. 转到“安全”选项卡，然后检查以下内容：  
    * 网络 DTC 访问
    * 允许入站
    * 允许出站
    * 不要求进行身份验证
5. 选择“确定”。 如果系统提示重新启动 MS DTC，请选择**是**。 

有关可能需要的其他设置，请参阅 [MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。

## <a name="configure-application-event-log-optional"></a>配置应用程序事件日志 （可选）

BizTalk Server 安装程序会将事件记录保留在应用程序事件日志中。 日志中所需的空间量可能会超出其限制，具体取决于已安装的 BizTalk Server 功能。 如果在应用程序事件日志在安装期间出现空间不足，安装将失败。 更改“应用程序事件日志”设置可防止此故障。

1. 在“开始”菜单中，打开“事件查看器”：

    * 或者，打开“管理工具”，然后选择“事件查看器”。
    * 或者，打开“服务器管理器”，选择“工具”，然后选择“事件查看器”。
  
2. 展开“Windows 日志”，右键单击“应用程序”，然后选择“属性”。 
3. 若要确定可用空间，请比较“日志大小”和“最大日志大小”属性。 

    * 若要添加空间，请在“日志最大大小”中输入一个更大的值。
    * 若要在日志变满时启用对旧事件的覆盖功能，请选择“按需要覆盖事件”。
    * 若要清除日志事件，请选择“清除日志”。

4. 选择“确定”。

## <a name="edge-cant-be-opened-optional"></a>无法打开 edge （可选）

使用 Edge 时，会显示以下消息：  
`Microsoft Edge can't be opened using the Built-in Administrator account. Sign in with a different account and try again.`

若要允许使用内置的管理员帐户打开 Edge：

1. 在“开始”菜单中，打开“本地安全策略”。 或者，打开“服务器管理器”，选择“工具”，然后选择“本地安全策略”。
2.  展开“本地策略”，然后选择“安全选项”。 
3.  转到“用户帐户控制：内置管理员帐户的管理员批准模式”策略，然后“启用”该策略。 
4. 选择“确定”，然后重启计算机。

## <a name="install-windows-updates"></a>安装 Windows 更新

请务必安装 Windows 最新重要更新。 

1. 在“开始”菜单上，打开“Windows 更新”，然后检查更新。 还可以打开“设置”，然后选择“更新和安全”。
2. 安装更新之后，你可能需要重新启动计算机。

## <a name="enable-iis"></a>启用 IIS
BizTalk Server 的下列功能需要 IIS：

- HTTP 适配器
- SOAP 适配器
- Windows SharePoint Services 适配器
- 安全套接字层 (SSL) 加密
- BAM 门户
- EDI

IIS 是作为“角色”或“功能”随附于操作系统，具体取决于 OS。 安装步骤：

1. 在“开始”菜单中，打开“打开或关闭 Windows 功能”。 或者，打开“服务器管理器”，选择“管理”，然后选择“添加角色和功能”。
2. 选择“Internet Information Services”或“Web 服务器 (IIS)”。 除了已默认选中的选项之外，还应选择以下选项： 

    **Windows 10**
   - 在“Web 管理工具”中，还需检查：  
       - IIS 6 管理兼容性
       - IIS 6 管理控制台
       - IIS 6 脚本工具（安装 adsutil.vbs）
       - IIS 元数据库和 IIS 6 配置兼容性
       - IIS 管理控制台
   - 在“万维网服务”中，展开“安全性”，同时检查：
       - 基本身份验证
       - Windows 身份验证    

     **Windows 服务器**
   - 在“安全性”中，还需检查： 
       - 基本身份验证
       - Windows 身份验证    
   - 在“管理工具”中，还需检查：  
       - IIS 管理控制台
       - IIS 6 管理兼容性
       - IIS 6 元数据库兼容性
       - IIS 6 管理控制台
       - IIS 6 脚本工具（安装 adsutil.vbs）

3. 继续进行安装，并且在系统提示时重启计算机。 

**另请参阅**：在 [Windows 8 或 Windows Server 2012](http://www.iis.net/learn/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012) 上安装 IIS。


## <a name="run-64-bit-bam-portal-optional"></a>运行 64 位 BAM 门户 （可选）
如果不使用 BAM 门户，则可以跳过此部分。 

在 32 位模式下运行 BAM 门户。 如果在 64 位环境中使用 Internet 信息服务 (IIS)，然后设置要在 32 位模式下运行的应用程序池。 

#### <a name="using-adsutilvbs"></a>使用 adsutil.vbs
1.  以管理员身份打开命令提示符。 
2.  在命令提示符下，输入：  
    `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`
3. 按 Enter。

#### <a name="using-iis-manager"></a>使用 IIS 管理器
1. 在“开始”菜单中，打开 "inetmgr"。
2.  展开计算机名称，然后选择“应用程序池”。
3.  右键单击“DefaultAppPool”，然后选择“高级设置”。 
4.  将“启用 32 位应用程序”的值更改为 **True**。 
5.  选择“确定”。

## <a name="install-windows-identity-foundation-wif-optional"></a>安装 Windows Identity Foundation (WIF)（可选）
如果使用 SharePoint Services 适配器，BizTalk Server 需要 WIF。 如果不使用 SharePoint Services 适配器，则可跳过本部分。

Windows Identity Foundation 作为一项**功能**包括在操作系统中。

1. 在“开始”菜单中，打开“打开或关闭 Windows 功能”。 或者，打开“服务器管理器”，选择“管理”，然后选择“添加角色和功能”。
2. 选择“Windows Identity Foundation 3.5”，然后继续进行安装。 
3. 如果系统提示，则重启计算机。

## <a name="install--configure-smtp-server-optional"></a>安装和配置 SMTP 服务器 （可选）
如果使用 BAM 警报时，BizTalk Server 需要 SMTP 服务器。 如果不使用 BAM 警报，则可跳过本部分。

SQL Server 数据库邮件使用 SMTP 服务器发送 BAM 警报。 SMTP 服务器可以本地安装在 BizTalk Server 上，也可以安装在其他已安装 IIS 的服务器上。 SMTP 服务器在客户端操作系统上不可用，例如 Windows 8.1 或 Windows 10。 

SMTP 服务器作为一项**功能**包括在服务器操作系统中。

1. 在“开始”菜单中，打开“打开或关闭 Windows 功能”。 或者，打开“服务器管理器”，选择“管理”，然后选择“添加角色和功能”。
2. 选择“SMTP 服务器”，然后继续进行安装。 
3. 如果系统提示，则重启计算机。

## <a name="install-excel-2016-or-2013-optional"></a>安装 Excel 2016 或 2013 （可选）
如果使用业务活动监视 (BAM)，BizTalk Server 需要 Excel。 如果不使用 BAM，则可跳过本部分。

可以使用 BAM Office Excel 工作簿来定义要监视的业务流程。 还可以使用 BAM Excel 工作簿定义业务用户查看 BAM 所收集的数据的方式。

> [!IMPORTANT] 
> * BizTalk Server 仅支持 32 位版本的 Microsoft Office。 
> * 若要成功将 BAM.xla 加载到 Excel 中，请在“Office 共享功能”下安装“Visual Basic for Applications”。 否则，可能会出现错误：`This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`

#### <a name="install-excel-2016"></a>安装 Excel 2016

Office 2016 是使用“即点即用”或“C2R 安装程序”进行安装的。 C2R 安装下载并安装 Office 中的所有程序。 对于 BAM，我们只需要 Excel。 若要解决此问题，请下载并安装 [Office 2016 部署工具](https://www.microsoft.com/download/details.aspx?id=49117)以自定义 C2R 安装程序。

1. 下载并安装 [Office 2016 部署工具](https://www.microsoft.com/download/details.aspx?id=49117)。
2. 在具有提取的 Office 2016 部署工具文件的文件夹中，使用文本编辑器，如记事本，打开 **configuration.xml**。
3. 将 `<Configuration>` 部分替换为以下内容：  

    ```
    <Configuration>
    <Add SourcePath="D:\" OfficeClientEdition="32">
    <Product ID="O365ProPlusRetail" >
      <Language ID="en-us" />
      <ExcludeApp ID="Access" />
      <ExcludeApp ID="Groove" />
      <ExcludeApp ID="InfoPath" />
      <ExcludeApp ID="Lync" />
      <ExcludeApp ID="OneDrive" />
      <ExcludeApp ID="OneNote" />
      <ExcludeApp ID="Outlook" />
      <ExcludeApp ID="PowerPoint" />
      <ExcludeApp ID="Project" />
      <ExcludeApp ID="Publisher" />
      <ExcludeApp ID="SharePointDesigner" />
      <ExcludeApp ID="Visio" />
      <ExcludeApp ID="Word" />
    </Product>
    </Add>
    </Configuration>
    ```
    
    将 "SourcePath" 替换为 Office 2016 ISO 文件的位置。
4. 在具有 Office 2016 部署工具文件的文件夹中，按住 **SHIFT** 键，然后右键单击该文件夹中的空白区域。 选择“在此处打开命令窗口”。 
5. 输入以下内容，以开始 Excel 安装：  
  `setup.exe /configure configuration.xml`

    > [!TIP]
    > `setup.exe /download configuration.xml` 下载所需的 Office 安装程序文件。
 
6. 选择“Excel”，然后继续安装。 
 
**另请参阅**：[Office 部署工具的配置选项](https://technet.microsoft.com/library/jj219426.aspx)和[安装 Office 2016 或 2013](https://support.office.com/article/Install-Office-on-your-PC-or-Mac-4414eaaf-0478-48be-9c42-23adc4716658)

#### <a name="install-excel-2013"></a>安装 Excel 2013
1. 运行 Microsoft Office 安装程序。
2. 选择“自定义安装”，然后选择“Excel”。
3. 继续安装。   

## <a name="install-visual-c-redistributable-package"></a>安装 Visual c + + 可再发行组件包

下载并安装[Visual c + + 可再发行组件包](https://support.microsoft.com/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package)。 即使使用的是 Visual Studio 2015，也需要 2013 版本。

[Visual c + + 下载](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)列出所有可用版本。

## <a name="install-visual-studio-2015-optional"></a>安装 Visual Studio 2015（可选）
BizTalk Server 需要 Visual Studio，以使用开发工具创建 BizTalk 项目。 如果这是临时或生产服务器，或没有在进行任何 BizTalk 开发，则跳过此部分。

建议使用 Visual Studio 企业版，但也支持专业版和社区版。 

1. 以管理员身份运行 Visual Studio 安装程序。
2. 选择“默认”安装。 BizTalk Server 不需要任何可选功能。

    > [!NOTE]
    > 如果对多个 BizTalk 项目使用 Visual Studio，则选择“自定义”安装来安装其他功能。 一些常用功能包括 Microsoft Web 开发人员工具、Microsoft Office 开发人员工具、适用于 Visual Studio 的 PowerShell 工具以及 ClickOnce 发布工具。
 
3. 继续进行安装，并且在系统提示时重启计算机。

**另请参阅**：[安装 Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx)

> [!IMPORTANT]
> - 如果在安装 BizTalk Server 之前安装 Visual Studio，然后升级到 Visual Studio Team Explorer，可能需要修复 BizTalk Server 安装。
> - Visual Studio 会自动安装 Microsoft SQL Server Express；而 BizTalk Server 并不使用它。 卸载 Microsoft SQL Server Express。 还可以卸载 Microsoft SQL Server Compact。  
> - BizTalk Server 开发工具基于 Visual Studio。 在安装 BizTalk Server 开发人员工具和 SDK 之前，至少需安装 Microsoft Visual C#® .NET 组件。
> - BizTalk Server 运行时组件需要 .NET Framework 4.6。 如果安装了 Windows Communication Foundation (WCF) 适配器或 WCF 侦听器，则需要.NET Framework 3.0

#### <a name="uninstall-sql-server-express"></a>卸载 SQL Server Express
1. 在“开始”菜单中，打开“程序和功能”。 或者，打开“控制面板”，然后选择“卸载程序”。
2. 卸载： 
    - Microsoft SQL Server 2014 Express LocalDb
    - Microsoft SQL Server Compact 4.0 SP1 x64 ENU
    - Microsoft SQL Server 2016 LocalDB (SQL Server 2016 Express LocalDB)
    
3. 继续进行卸载，并且在系统提示时重启计算机。 

## <a name="install-sql-server-2016"></a>安装 SQL Server 2016
BizTalk Server 需要 SQL Server。 SQL Server 可以和 BizTalk 安装在同一台计算机上，也可以安装在不同的计算机上。 大多数生产环境在不同的服务器上安装 BizTalk 和 SQL。 

> [!IMPORTANT]
> - 不建议使用或不支持 SQL Server Express Edition。 Express Edition 不包括 BizTalk Server 需要的某些功能。
> - BizTalk Server 支持 SQL 标准版。 但是，为使用业务活动监视实时聚合 (BAM RTA)，需安装 SQL Server Enterprise Edition。 SQL Server 标准版中不支持 BAM 实时聚合 (RTA)。
> - 若要从 Visual Studio 全面使用 BizTalk Server SDK 或部署 BizTalk Server 应用程序，请安装 SQL Server 开发工具。
> - BizTalk Server 支持所有区分大小写和不区分大小写的 SQL Server 排序规则，二进制排序规则例外。 不支持二进制排序规则。

**有关特定的安装步骤，请参阅**[安装 SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup)或[安装 SQL Server 2014](https://msdn.microsoft.com/library/bb500469(v=sql.120).aspx)。

1. 开始 SQL Server 安装。 
2. “功能”设置期间，选择以下内容：
   - 数据库引擎服务
       - SQL Server 复制
       - R Services （数据库内） (**可选**; 信息，请参阅[SQL Server R Services](https://docs.microsoft.com/sql/advanced-analytics/r/sql-server-r-services))
       - 用于搜索的全文和语义提取
   - Analysis Services
   - Reporting Services - 本机
   - 共享功能
       - 客户端工具连接
       - Integration Services

     > [!NOTE]
     > **SQL Server Data Tools** 未包含在 SQL Server 的默认安装中。 它不是必需的但可以从以下网址下载[SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt)。 下载可与所有 SQL Server 的支持版本兼容的 [**SQL Server Management Studio (SSMS)**](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)，其中包括 Azure SQL 数据库。 但是，若要连接到远程 SSIS 使用 BAM 时，需要与目标 SSIS 服务器安装相同版本的 SSMS。 例如，[安装 SSMS 16。*x* ](https://docs.microsoft.com/sql/ssms/sql-server-management-studio-changelog-ssms?view=sql-server-2017#previous-ssms-releases)安装相关驱动程序连接到 SQL 2016 SSIS。 SSMS 17。*x*无法连接到 SQL 2016 SSIS。 您可以安装 SSMS 的多个版本。 

3. 继续进行安装，并且在系统提示时重启计算机。

## <a name="disable-shared-memory"></a>禁用共享的内存

1. 打开 **SQL Server 配置管理器**。
2. 在 SQL Server 配置管理器中，展开**SQL Server 网络配置**，然后选择**MSSQLSERVER 的协议**。
3. 右键单击“共享内存”，然后选择“禁用”。
4. 选择**SQL Server Services**，右键单击 SQL **Server (MSSQLSERVER)**，然后选择**停止**。 服务已停止后，右键单击**SQL Server (MSSQLSERVER)**，然后选择**启动**。
5. 关闭“SQL Server 配置管理器”。

通常情况下，Shared Memory 协议只会影响与 SQL Server 在同一台计算机上安装的客户端 (BizTalk Server)。 在任务繁忙时（例如，客户端从同一计算机访问 SQL Server 时），SQL Server Shared Memory 协议可能会降低 BizTalk Server 性能。 禁用 Shared Memory 网络协议解决此问题。

> [!TIP]
> 如果 SQL Server 代理无法启动后禁用共享内存，然后确认[ODBC Driver 13.1 for SQL Server](https://www.microsoft.com/download/details.aspx?id=53339)安装。

## <a name="install-sql-xml-4"></a>安装 SQL XML 4
这是 BizTalk Server 运行时、管理工具和 BAM 所必需的。 

下载并安装[SqlXml 4.0](https://www.microsoft.com/download/details.aspx?id=30403)。

## <a name="configure-sql-database-mail-optional"></a>配置 SQL Database Mail （可选）
如果使用 BAM 警报时，BizTalk Server 需要 SQL Server Database Mail。 如果未使用 BAM 警报，则跳过此部分。 

**另请参阅**：[Database Mail](https://docs.microsoft.com/sql/relational-databases/database-mail/database-mail) 的详细信息。

> [!IMPORTANT]
> - 需要知道 SMTP 服务器的服务器名称和 TCP 端口号。 如果在此同一台计算机上安装 IIS 和 SMTP 服务器，则使用本地 SMTP 服务器。 如果 SMTP 服务器需要身份验证，则准备好 SMTP 服务器名称和密码。
> - BAM 门户和 BAM 警报是不同的功能。 如果使用 BAM 警报，则需要 SQL Server Database Mail。 如果不使用 BAM 警报，则不需要 SQL Server Database Mail。

**有关特定的配置步骤，请参阅**： 配置[SQL Server 2016 Database Mail](https://docs.microsoft.com/sql/relational-databases/database-mail/configure-database-mail)或[SQL Server 2014 Database Mail](https://msdn.microsoft.com/library/hh245116(v=sql.120).aspx)。

   
若要发送测试电子邮件： 
1.  右键单击“Database Mail”，然后选择“发送测试电子邮件”。 
2.  输入“收件人：”电子邮件地址，然后选择“发送测试电子邮件”。  
 
如果“收件人:”收到该电子邮件，则已配置 Database Mail。 

## <a name="install-winscp-optional"></a>安装 WinSCP （可选）
所需的 FTP 适配器。 如果不使用 FTP 适配器，则跳过此部分。 

下载并安装[WinSCP](http://winscp.net)。 

## <a name="next-step"></a>下一步
安装 [BizTalk Server 2016](../install-and-config-guides/install-biztalk-server-2016.md)。
