---
title: "消息修复和新提交故障排除 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, Message Repair and New Submission
- Message Repair and New Submission, troubleshooting
ms.assetid: bb07a286-6f02-4639-b5fa-a3647e356ac8
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d341a7f03c70e1ddcd242d7804b162338798e94
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="message-repair-and-new-submission-troubleshooting"></a>消息修复和新提交疑难解答
## <a name="a-repaired-message-cannot-be-submitted-if-the-envelope-schema-is-not-deployed"></a>无法提交修复后的消息，如果未部署信封架构  
  
### <a name="symptom"></a>故障现象  
 如果尝试以提交一条消息，您已修复，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]文章以下消息：  
  
 "适配器出现故障，以传输消息将发送端口"http://mrsrtest:80/StsWebReceive/default.aspx?PartnerId=Unparsed 和 FolderType = MessagesInbox"。 它将为此发送端口指定的重试时间间隔过后重新传输。 详细信息:"80131600"。 有关详细信息，请参阅帮助和支持中心[http://go.microsoft.com/fwlink/?LinkId=142493](http://go.microsoft.com/fwlink/?LinkId=142493)。  
  
### <a name="possible-cause"></a>可能的原因  
 未部署信封架构。 这适用于任何 MT*xxx*消息或分析失败的任何消息。  
  
### <a name="solution"></a>解决方案  
 部署使用每个消息架构信封架构 (\<驱动器\>: files\microsoft BizTalk Accelerator for SWIFT\<版本\>消息包 \SWIFT Messages\ A4SWIFT SRG\<版本\>\Category n\MTxxx.xsd) 和未分析的信封架构 (\<驱动器\>: files\microsoft BizTalk Accelerator for SWIFT\<版本\>消息包 \SWIFT Messages\ A4SWIFT SRG\<版本\>\ 未分析 Message\EnvelopeUnparsedMessage.xsd)。 有关详细信息，请参阅[部署 A4SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)。  
  
## <a name="you-cannot-submit-a-fixed-unparsed-message-from-a-mrsr-site-library-named-other-than-unparsed"></a>无法提交一个名为"Unparsed"以外的 MRSR 站点库中的固定未分析的消息  
  
### <a name="symptom"></a>故障现象  
 当你尝试提交已从 MRSR 站点文档库中未命名为"Unparsed"修复未分析的消息时，则操作将失败。  
  
### <a name="possible-cause"></a>可能的原因  
 A4SWIFT 无法成功提交未命名为"Unparsed"库中的消息。 如果你有现有的"Unparsed"文档库 MRSR 站点中安装 MRSR （消息修复） 功能之前，A4SWIFT 安装程序将创建一个后缀对名为"Unparsed"的未分析消息的库。 当它收到一条消息，A4SWIFT 无法分析时，它将将消息路由到它创建该库。 但是，当你尝试提交该库中的消息，该操作将失败。  
  
### <a name="solution"></a>解决方案  
 删除 MRSR 功能，删除未分析的库，然后重新安装 MRSR 功能。  
  
## <a name="cannot-loop-back-a-message-in-a-two-stage-workflow"></a>不能环回两阶段工作流中的消息  
  
### <a name="symptom"></a>故障现象  
 如果您具有仅创建阶段和修复阶段的工作流的修复阶段中拒绝了一条消息，提交失败。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息路由到 MessageBox 并发布以下的错误消息：  
  
 "无法重置到工作流中的第一个阶段。"  
  
### <a name="possible-cause"></a>可能的原因  
 具有仅创建阶段和修复阶段的工作流不支持消息环回。  
  
### <a name="solution"></a>解决方案  
 将另一个阶段添加到两个阶段工作流，或取消提交。  
  
## <a name="cannot-open-a-message-in-the-repair-inbox-in-mrsr"></a>无法打开在 MRSR 内的修复收件箱中的一条消息  
  
