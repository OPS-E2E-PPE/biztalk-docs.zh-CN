---
title: "安装并配置已知问题，请阅读 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c58d9dcb-7835-4181-a6cb-203c5d138e6a
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a09ff5969cc0c47da6a9e885118e227cc27c4ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="read-the-installation-and-configuration-known-issues"></a>读取的安装和配置的已知问题
  
## <a name="installing-over-terminal-server-creates-log-files-in-a-different-folder"></a>通过终端服务器安装的其他文件夹中创建日志文件  
 A4SWIFT 安装程序安装时 A4SWIFT 通过终端服务器连接，创建中的设置和配置日志文件*\<驱动器 >*: \Documents and 设置\\* \<用户名 >*\Local 设置文件夹。 通常情况下，安装程序将创建这些文件置于*\<驱动器 >*: \Documents and 设置\\*\<用户名 >*\Local Settings\temp 文件夹。 你可以查看这些日志文件，以确保你的计算机进行设置和配置正确。  
  
## <a name="silent-installation-is-not-recommended"></a>不建议无提示安装  
 无提示安装 A4SWIFT 安装程序支持，但不是建议由于所需的其他配置步骤的复杂性。  
  
## <a name="a4swift-setup-runs-with-the-installplatform-argument-that-overwrites-dlls-for-visualstudionet"></a>A4SWIFT 安装程序运行具有将 Dll 覆盖为 VisualStudio.Net /InstallPlatform 自变量  
 使用 /InstallPlatform 自变量始终运行 A4SWIFT 安装程序。 因此，A4SWIFT 安装始终安装 msvcr71.dll，mfc71u.dll、 msvcp71.dll，并且 atl71.dll，其所需的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 A4SWIFT 安装程序安装到 %WINDIR%\System32 文件夹中，这些 DLL 文件，是否 Dll 以前安装或不。  
  
## <a name="canceling-a4swift-configuration-will-fail"></a>取消 A4SWIFT 配置会失败  
 单击**取消**期间 A4SWIFT 配置不会取消配置。 配置过程将继续，直至完成。  
  
## <a name="after-unconfiguring-a4swift-you-cannot-reconfigure-in-the-same-instance-of-the-configuration-console"></a>未配置 A4SWIFT 之后, 不能重新配置配置控制台的同一实例中  
 如果你取消配置 A4SWIFT，或是 A4SWIFT 的一个组件，无法重新 A4SWIFT 或其组件配置而首先关闭 A4SWIFT 配置控制台中，然后重新打开它。 如果不这样做，配置控制台的某些字段将灰显，并且你将不能为其选择值。  
  
## <a name="configuration-of-a-web-components-only-installation-will-succeed-even-if-no-a4swift-database-exists"></a>配置 Web 组件仅安装将会成功，即使没有 A4SWIFT 数据库存在  
 如果你执行安装仅用于消息修复和新提交功能，Web 组件的自定义安装，然后为 SWIFT 配置向导运行 Microsoft BizTalk Accelerator，配置程序将成功甚至完成尽管没有 A4SWIFT 数据库。  
  
 A4SWIFT 数据库将显示在**用于消息修复和新提交的 Web 组件**窗格 A4SWIFT 配置对话框中，即使该数据库不存在。 警告将显示为 A4SWIFT 数据中的数据库存储窗格中，但，警告不会从继续阻止配置过程。  
  
## <a name="upgrade-process-does-not-create-a-new-root-folder"></a>升级过程不创建新的根文件夹  
 升级过程更新中现有的 A4SWIFT 文件*\<驱动器 >*: files\microsoft BizTalk Accelerator for A4SWIFT 2.3/3.0 文件夹。 它不创建新的文件夹以升级的文件，也不会改变到现有文件夹的名称*\<驱动器 >*: files\microsoft BizTalk Accelerator for SWIFT。  
  
## <a name="canceling-setup-during-an-upgrade-for-a4swift-may-leave-your-system-in-an-unknown-state"></a>在升级过程的 A4SWIFT 取消安装程序可能使系统处于未知状态  
 在某些情况下，单击**取消**按钮在升级期间可能会降低文件、 程序集、 BizTalk Server 项目和注册表项保持不变后安装程序已完成其回滚。  
  
 您可以手动删除所有项目，不会产生任何问题。  
  
