---
title: "与 BizTalk Server 中的 RosettaNet 快捷键的已知问题 |Microsoft 文档"
description: "请参阅已知的问题和解决方法与 0A1 通知，失败、 BAM、 安装和配置，并更在 BizTalk Server 中的 BTARN"
caps.latest.revision: "11"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 335eb3c9-b565-470f-b69c-2a771ef8b476
ms.author: mandia
ms.openlocfilehash: 59c6aabd6adf584bb27f5487ca31f852a0d11384
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues"></a>已知问题
本节介绍的有用信息有助于在使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 时避免错误。 已知问题归为以下几个方面：  
  
-   0A1 失败通知  
  
-   业务活动监视 (BAM)  
  
-   安装和配置  
  
-   杂项  
  
## <a name="0a1-notification-of-failure"></a>0A1 失败通知  
  
### <a name="btarn-does-not-perform-cross-field-validation-for-the-cidx-process-configuration-property-and-the-0a1-agreement-property"></a>BTARN 不对 CIDX 流程配置属性和 0A1 协议属性执行跨字段验证  
 在将使用某一流程配置配置文件的协议的“0A1 协议”属性设为“0A1”之后，即使 CIDX 不支持 0A1 协议，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 也不会禁止你将该配置文件的“标准”属性设为“CIDX”。  
  
## <a name="business-activity-monitoring"></a>业务活动监视  
  
### <a name="duplicate-column-data-appears-in-the-business-activity-monitoring-reports"></a>业务活动监视报表中出现重复的列数据  
 BAM 活动 Web 报表中的 ActivityID 和 PIPInstanceID 列包含相同的内容。 此数据精确地反映了合作伙伴接口流程 (PIP) 实例标识符。 ActivityID 将这个值用于内部关联。 可以忽略此消息。  
  
### <a name="empty-data-columns-in-the-business-activity-monitoring-web-reports"></a>业务活动监视 Web 报表中出现空的数据列  
 业务活动监视 (BAM) Web 报表不包含任何有关 0A1 消息流程的数据。 Web 报表中的 0A1 消息列是用“Initiated 0A1”硬编码而成的。  
  
## <a name="installation-and-configuration"></a>安装和配置  
  
### <a name="groups-and-users-in-either-the-biztalk-application-users-group-and-the-biztalk-server-administrators-group-must-be-in-the-same-domain"></a>BizTalk Application Users 组和 BizTalk Server Administrators 组中的组和用户必须在同一个域中  
 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 支持向 BizTalk Application Users 组或 BizTalk Server Administrators 组中添加组。 但是，属于 BizTalk Application Users 组或 BizTalk Server Administrators 组的各个用户帐户和组必须在同一个域中。  
  
### <a name="uninstallation-of-btarn-fails-if-biztalk-server-is-removed-first"></a>如果先删除 BizTalk Server，BTARN 的卸载将失败  
 如果先删除 [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]，然后再删除 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，则 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 的删除过程将失败，而且不报错。 若要解决此问题，请重新安装 [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]，并对其进行配置，然后再删除 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。  
  
### <a name="distributed-deployment-requires-a-domain-controller"></a>分布式部署需要域控制器  
 在多服务器环境中部署 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 需要域控制器，例如，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 安装在一台服务器上，而用于配置的 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库安装在另一台服务器上。  
  
### <a name="custom-pip-configurations-are-not-supported"></a>不支持自定义 PIP 配置  
 当前版本的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不支持使用自定义元素或其他非 RosettaNet 标准信息配置 PIP。  
  
### <a name="btarn-automatically-starts-the-single-sign-on-service"></a>BTARN 自动启动单一登录服务  
 当 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 要求单一登录 (SSO) 而 SSO 服务未运行时，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 会在事件中自动启动 SSO。  
  
### <a name="the-configuration-program-will-not-remove-btarn-virtual-directories-from-the-excluded-paths-list-when-webapps-is-not-configured-for-the-default-web-site"></a>如果没有为默认网站配置 WebApps，则配置程序将不会删除排除路径列表中的 BTARN 虚拟目录。  
 如果某个 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 安装中的 Web 应用程序虚拟文件夹配置为 SharePoint Server 而不是默认网站，则在取消配置该安装后，将必须从 SharePoint 中心管理站点的“排除路径”列表中手动删除 btarnapp 和 btarnhttpreceive 虚拟目录。 这是因为当将 Web 应用程序虚拟文件夹配置为 SharePoint Server 时，必须将 btarnapp 和 btarnhttpreceive 手动添加到“排除路径”列表中。 配置程序将无法自动从“排除路径”列表中删除它们。  
  
## <a name="miscellaneous"></a>杂项  
  
