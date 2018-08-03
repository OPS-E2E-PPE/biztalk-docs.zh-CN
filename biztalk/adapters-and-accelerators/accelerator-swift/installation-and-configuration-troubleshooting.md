---
title: 安装和配置故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, troubleshooting
- configuring, troubleshooting
- troubleshooting, configuring
- troubleshooting, installing
ms.assetid: 25a2f6c5-c049-4042-8e38-4f7a2556e066
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10c0816508d2efb05dbac14797f80ffef12765fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967174"
---
# <a name="installation-and-configuration-troubleshooting"></a>安装和配置故障排除
## <a name="setup-is-unable-to-deploy-the-runtimeschemas-assembly"></a>安装程序无法将 RuntimeSchemas 程序集部署  
  
### <a name="symptom"></a>故障现象  
 A4SWIFT 安装程序无法部署 RuntimeSchemas.dll。 如果在安装完成后没有手动部署该程序集，A4SWIFT 配置向导将失败。  
  
### <a name="possible-cause"></a>可能的原因  
 存在以下条件之一：  
  
- 当您尝试执行 A4SWIFT 的初始安装时已部署的运行时架构程序集。  
  
- Microsoft[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]尝试 A4SWIFT 安装在计算机上未启动。  
  
- 当尝试升级 A4SWIFT，且被另一个程序集的已部署的运行时架构程序集。 运行时架构程序集进行 A4SWIFT 此阻止取消部署升级程序。  
  
### <a name="solution"></a>解决方案  
 根据问题性质，则继续，如下所示：  
  
- 如果你尝试运行 A4SWIFT 的初始安装时已部署的运行时架构程序集，在 Microsoft 中打开 BizTalk 浏览器[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]，右键单击 Microsoft 的程序集。Solutions.FinancialServices.SWIFT.RuntimeSchemas，并单击取消部署。 使用 BizTalk 部署向导来部署最新版本从 RuntimeSchemas.dll *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies。  
  
- 如果[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]时未启动，启动[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]中[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]Service Manager。 使用 BizTalk 部署向导来部署最新版本从 RuntimeSchemas.dll *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies。  
  
- 如果运行时架构程序集已部署时尝试升级 A4SWIFT，且被的另一个程序集取消部署 BizTalk 浏览器中引用的程序集，并取消部署 RuntimeSchemas.dll 在 BizTalk 浏览器。 使用 BizTalk 部署向导来部署最新版本从 RuntimeSchemas.dll *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies。  
  
## <a name="after-the-web-components-feature-is-removed-message-repair-and-reconciliation-is-incorrectly-shown-as-uninstalled"></a>删除 Web 组件功能后，消息修复和对帐会错误地显示为已卸载  
  
### <a name="symptom"></a>故障现象  
 删除消息修复和新提交功能的 A4SWIFT Web 组件后，不能卸载、 安装或配置消息修复和对帐功能 （或 A4SWIFT 组件）。 如果安装了消息修复和对帐，A4SWIFT 不识别该功能的安装。 如果你尝试安装、 修改或删除消息修复和对帐源中添加/删除程序 （从控制面板中显示），添加/删除程序将指示未安装的功能。  
  
### <a name="possible-cause"></a>可能的原因  
 已从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组后已安装用于消息修复和新提交功能和消息修复和对帐功能的 Web 组件。 如果您然后删除该 Web 组件功能 (您可以执行此操作不是成员的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组)、 A4SWIFT 安装程序将删除该消息修复的文件和对帐功能具有依赖关系。 这些文件包括 ConfigFramework.exe。  
  
### <a name="solution"></a>解决方案  
 如果遇到此问题，请继续执行，如下所示：  
  
