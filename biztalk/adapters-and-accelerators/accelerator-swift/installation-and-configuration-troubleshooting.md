---
title: "安装和配置故障排除 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installing, troubleshooting
- configuring, troubleshooting
- troubleshooting, configuring
- troubleshooting, installing
ms.assetid: 25a2f6c5-c049-4042-8e38-4f7a2556e066
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc0f805011921fe259a0483fa2bcd50ab45d043b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installation-and-configuration-troubleshooting"></a>安装和配置故障排除
## <a name="setup-is-unable-to-deploy-the-runtimeschemas-assembly"></a>安装程序无法部署 RuntimeSchemas 程序集  
  
### <a name="symptom"></a>故障现象  
 无法部署 RuntimeSchemas.dll A4SWIFT 安装程序。 如果在安装后未手动部署程序集，则 A4SWIFT 配置向导将失败。  
  
### <a name="possible-cause"></a>可能的原因  
 下列情况之一存在：  
  
-   当你尝试执行的 A4SWIFT 的初始安装时已部署的运行时架构程序集。  
  
-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]你尝试在其安装 A4SWIFT 的计算机上未启动。  
  
-   当您尝试升级 A4SWIFT，并由另一个程序集引用了已部署的运行时架构程序集。 对运行时架构程序集进行 A4SWIFT 此无法取消部署升级程序。  
  
### <a name="solution"></a>解决方案  
 继续，如下所示，根据问题性质：  
  
-   如果运行时架构程序集已部署在试图运行的 A4SWIFT 初始安装时，打开 BizTalk 资源管理器中[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]，右键单击该程序集[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]。Solutions.FinancialServices.SWIFT.RuntimeSchemas，，然后单击取消部署。 使用 BizTalk 部署向导部署从 RuntimeSchemas.dll 的最新版本*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Assemblies。  
  
-   如果[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]已未启动，启动[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]中[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]Service Manager。 使用 BizTalk 部署向导部署从 RuntimeSchemas.dll 的最新版本*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Assemblies。  
  
-   如果运行时架构程序集已部署，当您尝试升级 A4SWIFT，并通过引用其他程序集，取消部署 BizTalk 浏览器中引用的程序集，并取消部署 RuntimeSchemas.dll BizTalk 浏览器中。 使用 BizTalk 部署向导部署从 RuntimeSchemas.dll 的最新版本*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Assemblies。  
  
## <a name="after-the-web-components-feature-is-removed-message-repair-and-reconciliation-is-incorrectly-shown-as-uninstalled"></a>删除 Web 组件功能后，将为已卸载未正确显示消息修复和调节  
  
### <a name="symptom"></a>故障现象  
 删除消息修复和新提交的功能 A4SWIFT Web 组件后，你无法卸载，安装，或配置消息修复并对帐功能 （或 A4SWIFT 组件）。 如果安装了消息修复和调节，A4SWIFT 无法识别该功能的安装。 如果你尝试安装、 修改或删除消息修复和对帐源 （从控制面板中显示） 的添加/删除程序内，添加/删除程序将指示未安装的功能。  
  
