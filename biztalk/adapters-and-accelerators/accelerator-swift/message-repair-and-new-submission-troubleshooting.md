---
title: 消息修复和新提交疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, Message Repair and New Submission
- Message Repair and New Submission, troubleshooting
ms.assetid: bb07a286-6f02-4639-b5fa-a3647e356ac8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bbf5114d26f4f3afd56e4a2a020238d4fe44fae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001478"
---
# <a name="message-repair-and-new-submission-troubleshooting"></a>消息修复和新提交疑难解答
## <a name="a-repaired-message-cannot-be-submitted-if-the-envelope-schema-is-not-deployed"></a>不能提交修复后的消息，如果信封架构未部署  
  
### <a name="symptom"></a>故障现象  
 当您尝试提交一条消息，你已修复，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]发布以下消息：  
  
 "适配器无法传输消息发往发送端口"<http://mrsrtest:80/StsWebReceive/default.aspx?PartnerId=Unparsed&FolderType=MessagesInbox>"。 它将为此发送端口指定的重试时间间隔后重新传输。 详细信息:"80131600"。 有关详细信息，请参阅帮助和支持中心， [ http://go.microsoft.com/fwlink/?LinkId=142493 ](http://go.microsoft.com/fwlink/?LinkId=142493)。  
  
### <a name="possible-cause"></a>可能的原因  
 信封架构未部署。 这适用于任何 MT*xxx*消息或分析失败的任何消息。  
  
### <a name="solution"></a>解决方案  
 部署使用每个消息架构的信封架构 (\<驱动器\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<版本\>消息包 \SWIFT Messages\ A4SWIFT SRG\<版本\>\Category n\MTxxx.xsd) 和未分析的信封架构 (\<驱动器\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<版本\>消息包 \SWIFT Messages\ A4SWIFT SRG\<版本\>\ 未分析 Message\EnvelopeUnparsedMessage.xsd)。 有关详细信息，请参阅[部署 A4SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)。  
  
## <a name="you-cannot-submit-a-fixed-unparsed-message-from-a-mrsr-site-library-named-other-than-unparsed"></a>无法提交一个名为"Unparsed"以外的 MRSR 网站库中的固定未分析的消息  
  
### <a name="symptom"></a>故障现象  
 当你尝试提交从 MRSR 站点文档库不是"Unparsed"已修复未分析的消息时，则操作将失败。  
  
### <a name="possible-cause"></a>可能的原因  
 A4SWIFT 无法成功提交一条消息从一个库，它不是"Unparsed"。 如果在安装 MRSR （消息修复） 功能之前 MRSR 站点中有现有的"Unparsed"文档库，A4SWIFT 安装程序将创建一个后缀对名为"Unparsed"的未分析消息的库。 当它收到一条消息，A4SWIFT 无法分析时，它会将消息路由到创建它的库。 但是，当你尝试提交该库中的消息，则操作将失败。  
  
### <a name="solution"></a>解决方案  
 删除 MRSR 功能，删除未分析的库，然后重新安装 MRSR 功能。  
  
## <a name="cannot-loop-back-a-message-in-a-two-stage-workflow"></a>不能返回循环中两个阶段工作流的消息  
  
### <a name="symptom"></a>故障现象  
 具有仅创建阶段和修复阶段的工作流在修复阶段拒绝消息，如果提交失败。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 将消息路由到 MessageBox，并将发布以下的错误消息：  
  
 "无法重置到工作流中的第一个阶段。"  
  
### <a name="possible-cause"></a>可能的原因  
 具有仅创建阶段和修复阶段的工作流不支持消息环回。  
  
### <a name="solution"></a>解决方案  
 将另一个阶段添加到两个阶段工作流，或取消提交。  
  
## <a name="cannot-open-a-message-in-the-repair-inbox-in-mrsr"></a>无法打开在 MRSR 修复收件箱中的一条消息  
  