### <a name="symptom"></a>故障现象  
 当你尝试在 MRSR 内的修复收件箱中打开一条消息时，你会收到一个弹出窗口中的以下错误消息：  
  
 "无法打开登录 A4SWIFT 中所请求的数据库。 登录失败。 用户 NT AUTHORITY\NETWORK SERVICE 登录失败。  
  
### <a name="possible-cause"></a>可能的原因  
 登录帐户有关的 web 应用程序下运行 A4SWIFT_MRSR web 服务帐户是 Network Service，不是本地或域帐户为 A4SWIFT 用户组中。  
  
### <a name="solution"></a>解决方案  
 更改 web 应用程序运行 A4SWIFT_MRSR web 服务的登录帐户。  
  
##### <a name="to-change-the-login-account-for-the-web-application-that-the-a4swiftmrsr-web-service-runs-under"></a>若要更改的 web 应用程序下运行 A4SWIFT_MRSR web 服务的登录帐户  
  
1.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在 IIS 管理器中，展开 ***\<服务器名称\>* （本地计算机）**节点，**应用程序池**节点和**Web站点**节点。 在网站节点下展开**Default Web Site**节点。  
  
3.  在 Default Web Site 节点中，右键单击**A4SWIFT_MRSR**，然后单击**属性**。  
  
4.  在 A4SWIFT_MRSR 属性对话框中，请注意应用程序池。  
  
5.  在 IIS 管理器对话框中的下的应用程序池节点中，右键单击 A4SWIFT_MRSR，应用程序池，然后单击**属性**。  
  
6.  在\<应用程序池名称\>属性对话框中，单击**标识**注意。 如果**预定义**单击和**网络服务**是处于选中状态，单击**可配置**，输入你的本地或域帐户，然后输入你的密码。 单击 **“确定”**。  
  
## <a name="a-message-created-in-mrsr-site-on-a-localized-computer-is-not-processed"></a>在本地化的计算机上的 MRSR 站点中创建的消息不处理  
  
### <a name="symptom"></a>故障现象  
 当用户使用的本地化的平台运行的 A4SWIFT 英语版本创建中的消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]MRSR 中的窗体和将消息提交成功，将显示该消息将使用的消息修复和新的提交业务流程，但未成功处理。 消息提交到发件箱，但不是由 BizTalk 适配器选取。 没有错误或警告发布在事件查看器中，并且不没有正在运行的业务流程实例 HAT 中的任何记录。  
  
### <a name="possible-cause"></a>可能的原因  
 为 STS 输入的 uri 的路径。发件箱接收位置包含的英语名称，而不是本地化名称。  
  
### <a name="solution"></a>解决方案  
 更改 STS 的 URI 地址。发件箱接收位置，如下所示：  
  
1.  在 BizTalk Server 2009 的管理控制台中，展开**BizTalk 组**，**应用程序**，和**BizTalk 应用程序 1 节点**。  
  
2.  单击**接收位置**。  
  
3.  双击**Sts.Outbox.Location**。  
  
4.  在接收位置属性对话框中，单击**配置**。  
  
5.  在传输属性对话框中中的值替换为**SharePointSite URL**与本地化的等效项。  
  
6.  单击**确定**，然后单击**确定**。  
  
## <a name="removing-a-role-while-it-is-processing-a-message-results-in-incomplete-removal-of-documents-and-artifacts"></a>删除角色时它正在处理的文档和项目中完全删除的消息结果  
  
### <a name="symptom"></a>故障现象  
 当你在配置文件的 Web 客户端中删除角色时，发布对话框中，该值指示将删除所有文档和与角色关联的项目。 但是，从在 A4SWIFT 管理控制台中，部门不删除角色和角色的文档文件夹 （收件箱和发送的项目） 不会从 MRSR 中删除。 删除方、 发送端口和协议与角色关联，并且未部署角色的配置文件。  
  
