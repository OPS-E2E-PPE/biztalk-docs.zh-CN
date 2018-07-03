---
title: 配置疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 902e591a-4ff4-4053-b329-0c022f44999a
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f79f2d2ec9e87a22d07802f52b063f279d65ab8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973190"
---
# <a name="troubleshooting-configuration"></a>排查配置问题
在 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序会在运行的一个或多个计算机上创建数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，将填充带有表、 角色、 数据库和存储过程由[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并部署到运行时期间使用的.NET 程序集BizTalk 管理数据库中。  
  
 本部分讨论用于解决配置错误的疑难解答方法。 它还列出了某些常见的配置问题以及解决这些问题的方法。  
  
## <a name="configuration-logging"></a>配置记录  
 配置程序将详细的信息写入到一个配置日志文件位于运行的计算机的 temp 目录中的默认情况下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 若要确定由 TEMP 环境变量指定的文件夹，请在此计算机上打开命令提示符，键入以下命令，然后按 Enter：  
  
 **echo %TEMP%**  
  
 配置日志文件中包含所执行的配置步骤的摘要，以及在配置过程中可能发生的任何故障的诊断信息。 如果出现配置错误，请在文本编辑器（如“记事本”）中打开配置日志，然后在日志中检查此错误的可能原因。  
  
## <a name="troubleshooting-tools"></a>疑难解答工具  
 使用 SQL Server Profiler、Filemon 或 Regmon 收集有关配置失败的其他信息。 有关这些工具的详细信息，请参阅[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="configuration-fails-when-biztalk-server-and-sql-server-are-installed-on-separate-computers"></a>当在单独的计算机上安装 BizTalk Server 和 SQL Server 时，配置失败  
  
##### <a name="problem"></a>问题  
 当尝试配置 Enterprise 单一登录 (SSO) 组件时，配置失败并出现如下错误：  
  
 尝试访问 SSO 数据库时出错。  
  
 函数： FieldInfoCreate  
  
 -或-  
  
 启用单一登录 (SSO) 服务失败（错误代码 0X800706BA）  
  
##### <a name="cause"></a>原因  
 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]则分布式事务处理协调器 (MSDTC) 事务的上下文下执行配置操作，并且必须可通过 MSDTC 功能安装在不同计算机上这些计算机之间的网络。 如果 MSDTC 功能将不可用通过网络运行的计算机之间[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]则会出现此错误。  
  
##### <a name="resolution"></a>解决方法  
 按照中的步骤[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)以确保通过网络运行的计算机之间的 MSDTC 功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
#### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a>防病毒软件干扰配置并导致配置失败  
  
##### <a name="problem"></a>问题  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 当防病毒软件错误地确定配置程序是一种病毒时，配置失败。  
  
##### <a name="cause"></a>原因  
 防病毒软件尚未更新，因此未将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置程序作为合法（非病毒）程序加入到其中。  
  
##### <a name="resolution"></a>解决方法  
 配置防病毒程序识别[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序正在运行时，配置程序作为合法 （非病毒） 程序，否则暂时禁用防病毒软件。  
  
#### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a>配置失败，并出现错误“找不到文件或程序集名称 FileName.dll，或找不到它的一个依赖项”  
  
##### <a name="problem"></a>问题  
 在配置过程中显示如下错误：  
  
 无法部署 BizTalk 系统程序集“C:\Program Files\Microsoft\  
  
 BizTalk Server 2009\Microsoft.BizTalk.DefaultPipelines.dll。 “未指定”  
  
 异常： 文件或程序集名称 FileName.dll 或其中一个其  
  
 或其依存关系之一。 找不到文件或程序集名称 FileName .dll  
  
 其依存关系之一。”  
  
##### <a name="cause"></a>原因  
 如果网络服务帐户运行的计算机上的临时文件夹没有写入权限，可能出现此错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在配置过程中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置使用 Windows 管理规范 (WMI) 将 .NET 程序集部署到 BizTalk 管理数据库。 在将这些程序集部署到 BizTalk 管理数据库时，WMI 模拟网络服务帐户，因此，网络服务帐户必须对运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上的临时文件夹具有写权限。  
  
##### <a name="resolution"></a>解决方法  
 向网络服务帐户授予对运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上的临时文件夹的写权限，并再次运行配置程序。 若要确定由 TEMP 环境变量指定的文件夹，打开命令提示符在计算机上，键入以下命令，然后按 ENTER:  
  
```  
echo %TEMP%  
```  
  
#### <a name="configuration-of-the-group-fails-if-the-netbios-name-of-the-computer-running-sql-server-exceeds-15-characters"></a>如果运行 SQL Server 的计算机的 NetBIOS 名称超过 15 个字符，则组的配置失败  
  
##### <a name="problem"></a>问题  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组配置失败，并且类似于以下的错误显示在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置日志：  
  
 2006-08-29 23:54:00:0902 [警告] AdminLib GetBTSMessage: hrErr = 80070547;  
  
 Msg=Configuration information could not be read from the domain  
  
 controller, either because the machine is unavailable, or access has  
  
 been denied.;  
  
##### <a name="cause"></a>原因  
 如果运行的计算机命名为 NetBIOS 的长度，会发生此问题[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]超过 15 个字符。 如果 NetBIOS 名称超过 15 个字符，则 Windows 将该 NetBIOS 名称截断至 15 个字符，NetBIOS 名称将不再与此计算机的完全限定域名 (FQDN) 或 DNS 名称的第一部分相符。 如果 NetBIOS 名称与计算机的 FQDN 的第一部分不符，组配置将失败。  
  
##### <a name="resolution"></a>解决方法  
 更改运行的计算机的 NetBIOS 名称[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]到包含不超过 15 个字符，然后再次运行的配置的名称。  
  
> [!NOTE]
>  如果对其重命名，则必须重新启动计算机。  
  
#### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a>如果 SQL Server 数据文件夹中已经存在与指定的数据库同名的 SQL Server 数据库文件，则配置将失败  
  
##### <a name="problem"></a>问题  
 配置失败，并出现如下错误：  
  
 无法设置 BAM 数据库  
  
 无法打开在登录“BAMPrimaryImport”中请求的数据库  
  
 登录失败。 用户的登录失败*BizTalk\BizTalkUser*  
  
##### <a name="cause"></a>原因  
 如果在运行 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的计算机的 \MSSQL\data 文件夹中已经存在 .mdf 文件或 .ldf 文件，而它们与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置程序正在尝试创建的 .mdf 文件或 .ldf 文件同名，则可能出现此错误。 为数据库创建的 .mdf 文件和 .ldf 文件的名称派生自在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置程序中指定的数据库的名称（附加 .mdf 和 .ldf 扩展名）。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此行为的问题，请执行以下操作之一：  
  
-   删除其名称与您要创建的任何数据库的名称匹配的任何 .mdf 文件或 .ldf 文件。  
  
-   选择数据库名称时，确保其与 SQL Server 的 \Program Files\Microsoft SQL Server\MSSQL\data 文件夹中已经存在的任何 .mdf 文件或 .ldf 文件的名称都不匹配。  
  
#### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a>当指定本地帐户时，域控制器上的配置失败  
  
##### <a name="problem"></a>问题  
 运行时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序的域控制器上，如果您为 BizTalkServerApplication 主机或 BizTalkIsolatedHost 主机指定本地组 （例如，BizTalk 主机用户组），则配置失败。  
  
##### <a name="cause"></a>原因  
 域控制器自动将本地 Windows 组视为域 Windows 组（在域控制器上不存在本地 Windows 组）。 如果在运行配置程序时为主机指定了本地 Windows 组，当您尝试为此组创建 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 登录时，配置将失败。 当服务器是域控制器时，配置程序不禁用本地 Windows 组选项。  
  
##### <a name="resolution"></a>解决方法  
 为在配置过程中创建的主机指定域组。  
  
#### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a>如果尚未重命名 SQL Server，配置将无法创建 SQL Server 分析数据库  
  
##### <a name="problem"></a>问题  
 如果您已经对安装了 SQL Server 分析服务器的计算机进行了重命名，当配置程序尝试新建 SQL Server 分析数据库时将失败，并且生成如下错误：  
  
 无法连接到存储库。  
  
 Analysis server:\<计算机名称\>  
  
 Error:  
  
 '\\\\< 计算机名称\>\MsOLAPRepository$\msmdrep.mdb 不是有效路径。  
  
 请确保正确拼写路径名称，并且已  
  
 并且您已连接到该文件所驻留的服务器。  
  
##### <a name="cause"></a>原因  
 配置程序无法确定您安装了 SQL Server 分析服务器的计算机的新名称。  
  
##### <a name="resolution"></a>解决方法  
 手动执行下列操作，以便用新的计算机名更新分析服务器：  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server**，指向**Analysis Services**，然后单击**分析管理器**。  
  
2.  在中**分析管理器**导航面板中，双击**分析服务器**节点以将其展开。  
  
3.  右键单击你想要编辑，然后选择的存储库连接字符串服务器**编辑存储库连接字符串**。  
  
4.  在中**编辑存储库连接字符串**对话框中，验证此字符串中的服务器名称，它更新为新的计算机名称是否正确。  
  
5.  导航到以下位置： \<*安装目录*\>\Program Files\Microsoft Analysis Services\Bin。  
  
6.  右键单击**Bin**文件夹，，然后单击**共享和安全**。 **Bin 属性**对话框随即出现。  
  
7.  在中**Bin 属性**对话框中，单击**共享**选项卡来验证所有联机分析处理 (OLAP) 管理员具有对此文件夹的完全权限。  
  
#### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a>当从 Visual Studio 中重新部署程序集时，项目从配置数据库中消失  
  
##### <a name="problem"></a>问题  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]内的项目级重新部署项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，包含在项目中引用正在重新部署该项目的所有项目都都消失时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]刷新 MMC。  
  
##### <a name="cause"></a>原因  
 为了说明此问题的原因，请看以下示例，此示例基于一个示例 BizTalk Server 解决方案，用户要在此解决方案中重新部署 Maps 项目。 请注意，对项目进行编译将生成单独的程序集。 下图表示用户在进行重新部署之前，此解决方案的状态。 项目之间的关系如下所示：  
  
- Orch1、Orch2、Maps、Pipelines 和 Schemas 为项目。  
  
- Orch1 引用 Maps，而 Maps 引用 Schemas。  
  
- Orch2 引用 Schemas。  
  
- Pipelines 引用 Schemas。  
  
  ![](../core/media/bcd-existingbiztalkserversolutionc.gif "bcd_ExistingBizTalkServerSolutionc")  
  
  如果用户使用默认的 Visual Studio 项目设置重新部署 Maps 项目，则 Orch1、Orch2 和 Pipeline 项目将消失，如下图所示。  
  
  ![](../core/media/bcd-biztalksolutionwlostartifactsc.gif "bcd_BizTalkSolutionWLostArtifactsc")  
  
  重新部署 Maps 的过程分为两步，首先取消部署当前已部署的 Maps.dll 程序集，然后部署新的 Maps.dll 文件。 Visual Studio 重新部署过程的一部分自动执行这些步骤。  
  
> [!NOTE]
>  严格来说，上面的描述并不正确，因为这些是 Visual Studio 一直执行的步骤，因此并没有考虑其方式是否适当。  
  
 关键在于，为了取消部署 BizTalk Server 程序集，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 必须取消部署依赖于这一已设置部署标志的程序集的所有程序集。 在本例中，要执行重新部署过程的第一个取消部署步骤，BizTalk Server 需要取消部署 Orch1.dll（而它依赖于 Maps.dll）。 在取消部署 Maps.dll 的过程中，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 还将取消部署 Schemas.dll（假定它已设置部署标志）。 为了取消部署 Schemas.dll，Visual Studio 需要取消部署 Orch2.dll 和 Pipelines.dll（这两者都依赖于 Schemas.dll）。  
  
 中的存在问题[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]重新部署仅 Maps.dll 以及它所依赖的程序集： 在本例中为 Schemas.dll。 因此，当用户刷新 BizTalk Server MMC，Orch1 和 Orch2，管道程序集似乎消失，但 Maps.dll 和 Schemas.dll 是仍然可见。  
  
##### <a name="resolution"></a>解决方法  
 主项目 （引用其他项目），请执行以下操作：  
  
1.  在解决方案资源管理器中，右键单击解决方案节点。  
  
2.  单击**属性**以打开**解决方案属性页**对话框。  
  
3.  单击**配置属性**，然后单击**配置**。  
  
4.  清除**部署**引用的项目的复选框。  
  
5.  在解决方案资源管理器中，执行新的解决方案级别部署。 若要执行此操作，右键单击解决方案节点，然后单击**部署解决方案**。  
  
#### <a name="supported-virtual-directory-types"></a>支持的虚拟目录类型  
 仅当关联的虚拟目录的类型，导出操作时从业务流程，并尝试执行 MSI 导出引用 Web 服务，将会成功**IIsWebVirtualDir**或**IIsWebDirectory**. **IIsWebVirtualDir**并**IIsWebDirectory**是显示在 IIS 元数据库中的节点类型。 **IIsWebVirtualDir**是与虚拟目录**路径**指向绝对文件夹的属性。 **IIsWebDirectory**是一个虚拟目录，而无需**路径**属性，因此指向相对文件夹中，通常的另一个子文件夹**IIsWebVirtualDir**或**IIsWebDirectory**节点。 这两种类型是元数据库层次中用于描述文件夹的常见类型。  
  
 类型的虚拟目录**IIsConfigObject**不受支持，并且，MSI 导出在此情况下将失败。 **IIsConfigObject**是 BizTalk Server 无法正确处理任一有效的节点类型的意外元数据库节点类型或相对值的指示正确创建 （并因此而无效） 元数据库条目。 在此情况下，BizTalk Server 将显示一条错误消息类似于以下内容： 预期的目录条目"iis: //lm/w3svc/1/root/badvdir/"，类型为 IIsConfigObject。  
  
#### <a name="unable-to-view-group-information-after-removing-stale-logons"></a>删除过时登录后无法查看组信息  
  
##### <a name="problem"></a>问题  
 如果在配置过程中遇到过时登录并删除它们，您可能无法查看组信息。  
  
##### <a name="cause"></a>原因  
 这是一个已知的配置问题。  
  
##### <a name="resolution"></a>解决方法  
 删除主机 Windows 组登录，然后重新配置，这种方法可能奏效。 如果组信息仍然不可用，请联系 Microsoft 产品支持人员。  
  
##### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a>安装 BizTalk Server 后将无法更改计算机名称  
  
###### <a name="problem"></a>问题  
 当您在运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上更改计算机名称，并重新启动计算机时，可能会出现错误消息。  
  
###### <a name="cause"></a>原因  
 SQL Server 不支持更改计算机名称，因此在安装和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持更改计算机名称。  
  
###### <a name="resolution"></a>解决方法  
 我们建议您在安装 BizTalk Server 后不要更改计算机名称。