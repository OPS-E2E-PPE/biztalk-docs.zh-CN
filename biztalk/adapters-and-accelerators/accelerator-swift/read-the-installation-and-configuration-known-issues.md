---
title: 阅读有关安装和配置的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c58d9dcb-7835-4181-a6cb-203c5d138e6a
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56536829ba789903899bdd661a789e5755e0cf3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377068"
---
# <a name="read-the-installation-and-configuration-known-issues"></a>阅读有关安装和配置的已知问题
  
## <a name="installing-over-terminal-server-creates-log-files-in-a-different-folder"></a>通过终端服务器安装在不同的文件夹中创建的日志文件  
 A4SWIFT 安装程序在 A4SWIFT 安装通过终端服务器连接时，创建中的安装和配置日志文件 *\<驱动器\>* : \Documents and 设置\\ *\<用户名\>* \Local 设置文件夹。 通常情况下，安装程序会创建这些文件置于 *\<驱动器\>* : \Documents and 设置\\ *\<用户名\>* \LocalSettings\temp 文件夹。 可以查看这些日志文件，以确保你的计算机进行设置并正确配置。  
  
## <a name="silent-installation-is-not-recommended"></a>不建议无提示安装  
 无提示安装支持的 A4SWIFT 安装程序，但不是建议由于其他配置步骤所需的复杂性。  
  
## <a name="a4swift-setup-runs-with-the-installplatform-argument-that-overwrites-dlls-for-visualstudionet"></a>A4SWIFT 安装运行使用将 Dll 覆盖为 VisualStudio.Net /InstallPlatform 自变量  
 A4SWIFT 安装程序始终使用 /InstallPlatform 参数运行。 结果，A4SWIFT 安装始终安装 msvcr71.dll、 mfc71u.dll、 msvcp71.dll 和 atl71.dll，所需的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 A4SWIFT 安装程序将安装是否 Dll 以前安装了或不到 %WINDIR%\System32 文件夹中，这些 DLL 文件。  
  
## <a name="canceling-a4swift-configuration-will-fail"></a>正在取消 A4SWIFT 配置将失败  
 单击**取消**期间 A4SWIFT 配置不会取消配置。 配置过程将继续，直到完成。  
  
## <a name="after-unconfiguring-a4swift-you-cannot-reconfigure-in-the-same-instance-of-the-configuration-console"></a>取消配置 A4SWIFT 之后, 你不能重新配置中配置控制台的同一实例  
 如果取消配置 A4SWIFT 或 A4SWIFT 组件时，您不能重新配置 A4SWIFT 或其组件而无需首先关闭 A4SWIFT 配置控制台中，然后再重新打开它。 如果不这样做，配置控制台的某些字段将灰显，并且您将不能选择它们的值。  
  
## <a name="configuration-of-a-web-components-only-installation-will-succeed-even-if-no-a4swift-database-exists"></a>配置 Web 组件仅安装将会成功，即使不存在任何 A4SWIFT 数据库  
 如果您执行安装的 Web 组件将为消息修复和新提交功能的自定义安装并运行 Microsoft BizTalk Accelerator for SWIFT 配置向导，配置程序将甚至已成功完成尽管没有 A4SWIFT 数据库。  
  
 A4SWIFT 数据库将显示在**用于消息修复和新提交的 Web 组件**窗格 A4SWIFT 配置对话框中，即使该数据库不存在。 警告将显示 A4SWIFT 数据库中数据存储窗格中，但警告不会继续阻止配置过程。  
  
## <a name="upgrade-process-does-not-create-a-new-root-folder"></a>升级过程不会创建一个新的根文件夹  
 升级进程会更新 A4SWIFT 文件中的现有 *\<驱动器\>* : \Program Files\Microsoft BizTalk Accelerator for A4SWIFT 2.3/3.0 文件夹。 它不会创建新文件夹的升级后的文件，也不会改变现有文件夹的名称 *\<驱动器\>* : \Program Files\Microsoft BizTalk Accelerator for SWIFT。  
  
## <a name="canceling-setup-during-an-upgrade-for-a4swift-may-leave-your-system-in-an-unknown-state"></a>在升级过程的 A4SWIFT 取消安装程序可能会使系统处于未知状态  
 在某些情况下，单击**取消**按钮在升级过程中可能会原样保留文件、 程序集、 BizTalk Server 项目和注册表项并且安装程序完成回滚后。  
  
 您可以手动删除没有任何问题的所有项目。  
  