### <a name="symptom"></a>故障现象  
 在您尝试在 MRSR 中的修复收件箱中打开一条消息，一个弹出窗口中收到以下错误消息：  
  
 "无法打开登录 A4SWIFT 中所请求的数据库。 登录失败。 用户 NT AUTHORITY\NETWORK SERVICE 登录失败。  
  
### <a name="possible-cause"></a>可能的原因  
 登录帐户运行 A4SWIFT_MRSR web 服务的 web 应用程序是网络服务，不是本地或域帐户是在 A4SWIFT 用户组。  
  
### <a name="solution"></a>解决方案  
 更改运行 A4SWIFT_MRSR web 服务的 web 应用程序的登录帐户。  
  
##### <a name="to-change-the-login-account-for-the-web-application-that-the-a4swiftmrsr-web-service-runs-under"></a>若要更改运行 A4SWIFT_MRSR web 服务的 web 应用程序的登录帐户  
  
1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在 IIS 管理器中，展开 ***\<服务器名称\>* （本地计算机）** 节点，**应用程序池**节点和**Web站点**节点。 在网站节点中，展开**Default Web Site**节点。  
  
3.  在默认网站节点中，右键单击**A4SWIFT_MRSR**，然后单击**属性**。  
  
4.  在 A4SWIFT_MRSR 属性对话框中，记下应用程序池。  
  
5.  在 IIS 管理器对话框中，在应用程序池节点下，右键单击 A4SWIFT_MRSR，应用程序池，然后单击**属性**。  
  
6.  在中\<应用程序池名称\>属性对话框，单击**标识**注意。 如果**预定义**单击和**网络服务**为选中状态，单击**可配置**，输入你的本地或域帐户，然后输入你的密码。 单击“确定” 。  
  
## <a name="a-message-created-in-mrsr-site-on-a-localized-computer-is-not-processed"></a>未处理的已本地化的计算机上的 MRSR 站点中创建一条消息  
  
### <a name="symptom"></a>故障现象  
 在本地化平台运行的 A4SWIFT 的英语版本上正常工作的用户创建中的消息时[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]MRSR，在窗体并将该消息提交成功，将显示该消息可供消息修复和新提交业务流程，但未成功处理。 将消息提交到发件箱，但 BizTalk 适配器不提取。 没有错误或警告时在事件查看器中，并且不没有正在运行的业务流程实例在 HAT 中的任何记录。  
  
### <a name="possible-cause"></a>可能的原因  
 为 STS URI 作为输入的路径。发件箱接收位置包含英语名称，而不是已本地化的名称。  
  
### <a name="solution"></a>解决方案  
 更改 STS 的 URI 地址。发件箱接收位置，如下所示：  
  
1.  在 BizTalk Server 2009 管理控制台中，展开**BizTalk 组**，**应用程序**，并**BizTalk Application 1 节点**。  
  
2.  单击**接收位置**。  
  
3.  双击**Sts.Outbox.Location**。  
  
4.  在接收位置属性对话框中，单击**配置**。  
  
5.  在传输属性对话框中的值替换为**SharePointSite URL**与本地化的等效项。  
  
6.  单击**确定**，然后单击**确定**。  
  
## <a name="removing-a-role-while-it-is-processing-a-message-results-in-incomplete-removal-of-documents-and-artifacts"></a>删除角色，但它还在处理消息会导致完全删除的文档和项目  
  
### <a name="symptom"></a>故障现象  
 在配置文件 Web 客户端中删除角色时, 对话框中会发布，该值指示将删除所有文档和与角色相关联的项目。 但是，角色不会从部门在 A4SWIFT 管理控制台中，并且不会从 MRSR 删除角色的文档文件夹 （收件箱和已发送的邮件）。 删除参与方、 发送端口和协议与角色关联，并将取消部署角色的配置文件。  
  