## <a name="download-the-a4swift-setup-exe-file-from-the-web-into-a-temp-folder"></a>到临时文件夹从 Web 下载 A4SWIFT 安装程序 exe 文件  
 如果想要从从 Web 下载的自解压可执行文件安装 A4SWIFT，请务必将该文件下载到临时文件夹。 到 BizTalk Server 根文件夹不下载文件 (files\microsoft BizTalk Server \<*你版本*>)。  
  
 如果从 BizTalk Server 根文件夹中运行 exe 文件，它会将 BizTalk Server 运行安装向导中，不 A4SWIFT 安装向导。  
  
## <a name="installing-a4swift-in-a-location-other-than-the-default-requires-changes-to-the-bredeploymentexeconfig-file"></a>在非默认位置安装 A4SWIFT 需要对 BREDeployment.exe.config 文件的更改  
 如果你安装 BizTalk Accelerator for SWIFT %programfiles%\Microsoft BizTalk Accelerator 默认路径之外的其他路径中 for SWIFT，则必须编辑产品以反映正确的路径的 SDK\Tools 子目录中的 BREDeployment.exe.config 文件BasePoliciesDirectory、 SchemasDirectory，和 VocabularyDirectory 中。  
  
 你必须进行此更改之前尝试部署任何与包含在你的项目，若要成功部署的相关的规则和词汇 SWIFT 架构关联的规则。  
  
## <a name="message-repair-is-not-supported-for-certain-batched-message-scenarios"></a>某些消息的批处理的方案不支持消息修复  
 A4SWIFT 消息修复只支持批处理方案的碎片。 在这些情况下，则可以修复批处理消息的交换部分。  
  
## <a name="you-cannot-submit-a-fixed-unparsed-message-from-a-mrsr-site-library-named-anything-other-than-unparsed"></a>无法提交一个名为 Unparsed 之外的任何内容的 MRSR 站点库中的固定未分析的消息  
 当你尝试提交未分析的消息具有固定从 MRSR 站点文档库中未命名为"Unparsed"时，操作失败，因为 A4SWIFT 无法成功提交从库未命名为"Unparsed。"消息  
  
 如果在安装消息修复和对帐功能之前，请 MRSR 站点中有现有的"未分析的"文档库，A4SWIFT 安装可创建未分析消息标题为"未分析"替换为后缀的库。  
  
 当 A4SWIFT 收到一条消息，它无法分析时，它将消息路由到安装程序创建的库。 但是，当你尝试提交该库中的消息，则操作将失败。  
  
 如果卸载 A4SWIFT 且不要从 MRSR 站点删除"未分析的"文档库，通常会出现此问题。  当重新 SWIFT 安装在这些情况下，安装程序创建新的文档库具有名称"Unparsed"替换为后缀。"  
  
 若要解决此问题，请执行以下过程：  
  
#### <a name="to-name-a-library-unparsed-in-order-to-submit-unparsed-messages"></a>若要提交未分析的消息命名库"Unparsed"  
  
1.  删除消息修复和调节功能。  
  
2.  手动删除未分析的库。 这不时不会删除卸载 A4SWIFT。  
  
3.  重新安装消息修复和对帐。 在重新安装，将使用名称"Unparsed"创建文档库和可以提交通过此文档库的固定未分析的消息。  
  
## <a name="bredeployment-utility-cannot-deploy-or-undeploy-policies-if-a4swift-vocabularies-are-not-correctly-configured"></a>BREDeployment 实用工具不能部署或取消部署的策略，如果未正确配置 A4SWIFT 词汇  
 如果你尝试取消 A4SWIFT 业务规则引擎策略部署使用 BREDeployment.exe 工具，并且 BREDeployment.exe 配置文件未指向正确的词汇文件位置，该工具可能报告错误。 如果你更改 BREDeployment.exe 配置文件中的位置和新的位置未包含的词汇文件，你将具有此问题。 错误通知您找不到词汇，并配置将停止。 部署和/或正在取消部署策略。  
  
 若要解决此问题，请使用标准**业务规则引擎部署向导**。 UI 的详细信息[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>另请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-swift/known-issues5.md)