---
title: 已知的安装问题 |Microsoft Docs
description: 已知的问题和常见的问题和解决方案安装和配置 BizTalk Server 时
ms.custom: ''
ms.date: 11/30/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4d0e707-6b9e-49e1-9f17-19b3bac1229e
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a38d3665e71ebc9e11c133dde49ad070f2aa0e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397103"
---
# <a name="troubleshoot-biztalk-server-setup"></a>对 BizTalk Server 安装程序进行故障排除

## <a name="introduction"></a>简介  
 本疑难解答指南列出了已知的问题，以及安装 BizTalk Server 时可能遇到的最常见问题。 本指南还包括自定义操作，它提供有关 Windows Server 徽标计划 BizTalk 服务器证书的详细信息。  它提供你的自定义 BizTalk Server 安装程序操作期间可能执行的操作列表。  
  
## <a name="review-install-steps"></a>查看安装步骤  
大多数 BizTalk Server 安装程序问题发生的原因未安装 BizTalk Server，或以前安装的 BizTalk Server 未完全卸载之前尝试新的安装前正确准备 BizTalk Server 计算机。  
  
查看以下两个清单，还可以在 BizTalk Server 安装指南，以确保您的计算机正确配置以支持 BizTalk Server 中找到。 如果查看此信息后，您的安装程序仍不成功，此文档的其余部分中的故障排除提示可能有用。  
  
1. 安装必备软件和程序：

    * [BizTalk Server 2016](set-up-and-install-prerequisites-for-biztalk-server-2016.md)
    * [BizTalk Server 2013 R2 & 2013](prepare-your-computer-for-installation.md)

2. 安装和配置 BizTalk Server:  

    1. 安装 BizTalk Server:[BizTalk 2016](install-biztalk-server-2016.md) ， [BizTalk 2013 R2 / 2013年](install-biztalk-server-2013-and-2013-r2.md)  
    2. [配置](configure-biztalk-server.md)BizTalk Server
    3. [配置后步骤](post-configuration-steps-to-optimize-your-environment.md)
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a>某些 EDI/AS2 项目是取消配置后仍处于活动状态  
  
**问题**  
 后取消对 BizTalk Server 中，与 EDI 有关的某些 BizTalk Server 项目的 BizTalk EDI/AS2 功能和 AS2 处理仍会在 BizTalk 组配置的上下文中处于活动状态。 这些项目将包括 EDI 和 AS2 管道以及批处理业务流程。 因此，您将仍然能够执行基本的 EDI 和 AS2 处理后取消 BizTalk EDI/AS2 功能的配置。  
  
**原因**   
 有活动与 EDI 和 AS2 处理关联的端口。 某些项目将继续工作时这些端口保持活动状态。  
  
**解决方法**  
 若要禁用所有 edi/as2 项目，应都禁用、 停止或删除与 EDI 和 AS2 处理关联的端口。  
  
## <a name="after-renaming-biztalk-or-sql-server-computer-the-configuration-wizard-fails"></a>重命名 BizTalk 或 SQL Server 计算机后, 配置向导失败  
  
**问题**  
 此问题可能表现几种方式：  
  
-   配置管理器将正确加载概述页，但在尝试配置功能时，不在屏幕上显示功能选项。  
  
-   配置向导无法连接到 SQL Server。  
  
-   尝试取消对所有 0}run 某些功能，但不是全部。  
  
**原因**   
 BizTalk Server 配置存储的计算机网络名称。 如果重命名计算机，configuration manager 和配置向导无法找到 BizTalk Server。 如果 SQL Server 计算机已重命名 BizTalk Server 配置后，将发生类似的问题。  
  
**解决方法**  
 不要重命名 BizTalk Server 计算机或 SQL Server 计算机。 如果必须重命名服务器，然后再重命名计算机取消所有 BizTalk 功能。 重命名计算机之后, 重新配置 BizTalk Server 功能。  
  
## <a name="business-rules-configuration-wizard-fails"></a>业务规则配置向导失败  
  
**问题**  
  
-   业务规则配置向导失败，出现错误"某些组件的配置失败和这些组件未应用任何设置。"  
  
-   在 BizTalk Server 计算机上为其业务规则引擎已成功配置，规则引擎更新服务无法启动，并不能手动启动。  
  