### <a name="possible-cause"></a>可能的原因  
 一条消息仍然在角色的收件箱中 MRSR，并且消息是在中打开其[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。  
  
### <a name="solution"></a>解决方案  
 将消息从 MRSR 站点收件箱，手动删除然后再删除与已删除的角色相关联的文档库。 关闭表单并再次删除角色。  
  
## <a name="message-processing-fails-as-a-result-of-an-error-in-the-bic-master-policy"></a>由于 BIC Master 策略中的错误的消息处理失败  
  
### <a name="symptom"></a>故障现象  
 当提交邮件以进行处理时，你将收到以下错误：  
  
 "执行 BicMasterPolicy 时发生错误。 检查有效值的策略。"  
  
### <a name="possible-cause"></a>可能的原因  
 SQL Server 名称、 BIC 数据库名称和 BIC_Master_Policy.xml 文件中的集成的安全性值*\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 策略包含用双引号括起来。 若要启用 BIC 验证，则输入这些字符串默认 BIC_Master_Policy.xml 文件中所述[启用验证 Bank 标识符代码的](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)。  
  
### <a name="solution"></a>解决方案  
 若要修复 BIC 主策略，请继续执行，如下所示：  
  
> [!NOTE]
>  有关部署 BIC 主策略的详细信息，请参阅[部署 BRE 规则](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md)。  
  
1.  业务规则编辑器，在取消部署的 BIC_Master_Policy，版本 1.0，然后再删除 BIC_Master_Policy。  
  
2.  在文本编辑器中，（如记事本） 打开中的 BIC_Master_Policy.xml *\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFTMessages\A4SWIFT SRG\<版本\>\Base 策略。 删除 SQL Server 名称两边添加双引号，BIC 数据库名称，并集成安全值。  
  
3.  在业务规则引擎的部署向导中，导入 BIC_Master_Policy.xml，，然后部署 BIC_Master_Policy.xml。  
  
4.  在服务 MMC 中，重新启动规则引擎更新服务和 BizTalk 接收主机服务。  
  
## <a name="a4swift-will-not-be-able-to-process-an-unparsed-message-without-proper-database-permissions"></a>A4SWIFT 将无法处理不正确的数据库权限的情况下一条未分析的消息  
  
### <a name="symptom"></a>故障现象  
 当您删除一条消息，无法分析 A4SWIFT 时，A4SWIFT 将无法处理消息，但失败并且具有未捕获的异常。  
  
### <a name="possible-cause"></a>可能的原因  
 没有数据库权限问题。 A4SWIFT 管理员和 A4SWIFT 用户组中不包括 BizTalk 服务，它们的默认值是 HostSvc 的登录帐户。  
  
### <a name="solution"></a>解决方案  
 将 BizTalk 服务的登录帐户添加到 A4SWIFT 管理员和 A4SWIFT 用户组。  
  
## <a name="a-timeout-of-the-infopath-repair-form-can-result-in-two-copies-of-a-message-in-different-stages-of-the-repair-workflow"></a>InfoPath 修复窗体的超时可能在修复工作流的不同阶段导致一条消息的两个副本  
  
### <a name="symptom"></a>故障现象  
 当你提交的 InfoPath 窗体中的消息 （任何工作流阶段），如果在提交表单中没有错误时，该错误可能导致在消息的两个副本。 一条消息仍在收件箱进行的当前阶段，并在工作流中的下一步角色的收件箱中的其他邮件是。 尝试处理这些消息将导致以下：  
  
-   如果提交来自工作流的下一步角色的收件箱的消息，消息将继续在工作流。  
  
-   如果你提交来自收件箱的消息的当前阶段已完成的处理消息的下一阶段的收件箱从中提交后，从当前的收件箱提交的邮件将被挂起用路由的失败。  
  
-   如果你提交收件箱中的消息的当前阶段完成下一阶段的收件箱从提交的邮件之前处理消息的当前阶段提交从收件箱的收件箱返回适用于该阶段中，和中，你将收到以下错误：  
    "重置由于工作流： 消息已被篡改或对于这一阶段用户无效。"  
    此后，如果下一个阶段，提交来自收件箱的消息的工作流将还重置。 它将为返回的收件箱对于当前阶段，你将收到以上错误。  
  
### <a name="possible-cause"></a>可能的原因  
 InfoPath 表单提交之后发送给 BizTalk Server 通过 Microsoft Windows Sharepoint Services 和会执行验证的自定义 Web 服务的消息。 提交一条消息中多个步骤完成，因为 Windows Sharepoint Services 不是事务性的可能不是事务性的这些步骤。 为了满足此限制，MRSR 业务流程具有内置的恢复逻辑来检测，并从因消息提交的错误中恢复。 MRSR 业务流程始终能够阻止发送到 SWIFT 重复消息。  
  
### <a name="solution"></a>解决方案  
 如果发生这种情况，应选择进一步沿工作流中的消息，并尝试处理处于早期阶段，工作流的其他消息之前完成其工作流。 沿工作流中的消息完成处理之后，您可以根据你的释放的第二个消息 （这与路由失败，已挂起）。  
  
 如果的消息进一步沿工作流中未完成处理处理第二条消息之前，您应再次修复进一步沿修复 InfoPath 窗体中工作流中的消息，然后将其提交。 允许其完成处理，然后提交第二条消息。 第二条消息已被挂起后，释放类型。  
  
## <a name="a-new-submission-with-no-verify-stage-will-result-in-a-suspended-message"></a>没有验证阶段新提交将导致将挂起的消息  
  
### <a name="symptom"></a>故障现象  
 当提交具有不验证阶段的工作流中的新消息时，会挂起消息。  
  
### <a name="possible-cause"></a>可能的原因  
 请验证阶段缺乏会导致将挂起的消息如果 A4SWIFT_MRSRLastStage 未设置为创建。  
  
### <a name="solution"></a>解决方案  
 使用订阅 A4SWIFT_MRSRLastStage = = 创建，以确保正确路由消息。  
  
## <a name="validation-of-message-results-a-parse-error-in-the-infopath-form-task-pane"></a>消息验证结果"分析错误"中的 InfoPath 窗体任务窗格  
  
### <a name="symptom"></a>故障现象  
 验证窗体任务窗格将显示"分析错误"没有任何说明 InfoPath 中的消息按钮。  
  
### <a name="solution"></a>解决方案  
 重新启动 MRSR web 服务或者执行 iisreset。  
  
## <a name="publishing-an-infopath-form-results-an-authorization-error"></a>InfoPath 窗体发布结果授权错误  
  
### <a name="symptom"></a>故障现象  
 InfoPath 窗体发布给出授权错误。  
  
### <a name="solution"></a>解决方案  
 用 MRSR 站点 URL 中的 localhost 替换计算机名称。  
  
## <a name="infopath-form-task-pane-shows-html-source-code"></a>InfoPath 窗体任务窗格中显示的 HTML 源代码  
  
### <a name="symptom"></a>故障现象  
 InfoPath 窗体任务窗格将显示而不是 Web 控件的 HTML 源代码。  
  
### <a name="solution"></a>解决方案  
 转到**工具**-> **安全选项卡** -> **Internet 区域**，并启用**根据内容而打开的文件不能对扩展**在杂项下。  
  
## <a name="profile-web-client-website-results-an-authentication-error"></a>配置文件 Web 客户端网站结果身份验证错误  
  
### <a name="symptom"></a>故障现象  
 配置文件 Web 客户端网站显示身份验证错误。  
  
### <a name="solution"></a>解决方案  
 运行**BTSharePointAdapterWSAppPool**和**DefaultAppPoolApplication** -> 和在 Internet 信息 Services(IIS) 池 administrator 帐户下。  
  
## <a name="see-also"></a>另请参阅  
 [疑难解答：问题和解决方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)