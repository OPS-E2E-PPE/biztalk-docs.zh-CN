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
ms.openlocfilehash: ed34079f38490b2e48f367c5b73bb3ec9bea4904
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398651"
---
# <a name="troubleshooting-configuration"></a>排查配置问题
在 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序会在运行的一个或多个计算机上创建数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，将填充带有表、 角色、 数据库和存储过程由[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并部署到运行时期间使用的.NET 程序集BizTalk 管理数据库中。  
  
 本部分讨论用于解决配置错误的故障排除技术。 它还列出了一些常见的配置问题以及如何解决这些问题。  
  
## <a name="configuration-logging"></a>配置日志记录  
 配置程序将详细的信息写入到一个配置日志文件位于运行的计算机的 temp 目录中的默认情况下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 若要确定由 TEMP 环境变量打开指定的文件夹，此计算机上的命令提示符下键入以下命令，然后按 ENTER:  
  
 **echo %TEMP%**  
  
 配置日志文件包含执行，这些配置步骤的摘要，以及有关在配置过程中可能发生的任何故障的诊断信息。 如果出现配置错误，在诸如记事本之类的文本编辑器中打开配置日志，并检查错误的可能原因的日志文件。  
  
## <a name="troubleshooting-tools"></a>故障排除工具  
 使用 SQL Server Profiler、 Filemon 或 Regmon 收集有关配置失败的其他信息。 有关这些工具的详细信息，请参阅[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="configuration-fails-when-biztalk-server-and-sql-server-are-installed-on-separate-computers"></a>当单独的计算机上安装 BizTalk Server 和 SQL Server 时配置失败  
  
##### <a name="problem"></a>问题  
 在尝试配置企业单一登录 (SSO) 组件时，配置将失败并出现错误如下所示：  
  
 尝试访问 SSO 数据库时出错。  
  
 函数：FieldInfoCreate  
  
 -或-  
  
 未能启用单一登录 (SSO) 服务 （错误代码 0X800706BA）  
  
##### <a name="cause"></a>原因  
 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]则分布式事务处理协调器 (MSDTC) 事务的上下文下执行配置操作，并且必须可通过 MSDTC 功能安装在不同计算机上这些计算机之间的网络。 如果 MSDTC 功能将不可用通过网络运行的计算机之间[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]则会出现此错误。  
  
##### <a name="resolution"></a>解决方法  
 按照中的步骤[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)以确保通过网络运行的计算机之间的 MSDTC 功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
#### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a>防病毒软件干扰配置并将导致配置失败  
  
##### <a name="problem"></a>问题  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 当防病毒软件错误地确定配置程序是一种病毒时，配置失败。  
  
##### <a name="cause"></a>原因  
 防病毒软件尚未更新以包括[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序作为合法 （非病毒） 程序。  
  
##### <a name="resolution"></a>解决方法  
 配置防病毒程序识别[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序正在运行时，配置程序作为合法 （非病毒） 程序，否则暂时禁用防病毒软件。  
  
#### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a>配置失败，出现"文件或程序集名称 FileName.dll，或其某个依赖项，未找到"错误  
  
##### <a name="problem"></a>问题  
 在配置过程中将显示类似于以下错误：  
  
 无法部署 BizTalk 系统程序集"C:\Program Files\Microsoft\  
  
 BizTalk Server 2009\Microsoft.BizTalk.DefaultPipelines.dll. “未指定”  
  
 异常：文件或程序集名称 FileName.dll 或其中一个其  
  
 依赖项，找不到。 文件或程序集名称 FileName.dll 或  
  
 其某个依赖项，未找到。"  
  
##### <a name="cause"></a>原因  
 如果网络服务帐户运行的计算机上的临时文件夹没有写入权限，可能出现此错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在配置期间，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置使用 Windows Management Instrumentation (WMI) 将.NET 程序集部署到 BizTalk 管理数据库。 这些程序集部署到 BizTalk 管理数据库时，WMI 模拟网络服务帐户，因此网络服务帐户必须运行的计算机上的临时文件夹具有写访问权限[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
##### <a name="resolution"></a>解决方法  
 授予网络服务帐户写入访问权限运行的计算机上的临时文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并再次运行配置程序。 若要确定由 TEMP 环境变量指定的文件夹，打开命令提示符在计算机上，键入以下命令，然后按 ENTER:  
  
```  
echo %TEMP%  
```  
  
#### <a name="configuration-of-the-group-fails-if-the-netbios-name-of-the-computer-running-sql-server-exceeds-15-characters"></a>如果运行 SQL Server 的计算机的 NetBIOS 名称超过 15 个字符的组的配置将失败  
  
##### <a name="problem"></a>问题  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组配置失败，并且类似于以下的错误显示在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置日志：  
  
 2006-08-29 23:54:00:0902 [WARN] AdminLib GetBTSMessage: hrErr=80070547;  
  
 Msg = 无法从域中读取信息的配置  
  
 控制器，或者因为计算机不可用，或者是具有访问权限  
  
 已拒绝。;  
  
##### <a name="cause"></a>原因  
 如果运行的计算机命名为 NetBIOS 的长度，会发生此问题[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]超过 15 个字符。 如果 NetBIOS 名称超过 15 个字符 Windows 然后截断至 15 个字符的 NetBIOS 名称和 NetBIOS 名称将不再匹配的完全限定的域名 (FQDN) 或此计算机的 DNS 名称的第一部分。 如果 NetBIOS 名称不匹配的计算机的 FQDN 的第一部分，组配置将失败。  
  
##### <a name="resolution"></a>解决方法  
 更改运行的计算机的 NetBIOS 名称[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]到包含不超过 15 个字符，然后再次运行的配置的名称。  
  
> [!NOTE]
>  如果您重命名，必须重新启动计算机。  
  
#### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a>如果已具有相同的名称，因为指定的数据库的 SQL Server 数据库文件存在于 SQL Server 数据文件夹配置失败  
  
##### <a name="problem"></a>问题  
 配置失败并出现类似于以下的错误：  
  
 无法设置 BAM 数据库  
  
 无法打开登录 BAMPrimaryImport 中所请求的数据库  
  
 登录失败。 用户的登录失败*BizTalk\BizTalkUser*  
  
##### <a name="cause"></a>原因  
 如果运行的计算机的 \MSSQL\data 文件夹中已存在的.mdf 文件或.ldf 文件，可能出现此错误[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]具有相同的名称为.mdf 文件或.ldf 文件的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序尝试创建。 为数据库派生自中指定的数据库的名称创建的.mdf 文件和.ldf 文件的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].mdf 和.ldf 扩展名追加配置程序。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请使用以下方法之一：  
  
-   删除任何.mdf 文件或.ldf 文件与要创建的任何数据库的名称匹配的名称。  
  
-   选择数据库名称不匹配的任何.mdf 文件或.ldf 文件已存在 SQL server 的 \Program Files\Microsoft SQL Server\MSSQL\data 文件夹中的名称。  
  
#### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a>指定本地帐户时，配置在域控制器上失败  
  
##### <a name="problem"></a>问题  
 运行时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序的域控制器上，如果您为 BizTalkServerApplication 主机或 BizTalkIsolatedHost 主机指定本地组 （例如，BizTalk 主机用户组），则配置失败。  
  
##### <a name="cause"></a>原因  
 域控制器会自动将本地 Windows 组视为域 Windows 组 （没有就没有域控制器上的本地 Windows 组）。 如果您运行配置程序时为主机指定本地 Windows 组，配置将失败时尝试创建[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]组登录。 当服务器是域控制器时，配置程序不会禁用本地 Windows 组选项。  
  
##### <a name="resolution"></a>解决方法  
 在配置期间创建的主机指定域组。  
  
#### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a>无法创建 SQL Server 分析数据库，如果已重命名 SQL server 配置  
  
##### <a name="problem"></a>问题  
 如果已重命名在其安装 SQL Server 分析服务器的计算机，配置程序将失败时尝试创建新的 SQL Server 分析数据库并生成类似于以下错误：  
  
 无法连接到存储库。  
  
 Analysis server:\<计算机名称\>  
  
 错误：  
  
 '\\\\< 计算机名称\>\MsOLAPRepository$\msmdrep.mdb 不是有效路径。  
  
 请确保正确拼写路径名称，并且您已  
  
 连接到该文件所驻留的服务器。  
  
##### <a name="cause"></a>原因  
 配置程序不能确定在其安装 SQL Server 分析服务器的计算机的新名称。  
  
##### <a name="resolution"></a>解决方法  
 执行以下手动步骤，以使用新的计算机名更新分析服务器：  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server**，指向**Analysis Services**，然后单击**分析管理器**。  
  
2.  在中**分析管理器**导航面板中，双击**分析服务器**节点以将其展开。  
  
3.  右键单击你想要编辑，然后选择的存储库连接字符串服务器**编辑存储库连接字符串**。  
  
4.  在中**编辑存储库连接字符串**对话框中，验证此字符串中的服务器名称，它更新为新的计算机名称是否正确。  
  
5.  导航到以下位置： \<*安装目录*\>\Program Files\Microsoft Analysis Services\Bin。  
  
6.  右键单击**Bin**文件夹，，然后单击**共享和安全**。 **Bin 属性**对话框随即出现。  
  
7.  在中**Bin 属性**对话框中，单击**共享**选项卡来验证所有联机分析处理 (OLAP) 管理员具有对此文件夹的完全权限。  
  
#### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a>项目将从配置数据库上重新部署程序集从 Visual Studio 中消失  
  
##### <a name="problem"></a>问题  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]内的项目级重新部署项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，包含在项目中引用正在重新部署该项目的所有项目都都消失时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]刷新 MMC。  
  
##### <a name="cause"></a>原因  
 为了说明此问题的原因，请考虑下面的示例基于示例用户要重新部署 Maps 项目的 BizTalk Server 解决方案。 请注意，编译项目生成单独的程序集。 用户在进行重新部署之前下, 图指示解决方案的状态。 项目之间的关系如下所示：  
  
- Orch1、 Orch2、 映射、 管道和架构项目。  
  
- Orch1 引用 Maps，后者又引用架构。  
  
- Orch2 引用 Schemas。  
  
- Pipelines 引用 Schemas。  
  
  ![](../core/media/bcd-existingbiztalkserversolutionc.gif "bcd_ExistingBizTalkServerSolutionc")  
  
  如果用户重新部署 Maps 项目使用默认 Visual Studio 项目设置，Orch1、 Orch2 和管道项目将消失下, 图中所示。  
  
  ![](../core/media/bcd-biztalksolutionwlostartifactsc.gif "bcd_BizTalkSolutionWLostArtifactsc")  
  
  重新部署 Maps 是一个两步过程以及取消部署当前已部署的 Maps.dll 程序集，然后部署新的 Maps.dll 文件。 Visual Studio 重新部署过程的一部分自动执行这些步骤。  
  
> [!NOTE]
>  上面的描述不完全正确，因为这些是 Visual Studio 一直执行的步骤因此没有考虑其方式是否适当。  
  
 关键之处在于，为了取消部署 BizTalk Server 程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]必须取消部署所有程序集依赖于该程序集的设置部署标志。 在本示例中，若要执行的重新部署，首先取消部署 BizTalk Server 需要取消部署 Orch1.dll （而它依赖于 Maps.dll）。 在取消部署 Maps.dll 的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]还将取消部署 Schemas.dll （假定它已设置部署标志）。 为了取消部署 Schemas.dll，Visual Studio 需要取消部署 Orch2.dll 和 Pipelines.dll （这两者都依赖于 Schemas.dll）。  
  
 中的存在问题[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]重新部署仅 Maps.dll 以及它所依赖的程序集： 在本例中为 Schemas.dll。 因此，当用户刷新 BizTalk Server MMC，Orch1 和 Orch2，管道程序集似乎消失，但 Maps.dll 和 Schemas.dll 是仍然可见。  
  
##### <a name="resolution"></a>解决方法  
 主项目 （引用其他项目），请执行以下操作：  
  
1.  在解决方案资源管理器，右键单击解决方案节点。  
  
2.  单击**属性**以打开**解决方案属性页**对话框。  
  
3.  单击**配置属性**，然后单击**配置**。  
  
4.  清除**部署**引用的项目的复选框。  
  
5.  在解决方案资源管理器中执行新的解决方案级部署。 若要执行此操作，右键单击解决方案节点，然后单击**部署解决方案**。  
  
#### <a name="supported-virtual-directory-types"></a>支持的虚拟目录类型  
 仅当关联的虚拟目录的类型，导出操作时从业务流程，并尝试执行 MSI 导出引用 Web 服务，将会成功**IIsWebVirtualDir**或**IIsWebDirectory**. **IIsWebVirtualDir**并**IIsWebDirectory**是显示在 IIS 元数据库中的节点类型。 **IIsWebVirtualDir**是与虚拟目录**路径**指向绝对文件夹的属性。 **IIsWebDirectory**是一个虚拟目录，而无需**路径**属性，因此指向相对文件夹中，通常的另一个子文件夹**IIsWebVirtualDir**或**IIsWebDirectory**节点。 这两种类型是通常会出现在元数据库层次结构中用于描述文件夹。  
  
 类型的虚拟目录**IIsConfigObject**不受支持，并且，MSI 导出在此情况下将失败。 **IIsConfigObject**是 BizTalk Server 无法正确处理任一有效的节点类型的意外元数据库节点类型或相对值的指示正确创建 （并因此而无效） 元数据库条目。 在此情况下 BizTalk Server 将显示一条错误消息类似于以下内容：预期的目录条目"iis: //lm/w3svc/1/root/badvdir/"，类型为 IIsConfigObject。  
  
#### <a name="unable-to-view-group-information-after-removing-stale-logons"></a>无法查看组信息删除过时登录后  
  
##### <a name="problem"></a>问题  
 如果在配置期间，你会遇到并删除过时登录，你可能无法查看组信息。  
  
##### <a name="cause"></a>原因  
 这是一个已知的配置问题。  
  
##### <a name="resolution"></a>解决方法  
 它可能有助于删除主机 Windows 组登录，然后重新配置。 如果组信息仍不可用，请联系 Microsoft 产品支持。  
  
##### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a>安装 BizTalk Server 后无法更改计算机名称  
  
###### <a name="problem"></a>问题  
 当您更改运行的计算机上的计算机名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并重新启动 （重启） 计算机，可能会出现错误消息。  
  
###### <a name="cause"></a>原因  
 SQL Server 不支持更改计算机名称，因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持一次更改计算机名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装和配置。  
  
###### <a name="resolution"></a>解决方法  
 我们建议在安装 BizTalk Server 后不会更改计算机名称。