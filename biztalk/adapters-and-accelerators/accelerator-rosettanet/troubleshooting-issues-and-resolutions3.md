---
title: 疑难解答： 问题和 Resolutions3 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 40f59f54-183e-43db-afb5-0a45b437697f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab1f869d8d7c06260a1f7f8388991a0e18a2ff09
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50758692"
---
# <a name="troubleshooting-issues-and-resolutions"></a>故障排除： 问题和解决方法
本主题介绍与运行 Microsoft® 相关的问题[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。 每个问题都详细描述了一种特定的症状、其可能的原因以及解决方案。  
  
## <a name="error-publishing-a-batch-of-n-messages"></a>发布一批（“n”条）消息时出错  
  
### <a name="symptom"></a>故障现象  
 在事件日志中接收到以下或类似的错误：  
  
 消息引擎向传输适配器“BizTalk HTTP Receiver”的 MessageBox 数据库发布包含“n”条消息的批时遇到了错误。 请使用运行状况与活动跟踪工具来了解有关此故障的详细信息，并检查是否正确配置了终结点绑定。  
  
### <a name="possible-cause"></a>可能的原因  
 此错误可能由以下某个原因引起：  
  
- 缺少解密证书  
  
- 未正确加密消息  
  
- 未经授权的消息（未将源识别为有效的合作伙伴）  
  
- 消息未能通过对任意标头部分（前导头、传递头或服务头）的验证。  
  
  此消息之前可能有另一个详细说明原因的错误消息。  
  
### <a name="solution"></a>解决方案  
 请查看随错误消息提供的详细信息，以获取其他帮助。 正在重启 Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]™ 可能会解决此问题。  
  
## <a name="you-cannot-unenlist-all-artifacts"></a>无法取消登记所有项目  
  
### <a name="symptom"></a>故障现象  
 运行 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Clean 实用工具不能取消登记所有项目。  
  
### <a name="possible-cause"></a>可能的原因  
 如果您运行[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]删除协议和合作伙伴从 Microsoft® 管理控制台 (MMC) 之前的 Clean 实用工具，BtarnClean 实用工具将不能取消登记所有项目，因为仍使用它们。  
  
### <a name="solution"></a>解决方案  
  
##### <a name="to-remove-artifacts-using-the-loopback-utility"></a>使用环回实用工具删除项目  
  
1.  在命令提示符下，键入：  
  
    ```  
    lookback.exe /disable <home org or partner>  
    ```  
  
2.  运行 BtarnClean.exe 文件。  
  
3.  在 BizTalk 浏览器中，删除参与方。  
  
## <a name="installing-btarn-on-a-computer-without-biztalk-server-causes-missing-files"></a>在未安装 BizTalk Server 的计算机上安装 BTARN 会导致文件丢失  
  
### <a name="symptom"></a>故障现象  
 运行 ConfigFramework.exe 文件产生不具有 MicrosoftBizTalk 服务器或 Microsoft 的计算机上的任何结果[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]安装。 只能将此 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 配置作为 HTTP 客户端使用。  
  
### <a name="possible-cause"></a>可能的原因  
 安装过程中缺少两个 DLL 文件。  
  
### <a name="solution"></a>解决方案  
 在计算机上安装 SQLXML，然后手动将 Msxml4.dll 和 Atl71.dll 文件复制到 System 文件夹。  
  
## <a name="you-receive-an-access-error-when-attempting-to-change-the-btarn-configuration"></a>试图更改 BTARN 配置时出现访问错误  
  
### <a name="symptom"></a>故障现象  
 使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台导入配置文件时收到以下错误消息：  
  
 无法将发送端口“RNSTT.Async”的主传输的传输类型数据存储到配置存储。 拒绝访问。  
  
 在试图通过如创建新的合作伙伴等操作来更改配置时，也可能会出现此错误。  
  
### <a name="possible-cause"></a>可能的原因  
 当前用户不是 BizTalk Administrators 组的成员。  
  
### <a name="solution"></a>解决方案  
 确保当前用户为 BizTalk Administrators 组的成员。  
  
## <a name="you-receive-bam-errors"></a>出现 BAM 错误  
  
### <a name="symptom"></a>故障现象  
 事件查看器中出现以下错误消息：  
  
 跟踪消息活动时出错。 错误消息为“存储过程不存在”。  
  
 -或-  
  
 终止 id 的 BAM 消息活动时出错 *\<ID 号\>*。  
  
### <a name="possible-cause"></a>可能的原因  
 未安装业务活动监视 (BAM) 跟踪工具。  
  