1. 在计算机管理窗口中，将您自己添加回[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组，注销计算机，然后重新登录。  
  
2. 重新安装消息修复和新提交的功能的 Web 组件。  
  
   > [!NOTE]
   >  步骤 2 将 ConfigFramework.exe 添加回 A4SWIFT 安装。  
  
3. 重新安装 MRSR 功能。  
  
4. 如果你仍不希望 Web 组件用于消息修复和新提交功能，请将其删除。  
  
## <a name="repairing-a4swift-to-add-the-service-folder-can-result-in-improper-access-permissions-for-that-folder"></a>修复 A4SWIFT 若要添加的服务文件夹可能会导致为该文件夹不正确的访问权限  
  
### <a name="symptom"></a>故障现象  
 如果删除该文件夹 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service A4SWIFT 安装程序以添加服务器文件夹的修复功能重新设置 A4SWIFT 正确配置的 A4SWIFT 安装，然后运行安装中，服务文件夹的访问权限不会正确。 正确的权限是完全控制 A4SWIFT 管理员和读取和执行 A4SWIFT 用户。  
  
 如果您的服务文件夹存在时运行的 A4SWIFT 安装程序修复功能也会发生这种情况。 访问权限，所设置的 A4SWIFT 配置向导中，将被覆盖不正确的值。  
  
### <a name="possible-cause"></a>可能的原因  
 安装 Web 组件用于消息修复和新提交功能将添加的服务文件夹。 如果你删除该文件夹，然后运行要添加 Web 组件的消息修复和新提交 A4SWIFT 安装程序的修复选项，A4SWIFT 安装程序不会无法运行配置向导 (ConfigFramework.exe) 设置文件夹的权限。 由于已运行配置向导，它是很难再次运行向导以重置配置。 因此，修复选项将重新创建所有已删除的文件和文件夹，但它将不会正确设置访问权限。  
  
 如果该文件夹存在运行修复时，修复过程也将覆盖服务文件夹的权限。 作为运行修复之前删除服务文件夹的情况下它会很难运行配置程序来设置权限。 在此情况下，，权限将不正确，必须手动将它们设置。  
  
### <a name="solution"></a>解决方案  
 如果遇到此问题，手动设置的服务文件夹的以下访问权限：  
  
|组或用户名|权限|  
|------------------------|----------------|  
|A4SWIFT 管理员|完全控制|  
|A4SWIFT 用户|读取及执行|  
  
 若要设置这些权限，请继续阅读，如下所示：  
  
 在中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，转到 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service。  
  
1.  右键单击服务文件夹，单击**属性**，然后单击**安全**选项卡。  
  
2.  在组或用户名称窗格的服务属性对话框中，单击**外**，输入 ***\<服务器名称\>* \A4SWIFT 管理员**，然后单击**确定**.  
  
    > [!NOTE]
    >  如果 A4SWIFT Administrators 组的域组，请输入 ***\<域名\>* \A4SWIFT 管理员**。  
  
3.  重复步骤 2 ***\<服务器名称\>* \A4SWIFT 用户**，或 **\<*域名*\>\A4SWIFT 用户**如果A4SWIFT 用户组是域组。  
  
4.  在组或用户名称窗格中，选择**A4SWIFT 管理员**。 在权限窗格中，选择**允许**有关**完全控制**。  
  
5.  在组或用户名称窗格中，选择**A4SWIFT 用户**。 在权限窗格中，单击**允许**有关**读取和执行**，**列出文件夹内容**，以及**读取**。  
  
6.  单击“确定” 。  
  
## <a name="upgrade-results-in-a-side-by-side-installation-of-two-versions-of-a4swift"></a>在两个版本的 A4SWIFT 通过并行安装的升级结果  
  
### <a name="symptom"></a>故障现象  
 当你尝试升级到[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，以前版本的 A4SWIFT 可能不会完全删除。 如果从控制面板运行添加/删除程序，当前和以前的版本可能会显示当前安装的程序的列表。  
  
### <a name="possible-cause"></a>可能的原因  
 任何以下情况可能会导致上述发生：  
  
- 尝试升级的用户不是成员的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
- [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] (MSSQLSERVER) 服务已停止。  
  
- 执行无提示升级 using **setup.exe /addlocal**命令。  
  
### <a name="solution"></a>解决方案  
 若要阻止通过并行安装的[!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)]并[!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)]发生在升级过程中，确保你 （登录的用户） 的成员[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组，并且[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]启动服务 (MSSQLSERVER)。  
  
 如果您得到的通过并行安装[!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)]或[!INCLUDE[btaA4SWIFT2.1abbrev](../../includes/btaa4swift2-1abbrev-md.md)]和[!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)]，继续操作，如下所示：  
  
1. 备份 SWIFT 消息文件夹中的数据。  
  
2. 登录到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为 BTS 管理员的成员的组，并确保 MSSQLSERVER 服务正在运行。  
  
3. 删除以前版本的 A4SWIFT。  
  
4. 再次升级到 A4SWIFT 的最新版本。 这一次将进行升级，并且将创建不通过并行安装。  
  
5. 使用 BizTalk 部署实用工具，手动取消部署 Microsoft。Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll，然后从 A4SWIFT 安装位置的程序集文件夹重新部署。 有关此工具的详细信息，请参阅[BRE 部署实用工具](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md)。  
  
## <a name="the-uninstall-or-upgrade-process-may-not-complete-correctly-if-you-do-not-restart-when-prompted"></a>如果你不重新启动系统提示时，在卸载或升级过程可能无法正确完成  
  
### <a name="symptom"></a>故障现象  
 卸载或升级过程未正确完成。  
  