### <a name="possible-cause"></a>可能的原因  
 已从删除[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组后则按照初次安装 Web 组件的消息修复和新提交功能以及消息修复和对帐功能。 如果您然后移除 Web 组件功能 (这可以不是成员的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组)、 A4SWIFT 安装程序将删除该消息修复的文件和对帐功能具有的依赖关系。 这些文件包括 ConfigFramework.exe。  
  
### <a name="solution"></a>解决方案  
 如果你遇到此问题，请继续执行，如下所示：  
  
1.  在计算机管理窗口中，将自己添加回[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组、 注销计算机，然后重新登录。  
  
2.  重新安装消息修复和新提交功能将 Web 组件。  
  
    > [!NOTE]
    >  步骤 2 将 ConfigFramework.exe 添加回 A4SWIFT 安装。  
  
3.  重新安装 MRSR 功能。  
  
4.  如果你仍不希望 Web 组件为消息修复和新提交功能，请将其删除。  
  
## <a name="repairing-a4swift-to-add-the-service-folder-can-result-in-improper-access-permissions-for-that-folder"></a>修复 A4SWIFT 若要添加的服务文件夹可以导致为该文件夹不正确的访问权限  
  
### <a name="symptom"></a>故障现象  
 如果你删除文件夹*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Service 从 A4SWIFT 安装程序以添加服务器文件夹的修复功能重新设置 A4SWIFT 正确配置的 A4SWIFT 安装，并再次运行安装，服务文件夹的访问权限不会正确。 完全控制 A4SWIFT 管理员和读取和执行 A4SWIFT 用户，将不正确的权限。  
  
 如果在运行 A4SWIFT 安装程序的修复功能的服务文件夹存在时也会发生这种情况。 访问权限，如所 A4SWIFT 配置向导中，设置将被覆盖不正确的值。  
  
### <a name="possible-cause"></a>可能的原因  
 安装 Web 组件的消息修复和新提交功能将添加的服务文件夹。 如果你删除该文件夹，然后运行 A4SWIFT 安装程序的修复选项，将 Web 组件添加消息修复和新的提交，A4SWIFT 安装程序不会无法运行配置向导 (ConfigFramework.exe) 设置文件夹的权限。 由于未运行配置向导，它是很难再次运行向导以重置配置。 因此，修复选项将重新创建所有已删除的文件和文件夹，但它不会正确设置访问权限。  
  
 如果该文件夹存在运行修复时，修复过程还将覆盖服务文件夹的权限。 为在运行修复之前, 删除的服务文件夹的大小写与它将是很难运行配置程序来设置权限。 在此情况下，同样，权限会不正确，并将需要手动将它们设置。  
  
### <a name="solution"></a>解决方案  
 如果你遇到此问题，手动设置的服务文件夹的以下访问权限：  
  
|组或用户名|权限|  
|------------------------|----------------|  
|A4SWIFT 管理员|完全控制|  
|A4SWIFT 用户|读取及执行|  
  
 若要设置这些权限，请继续执行，如下所示：  
  
 在[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器中，移动到*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Service。  
  
1.  右键单击服务文件夹，单击**属性**，然后单击**安全**选项卡。  
  
2.  在组或用户名称窗格中的服务属性对话框中，单击**添加**，输入 ***\<服务器名称 >*\A4SWIFT 管理员**，然后单击**确定**。  
  
    > [!NOTE]
    >  如果 A4SWIFT Administrators 组的域组，请输入 ***\<域名 >*\A4SWIFT 管理员**。  
  
3.  重复步骤 2  ***\<服务器名称 >*\A4SWIFT 用户**，或  **\<*域名*> \A4SWIFT用户 * * 如果 A4SWIFT 用户组是域组。  
  
4.  在组或用户名称窗格中，选择**A4SWIFT 管理员**。 在权限窗格中，选择**允许**为**完全控制**。  
  
5.  在组或用户名称窗格中，选择**A4SWIFT 用户**。 在权限窗格中，单击**允许**为**读取和执行**，**列出文件夹内容**，和**读取**。  
  
6.  单击 **“确定”**。  
  
## <a name="upgrade-results-in-a-side-by-side-installation-of-two-versions-of-a4swift"></a>在两个版本的 A4SWIFT 通过并行安装的升级结果  
  
### <a name="symptom"></a>故障现象  
 当你尝试升级到[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，以前版本的 A4SWIFT 可能不会完全删除。 如果你从控制面板运行添加/删除程序，当前安装的程序的列表可能显示当前和以前的版本。  
  
### <a name="possible-cause"></a>可能的原因  
 以下任何条件可能会导致上述发生：  
  
-   试图进行升级的用户不是成员的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组。  
  
-   [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] (MSSQLSERVER) 服务已停止。  
  
-   执行无提示升级 using **setup.exe /addlocal**命令。  
  
### <a name="solution"></a>解决方案  
 若要阻止通过并行安装的[!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)]和[!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)]发生在升级过程中，确保你 （登录的用户） 的成员[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组中，且[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)](MSSQLSERVER) 服务已启动。  
  
 如果你结束与通过并行安装的[!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)]或[!INCLUDE[btaA4SWIFT2.1abbrev](../../includes/btaa4swift2-1abbrev-md.md)]和[!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)]，继续，如下所示：  
  
1.  备份 SWIFT 消息文件夹中的数据。  
  
2.  登录到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为成员 BTS 管理员组，并确保 MSSQLSERVER 服务正在运行。  
  
3.  删除 A4SWIFT 的以前版本。  
  
4.  再次升级到 A4SWIFT 的最新版本。 此时将进行升级，并且将创建没有通过并行安装。  
  
5.  使用 BizTalk 部署实用工具手动取消部署[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]。Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll，然后从 A4SWIFT 安装位置的程序集文件夹重新部署。 有关此工具的详细信息，请参阅[BRE 部署实用工具](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md)。  
  
## <a name="the-uninstall-or-upgrade-process-may-not-complete-correctly-if-you-do-not-restart-when-prompted"></a>如果你不重新启动出现提示时，在卸载或升级过程可能无法正确完成  
  
### <a name="symptom"></a>故障现象  
 卸载或升级过程不会正确完成。  
  