### <a name="solution"></a>解决方案  
 安装 BAM 跟踪工具使用**自定义安装**选项。 如果不需要 BAM 功能，可忽略这些消息，或使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台禁用跟踪。 禁用跟踪后，必须重新启动 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 和 Internet 信息服务 (IIS)。  
  
## <a name="your-xsd-schema-does-not-display-properly-in-biztalk-editor"></a>XSD 架构在 BizTalk 编辑器中显示不正确  
  
### <a name="symptom"></a>故障现象  
 无法在 BizTalk 编辑器中正确查看架构的内容。  
  
### <a name="possible-cause"></a>可能的原因  
 该架构缺少 `displayroot_reference` 元素的 `schemaInfo` 属性。  
  
### <a name="solution"></a>解决方案  
 在记事本或其他文本编辑器中打开该架构，然后将 `displayroot_reference` 属性添加到 `schemaInfo` 元素中。 `displayroot_reference` 属性的值应与 `root_reference` 属性的值相同。  
  
 例如：  
  
 \<schemaInfo document_type ="4A1"版本 ="V02_00"xmlns ="<http://schemas.microsoft.com/BizTalk/2003>" *displayroot_reference ="Pip4A1StrategicForecastNotification"* root_reference ="Pip4A1StrategicForecastNotification" \>  
  
## <a name="404-not-found-error-when-sending-a-http-request"></a>发送 HTTP 请求时出现“404 找不到”错误  
  
### <a name="symptom"></a>故障现象  
 发送 HTTP 请求时收到以下或类似的错误：  
  
 远程服务器返回错误：(404) 找不到。  
  
 无法将消息发送到 ../BTSHttpReceive.dll。  
  
### <a name="possible-cause"></a>可能的原因  
 Internet 信息服务 (IIS) 中未配置 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Internet Server API (ISAPI) 扩展 DLL (BTSHttpReceive.dll)。 如果未配置 HwsMessages HttpReceive Web Services 扩展或配置了此 Web Services 扩展但不允许使用它，则发生此错误。  
  
### <a name="solution"></a>解决方案  
 若要确定是否配置了 HwsMessages HttpReceive Web Services 扩展，以及在配置后如何允许使用它，请执行以下过程。  
  
##### <a name="to-configure-the-biztalk-isapi-extension-dll-in-iis"></a>在 IIS 中配置 BizTalk ISAPI 扩展 DLL  
  
1. 单击**启动**，依次指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2. 展开**\<计算机名\>（本地计算机）**，然后单击**Web 服务扩展**。  
  
3. 在中**Web 服务扩展**窗格中，验证是否允许 HwsMessages HttpReceive 的状态。 如果没有，请右键单击**HwsMessages HttpReceive**，然后单击**允许**。  
  
   如果未配置 HwsMessages HttpReceive Web Services 扩展（它没有包含在 IIS 管理器的“Web Services 扩展”列表中），则请执行以下过程。  
  
##### <a name="to-configure-the-biztalk-isapi-extension-dll-in-iis"></a>在 IIS 中配置 BizTalk ISAPI 扩展 DLL  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2.  展开**\<计算机名\>（本地计算机）**，右键单击**Web 服务扩展**，然后单击**添加一个新的 Web 服务扩展**.  
  
3.  中**新的 Web 服务扩展**对话框中**扩展名**框中，键入**BizTalk ISAPI 扩展**，然后单击**添加**。  
  
4.  在中**Add File**对话框中**文件的路径**框中，键入**\<驱动器\>: \Program Files\Microsoft BizTalk Server\<版本\>\HttpReceive\BTSHttpReceive.dll**，然后单击**确定**。  
  
5.  在**新的 Web 服务扩展**对话框中，选择**为允许设置扩展状态**，然后单击**确定**。  
  
## <a name="an-access-violation-occurs-when-running-the-configuration-wizard"></a>运行配置向导时出现访问冲突  
  
### <a name="symptom"></a>故障现象  
 在事件日志中接收到以下或类似的错误：  
  
 使用用户帐户“\HostSvc”配置的 BizTalk 独立主机实例要么未运行，要么在此计算机上不存在。 请使用 BizTalk 管理控制台新建一个独立主机，或者重新配置一个现有主机，使其以“\hostsvc”的身份运行。  
  
### <a name="possible-cause"></a>可能的原因  
 若要运行配置向导，用户应配置为\<*机器名*\>\hostsvc，不是 \hostsvc。  
  
### <a name="solution"></a>解决方案  
 打开 BizTalk 管理控制台中，并更改 \hostsvc 帐户下运行的主机，使它们在帐户下运行\<*机器名*\>\hostsvc。  
  
