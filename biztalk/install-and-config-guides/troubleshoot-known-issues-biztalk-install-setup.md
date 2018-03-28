---
title: 已知的安装问题 |Microsoft 文档
description: 已知的问题和常见问题和解决方法时安装和配置 BizTalk Server
ms.custom: ''
ms.date: 11/30/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4d0e707-6b9e-49e1-9f17-19b3bac1229e
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90217a4e80df6f017b451dd7c40f6a1dfe3898ac
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="troubleshoot-biztalk-server-setup"></a>BizTalk Server 安装程序疑难解答

## <a name="introduction"></a>简介  
 本疑难解答指南列出已知的问题，以及安装 BizTalk Server 时可能遇到的最常见问题。 本指南还包括自定义操作，提供有关 Windows Server 徽标计划的 BizTalk Server 认证的详细信息。  它提供你的 BizTalk Server 安装程序操作过程中可能会执行的自定义操作的列表。  
  
## <a name="review-install-steps"></a>查看安装步骤  
绝大部分 BizTalk Server 安装问题出现的原因为在安装 BizTalk Server 前未正确准备 BizTalk Server 计算机，或是在尝试新的安装前之前没有完全卸载以前的 BizTalk Server 安装。  
  
查看两个检查表，下面，你还可以在 BizTalk Server 安装指南，以确保您的计算机正确配置以支持 BizTalk Server 中找到。 如果在检查该信息之后，您的安装仍然无法成功完成，本文档其他部分中的疑难解答提示可能会有所帮助。  
  
1. 安装必备软件和程序：

    * [BizTalk Server 2016](set-up-and-install-prerequisites-for-biztalk-server-2016.md)
    * [BizTalk Server 2013 R2 & 2013](prepare-your-computer-for-installation.md)

2. 安装和配置 BizTalk Server:  

    1. 安装 BizTalk Server: [BizTalk 2016](install-biztalk-server-2016.md) ， [BizTalk 2013 R2 / 2013年](install-biztalk-server-2013-and-2013-r2.md)  
    2. [配置](configure-biztalk-server.md)BizTalk Server
    3. [配置后步骤](post-configuration-steps-to-optimize-your-environment.md)
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a>某些 EDI/AS2 项目仍处于活动状态后未配置  
  
**问题**  
 后取消配置 BizTalk Server 中，与 EDI 某些 BizTalk 服务器项目的 BizTalk EDI/AS2 功能和 AS2 处理将仍然处于活动状态的 BizTalk 组配置的上下文中。 这些项目将包括 EDI 和 AS2 管道以及批处理业务流程。 因此，即使在取消对 BizTalk EDI/AS2 功能的配置后，您仍然能够执行基本的 EDI 和 AS2 处理。  
  
**可能的原因**   
 存在与 EDI 和 AS2 处理关联的活动端口。 某些项目在这些端口保持活动时会继续工作。  
  
**解决方法**  
 若要禁用所有 EDI/AS2 项目，应禁用、停止或删除与 EDI 和 AS2 处理关联的端口。  
  
## <a name="after-renaming-biztalk-or-sql-server-computer-the-configuration-wizard-fails"></a>重命名后 BizTalk 或 SQL Server 的计算机，则配置向导将失败  
  
**问题**  
 此问题的表现方式有多种：  
  
-   配置管理器可以正确加载“概述”页，但是在尝试配置功能时，屏幕中不显示功能选项。  
  
-   配置向导无法连接到 SQL Server。  
  
-   尝试使用“取消对所有功能的配置”时仅取消了对部分功能而不是所有功能的配置。  
  
**可能的原因**   
 BizTalk Server 配置存储了计算机的网络名称。 在计算机重命名后，configuration manager 和配置向导找不到 BizTalk Server。 如果在对 BizTalk Server 进行配置之后重命名了 SQL Server 计算机，将会出现类似的问题。  
  
**解决方法**  
 请不要重命名 BizTalk Server 计算机或 SQL Server 计算机。 如果必须对服务器进行重命名，请取消对所有 BizTalk 功能的配置，然后再重命名计算机。 在重命名计算机后，请重新配置 BizTalk Server 功能。  
  