### <a name="possible-cause"></a>可能的原因  
 如果不具有取消部署一个项目引用现有的部署程序集，你可能会收到一个提示，表明必须重新启动系统 A4SWIFT 配置更改才能生效。 如果不单击**是**可立即重新启动，在全局程序集缓存中删除已分配的一些程序集可能不会删除，从而导致其他卸载或升级过程无法正确完成。  
  
### <a name="solution"></a>解决方案  
 取消引用一个现有的部署程序集，任何项目，然后再次运行卸载或升级过程。  
  
## <a name="if-the-iis-admin-service-is-stopped-during-setup-you-must-reconfigure-the-webservice-feature"></a>如果 IIS Admin Service 已停止安装过程中，你必须重新配置 web 服务功能  
  
### <a name="symptom"></a>故障现象  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置向导不会正确配置 web 服务功能。 你收到以下错误：  
  
 "无法创建 MRSR 项目： 无法连接到远程服务器。"  
  
### <a name="possible-cause"></a>可能的原因  
 IIS Admin Service 已停止运行时[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置向导。  
  
### <a name="solution"></a>解决方案  
 若要成功完成配置过程，继续执行，如下所示：  
  
1.  关闭[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台。  
  
2.  重新启动 IIS Admin Service。  
  
3.  执行*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Configuration.exe。  
  
4.  在[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台中，选择**取消配置功能**，然后选择**WebService**。  
  
5.  确保配置控制台中的 web 服务功能的状态都显示为未配置。  
  
6.  选择**应用配置**。  
  
    > [!NOTE]
    >  A4SWIFT 配置向导现在将正确配置 web 服务功能。  
  
## <a name="a4swift-configuration-will-fail-if-the-biztalkserverapplication-host-was-not-created-in-biztalk-server-configuration"></a>如果在 BizTalk Server 配置中未创建 BizTalkServerApplication 主机 A4SWIFT 配置将失败  
  
### <a name="symptom"></a>故障现象  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置向导不会正确配置 web 服务功能。 你收到以下错误：  
  
 "无法创建 MRSR 项目： 对象引用未设置为对象的实例。"  
  
### <a name="possible-cause"></a>可能的原因  
 在 BizTalk Server 运行时配置期间未创建进程内主机和主机实例。  
  
### <a name="solution"></a>解决方案  
 若要修复 A4SWIFT 配置，继续执行，如下所示：  
  
-   在 BizTalk Server 管理中创建主机。 没有无需现在具有正在运行的实例。  
  
-   在运行该 RepairBAS 工具*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools A4SWIFT 安装文件夹。  
  
 若要执行此操作，继续执行，如下所示：  
  
1.  启动**BizTalk Server 管理**控制台。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，然后展开**BizTalk 组**，然后展开**平台设置。**  
  
3.  右键单击**主机**，指向**新建**，然后选择**主机**。  
  
4.  在主机属性屏幕中，在常规的窗格中，输入以下信息：  
  
    -   主机名： **BizTalkServerApplication**  
  
    -   类型：**进程内**  
  
    -   Windows 组：   **\<*域*> \BizTalk 应用程序用户 * * （或设置在 BizTalk Server 配置为在进程内 BizTalk 应用程序内运行的帐户）  
  
    -   在选项部分中，选择这两个**允许主机跟踪**和**使此组中的默认主机**。  
  
5.  单击 **“确定”**。  
  
6.  单击**启动**，然后单击运行。 类型**cmd** ，然后单击**确定**。  
  
7.  在命令提示符处，导航到*%programfiles%***\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools**。  
  
8.  类型**RepairBAS.exe**然后按**Enter**。  
  
## <a name="you-must-change-the-bre-deployment-configuration-file-when-running-the-bre-deployment-utility-on-a-64-bit-computer"></a>在 64 位计算机上运行 BRE 部署实用工具时，必须更改 BRE 部署配置文件  
  
### <a name="symptom"></a>故障现象  
 BRE 部署实用工具无法正常工作时你它在 64 位计算机上或在非默认的目录 （而不是 C:\Program Files\Microsoft BizTalk Accelerator for SWIFT) 的计算机上运行 32 位。  
  
### <a name="possible-cause"></a>可能的原因  
 BRE 部署实用工具将无法正常工作之前更改位于 BREDeployment.exe.config 文件中的路径\<驱动器 >: files\microsoft BizTalk Accelerator for SWIFT\SDK\Tools 文件夹。  
  
### <a name="solution"></a>解决方案  
 在记事本中，打开 BREDeployment.exe.config 并更改基策略、 架构和词汇目录的文件夹中更新该实用程序的配置。  
  
## <a name="see-also"></a>另请参阅  
 [疑难解答： 问题和解决方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)