## <a name="you-receive-an-error-when-importing-and-compiling-a-rosettanet-next-generation-pip-schema"></a>导入和编译 RosettaNet 下一代 PIP 架构时出现错误  
  
### <a name="symptom"></a>故障现象  
 在事件日志中接收到以下或类似的错误：  
  
 错误 CS0234：类或命名空间“RosettaNet.Schemas.System”中不存在类型名或命名空间名“SerializableAttribute”（是否缺少程序集引用？）。  
  
### <a name="possible-cause"></a>可能的原因  
 例如，其中一个架构 StandardDocumentHeader.xsd 有一个名为 RosettaNet.Schemas.System 的 [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 命名空间。  
  
### <a name="solution"></a>解决方案  
 删除此架构的 [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 命名空间中的“System”，以便命名空间名为 RosettaNet.Schemas。  
  
## <a name="you-receive-an-error-when-trying-to-manually-deploy-the-bam-package"></a>试图手动部署 BAM 软件包时出现错误  
  
### <a name="symptom"></a>故障现象  
 当您尝试手动部署的 BAM 软件包[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，你收到一个错误，指示在不能部署包。  
  
### <a name="possible-cause"></a>可能的原因  
 系统上所安装的 DTS 软件包 BAM_DM_Process 和 BAM_DM_Message 妨碍了 BAM 软件包的部署。  
  
### <a name="solution"></a>解决方案  
  
##### <a name="to-recover-from-the-error-condition-and-deploy-the-bam-package"></a>从错误情况中恢复并部署 BAM 软件包  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server**，然后单击**企业管理器**。  
  
2.  在企业管理器中，展开**Microsoft SQL Servers**， **SQL Server 组**， **（本地） (Windows NT)**，和**Data Transformation Services**.  
  
3.  单击**Local Packages**，右键单击**BAM_DM_Message**，然后单击**删除**。  
  
4.  右键单击**BAM_DM_Process**，然后单击**删除**。  
  
5.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
6.  在命令提示符下键入以下代码以部署跟踪文件，然后单击**确定**。  
  
    ```  
    cd %ProgramFiles%\Microsoft BizTalk Server <version>\Tracking  
    bm deploy all  "%ProgramFiles%\Microsoft BizTalk <version> Accelerator for RosettaNet\BAMTracking\tracking.xml"  
    ```  
  
## <a name="you-receive-an-error-when-adding-a-new-pip"></a>添加新的 PIP 时出现错误  
  
### <a name="symptom"></a>故障现象  
 在事件日志中接收到以下或类似的错误：  
  
 UNP.SCON.VALERR：验证服务内容时出错。  
  
 详细信息：按消息类型查找文档规范失败。 请验证已正确部署架构。  
  
### <a name="possible-cause"></a>可能的原因  
 实例 Pip4A5NotifyofForecastReply 的已部署架构的文档命名空间或根节点属性不正确。  
  
### <a name="solution"></a>解决方案  
 请验证实例 Pip4A5NotifyofForecastReply 的已部署架构的文档命名空间和根节点属性正确。  
  
## <a name="error-during-the-configuration-of-btarn-at-installation-time-caused-by-presumed-network-connectivity-issues"></a>安装时配置 BTARN 的过程中出错，这是由假设存在的网络连接问题造成的  
  
### <a name="symptom"></a>故障现象  
 在配置过程中，错误对话框中出现一个错误，指出计算机与网络的连接不正确，而实际上连接正确。  
  
### <a name="possible-cause"></a>可能的原因  
 此错误可能是由于 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 配置程序错误解释 IP 地址造成的。 C:\Windows\system32\drivers\etc 下的主机文件中包含一个将 localhost 主机名映射为 IP 地址 127.0.0.1 的条目。 配置程序可能将这个值与环回地址相混淆，因而假定计算机与网络的连接不正确。  
  
### <a name="solution"></a>解决方案  
  
##### <a name="to-avoid-this-error-and-complete-the-configuration-process"></a>避免此错误并完成配置过程  
  
1. 在 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 浏览器中，切换到 C:\Windows\system32\drivers\etc，然后使用记事本打开主机文件。  
  
2. 注释掉"127.0.0.1 localhost"通过将"#"放置在行的开头。 保存更改过的主机文件。  
  
3. 单击**重试**在错误对话框中。  
  
4. 配置成功完成后，重新在记事本中打开主机文件，删除映射 localhost 的行前的注释标记，然后保存主机文件。  
  
## <a name="you-receive-an-error-regarding-incorrect-signature-length"></a>出现指出签名长度不正确的错误  
  
### <a name="symptom"></a>故障现象  
 在事件日志中接收到以下或类似的错误：  
  
 执行接收管道时失败：“Microsoft.Solutions.BTARN.Pipelines.Receive”源：“MIME/SMIME 解码器”接收位置：“/BTARNHttpReceive/BTSHTTPReceive.dll?xRNResponseType=async”原因：签名长度不正确，值 = 1935897193。  
  
### <a name="possible-cause"></a>可能的原因  
 此错误消息指出，签名长度不正确。 除了上述原因以外，不正确或不完整的头内容长度会导致签名长度的字节读数错误，这也可能造成此错误。  
  
### <a name="solution"></a>解决方案  
 请验证签名长度和头内容长度正确。  
  
## <a name="you-receive-503-service-unavailable-from-internet-explorer-on-64-bit-machine"></a>在 64 位计算机上从 Internet Explorer 收到“503：服务不可用”  
  
### <a name="symptom"></a>故障现象  
 之后[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]完成配置，当您尝试访问[ http://localhost ](http://localhost/)或[ http://localhost/BtarnApp/RnifSend.aspx ](http://localhost/BtarnApp/RnifSend.aspx)，可能会收到以下或类似错误：  
  
 503：服务不可用  
  
### <a name="possible-cause"></a>可能的原因  
 此错误可能是由 ISAPI 筛选器造成的，该筛选器可在 IIS 网站上设置的 C:\windows\system32\rpcproxy\rpcproxy.dll 下找到。  
  
### <a name="solution"></a>解决方案  
  
##### <a name="to-remove-rpcproxy-filter-entry-in-iis"></a>删除 IIS 中的 RpcProxy 筛选器条目  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2.  展开**\<计算机名\>（本地计算机）**，右键单击**网站**，然后单击**属性**。  
  
3.  选择**ISAPI 筛选器**选项卡。  
  
4.  选择**RpcProxy 筛选器**，然后单击**删除**。  
  
5.  单击“确定” 。  
  
6.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
7.  在命令提示符处，键入以下代码，以重置 IIS。  
  
    ```  
    iisreset  
    ```  
  
> [!NOTE]
>  如果你尝试访问 http://localhost 或 http://localhost/BtarnApp/RnifSend.aspx 再次执行上述步骤后，你将收到 HTTP 400 消息返回来自 Internet 资源管理器，这意味着 IIS 现在运行正常。  
  
## <a name="the-hubscenario-sample-will-not-be-installed-correctly-if-the-assembly-key-files-are-not-entered-for-the-projects"></a>如果没有为项目输入程序集密钥文件，则 HubScenario 示例将无法正确安装  
  
### <a name="symptom"></a>故障现象  
 当你运行 setup.bat *\<驱动器\>*: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\HubScenario 设置HubScenario 示例时，则操作将失败。  
  
### <a name="possible-cause"></a>可能的原因  
 由于项目中没有设置程序集密钥文件，HubScenario 和 HubHelper 程序集没有正确部署。  
  
### <a name="solution"></a>解决方案  
 为 HubScenario 和 HubHelper 项目设置程序集密钥文件。 有关详细信息，请参阅[HubScenario 示例](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md)。  
  
## <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample-on-sql-server-2008-r22008-sp1"></a>在 SQL Server 2008 R2/2008 SP1 上运行 setupx64.bat 设置“双操作 PIPAutomation 业务流程”示例  
  
### <a name="symptom"></a>故障现象  
 当你运行 setup.bat 以生成和初始化“双操作 PIPAutomation 业务流程”示例时，BTARNData 数据库中未创建 PipAutomationGetAction 存储过程。  
  
### <a name="possible-cause"></a>可能的原因  
 在 64 位计算机上或在 SQL Server 2008 R2/2008 SP1 运行的 BizTalk Server 安装上运行了 setup.bat。 这两种情况要求你运行 setupx64.bat。  
  
### <a name="solution"></a>解决方案  
 运行 setupx64.bat 以创建该存储过程。 有关详细信息，请参阅[双操作 PIPAutomation 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)。  
  
## <a name="enable-the-btarn-application-pools-for-32-bit-on-windows-server-2008-64-bit-windows-operating-system-os"></a>为 Windows Server 2008（64 位 Windows 操作系统 (OS)）上的 32 位程序启用 BTARN 应用程序池  
 要在 Windows Server 2008（64 位 Windows 操作系统 (OS)）、Internet 信息服务管理器 7.5/7.0 上运行 BTARN 端对端方案：  
  
 1. 启用 32 位程序的 BTARN 应用程序池。  
  
 2. 添加的 HTTP 处理程序\*.dll 引用 IsapiModule 筛选器。  
  
## <a name="see-also"></a>请参阅  
 [BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md)   
 [Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)