## <a name="download-the-a4swift-setup-exe-file-from-the-web-into-a-temp-folder"></a>A4SWIFT 安装程序 exe 文件从 Web 下载到临时文件夹  
 如果要从 Web 下载的自解压缩可执行文件从安装 A4SWIFT，请务必将该文件下载到临时文件夹。 到 BizTalk Server 根文件夹不再下载该文件 (BizTalk Server \Program Files\Microsoft \<*版本*\>)。  
  
 如果从 BizTalk Server 根文件夹运行 exe 文件，它运行 BizTalk Server 安装向导中，不是 A4SWIFT 安装向导。  
  
## <a name="installing-a4swift-in-a-location-other-than-the-default-requires-changes-to-the-bredeploymentexeconfig-file"></a>在非默认位置中安装 A4SWIFT 需要更改的 BREDeployment.exe.config 文件  
 如果你安装 BizTalk Accelerator for SWIFT 中路径之外的默认路径的 %programfiles%\Microsoft BizTalk Accelerator for SWIFT，则必须编辑产品以反映正确的路径的 SDK\Tools 子目录中的 BREDeployment.exe.config 文件BasePoliciesDirectory、 SchemasDirectory，和 VocabularyDirectory。  
  
 必须进行此更改之前尝试部署任何与 SWIFT 架构项目若要成功部署相关规则和词汇中包含关联的规则。  
  
## <a name="message-repair-is-not-supported-for-certain-batched-message-scenarios"></a>某些消息批的情况下不支持消息修复  
 A4SWIFT 只支持使用消息修复碎片批处理方案。 在这些情况下，可以修复批处理消息的交换部分。  
  
## <a name="you-cannot-submit-a-fixed-unparsed-message-from-a-mrsr-site-library-named-anything-other-than-unparsed"></a>无法提交一个名为 Unparsed 之外的任何内容的 MRSR 站点库中的固定未分析的消息  
 当你尝试提交从 MRSR 站点文档库不是"Unparsed"已修复未分析的消息时，操作失败，因为 A4SWIFT 无法成功提交一条消息从一个库，它不是"Unparsed。"  
  
 如果在安装消息修复和对帐功能之前 MRSR 站点中有现有的"未分析的"文档库，A4SWIFT 安装程序将创建未分析的消息标题为"未分析"为后缀的库。  
  
 当 A4SWIFT 收到一条消息，它不能分析时，它将消息路由到安装程序创建的库。 但是，当你尝试提交该库中的消息，则操作将失败。  
  
 如果卸载 A4SWIFT 并且不要从 MRSR 站点中删除"未分析的"文档库，通常会出现此问题。  时重新 SWIFT 安装在这些情况下，安装程序创建一个新文档库具有名称"Unparsed"为后缀。"  
  
 若要解决此问题，请执行此过程：  
  
#### <a name="to-name-a-library-unparsed-in-order-to-submit-unparsed-messages"></a>若要命名库"Unparsed"以便提交未分析的消息  
  
1.  删除消息修复和对帐功能。  
  
2.  手动删除未分析的库。 这不会时不会删除卸载 A4SWIFT。  
  
3.  重新安装消息修复和对帐。 在重新安装期间将使用名称"Unparsed"创建文档库和可以提交此文档库通过固定未分析的消息。  
  
## <a name="bredeployment-utility-cannot-deploy-or-undeploy-policies-if-a4swift-vocabularies-are-not-correctly-configured"></a>BREDeployment 实用工具不能部署或取消部署策略，如果未正确配置 A4SWIFT 词汇  
 如果尝试通过使用 BREDeployment.exe 工具中，取消部署 A4SWIFT 业务规则引擎策略和 BREDeployment.exe 配置文件未指向正确的词汇文件位置，该工具可能会报告错误。 如果更改 BREDeployment.exe 配置文件中的位置和新的位置不包含词汇文件，将具有此问题。 该错误，通知您找不到词汇，并配置将停止部署和/或取消部署策略。  
  
 若要解决此问题，请使用标准**业务规则引擎部署向导**。 UI 的详细信息[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-swift/known-issues5.md)