### <a name="possible-cause"></a>可能的原因  
 如果不具有取消部署一个项目引用现有的已部署程序集，可能会收到一个提示，指示您必须重新启动系统，A4SWIFT 配置更改才能生效。 如果不单击**是**以立即重新启动，在全局程序集缓存中删除已分配某些程序集可能不会删除，从而导致额外的卸载或升级进程，以正确完成。  
  
### <a name="solution"></a>解决方案  
 取消部署任何项目都引用一个现有的已部署程序集，然后再次运行卸载或升级过程。  
  
## <a name="if-the-iis-admin-service-is-stopped-during-setup-you-must-reconfigure-the-webservice-feature"></a>如果在安装过程已停止 IIS 管理服务，则必须重新配置 web 服务功能  
  
### <a name="symptom"></a>故障现象  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置向导不会正确配置的 web 服务功能。 您收到以下错误：  
  
 "无法创建 MRSR 项目： 无法连接到远程服务器。"  
  
### <a name="possible-cause"></a>可能的原因  
 IIS 管理服务已停止运行时[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置向导。  
  
### <a name="solution"></a>解决方案  
 若要成功完成配置过程，请继续阅读，如下所示：  
  
1. 关闭[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台。  
  
2. 重新启动 IIS 管理服务。  
  
3. 执行 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Configuration.exe。  
  
4. 在中[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台中，选择**取消对功能**，然后选择**WebService**。  
  
5. 请确保配置控制台中的 web 服务功能的状态都显示为未配置。  
  
6. 选择**应用配置**。  
  
   > [!NOTE]
   >  A4SWIFT 配置向导现在将正确配置的 web 服务功能。  
  
## <a name="a4swift-configuration-will-fail-if-the-biztalkserverapplication-host-was-not-created-in-biztalk-server-configuration"></a>如果在 BizTalk Server 配置中未创建 BizTalkServerApplication 主机 A4SWIFT 配置将失败  
  
### <a name="symptom"></a>故障现象  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置向导不会正确配置的 web 服务功能。 您收到以下错误：  
  
 "无法创建 MRSR 项目： 对象引用未设置为某个对象的实例。"  
  
### <a name="possible-cause"></a>可能的原因  
 BizTalk Server 运行时配置过程中未创建进程内主机和主机实例。  
  
### <a name="solution"></a>解决方案  
 若要修复的 A4SWIFT 配置，请继续阅读，如下所示：  
  
- 在 BizTalk Server 管理中创建一个主机。 没有必要现在具有正在运行的实例。  
  
- 在运行 RepairBAS 工具 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\SDK\Tools 文件夹的 A4SWIFT 安装。  
  
  为此，请继续操作，如下所示：  
  
1.  启动**BizTalk Server 管理**控制台。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，然后展开**BizTalk 组**，然后展开**平台设置。**  
  
3.  右键单击**主机**，依次指向**新建**，然后选择**主机**。  
  
4.  在主机属性屏幕中，在常规窗格中，输入以下信息：  
  
    -   主机名： **BizTalkServerApplication**  
  
    -   类型：**进程内**  
  
    -   Windows 组：  **\<*域*\>\BizTalk 应用程序用户**（或在用于运行 BizTalk 进程内的 BizTalk Server 配置过程中设置的帐户应用程序）  
  
    -   在选项部分中，选择这两**允许主机跟踪**并**组中将此默认主机**。  
  
5.  单击“确定” 。  
  
6.  单击**启动**，然后单击运行。 类型**cmd** ，然后单击**确定**。  
  
7.  在命令提示符处，导航到 * %programfiles%***\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools**。  
  
8.  类型**RepairBAS.exe** ，然后按**Enter**。  
  
## <a name="you-must-change-the-bre-deployment-configuration-file-when-running-the-bre-deployment-utility-on-a-64-bit-computer"></a>在 64 位计算机上运行 BRE 部署实用工具时，必须更改 BRE 部署配置文件  
  
### <a name="symptom"></a>故障现象  
 BRE 部署实用工具不会无法正常运行时在 64 位计算机上或在非默认的目录 （而不是 C:\Program Files\Microsoft BizTalk Accelerator for SWIFT) 的 32 位计算机上。  
  
### <a name="possible-cause"></a>可能的原因  
 BRE 部署实用工具将无法正常工作之前更改中的 BREDeployment.exe.config 文件中的路径\<驱动器\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools 文件夹。  
  
### <a name="solution"></a>解决方案  
 在记事本中，打开 BREDeployment.exe.config 并更改的基本策略、 架构和词汇目录的文件夹中更新该实用程序的配置。  
  
## <a name="see-also"></a>请参阅  
 [疑难解答：问题和解决方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)