## <a name="business-rules-configuration-wizard-fails"></a>业务规则配置向导将失败  
  
**问题**  
  
-   业务规则配置向导失败，并显示错误“某些组件的配置失败，这些组件未应用任何设置”。  
  
-   在已为其成功配置业务规则引擎的 BizTalk Server 计算机上，规则引擎更新服务启动失败并且不能手动启动。  
  
出现此问题时，可能会在 BizTalk Server 计算机的应用程序日志中生成与下面类似的错误：  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
**可能的原因**   
 Microsoft 恶意软件防护中心发布上 9，2010 年 3 月来解决从 SettingsModifier:Win32 可能威胁的更新的签名文件 / PossibleHostsFileHijack。 此更新的签名文件可能导致 Microsoft 恶意软件检测软件（例如 Windows Defender）更新本地 HOSTS 文件，以缓解来自 SettingsModifier:Win32/PossibleHostsFileHijack 的威胁。 由于这些更改，BizTalk Server 规则引擎更新服务可能启动失败。  
  
**解决方法**  
 更新本地 HOSTS 文件以包括以下行：  
  
```  
127.0.0.1         localhost  
```  
  
 HOSTS 文件位于 %systemroot%\drivers\etc\ 目录中。  
  
> [!NOTE]
> 请参阅更新，以从的地址可能发生的威胁的 Microsoft 恶意软件防护中心签名[SettingsModifier:Win32 / PossibleHostsFileHijack](http://go.microsoft.com/fwlink/?LinkId=146221)。  
  
## <a name="configuration-logging"></a>配置记录  
 配置程序将写入配置日志文件位于默认情况下运行 BizTalk Server 的计算机的临时目录中的详细的信息。 若要确定由 TEMP 环境变量指定的文件夹，请在此计算机上打开命令提示符，键入以下命令，然后按 Enter：  
  
 **echo %TEMP%**  
  
 配置日志文件中包含所执行的配置步骤的摘要，以及在配置过程中可能发生的任何故障的诊断信息。 如果出现配置错误，请在文本编辑器（如“记事本”）中打开配置日志，然后在日志中检查此错误的可能原因。  
  
## <a name="troubleshooting-tools"></a>疑难解答工具  
 使用 SQL Server Profiler、Filemon 或 Regmon 收集有关配置失败的其他信息。 请参阅[用于故障排除工具和实用程序](../core/tools-and-utilities-to-use-for-troubleshooting.md)。  
  
### <a name="configuration-fails-when-biztalk-and-sql-are-installed-on-separate-computers"></a>单独的计算机上安装 BizTalk 和 SQL 时，配置将会失败  
  
**问题**  
 当尝试配置 Enterprise 单一登录 (SSO) 组件时，配置失败并出现如下错误：  
  
```
An error occurred while attempting to access the SSO database.  
Function: FieldInfoCreate  
```
  
 - 或 -  
  
```Failed to enable the Single Sign-On (SSO) Service (error code 0X800706BA)```  
  
**可能的原因**    
 如果在不同计算机上安装 BizTalk Server 和 SQL Server 的 Microsoft 分布式事务处理协调器 (MSDTC) 事务的上下文中执行的配置操作然后 MSDTC 功能必须可通过这些计算机之间的网络。 如果通过运行 BizTalk Server 和 SQL Server 的计算机之间的网络 MSDTC 功能不可用，可能发生此错误。  
  
**解决方法**    
使用[问题疑难解答与 MSDTC](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues)确保 MSDTC 功能将通过运行 BizTalk Server 和 SQL Server 的计算机之间的网络。  
  
### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a>防病毒软件干扰配置并导致配置失败  
  
**问题**   
 当防病毒软件未正确确定配置程序是病毒，BizTalk Server 配置将失败。  
  
**可能的原因**  
 防病毒软件尚未更新为包括为合法的 （非病毒） 程序的 BizTalk Server 配置程序。  
  
**解决方法**  
 配置防病毒程序来将 BizTalk Server 配置程序识别为合法的 （非病毒） 程序或者暂时禁用防病毒软件配置程序运行时。  
  
### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a>配置失败，并出现错误“找不到文件或程序集名称 FileName.dll，或找不到它的一个依赖项”  
  
**问题**  
 在配置过程中显示如下错误：  
  
 无法部署 BizTalk 系统程序集"C:\Program Files\Microsoft\BizTalk Server 20xx\Microsoft.BizTalk.DefaultPipelines.dll。 未指定的异常： 未找到文件或程序集名称 FileName.dll，或其依赖项之一。"  
  
**可能的原因**  
 如果网络服务帐户没有写入权限的临时文件夹运行 BizTalk Server 的计算机上，可能出现此错误。 在配置期间，BizTalk Server 配置使用 Windows Management Instrumentation (WMI) 将.NET 程序集部署到 BizTalk 管理数据库。 WMI 将这些程序集部署到 BizTalk 管理数据库时模拟的网络服务帐户，因此网络服务帐户必须具有写入访问权限运行 BizTalk Server 的计算机上的临时文件夹。  
  
**解决方法**  
 授予对运行 BizTalk Server 的计算机上的临时文件夹的网络服务帐户写入访问权限，然后重新运行配置程序。 若要确定由 TEMP 环境变量指定的文件夹，打开命令提示符的计算机上，键入以下命令，然后按 ENTER:  
  
```  
echo %TEMP%  
```  
  
### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a>如果 SQL Server 数据文件夹中已经存在与指定的数据库同名的 SQL Server 数据库文件，则配置将失败  
  
#### <a name="problem"></a>问题  
 配置失败，并出现如下错误：  
  
```
Failed to set up BAM database(s)  
  
Cannot open database requested in login 'BAMPrimaryImport'  
  
Logon fails. Logon failed for user '*BizTalk\BizTalkUser*'  
```
  
**可能的原因**  
 如果.mdf 文件，会出现此错误，或运行具有.mdf 文件或 BizTalk Server 配置程序尝试创建的.ldf 文件的名称相同的 SQL Server 的计算机的 \MSSQL\data 文件夹中已存在的.ldf 文件。 为数据库创建的.mdf 文件和.ldf 文件的名称派生而来的数据库的.mdf 和.ldf 扩展名追加与 BizTalk Server 配置程序中指定的名称。  
  
**解决方法**  
 若要解决此行为的问题，请执行以下操作之一：  
  
-   删除其名称与您要创建的任何数据库的名称匹配的任何 .mdf 文件或 .ldf 文件。  
  
-   选择数据库名称时，确保其与 SQL Server 的 \Program Files\Microsoft SQL Server\MSSQL\data 文件夹中已经存在的任何 .mdf 文件或 .ldf 文件的名称都不匹配。  
  
### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a>当指定本地帐户时，域控制器上的配置失败  
  
**问题**  
 在运行 BizTalk Server 配置程序时的域控制器上，配置有 BizTalkServerApplication 主机或 BizTalkIsolatedHost 主机失败如果指定的本地组 （例如，BizTalk 主机用户组）。  
  
**可能的原因**  
 域控制器自动将本地 Windows 组视为域 Windows 组（在域控制器上不存在本地 Windows 组）。 如果运行配置程序时为主机指定本地 Windows 组，则配置会失败时尝试创建组的 SQL Server 登录。 当服务器是域控制器时，配置程序不禁用本地 Windows 组选项。  
  
**解决方法**  
 为在配置过程中创建的主机指定域组。  
  
### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a>如果尚未重命名 SQL Server，配置将无法创建 SQL Server 分析数据库  
  
**问题**  
 如果您已经对安装了 SQL Server 分析服务器的计算机进行了重命名，当配置程序尝试新建 SQL Server 分析数据库时将失败，并且生成如下错误：  

```  
 Cannot connect to the repository.  
  
 Analysis server: <machine name\>  
  
 Error:  
  
 '\\\\<machine name\>\MsOLAPRepository$\msmdrep.mdb' is not a valid path.  
  
 Make sure that you correctly spell the path name and that you are  
  
 connected to the server on which the file resides.  
```
  
**可能的原因**  
 配置程序无法确定您安装了 SQL Server 分析服务器的计算机的新名称。  
  
**解决方法**  
 手动执行下列操作，以便用新的计算机名更新分析服务器：  
  
1.  在 SQL 服务器上，打开**Microsoft SQL Server**，选择**Analysis Services**，然后单击**Analysis Manager**。  
  
2.  在 **Analysis Manager** 导航面板中，双击 **分析服务器** 节点以将其展开。  
  
3.  右键单击你想要编辑，，然后选择的存储库连接字符串服务器 **编辑储存库连接字符串**。  
  
4.  在 **编辑储存库连接字符串** 对话框中，验证此字符串中的服务器名称，为新的计算机名称进行更新，如果不正确。  
  
5.  导航到以下位置︰ <*安装目录*> files\microsoft Analysis Services\Bin。  
  
6.  右键单击 **Bin** 文件夹，，然后单击 **共享和安全**。 **Bin 属性** 对话框随即出现。  
  
7.  在 **Bin 属性** 对话框中，单击 **共享** 选项卡以验证所有联机分析处理 (OLAP) 管理员具有对此文件夹的完全权限。  
  
### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a>从配置数据库消失上的 Visual Studio 中的程序集的重新部署的项目  
  
**问题**  
 当 BizTalk 服务器项目重新部署后在 Visual Studio 中的项目级引用正在重新部署项目看起来消失时刷新 BizTalk Server MMC 项目中包含的所有项目。  
  
**可能的原因**  
 为了说明此问题的原因，请看以下示例，此示例基于一个示例 BizTalk Server 解决方案，用户要在此解决方案中重新部署 Maps 项目。 请注意，对项目进行编译将生成单独的程序集。 下图表示用户在进行重新部署之前，此解决方案的状态。 项目之间的关系如下所示：  
  
-   Orch1、Orch2、Maps、Pipelines 和 Schemas 为项目。  
  
-   Orch1 引用 Maps，而 Maps 引用 Schemas。  
  
-   Orch2 引用 Schemas。  
  
-   Pipelines 引用 Schemas。  
  
![bcd_ExistingBizTalkServerSolutionc](../install-and-config-guides/media/bcd_ExistingBizTalkServerSolutionc.gif)  
  
如果用户使用默认的 Visual Studio 项目设置重新部署 Maps 项目，则 Orch1、Orch2 和 Pipeline 项目将消失，如下图所示。  
  
![bcd_BizTalkSolutionWLostArtifactsc](../install-and-config-guides/media/bcd_BizTalkSolutionWLostArtifactsc.gif)  
  
 重新部署 Maps 的过程分为两步，首先取消部署当前已部署的 Maps.dll 程序集，然后部署新的 Maps.dll 文件。 Visual Studio 会重新部署过程的一部分自动执行以下步骤。  
  
> [!NOTE]
>  严格来说，上面的描述并不正确，因为这些是 Visual Studio 一直执行的步骤，因此并没有考虑其方式是否适当。  
  
 关键之处在于，若要取消部署的 BizTalk Server 程序集，Visual Studio 必须取消部署的所有程序集依赖于该程序集，将部署标志设置。 在本例中，要执行重新部署过程的第一个取消部署步骤，BizTalk Server 需要取消部署 Orch1.dll（而它依赖于 Maps.dll）。 期间的 Maps.dll 取消部署，Visual Studio 还取消部署 Schemas.dll （假设它已将部署标志设）。 为了取消部署 Schemas.dll，Visual Studio 需要取消部署 Orch2.dll 和 Pipelines.dll（这两者都依赖于 Schemas.dll）。  
  
 只有 Maps.dll 和它取决于程序集，将重新部署 Visual Studio，因为存在问题： 在此情况下，Schemas.dll。 因此，当用户刷新 BizTalk Server MMC，Orch1、 Orch2，和管道程序集似乎已消失，但 Maps.dll 和 Schemas.dll 仍将可见。  
  
**解决方法**  
 主要项目 （引用其他项目） 执行以下操作︰  
  
1.  在解决方案资源管理器中，右键单击解决方案节点。  
  
2.  单击 **属性** 以打开 **解决方案属性页** 对话框。  
  
3.  单击 **配置属性**, ，然后单击 **配置**。  
  
4.  清除 **部署** 引用的项目的复选框。  
  
5.  在解决方案资源管理器中，执行新的解决方案级别部署。 若要执行此操作，右键单击解决方案节点，然后单击 **部署解决方案**。  
  
### <a name="supported-virtual-directory-types"></a>支持的虚拟目录类型  
 仅当关联的虚拟目录的类型，在导出操作时从业务流程和尝试的操作的 MSI 导出中引用 Web 服务，将会成功 **IIsWebVirtualDir** 或 **IIsWebDirectory**。 **IIsWebVirtualDir** 和 **IIsWebDirectory** 是显示在 IIS 元数据库中的节点类型。 **IIsWebVirtualDir** 是使用的虚拟目录 **路径** 指向绝对文件文件夹的属性。 **IIsWebDirectory** 而不是虚拟目录 **路径** 属性，并因此将路由到相对文件文件夹，通常的另一个子文件夹 **IIsWebVirtualDir** 或 **IIsWebDirectory** 节点。 这两种类型是元数据库层次中用于描述文件夹的常见类型。  
  
 类型的虚拟目录 **IIsConfigObject** 不支持和 MSI 导出将会在这种情况下失败。 **IIsConfigObject** 意外元数据库节点类型，是一个有效的节点类型不正确处理 BizTalk Server 或不正确创建 （并因此无效） 元数据库条目的相对值。 在此情况下，BizTalk 服务器会显示一条错误消息类似于以下内容︰ 类型为 IIsConfigObject 意外的目录项"IIS://LM/W3SVC/1/ROOT/BadVdir/"。  
  
### <a name="unable-to-view-group-information-after-removing-stale-logons"></a>删除过时登录后无法查看组信息  
  
**问题**  
 如果在配置过程中遇到过时登录并删除它们，您可能无法查看组信息。  
  
**可能的原因**  
 这是一个已知的配置问题。  
  
**解决方法**  
 删除主机 Windows 组登录，然后重新配置，这种方法可能奏效。 如果组信息仍然不可用，请联系 Microsoft 产品支持人员。  
  
### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a>安装 BizTalk Server 后将无法更改计算机名称  
  
**问题**  
 当你更改运行 BizTalk Server 的计算机上的计算机名称并重新启动 （重启） 计算机，错误消息可能会出现。  
  
**可能的原因**  
 SQL Server 不支持更改计算机名称，因此 BizTalk Server 不支持更改计算机名称后安装并配置 BizTalk Server。  
  
**解决方法**  
 我们建议您在安装 BizTalk Server 后不要更改计算机名称。  
  
### <a name="known-issues-with-enterprise-single-sign-on"></a>与企业单一登录有关的已知问题  
 该部分介绍了可能与企业单一登录 (SSO) 有关的安装和配置问题。  
  
##### <a name="entsso-service-fails-to-start"></a>ENTSSO 服务启动失败  
  
**问题**  
 ENTSSO 服务启动失败。  
  
**可能的原因**  
 如果 ENTSSO 服务没有在有效的 SSO 管理员帐户下运行，将无法启动。  
  
**解决方法**  
 请为 ENTSSO 服务指定有效的 SSO 管理员帐户，然后从服务控制管理器 (SCM) 管理单元重新启动该服务。  
  
##### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a>依赖于企业单一登录服务 (ENTSSO) 的 BizTalk Services 未能在重新启动后启动  
  
**问题**  
 BTSSvc$BizTalkServerApplication 依赖于企业单一登录服务 (ENTSSO)，且在重新启动之后的启动过程中可能超时。  
  
**可能的原因**  
 企业单一登录服务可能需要约 3 分钟时间才能启动。  
  
**解决方法**  
 通过“自动(延迟的启动)”启动类型选项配置“BizTalk 服务 BizTalk 组: BizTalkServerApplication”服务。 这将在所有自动服务完成其启动例程后开始启动服务。  
  
##### <a name="cannot-access-an-affiliate-application"></a>无法访问关联应用程序  
  
**问题**  
 如果与关联应用程序关联的应用程序管理员帐户无效，则企业单一登录禁用关联应用程序。  
  
**可能的原因**  
 SSO 应用程序管理员帐户无效。  
  
**解决方法**  
 在创建关联应用程序之前，请确保 SSO 应用程序管理员帐户有效。 然后，您必须使关联应用程序能够使用该应用程序。  
  
##### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a>如果连接到客户端计算机会出现 RPC 错误  
  
**问题**  
 当你运行命令如**ssomanage-displayapp** *< applicationname\>*，其中计算机尝试连接到远程的 SSO 服务器以检索信息，你收到以下错误： 错误： 0x800706BA: RPC 服务器不可用。  
  
**可能的原因**  
 当您指定了错误的服务器信息时，或者当 SSO 服务在远程服务器上不可用时，会发生此错误。  
  
**解决方法**  
  
-   按照中的步骤[设置 SSO 服务器](../core/how-to-set-the-sso-server.md)若要确保你连接到正确的 SSO 服务器。  
  
-   确保 SSO 服务已启用并且运行在您要连接到的 SSO 服务器中。  
  
##### <a name="master-secret-is-missing-or-corrupt"></a>主密钥已丢失或损坏  
  
**问题**  
 缺少主密钥，或者主密钥已损坏。 主密钥通常在配置期间生成。 如果缺少该密钥，当企业单一登录服务启动时事件日志中便会显示下列消息之一。  
  
```
MessageId=10520  
Severity=Warning  
SSO_WARN_NO_SECRETS  
MessageId=10565  
Severity=Error  
SSO_ERROR_SECRET_VALIDATE_FAILED  
MessageId=10521  
Severity=Error  
SSO_ERROR_SECRETS_NOT_LOADED  
```

**可能的原因**  
 如果企业单一登录服务 (SSO) 在某个服务帐户下运行时生成密钥，又更改了该服务帐户，则可能出现此问题。 但是，该密钥以加密的形式存储在注册表中，并且使用基于此服务帐户标识（ENTSSO 在该帐户下运行）的密钥进行加密。  
  
**解决方法**  
 将 ENTSSO 在其下运行的服务帐户更改为创建主密钥时的原始服务帐户。  
  
1.  备份主密钥。 请参阅[备份主密钥](../core/how-to-back-up-the-master-secret.md)。  
  
2.  停止企业单一登录服务。  
  
3.  更改服务帐户。  
  
4.  重新启动 SSO，并忽略有关受损密钥的任何事件日志错误。  
  
5.  还原主密钥。 请参阅[还原主密钥](../core/how-to-restore-the-master-secret.md)。  
  
### <a name="custom-action"></a>自定义操作  
 本主题提供有关 Windows Server 徽标程序适用于 BizTalk Server 认证的详细信息。 在 BizTalk Server 安装操作期间可能执行以下自定义操作。  
  
|自定义操作|Description|  
|-------------------|-----------------|  
|ReadComplusData|阅读自定义 COM+ 表、创建 XML 文档并将其保存在 Complus_XML_Data 属性中。|  
|SchedXmlConfig|用于配置具有 RFID 数据的计算机。|  
|CheckBaseEDI|检查是否存在旧版本的 EDI|  
|CheckMQSeries|检查是否存在 MQSeries|  
|CheckNET30Vista|检查是否存在 WCF|  
|CheckWSSV3SP1|检查是否存在 Windows SharePoint Services 3.0 SP1。|  
|CheckWSSV4|检查是否存在 Windows SharePoint Services 4|  
|GetFrameworkPath|在包含 Microsoft .Net framework 4 和 2.0 的安装路径的安装程序中设置安装程序属性。|  
|Set_BAMClientExcelDir|创建一个 Excel 应用程序对象，以设置一个用于包含安装程序中 Microsoft Office 库路径的属性。|  
|Set_CurrentUser|设置当前用户的域\用户名信息|  
|ViewInstallGuide|从安装源目录启动 BizTalk Server 安装指南。|  
|CA_CheckSTSLanguage|当 WSS 和 BizTalk 的语言集相同时设置 STS_Language_Property 属性。|  
|CA_CleanupRegistry|卸载 BizTalk Server 时，会清除在 BizTalk Server 配置期间创建的注册表项。|  
|CA_CleanupRegistry_OldProducts|清除属于旧版本的 BizTalk Server 的注册表项以及 BizTalk Server 的全新安装不需要的注册表项。|  
|CA_RemovePatches|卸载 BizTalk Server 时删除 Microsoft BizTalk Server 更新。|  
|CA_ResolveWellKnownNames|使用熟知的名称创建安装程序属性，并为这些属性分配相应的 SID。|  
|CA_SaveTargetVSVersionToRegistry|将 TargetVSVersion_Property 属性设置为受支持版本的 Visual Studio 的值。|  
|CA_StopServices|停止 IISAdmin、规则引擎更新和 EDI 子系统服务。|  
|CleanupUsersKeys|从 HKEY_CURRENT_USER 注册表项中删除与 BizTalk Server 相关的项。|  
|DevEnvRunning|检查 Visual Studio 是否正在运行|  
|ValidateINSTALLDIR|验证 BizTalk Server 安装目录格式|  
|StartHostInstances|启动 BizTalk Server 主机实例。|  
|StopHostInstances|停止 BizTalk Server 主机实例。|  
|MQSUnConfig|对于未配置的 MQSeries 代理启动 MQSeries 配置向导。|  
|LaunchConfigFmk|启动 BizTalk Server 配置向导|  
|CHKASPNET|检查 ASP.NET 的安装状态|  
|CHKIIS|检查 IIS 的安装状态|  
|TBExpired|检查 BizTalk Server TimeBomb 是否已过期|  
|BrandSKU|对依赖于 SKU 安装的 BizTalk Server timebomb 的值进行更新。|  
|CA_ERROR|返回安装故障|  
|InstallComplus|安装 Complus 应用程序和组件。|  
|BAM_Add_Perf_Silent|安装 BAM 的性能计数器|  
|RegsvcsApplicationDeployment|在 BizTalk 部署 COM+ 应用程序 DLL 上运行 Regsvcs.exe（.NET 服务安装工具）|  
|RegsvcsDeployment|在 DLL 上运行 Regsvcs.exe|  
|RegsvcsMQSAdapter|在 DLL 上运行 Regsvcs.exe|  
|RegsvcsSQLAdapter|在 DLL 上运行 Regsvcs.exe|  
|WMI_Add_MSBTS_Silent|向 WMI 注册 BizTalk Server 命名空间和类。|  
|LaunchConfigFmk_SlashUP|取消对 BizTalk Server 的配置|  
|CleanupComplus|卸载 Complus 应用程序和组件。|  
|RemoveSKU|删除 BizTalk Server TimeBomb 数据。|  
|BAM_Remove_Perf|卸载 BAM 的性能计数器。|  
|LoadBTSCounters|加载 BizTalk Server 性能计数器。|  
|RegisterBtprojExtn|注册 BizTalk 项目文件 (.btproj) 扩展。|  
|UnRegisterBtprojExtn|注销 BizTalk 项目文件 (.btproj) 扩展。|  
|UnRegsvcsApplicationDeployment|卸载 BizTalk Server 时在某些 DLL 上运行 Regsvcs.exe|  
|UnRegsvcsDeployment|卸载 BizTalk Server 时在某些 DLL 上运行 Regsvcs.exe|  
|UnRegsvcsMQSAdapter|卸载 BizTalk Server 时在某些 DLL 上运行 Regsvcs.exe|  
|UnRegsvcsSQLAdapter|卸载 BizTalk Server 时在某些 DLL 上运行 Regsvcs.exe|  
|UnloadBTSCounters|卸载 BizTalk Server 性能计数器。|  
|WMI_Remove_MSBTS|从 WMI 中删除 BizTalk Server 命名空间。|  
|RegisterComsvcs|在 comsvcs.dll 上无提示地运行 regsvr32.exe|  
|DevenvSetupUninstall|运行 DevEnv.exe/Setup/resetskippkgs。|  
|RollbackComplus|回滚 Complus 应用程序和组件的安装。|  
|ResRegsvcsMQSAdapter|对给定二进制文件运行 regsvcs.exe|  
|ResRegsvcsSQLAdapter|对给定二进制文件运行 regsvcs.exe|  
|RestoreRegsvcsApplicationDeployment|在 Microsoft.BizTalk.ApplicationDeployment.Engine.dll 后追加框架的路径。|  
|RestoreRegsvcsDeployment|在 Microsoft.BizTalk.ApplicationDeployment.Engine.dll 后追加框架的路径。|  
|BrandSKURollback|在发生安装失败时，回滚注册的 SKU 信息。|  
|CA_RestartServices_rollback|重新启动停止的服务。|  
|RemoveSKURollback|更新注册表中的 SKU 值。|  
|BAM_Res_Perf_Silent|在无提示安装过程中将 Microsoft.BizTalk.Bam.EventObservation.dll 注册为 BAM 性能计数器 DLL。|  
|BAM_Rollback_Perf|注销作为 BAM 性能计数器 DLL 的 Microsoft.BizTalk.Bam.EventObservation.dll|  
|RBKRegsvcsMQSAdapter|对给定二进制文件运行 regsvcs.exe。|  
|RBKRegsvcsSQLAdapter|对给定二进制文件运行 regsvcs.exe。|  
|RestoreBTSCounters|还原包含性能计数器 .ini 文件名的属性。|  
|RollbackBTSCounters|运行命令 unlodctr BTSSvc.3.0。|  
|RollbackRegsvcsApplicationDeployment|设置 [FrameworkPath]&#124;[INSTALLDIR]Microsoft.BizTalk.ApplicationDeployment.Engine.dll for 失败的安装方案。|  
|RollbackRegsvcsDeployment|在卸载/回滚方案过程中调用 regsvcs.exe。|  
|WMI_Restore_MSBTS_Silent|调用 mofcomp 以注册 WMI 架构|  
|WMI_Rollback_MSBTS|从 WMI 中删除 BizTalk Server 命名空间。|  
|CA_RestartServices_commit|重新启动停止的服务|  
|DevenvSetup|在 BizTalk Server 安装/卸载过程中都运行 DevEnv.exe /Setup /resetskippkgs。|  
|ExecXmlConfig|用于 machine.config 进行配置更改以便获得与 RFID 相关的数据。|  
|ExecXmlConfigRollback|用于 machine.config 进行配置更改以便获得与 RFID 相关的数据。|  
  
#### <a name="running-biztalk-components"></a>运行 BizTalk 组件  
 下表列出了必须使用管理权限或最高可用权限运行的 BizTalk 组件。  
  
|文件夹路径|文件名|用户特权|  
|-----------------|---------------|---------------------|  
|\Program Files (x86)\Common Files\Microsoft shared\Help 9\Microsoft Document Explorer 2008|Install.exe|最高可用权限|  
|\Program files (x86) \Microsoft BizTalk Server*你的版本*|BTSHatApp.exe|最高可用权限|  
|\Program files (x86) \Microsoft BizTalk Server*你的版本*|BTSMMCLauncher.exe|最高可用权限|  
|\Program files (x86) \Microsoft BizTalk Server*你的版本*|BtsWcfServicePublishingWizard.exe|最高可用权限|  
|\Program files (x86) \Microsoft BizTalk Server*你的版本*|BTSWebSvcWiz.exe|最高可用权限|  
|\Program files (x86) \Microsoft BizTalk Server*你的版本*|Configuration.exe|最高可用权限|  
|\Program files (x86) \Microsoft BizTalk Server*你的版本*|REDeployWiz.exe|最高可用权限|  
|\Program files (x86) \Microsoft BizTalk Server*你的版本*|Setup.exe|管理权限|  
|\Program files (x86) \Microsoft BizTalk Server*你版本*\XSD Schema\EDI|MicrosoftEdiXSDTemplates.exe|Self-extracting .exe 文件。|  
|\Program Files (x86)\Microsoft UDDI Services\config|Configuration .exe|管理权限|  
|\Program Files\ Microsoft BizTalk RFID\bin|BTSMMCLauncher.exe|最高可用权限|  
|\Program Files\Microsoft BizTalk RFID\BREConfi guration|Configuration .exe|管理权限|  