### <a name="possible-cause"></a>可能的原因  
 仍在角色的收件箱中 MRSR，是一条消息和消息是在中打开其[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。  
  
### <a name="solution"></a>解决方案  
 手动删除该消息从 MRSR 站点收件箱，然后再删除与已删除的角色相关联的文档库。 关闭窗体并再次删除该角色。  
  
## <a name="message-processing-fails-as-a-result-of-an-error-in-the-bic-master-policy"></a>由于 BIC Master 策略中的错误消息处理失败  
  
### <a name="symptom"></a>故障现象  
 当用户提交邮件以进行处理时，您将收到以下错误：  
  
 "执行 BicMasterPolicy 时发生错误。 检查有效的值的策略。"  
  
### <a name="possible-cause"></a>可能的原因  
 SQL Server 名称、 BIC 数据库名称和 BIC_Master_Policy.xml 文件中的集成的安全值*\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 策略包含在双引号内。 若要启用 BIC 验证，则这些字符串中输入默认 BIC_Master_Policy.xml 文件中所述[启用验证的银行标识代码](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)。  
  
### <a name="solution"></a>解决方案  
 若要修复 BIC 主策略，请继续阅读，如下所示：  
  
> [!NOTE]
>  部署 BIC 主策略的详细信息，请参阅[部署 BRE 规则](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md)。  
  
1.  在业务规则编辑器中，取消部署的 BIC_Master_Policy，版本 1.0，然后删除 BIC_Master_Policy。  
  
2.  在文本编辑器中，（如记事本） 打开在 BIC_Master_Policy.xml *\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFTMessages\A4SWIFT SRG\<版本\>\Base 策略。 删除 SQL Server 名称两边添加双引号、 BIC 数据库名称，并集成安全值。  
  
3.  在业务规则引擎部署向导中，导入 BIC_Master_Policy.xml，，然后部署 BIC_Master_Policy.xml。  
  
4.  在服务 MMC 中，重新启动规则引擎更新服务和 BizTalk 接收主机服务。  
  
## <a name="a4swift-will-not-be-able-to-process-an-unparsed-message-without-proper-database-permissions"></a>A4SWIFT 将不能处理未分析的消息不具有正确的数据库权限  
  
### <a name="symptom"></a>故障现象  
 在删除一条消息，不能分析 A4SWIFT，A4SWIFT 无法处理该消息，但失败，出现未捕获的异常。  
  
### <a name="possible-cause"></a>可能的原因  
 没有数据库权限问题。 A4SWIFT 管理员和 A4SWIFT 用户组中不包括 BizTalk 服务，它默认情况下是 HostSvc 的登录帐户。  
  
### <a name="solution"></a>解决方案  
 将 BizTalk 服务的登录帐户添加到 A4SWIFT 管理员和 A4SWIFT 用户组。  
  
## <a name="a-timeout-of-the-infopath-repair-form-can-result-in-two-copies-of-a-message-in-different-stages-of-the-repair-workflow"></a>InfoPath 修复窗体的超时可能会导致一条消息的两个副本在修复工作流的不同阶段  
  
### <a name="symptom"></a>故障现象  
 提交时的 InfoPath 窗体中的消息 （适用于任何工作流阶段），如果在提交窗体中的错误，错误可能导致消息的两个副本。 为当前阶段，是仍在收件箱中的一条消息和另一条消息是在工作流中的下一步角色的收件箱中。 尝试处理这些消息将导致以下：  
  
-   如果您提交的工作流的下一个角色的收件箱中的消息，消息将继续执行工作流。  
  
-   如果从下一阶段的收件箱中提交的消息已处理完后，可以为当前阶段提交将消息从收件箱，从当前的收件箱中提交的消息将挂起的路由故障。  
  
-   如果之前已完成从下一阶段的收件箱中提交的消息为当前阶段提交收件箱中的消息处理时，为当前阶段提交从收件箱的邮件的收件箱返回适用于该阶段，你将收到以下错误：  
    "重置由于工作流： 消息已被篡改或为此阶段用户无效。"  
    在此之后，如果将消息从收件箱提交的下一阶段，它的工作流将还重置。 它将返回到收件箱为当前阶段，并且你将收到以上错误。  
  
### <a name="possible-cause"></a>可能的原因  
 在 InfoPath 窗体提交到 BizTalk Server 通过 Microsoft Windows Sharepoint Services 和执行验证的自定义 Web 服务的消息。 提交消息需要完成多个步骤，这些步骤不是事务性的因为 Windows Sharepoint Services 不是事务性的。 为了适应这种限制，MRSR 业务流程具有内置的恢复逻辑来检测和从提交消息中出现的错误中恢复。 MRSR 业务流程始终阻止发送到 SWIFT 重复消息。  
  
### <a name="solution"></a>解决方案  
 如果发生这种情况，应选择更甚工作流中的消息，并在尝试处理工作流的更早的阶段中的其他消息之前完成其工作流。 更甚工作流中的消息完成处理之后，您可以根据需要释放的第二个消息 （其中已暂停，并路由故障）。  
  
 如果消息的进一步沿工作流中未完成处理处理第二条消息之前，您应再一次修复更甚修复 InfoPath 窗体中的工作流中的消息，然后将其提交。 允许完成处理，并提交第二条消息。 第二条消息已挂起后，释放它。  
  
## <a name="a-new-submission-with-no-verify-stage-will-result-in-a-suspended-message"></a>没有验证阶段与新提交会导致挂起消息  
  
### <a name="symptom"></a>故障现象  
 当您提交具有没有验证阶段的工作流中的新消息时，则会挂起消息。  
  
### <a name="possible-cause"></a>可能的原因  
 如果 A4SWIFT_MRSRLastStage 未设置为创建缺少的验证阶段导致挂起消息。  
  
### <a name="solution"></a>解决方案  
 使用订阅 A4SWIFT_MRSRLastStage = = 创建，以确保正确路由该消息。  
  
## <a name="validation-of-message-results-a-parse-error-in-the-infopath-form-task-pane"></a>"分析错误"InfoPath 窗体任务窗格中的消息验证结果  
  
### <a name="symptom"></a>故障现象  
 验证在 InfoPath 窗体任务窗格将显示"分析错误"没有任何说明中的消息按钮。  
  
### <a name="solution"></a>解决方案  
 重新启动 MRSR web 服务或者执行 iisreset。  
  
## <a name="publishing-an-infopath-form-results-an-authorization-error"></a>InfoPath 窗体发布结果授权错误  
  
### <a name="symptom"></a>故障现象  
 发布 InfoPath 窗体时出现授权错误。  
  
### <a name="solution"></a>解决方案  
 将计算机名称替换为 MRSR 站点 URL 中的 localhost。  
  
## <a name="infopath-form-task-pane-shows-html-source-code"></a>InfoPath 窗体任务窗格中显示 HTML 源代码  
  
### <a name="symptom"></a>故障现象  
 InfoPath 窗体任务窗格显示而不是 Web 控件的 HTML 源代码。  
  
### <a name="solution"></a>解决方案  
 转到**工具**-> **安全选项卡** -> **Internet 区域**，并启用**根据内容而打开的文件不在扩展**在杂项下。  
  
## <a name="profile-web-client-website-results-an-authentication-error"></a>配置文件 Web 客户端网站生成身份验证错误  
  
### <a name="symptom"></a>故障现象  
 配置文件 Web 客户端网站显示身份验证错误。  
  
### <a name="solution"></a>解决方案  
 运行**BTSharePointAdapterWSAppPool**并**DefaultAppPoolApplication** -> 和在 Internet 信息 Services(IIS) 池的管理员帐户。  
  
## <a name="see-also"></a>请参阅  
 [疑难解答：问题和解决方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)