### <a name="btarn-will-receive-messages-encrypted-in-either-encryption-algorithm"></a>BTARN 将接收用下列任一种加密算法加密的消息  
 即使加密消息所用的协议与此字段中的编码设置不匹配，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 接收管道也将接收并解密消息。 因此，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]接收 RC2 40 或 3DES 进行加密的消息。  
  
### <a name="btarn-requires-a-signal-in-a-single-action-synchronous-scenario"></a>在单一操作同步方案中 BTARN 需要信号  
 在单一操作同步方案中，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]始终需要和生成信号。 此行为与 RosettaNet 规范允许的行为（在单一操作同步方案中信号可有可无）有所不同。 如果 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 为响应方，它总是生成信号来响应来自发起方的消息。 如果[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]为发起方，它始终要求和响应方的信号。 如果 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 未收到信号，它将在流程配置设置中的 `Time To Perform` 属性所指定的时间间隔后超时，并生成 0A1 消息。  
  
### <a name="btarn-supports-utf-16-in-received-messages"></a>BTARN 支持接收的消息中使用 UTF-16  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]接收并处理具有 utf-16 字符集的消息。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将使用 utf-8 的字符集的消息发送。  
  
### <a name="namespaces-must-be-stripped-from-response-messages-mapped-from-request-messages"></a>从请求消息映射的响应消息中必须去掉命名空间  
 如果在双操作方案的专用流程中使用 BizTalk 映射器，则 BizTalk 映射器将向从请求消息映射的响应消息实例中的一些元素标记添加命名空间。 这些命名空间会导致在发送管道中发生故障。 必须删除这些命名空间。 使用 HeaderHelper 示例可实现这一目的。 有关详细信息，请参阅[Double 操作 PIPAutomation 业务流程和 #91;RN3 & #93;](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)和[步骤 4： 创建 HeaderHelper 项目 & #91;RN3 & #93;](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md).  
  
### <a name="changing-uri-settings-requires-iisreset"></a>更改 URI 设置需要 IISRESET  
 运行安装程序时，需要设置接收和发送 .aspx 页使用的 URI 设置以及接收和发送适配器使用的 URI 设置。 如果你更改了安装了 .aspx 页或适配器的计算机的名称，则必须更改这些设置。 可以通过重新运行配置进程更改这些设置，但这需要重置所有配置设置。 可通过更改相关的注册表项（`AsyncReceivePortURI`、`RNIFSenderURI` 和 `SyncReceivePortURI`）来更改 URI 设置。 更改这些注册表设置中的任一项后，必须运行 IISRESET 才能使更改生效。 这是因为 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 仅缓存这些设置供自己使用。 运行 IISRESET 后，还必须重新启动 BizTalk 服务。  
  
### <a name="btarn-does-not-enforce-restrictions-on-rnif-v11-enumerations"></a>BTARN 不对 RNIF v1.1 枚举进行限制  
 RosettaNet 实现框架 (RNIF) 规范 v1.1 对某些 RNIF 架构枚举指定限制。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不会强制这些限制，并不会验证针对这些限制。 这些限制不适用于 RNIF v2.01。  
  
 这适用于下列服务头元素：  
  
-   `GlobalBusinessActionCode`  
  
-   `GlobalPartnerClassificationCode`  
  
-   `GlobalBusinessServiceCode`  
  
-   `GlobalProcessCode`  
  
-   `GlobalProcessIndicatorCode`  
  
-   `VersionIdentifier`  
  
### <a name="performancecontrolrequest-parameters-will-not-override-default-process-configuration-settings"></a>PerformanceControlRequest 参数不覆盖默认的流程配置设置  
 传入消息可以在服务头中包含 `PerformanceControlRequest` 参数。 这些参数包括到确认 （接收） 的时间和执行，时间的时间延迟参数值中所做的过程配置设置中设置[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不会动态设置基于时间延迟`PerformanceControlRequest`传入消息中的参数。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]始终会花时间从过程配置设置中设置的默认 PIP 值的时间延迟问题。 这符合 RosettaNet 实现框架 (RNIF) 规范 v1.1。  
  
### <a name="the-pip-name-and-pip-version-of-double-action-messages-are-case-sensitive"></a>双操作消息的 PIP 名称和 PIP 版本区分大小写  
 如果响应消息的 PIP 名称和 PIP 版本与原始双操作请求消息的相应值具有不同的大小写，则发起方 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 会将该响应消息视为无效消息加以拒绝，并向响应方返回一个异常。  
  
### <a name="btarn-does-not-support-changing-agreement-settings-while-there-are-active-processes"></a>BTARN 不支持在流程处于活动状态时更改协议设置  
 将应用到协议属性的更改，只要你单击**应用**或**确定**以接受这些条款。 更改协议后，已在运行的流程以及涉及该协议的任何新流程中的任何新活动都将使用更改的协议属性。 如果更改协议时有正在运行的流程，则该流程可能已经为消息使用了以前的协议属性。 该流程的新消息将使用新的协议设置，这会产生不可预测的结果。 建议你在所有流程都处于关闭状态时更改协议设置。  
  
### <a name="btarn-will-not-perform-cross-field-validation-after-changes-to-a-process-configuration-profile"></a>在对流程配置的配置文件进行更改后，BTARN 不执行跨字段验证  
 创建流程配置的配置文件并接着创建协议时，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将执行跨字段验证，以确保协议和配置文件的属性是兼容的。 例如，它会对“标准”属性设为“CIDX”的配置文件进行检查，将协议的 0A1 协议属性设为“非 0A1”。 但是，如果你在创建协议之后更改流程配置的配置文件，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将不执行跨字段验证。 如果你将“标准”属性的值从“RosettaNet”更改为“CIDX”，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将不检验协议的 0A1 协议属性是否设为“非 0A1”。  
  
### <a name="errors-will-result-if-all-orchestrations-are-not-started"></a>如果所有业务流程均未启动，将出现错误  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 安装程序共安装 9 个业务流程。 有关[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]若要成功处理消息，必须将绑定、 登记，并在启动处理之前启动的这些业务流程的所有包含 9 个。 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] 帮助中的“BizTalk 浏览器中的业务流程管理”或“管理业务流程”主题。  
  
### <a name="rnifreceiveaspx-does-not-remove-the-mime-bottom-boundary-from-a-message"></a>RNIFReceive.aspx 不删除消息中的 MIME 下边界  
 RNIFReceive.aspx 页收到来自合作伙伴的 RNIFSend.aspx 页的消息时，该消息包含了 MIME 头以及 MIME 上边界和下边界（用 Base64 数字表示）。 RNIFSend.aspx 将头和边界添加到消息中以便进行 RNIF 传输。 将消息提交到公用流程之前，RNIFReceive.aspx 应将 MIME 头和边界从消息中删除。 RNIFReceive.aspx 删除 MIME 头和上边界，但不删除下边界。 下边界的存在不会影响公用流程中消息的处理。  
  
### <a name="btarn-does-not-support-a-case-sensitive-configuration-of-sql-server-databases"></a>BTARN 不支持 SQL Server 数据库的区分大小写的配置  
 如果你进行[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库和数据库对象区分大小写，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台找不到数据库资源，并引发异常。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库和数据库对象必须是不区分大小写。  
  
### <a name="all-queries-in-database-maintenance-scripts-should-be-written-for-utc-time"></a>数据库维护脚本中的所有查询都应使用 UTC 时间  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库使用 UTC（协调通用时间）时间，所以为维护这些数据库之一而创建的任何查询都必须使用 UTC 时间。 例如，假设你的维护脚本使用的是 `GetDate()` 命令，应将其更改为 `GetUTCDate()`。  
  
### <a name="a-publicresponder-orchestration-will-reject-a-duplicate-request-action-message"></a>PublicResponder 业务流程将拒绝重复的请求操作消息  
 如果 `PublicResponder` 业务流程 (PublicResponderV11.odx) 收到重复的请求操作消息，它将在事件日志中记录一条警告，然后拒绝该消息。 如果在响应方业务流程完成后收到重复的消息，则 BizTalk Server 将终止该消息，因为不存在针对它的订阅。  
  
### <a name="transmission-errors-will-not-be-shown-in-bam-if-the-public-process-has-stopped"></a>如果公用流程被终止，BAM 不显示传输错误  
 如果公用流程业务流程在处理其最终消息时出现传输错误，事件日志和 HAT 将显示该错误，但 BAM 不显示该错误。 BAM 之所以不能显示该消息，是因为业务流程已停止。  
  
### <a name="the-pipelineexe-tool-cannot-be-used-to-debug-a-btarn-receive-pipeline"></a>pipeline.exe 工具不能用于调试 BTARN 接收管道  
 如果要调试接收管道，必须创建承载该管道的端口。 你无法调试使用 pipeline.exe 工具，[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]提供。  
  
### <a name="an-error-may-be-generated-for-a-retried-message-that-is-successfully-processed-after-the-orchestration-finishes"></a>在业务流程完成后，如果重试已经成功处理过的消息，则可能会产生错误  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用业务流程来表示流程。 在重试一些已经重试过的消息时，业务流程可能在重试消息到达 BizTalk MessageBox 之前已成功完成。 如果出现这种行为，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 将生成一个相应的“已完成但被删除”错误消息。 此时应查看业务线 (LOB) 应用程序，确定该流程是否已完成。 如果 LOB 应用程序指出已成功完成，则可以忽略“已完成但被删除”消息。  
  
### <a name="an-xml-file-exported-from-trackingxls-may-have-incorrect-fields"></a>从 tracking.xls 导出的 XML 文件可能包含错误的字段  
 在跟踪 XLS 文件中定义新的跟踪视图并从该跟踪 XLS 文件导出 XML 文件时，某些字段名可能会被稍做改动。 若要更正此操作，请验证你的自定义跟踪中的字段通过针对标准 tracking.xml 字段的 XML 文件安装[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序。  
  
### <a name="rnif-11-service-header-schema-for-signals-and-responses-may-need-modification"></a>信号和响应的 RNIF 1.1 服务头架构可能需要修改  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]现成的附带 RosettaNet 标头的所有架构。 一些实现与其他实现相比，使用“信号控制”和“操作控制”节点的方式不同，请见下述。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 提供以下即时可用的“信号控制”元素。 请注意，“操作控制”元素也是即时可用的。  
  
```  
<!ELEMENT SignalControl (  
          InstanceIdentifier,  
          PartnerRoute,  
          SignalIdentity,  
          inResponseTo)>  
```  
  
 如果你的解决方案需要此序列，则你无需执行任何操作。  
  
 而另一方面，其他一些实现使用以下代码：  
  
```  
<!ELEMENT SignalControl (  
          inResponseTo,  
          InstanceIdentifier,  
          PartnerRoute,  
          SignalIdentity)>  
```  
  
 如果您的解决方案需要此序列，请参阅 KB 889523。 此软件更新程序将更改相应的 XML 架构。 请注意，此更新程序仅影响 RNIF 1.1 流程。  
  
### <a name="pipautomationgetaction-sql-stored-procedure-needs-update"></a>PipAutomationGetAction SQL 存储过程需要更新  
 需要更新 PipAutomationGetAction SQL 存储过程才能锁定各条记录。 请删除以下各行：  
  
```  
IF @@ERROR <> 0  
    UPDATE MessagesToLOB SET Delivered = -1 WHERE MessageID = @tempGUID  
```  
  
 正确的 PipAutomationGetAction 存储过程如下所示：  
  
```  
CREATE PROCEDURE PipAutomationGetAction  
AS  
 SET TRANSACTION ISOLATION LEVEL READ COMMITTED  
BEGIN TRANSACTION  
DECLARE @tempGUID nvarchar(36)  
SELECT TOP 1 @tempGUID = MessageID FROM MessagesToLOB WITH (READPAST,UPDLOCK,ROWLOCK)  
   WHERE Delivered = 0 AND MessageCategory = 10  
  ORDER BY TimeCreated  
  SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion, ServiceContent FROM MessagesToLOB  
   WHERE MessageID = @tempGUID  
For xml auto  
UPDATE MessagesToLOB SET Delivered = 1 WHERE MessageID = @tempGUID  
 COMMIT TRANSACTION  
GO  
```  
  
### <a name="you-can-customize-aspx-code-to-return-the-error-description"></a>可自定义 aspx 代码，以返回错误说明  
 如果需要记录或发送错误说明，可自定义 aspx 代码，在响应中返回实际的文本。 为此，请使用 HttpResponse.Status 或 HttpWebResponse.StatusDescription，前者是内部 asp 请求的响应对象，而后者则是通过对 HttpWebRequest 对象的 GetResponse 方法进行 [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 调用返回的。 要从其中一个适用的响应对象中得到返回值，请设置 Response.Status 值，设置方法类似于在随 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发布的 aspx 代码中设置 Response.StatusCode。  
  
### <a name="rnif-11-messages-cannot-be-read-in-plain-text-from-non-repudiation-tables-if-the-encoding-method-is-set-to-base64"></a>如果编码方法设置为 Base64，则无法以纯文本形式从不可否认性表中读取 RNIF 1.1 消息  
 只有编码方法设置为 Base64 时才会出现这种情况。 如果编码方法设置为“quoted-printable”或“8 bit”，则可以明文形式从不可否认性表中读取消息。 需要以 *.eml 扩展名保存消息文件，然后使用 Outlook Express 打开才能读取消息内容，因为 Outlook Express 可以对消息进行解码。 还可使用以下代码从不可否认性表中读取用 Base64 编码的消息。  
  
```  
byte[] textBytes = Convert.FromBase64String(txtEncodedText.Text);  
string plainText = Encoding.UTF8.GetString(textBytes);  
txtOutput.Text = plainText;  
```  
  
## <a name="see-also"></a>另请参阅  
[疑难解答和已知问题](troubleshooting-and-known-issues-in-rosettanet.md)