发生此问题时，可能会在 BizTalk Server 计算机应用程序日志中生成如下错误：  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
**原因**   
 Microsoft 恶意软件防护中心发布的更新的签名文件在 2010 年 3 月 9 日，来解决可能来自 SettingsModifier:Win32 威胁 / PossibleHostsFileHijack。 此更新的签名文件可能会导致 Microsoft 恶意软件检测软件，如 Windows Defender 更新本地 HOSTS 文件，以消除威胁 SettingsModifier:Win32 / PossibleHostsFileHijack。 这些更改会导致 BizTalk Server 规则引擎更新服务可能无法启动。  
  
**解决方法**  
 更新本地 HOSTS 文件，以包含以下行：  
  
```  
127.0.0.1         localhost  
```  
  
 主机文件位于 %systemroot%\drivers\etc\ 目录中。  
  
> [!NOTE]
> 请参阅 Microsoft 恶意软件防护中心签名更新从的地址可能威胁[SettingsModifier:Win32 / PossibleHostsFileHijack](http://go.microsoft.com/fwlink/?LinkId=146221)。  
  
## <a name="configuration-logging"></a>配置日志记录  
 配置程序写入配置日志文件，默认情况下位于运行 BizTalk Server 的计算机的临时目录中的详细的信息。 若要确定由 TEMP 环境变量打开指定的文件夹，此计算机上的命令提示符下键入以下命令，然后按 ENTER:  
  
 **echo %TEMP%**  
  
 配置日志文件包含执行，这些配置步骤的摘要，以及有关在配置过程中可能发生的任何故障的诊断信息。 如果出现配置错误，在诸如记事本之类的文本编辑器中打开配置日志，并检查错误的可能原因的日志文件。  
  
## <a name="troubleshooting-tools"></a>故障排除工具  
 使用 SQL Server Profiler、 Filemon 或 Regmon 收集有关配置失败的其他信息。 请参阅[要用于故障排除的工具和实用程序](../core/tools-and-utilities-to-use-for-troubleshooting.md)。  
  
### <a name="configuration-fails-when-biztalk-and-sql-are-installed-on-separate-computers"></a>当单独的计算机上安装 BizTalk 和 SQL 时配置失败  
  
**问题**  
 在尝试配置企业单一登录 (SSO) 组件时，配置将失败并出现错误如下所示：  
  
```
An error occurred while attempting to access the SSO database.  
Function: FieldInfoCreate  
```
  
 -或-  
  
```Failed to enable the Single Sign-On (SSO) Service (error code 0X800706BA)```  
  
**原因**    
 如果在不同计算机上安装 BizTalk Server 和 SQL Server 则 Microsoft 分布式事务处理协调器 (MSDTC) 事务的上下文中执行配置操作，并且必须可通过 MSDTC 功能这些计算机之间的网络。 如果通过网络在运行 BizTalk Server 和 SQL Server 的计算机之间的 MSDTC 功能不可用，则可以发生此错误。  
  
**解决方法**    
使用[MSDTC 疑难解答](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues)以确保通过网络在运行 BizTalk Server 和 SQL Server 的计算机之间的 MSDTC 功能。  
  
### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a>防病毒软件干扰配置并将导致配置失败  
  
**Problem**   
 当防病毒软件错误地确定配置程序是一种病毒时，BizTalk Server 配置失败。  
  
**原因**  
 防病毒软件尚未更新以包括 BizTalk Server 配置程序作为合法 （非病毒） 程序。  
  
**解决方法**  
 配置防病毒程序来将 BizTalk Server 配置程序识别为合法 （非病毒） 程序，否则配置程序正在运行时暂时禁用防病毒软件。  
  
### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a>配置失败，出现"文件或程序集名称 FileName.dll，或其某个依赖项，未找到"错误  
  
**问题**  
 在配置过程中将显示类似于以下错误：  
  
 无法部署 BizTalk 系统程序集"C:\Program Files\Microsoft\BizTalk Server 20xx\Microsoft.BizTalk.DefaultPipelines.dll。 未指定的异常：文件或程序集名称 FileName.dll 或其某个依赖项，未找到。"  
  
**原因**  
 如果网络服务帐户不具有写入权限的临时文件夹运行 BizTalk Server 的计算机上，可以发生此错误。 在配置期间，BizTalk Server 配置使用 Windows Management Instrumentation (WMI) 将.NET 程序集部署到 BizTalk 管理数据库。 这些程序集部署到 BizTalk 管理数据库时，WMI 模拟网络服务帐户，因此网络服务帐户必须在运行 BizTalk Server 的计算机上的临时文件夹具有写访问权限。  
  
**解决方法**  
 授予网络服务帐户写入访问权限运行 BizTalk Server 的计算机上的临时文件夹，然后再次运行配置程序。 若要确定由 TEMP 环境变量指定的文件夹，打开命令提示符在计算机上，键入以下命令，然后按 ENTER:  
  
```  
echo %TEMP%  
```  
  
### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a>如果已具有相同的名称，因为指定的数据库的 SQL Server 数据库文件存在于 SQL Server 数据文件夹配置失败  
  
#### <a name="problem"></a>问题  
 配置失败并出现类似于以下的错误：  
  
```
Failed to set up BAM database(s)  
  
Cannot open database requested in login 'BAMPrimaryImport'  
  
Logon fails. Logon failed for user '*BizTalk\BizTalkUser*'  
```
  
**原因**  
 可能出现此错误，如果.mdf 文件或.ldf 文件已存在运行与.mdf 文件或.ldf 文件的 BizTalk Server 配置程序尝试创建同名的 SQL Server 的计算机的 \MSSQL\data 文件夹中。 为数据库创建的.mdf 文件和.ldf 文件的名称派生自指定.mdf 和.ldf 扩展名追加在 BizTalk Server 配置程序中的数据库的名称。  
  
**解决方法**  
 若要解决此问题，请使用以下方法之一：  
  
-   删除任何.mdf 文件或.ldf 文件与要创建的任何数据库的名称匹配的名称。  
  
-   选择数据库名称不匹配的任何.mdf 文件或.ldf 文件已存在 SQL server 的 \Program Files\Microsoft SQL Server\MSSQL\data 文件夹中的名称。  
  
### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a>指定本地帐户时，配置在域控制器上失败  
  
**问题**  
 运行时 BizTalk Server 配置程序的域控制器上，配置用于 BizTalkServerApplication 主机或 BizTalkIsolatedHost 主机失败如果指定本地组 （例如，BizTalk 主机用户组）。  
  
**原因**  
 域控制器会自动将本地 Windows 组视为域 Windows 组 （没有就没有域控制器上的本地 Windows 组）。 如果您运行配置程序时为主机指定本地 Windows 组，配置将失败时尝试创建 SQL Server 登录组。 当服务器是域控制器时，配置程序不会禁用本地 Windows 组选项。  
  
**解决方法**  
 在配置期间创建的主机指定域组。  
  
### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a>无法创建 SQL Server 分析数据库，如果已重命名 SQL server 配置  
  
**问题**  
 如果已重命名在其安装 SQL Server 分析服务器的计算机，配置程序将失败时尝试创建新的 SQL Server 分析数据库并生成类似于以下错误：  

```  
 Cannot connect to the repository.  
  
 Analysis server: <machine name\>  
  
 Error:  
  
 '\\\\<machine name\>\MsOLAPRepository$\msmdrep.mdb' is not a valid path.  
  
 Make sure that you correctly spell the path name and that you are  
  
 connected to the server on which the file resides.  
```
  
**原因**  
 配置程序不能确定在其安装 SQL Server 分析服务器的计算机的新名称。  
  
**解决方法**  
 执行以下手动步骤，以使用新的计算机名更新分析服务器：  
  
1.  在 SQL Server 上打开**Microsoft SQL Server**，选择**Analysis Services**，然后单击**Analysis Manager**。  
  
2.  在中**分析管理器**导航面板中，双击**分析服务器**节点以将其展开。  
  
3.  右键单击你想要编辑，然后选择的存储库连接字符串服务器**编辑存储库连接字符串**。  
  
4.  在中**编辑存储库连接字符串**对话框中，验证此字符串中的服务器名称，它更新为新的计算机名称是否正确。  
  
5.  导航到以下位置： <*安装目录*> \Program Files\Microsoft Analysis Services\Bin。  
  
6.  右键单击**Bin**文件夹，，然后单击**共享和安全**。 **Bin 属性**对话框随即出现。  
  
7.  在中**Bin 属性**对话框中，单击**共享**选项卡来验证所有联机分析处理 (OLAP) 管理员具有对此文件夹的完全权限。  
  
### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a>从配置数据库消失的程序集从 Visual Studio 重新部署的项目  
  
**问题**  
 当 BizTalk Server 项目重新部署在 Visual Studio 中，项目级别引用正在重新部署该项目将显示消失刷新 BizTalk Server MMC 时在项目中包含的所有项目。  
  
**原因**  
 为了说明此问题的原因，请考虑下面的示例基于示例用户要重新部署 Maps 项目的 BizTalk Server 解决方案。 请注意，编译项目生成单独的程序集。 用户在进行重新部署之前下, 图指示解决方案的状态。 项目之间的关系如下所示：  
  
-   Orch1、 Orch2、 映射、 管道和架构项目。  
  
-   Orch1 引用 Maps，后者又引用架构。  
  
-   Orch2 引用 Schemas。  
  
-   Pipelines 引用 Schemas。  
  
![bcd_ExistingBizTalkServerSolutionc](../install-and-config-guides/media/bcd_ExistingBizTalkServerSolutionc.gif)  
  
如果用户重新部署 Maps 项目使用默认 Visual Studio 项目设置，Orch1、 Orch2 和管道项目将消失下, 图中所示。  
  
![bcd_BizTalkSolutionWLostArtifactsc](../install-and-config-guides/media/bcd_BizTalkSolutionWLostArtifactsc.gif)  
  
 重新部署 Maps 是一个两步过程以及取消部署当前已部署的 Maps.dll 程序集，然后部署新的 Maps.dll 文件。 Visual Studio 重新部署过程的一部分自动执行这些步骤。  
  
> [!NOTE]
>  上面的描述不完全正确，因为这些是 Visual Studio 一直执行的步骤因此没有考虑其方式是否适当。  
  
 关键在于，为了取消部署 BizTalk Server 程序集，Visual Studio 必须取消部署所有程序集依赖于该程序集的设置部署标志。 在本示例中，若要执行的重新部署，首先取消部署 BizTalk Server 需要取消部署 Orch1.dll （而它依赖于 Maps.dll）。 在取消部署 Maps.dll 的 Visual Studio 还将取消部署 Schemas.dll （假定它已设置部署标志）。 为了取消部署 Schemas.dll，Visual Studio 需要取消部署 Orch2.dll 和 Pipelines.dll （这两者都依赖于 Schemas.dll）。  
  
 Visual Studio 重新部署仅 Maps.dll 以及它所依赖的程序集存在问题： 在本例中为 Schemas.dll。 因此，当用户刷新 BizTalk Server MMC，Orch1 和 Orch2，管道程序集似乎消失，但 Maps.dll 和 Schemas.dll 是仍然可见。  
  
**解决方法**  
 主项目 （引用其他项目），请执行以下操作：  
  
1.  在解决方案资源管理器，右键单击解决方案节点。  
  
2.  单击**属性**以打开**解决方案属性页**对话框。  
  
3.  单击**配置属性**，然后单击**配置**。  
  
4.  清除**部署**引用的项目的复选框。  
  
5.  在解决方案资源管理器中执行新的解决方案级部署。 若要执行此操作，右键单击解决方案节点，然后单击**部署解决方案**。  
  
### <a name="supported-virtual-directory-types"></a>支持的虚拟目录类型  
 仅当关联的虚拟目录的类型，导出操作时从业务流程，并尝试执行 MSI 导出引用 Web 服务，将会成功**IIsWebVirtualDir**或**IIsWebDirectory**. **IIsWebVirtualDir**并**IIsWebDirectory**是显示在 IIS 元数据库中的节点类型。 **IIsWebVirtualDir**是与虚拟目录**路径**指向绝对文件夹的属性。 **IIsWebDirectory**是一个虚拟目录，而无需**路径**属性，因此指向相对文件夹中，通常的另一个子文件夹**IIsWebVirtualDir**或**IIsWebDirectory**节点。 这两种类型是通常会出现在元数据库层次结构中用于描述文件夹。  
  
 类型的虚拟目录**IIsConfigObject**不受支持，并且，MSI 导出在此情况下将失败。 **IIsConfigObject**是 BizTalk Server 无法正确处理任一有效的节点类型的意外元数据库节点类型或相对值的指示正确创建 （并因此而无效） 元数据库条目。 在此情况下 BizTalk Server 将显示一条错误消息类似于以下内容：预期的目录条目"iis: //lm/w3svc/1/root/badvdir/"，类型为 IIsConfigObject。  
  
### <a name="unable-to-view-group-information-after-removing-stale-logons"></a>无法查看组信息删除过时登录后  
  
**问题**  
 如果在配置期间，你会遇到并删除过时登录，你可能无法查看组信息。  
  
**原因**  
 这是一个已知的配置问题。  
  
**解决方法**  
 它可能有助于删除主机 Windows 组登录，然后重新配置。 如果组信息仍不可用，请联系 Microsoft 产品支持。  
  
### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a>安装 BizTalk Server 后无法更改计算机名称  
  
**问题**  
 当您更改运行 BizTalk Server 的计算机上的计算机名称并重新启动 （重新启动） 的计算机，错误消息可能会发生。  
  
**原因**  
 SQL Server 不支持更改计算机名称，因此 BizTalk Server 不支持更改计算机名称后安装并配置 BizTalk Server。  
  
**解决方法**  
 我们建议在安装 BizTalk Server 后不会更改计算机名称。  
  
### <a name="known-issues-with-enterprise-single-sign-on"></a>使用企业单一登录的已知的问题  
 本部分介绍可能相关到企业单一登录 (SSO) 的安装和配置问题。  
  
##### <a name="entsso-service-fails-to-start"></a>ENTSSO 服务启动失败  
  
**问题**  
 ENTSSO 服务启动失败。  
  
**原因**  
 如果 ENTSSO 服务没有在有效的 SSO 管理员帐户下运行，将无法启动。  
  
**解决方法**  
 请为 ENTSSO 服务指定有效的 SSO 管理员帐户，然后从服务控制管理器 (SCM) 管理单元重新启动该服务。  
  
##### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a>BizTalk 服务依赖于企业单一登录服务 (ENTSSO) 不能在重启后启动  
  
**问题**  
 BTSSvc$BizTalkServerApplication 依赖于企业单一登录服务 (ENTSSO)，且在重新启动之后的启动过程中可能超时。  
  
**原因**  
 企业单一登录服务可能需要约 3 分钟时间才能启动。  
  
**解决方法**  
 配置"BizTalk 服务 BizTalk 组：具有自动 （延迟启动） 启动类型选项 BizTalkServerApplication"服务。 这将在所有自动服务完成其启动例程后开始启动服务。  
  
##### <a name="cannot-access-an-affiliate-application"></a>无法访问关联应用程序  
  
**问题**  
 如果与关联应用程序关联的应用程序管理员帐户无效，则企业单一登录禁用关联应用程序。  
  
**原因**  
 SSO 应用程序管理员帐户无效。  
  
**解决方法**  
 在创建关联应用程序之前，请确保 SSO 应用程序管理员帐户有效。 然后，您必须使关联应用程序能够使用该应用程序。  
  
##### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a>连接到客户端计算机时发生 RPC 错误  
  
**问题**  
 当运行命令如**ssomanage-displayapp** *< applicationname\>*，其中计算机尝试连接到远程 SSO 服务器以检索信息，你收到以下错误：错误：0x800706BA:RPC 服务器不可用。  
  
**原因**  
 此错误发生时指定错误的服务器信息，或者当 SSO 服务不在远程服务器上可用。  
  
**解决方法**  
  
-   按照中的步骤[设置 SSO 服务器](../core/how-to-set-the-sso-server.md)以确保您连接到正确的 SSO 服务器。  
  
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

**原因**  
 如果企业单一登录服务 (SSO) 在某个服务帐户下运行时生成密钥，又更改了该服务帐户，则可能出现此问题。 但是，该密钥以加密的形式存储在注册表中，并且使用基于此服务帐户标识（ENTSSO 在该帐户下运行）的密钥进行加密。  
  
**解决方法**  
 将 ENTSSO 在其下运行的服务帐户更改为创建主密钥时的原始服务帐户。  
  
1.  备份主密钥。 请参阅[备份主密钥](../core/how-to-back-up-the-master-secret.md)。  
  
2.  停止企业单一登录服务。  
  
3.  更改服务帐户。  
  
4.  重新启动 SSO，并忽略有关受损密钥的任何事件日志错误。  
  
5.  还原主密钥。 请参阅[还原主密钥](../core/how-to-restore-the-master-secret.md)。  
  
### <a name="custom-action"></a>自定义操作  
 本主题提供有关 Windows Server 徽标计划 BizTalk 服务器证书的详细信息。 在 BizTalk Server 安装程序操作期间可能会执行以下自定义操作。  
  
|自定义操作|Description|  
|-------------------|-----------------|  
|ReadComplusData|读取自定义 COM + 表、 创建 XML 文档，并将其保存在 Complus_XML_Data 属性。|  
|SchedXmlConfig|用于配置具有 RFID 数据的计算机。|  
|CheckBaseEDI|检查存在旧版本的 EDI|  
|CheckMQSeries|检查存在 MQSeries|  
|CheckNET30Vista|检查存在 WCF|  
|CheckWSSV3SP1|检查存在 Windows SharePoint Services 3.0 SP1。|  
|CheckWSSV4|检查存在 Windows SharePoint Services 4|  
|GetFrameworkPath|设置安装程序属性中的安装程序保存到 Microsoft.Net framework 4 和 2.0 的安装路径。|  
|Set_BAMClientExcelDir|创建一个 Excel 应用程序对象用于设置属性，在安装程序中包含的 Microsoft Office 库路径。|  
|Set_CurrentUser|设置当前用户的域 \ 用户名信息|  
|ViewInstallGuide|启动从安装源目录的 BizTalk Server 安装指南。|  
|CA_CheckSTSLanguage|当 WSS 和 BizTalk 设置的语言相同时设置 STS_Language_Property 属性。|  
|CA_CleanupRegistry|当你卸载 BizTalk Server 后时，该向导会清除在 BizTalk Server 配置期间创建的注册表项。|  
|CA_CleanupRegistry_OldProducts|清除属于旧版本的 BizTalk Server 并不需要的 BizTalk Server 的全新安装的注册表项。|  
|CA_RemovePatches|卸载 BizTalk Server 时，请删除 Microsoft BizTalk Server 更新。|  
|CA_ResolveWellKnownNames|使用熟知的名称创建安装程序属性，并将其分配相应的 SID。|  
|CA_SaveTargetVSVersionToRegistry|将 TargetVSVersion_Property 属性设置为受支持版本的 Visual Studio 的值。|  
|CA_StopServices|停止 IISAdmin、 规则引擎更新和 EDI 子系统服务。|  
|CleanupUsersKeys|删除 BizTalk Server 从 HKEY_CURRENT_USER 注册表项相关条目。|  
|DevEnvRunning|检查是否正在运行 Visual Studio|  
|ValidateINSTALLDIR|验证 BizTalk Server 安装目录格式|  
|StartHostInstances|启动 BizTalk Server 主机实例。|  
|StopHostInstances|停止 BizTalk Server 主机实例。|  
|MQSUnConfig|启动 MQSeries 配置向导，以未配置的 MQSeries 代理。|  
|LaunchConfigFmk|启动 BizTalk Server 配置向导|  
|CHKASPNET|检查 ASP.NET 的安装状态|  
|CHKIIS|检查 IIS 的安装状态|  
|TBExpired|检查 BizTalk Server TimeBomb 是否已过期|  
|BrandSKU|更新它依赖于 SKU 安装 BizTalk Server timebomb 的值。|  
|CA_ERROR|返回安装故障|  
|InstallComplus|安装 Complus 应用程序和组件。|  
|BAM_Add_Perf_Silent|安装 BAM 的性能计数器|  
|RegsvcsApplicationDeployment|在 BizTalk 部署 COM + 应用程序 Dll 上运行 Regsvcs.exe （.NET 服务安装工具）|  
|RegsvcsDeployment|在 Dll 上运行 Regsvcs.exe|  
|RegsvcsMQSAdapter|在 Dll 上运行 Regsvcs.exe|  
|RegsvcsSQLAdapter|在 Dll 上运行 Regsvcs.exe|  
|WMI_Add_MSBTS_Silent|注册 BizTalk Server 命名空间和类到 WMI。|  
|LaunchConfigFmk_SlashUP|取消配置 BizTalk Server|  
|CleanupComplus|卸载 Complus 应用程序和组件。|  
|RemoveSKU|删除 BizTalk Server TimeBomb 数据。|  
|BAM_Remove_Perf|卸载 BAM 性能计数器。|  
|LoadBTSCounters|加载 BizTalk Server 性能计数器。|  
|RegisterBtprojExtn|注册 BizTalk 项目文件 (.btproj) 扩展。|  
|UnRegisterBtprojExtn|注销 BizTalk 项目文件 (.btproj) 扩展。|  
|UnRegsvcsApplicationDeployment|卸载 BizTalk Server 时，在某些 Dll 上运行 Regsvcs.exe|  
|UnRegsvcsDeployment|卸载 BizTalk Server 时，在某些 Dll 上运行 Regsvcs.exe|  
|UnRegsvcsMQSAdapter|卸载 BizTalk Server 时，在某些 Dll 上运行 Regsvcs.exe|  
|UnRegsvcsSQLAdapter|卸载 BizTalk Server 时，在某些 Dll 上运行 Regsvcs.exe|  
|UnloadBTSCounters|卸载 BizTalk Server 性能计数器。|  
|WMI_Remove_MSBTS|从 WMI 中删除 BizTalk Server 命名空间。|  
|RegisterComsvcs|以无提示方式在 comsvcs.dll 上运行 regsvr32.exe。|  
|DevenvSetupUninstall|运行 DevEnv.exe/Setup/resetskippkgs。|  
|RollbackComplus|回滚 Complus 应用程序和组件的安装。|  
|ResRegsvcsMQSAdapter|对给定二进制文件运行 regsvcs.exe|  
|ResRegsvcsSQLAdapter|对给定二进制文件运行 regsvcs.exe|  
|RestoreRegsvcsApplicationDeployment|将追加 microsoft.biztalk.applicationdeployment.engine.dll 框架的路径。|  
|RestoreRegsvcsDeployment|将追加 microsoft.biztalk.applicationdeployment.engine.dll 框架的路径。|  
|BrandSKURollback|如果发生安装失败时，回滚注册的 SKU 信息。|  
|CA_RestartServices_rollback|重新启动已停止的服务。|  
|RemoveSKURollback|更新注册表中的 SKU 值。|  
|BAM_Res_Perf_Silent|在无提示安装过程中将 Microsoft.BizTalk.Bam.EventObservation.dll 注册为 BAM 性能计数器 Dll。|  
|BAM_Rollback_Perf|注销作为 BAM 性能计数器 DLL 的 Microsoft.BizTalk.Bam.EventObservation.dll|  
|RBKRegsvcsMQSAdapter|对给定二进制文件运行 regsvcs.exe。|  
|RBKRegsvcsSQLAdapter|对给定二进制文件运行 regsvcs.exe。|  
|RestoreBTSCounters|还原包含性能计数器.ini 文件名称的属性。|  
|RollbackBTSCounters|运行命令 unlodctr BTSSvc.3.0。|  
|RollbackRegsvcsApplicationDeployment|设置 [FrameworkPath]&#124;[INSTALLDIR]Microsoft.BizTalk.ApplicationDeployment.Engine.dll 有关失败的安装方案。|  
|RollbackRegsvcsDeployment|在卸载/回滚方案过程中调用 regsvcs.exe。|  
|WMI_Restore_MSBTS_Silent|调用 mofcomp 以注册 WMI 架构|  
|WMI_Rollback_MSBTS|从 WMI 中删除 BizTalk Server 命名空间。|  
|CA_RestartServices_commit|重新启动已停止的服务|  
|DevenvSetup|在 BizTalk Server 安装/卸载过程运行 DevEnv.exe /Setup /resetskippkgs。|  
|ExecXmlConfig|用于对 machine.config 进行配置更改，rfid 相关的数据。|  
|ExecXmlConfigRollback|用于对 machine.config 进行配置更改，rfid 相关的数据。|  
  
#### <a name="running-biztalk-components"></a>运行 BizTalk 组件  
 下表列出了必须使用管理权限运行的 BizTalk 组件或最高可用权限。  
  
|文件夹路径|File name|用户权限|  
|-----------------|---------------|---------------------|  
|\Program Files (x86)\Common Files\Microsoft shared\Help 9\Microsoft Document Explorer 2008|Install.exe|最高可用权限|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|BTSHatApp.exe|最高可用权限|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|BTSMMCLauncher.exe|最高可用权限|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|BtsWcfServicePublishingWizard.exe|最高可用权限|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|BTSWebSvcWiz.exe|最高可用权限|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|Configuration.exe|最高可用权限|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|REDeployWiz.exe|最高可用权限|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|Setup.exe|管理权限|  
|\Program 文件 (x86) \Microsoft BizTalk Server*版本*\XSD Schema\EDI|MicrosoftEdiXSDTemplates.exe|自解压.exe 文件。|  
|\Program Files (x86)\Microsoft UDDI Services\config|配置.exe|管理权限|  
|\Program Files\ Microsoft BizTalk RFID\bin|BTSMMCLauncher.exe|最高可用权限|  
|\Program Files\Microsoft BizTalk RFID\BREConfi guration|配置.exe|管理权限|  
