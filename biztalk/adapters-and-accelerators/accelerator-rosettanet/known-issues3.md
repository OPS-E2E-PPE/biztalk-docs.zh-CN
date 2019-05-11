---
title: 使用 BizTalk Server 中的 RosettaNet 加速器的已知问题 |Microsoft Docs
description: 查看已知的问题和解决方法与 0A1 通知，失败、 BAM、 安装和配置，并在 BizTalk Server 中的 BTARN 中的更多
caps.latest.revision: 11
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 335eb3c9-b565-470f-b69c-2a771ef8b476
ms.author: mandia
ms.openlocfilehash: d4f14eff559c3952457b1c5473cd04ece7a39987
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283353"
---
# <a name="known-issues"></a>已知问题
本部分包含可帮助你避免 Microsoft® 的错误的有用信息[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。 已知的问题分为以下几个方面：  
  
-   0A1 失败通知  
  
-   业务活动监视 (BAM)  
  
-   安装和配置  
  
-   杂项  
  
## <a name="0a1-notification-of-failure"></a>0A1 失败通知  
  
### <a name="btarn-does-not-perform-cross-field-validation-for-the-cidx-process-configuration-property-and-the-0a1-agreement-property"></a>BTARN 不对 CIDX 流程配置属性和 0A1 协议属性执行跨字段验证  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不会阻止您后即使 CIDX 不支持 0A1 协议设置为"0A1"，该配置文件使用的协议的"0A1 协议"属性设置为"CIDX"流程配置的配置文件的"标准"属性。  
  
## <a name="business-activity-monitoring"></a>业务活动监视  
  
### <a name="duplicate-column-data-appears-in-the-business-activity-monitoring-reports"></a>业务活动监视报表中出现重复的列数据  
 BAM 活动 Web 报表中的 ActivityID 和 PIPInstanceID 列包含相同的内容。 此数据精确地反映了合作伙伴接口流程 (PIP) 实例标识符。 ActivityID 将这个值用于内部关联。 可以忽略此消息。  
  
### <a name="empty-data-columns-in-the-business-activity-monitoring-web-reports"></a>在业务活动监视 Web 报表中的空的数据列  
 业务活动监视 (BAM) Web 报表不包含任何有关 0A1 消息流程的数据。 Web 报表中的 0A1 消息列是用"Initiated 0A1"硬编码。  
  
## <a name="installation-and-configuration"></a>安装和配置  
  
### <a name="groups-and-users-in-either-the-biztalk-application-users-group-and-the-biztalk-server-administrators-group-must-be-in-the-same-domain"></a>组和 BizTalk Application Users 组和 BizTalk Server Administrators 组中的用户必须位于同一域中  
 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 支持将组添加到 BizTalk Application Users 组或 BizTalk Server Administrators 组。 但是，单个用户帐户和属于 BizTalk Application Users 组或 BizTalk Server Administrators 组的组必须是同一个域的一部分。  
  
### <a name="uninstallation-of-btarn-fails-if-biztalk-server-is-removed-first"></a>如果先删除 BizTalk Server 的 BTARN 的卸载将失败  
 如果在删除之前删除 BizTalk Server [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，则[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]删除过程将失败且未出错。 若要解决此问题，重新安装和重新配置 BizTalk Server，然后删除[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。  
  
### <a name="distributed-deployment-requires-a-domain-controller"></a>分布式的部署需要域控制器  
 部署[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]多服务器环境中时，需要一个域控制器，例如，你已安装[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]一台服务器上和[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]可使用另一台服务器上配置的数据库。  
  
### <a name="custom-pip-configurations-are-not-supported"></a>不支持自定义 PIP 配置  
 当前版本的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不支持使用自定义元素或其他非 RosettaNet 标准信息配置 Pip。  
  
### <a name="btarn-automatically-starts-the-single-sign-on-service"></a>BTARN 自动启动单一登录服务  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 在事件中自动启动单一登录 (SSO) 时[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]要求它和 SSO 服务未运行。  
  
### <a name="the-configuration-program-will-not-remove-btarn-virtual-directories-from-the-excluded-paths-list-when-webapps-is-not-configured-for-the-default-web-site"></a>配置程序不会删除 BTARN 虚拟目录从排除的路径列表时没有为默认网站上配置 web 应用  
 如果取消配置[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]安装 Web 应用程序虚拟文件夹已配置为 SharePoint Server，没有默认 Web 站点之后，将的必须手动删除 btarnapp 和 btarnhttpreceive 虚拟从 SharePoint 管理中心网站中的排除路径列表的目录。 发生这种情况是因为在配置 Web 应用程序虚拟文件夹，为 SharePoint Server 时，您必须将 btarnapp 和 btarnhttpreceive 手动添加到排除路径列表。 配置程序将不能自动从排除路径列表中删除它们。  
  
## <a name="miscellaneous"></a>杂项  
  
### <a name="btarn-will-receive-messages-encrypted-in-either-encryption-algorithm"></a>BTARN 将接收中任一加密算法加密的消息  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]接收管道接收并解密消息，即使不匹配的协议，用于加密消息和此字段中的编码设置。 因此， [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RC2-40 或 3DES 中接收消息进行加密。  
  
### <a name="btarn-requires-a-signal-in-a-single-action-synchronous-scenario"></a>BTARN 需要信号在单一操作同步方案  
 在单一操作同步方案中，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]总是期望并生成信号。 此行为与 RosettaNet 规范的信号可能或可能不需要在单一操作同步方案中不同。 如果[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]作为响应方，它总是生成信号来响应消息从发起方。 如果[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]为发起方，它总是期望收到从响应方返回的信号。 如果[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不会收到信号，它在指定时间间隔后超时`Time To Perform`属性在流程配置设置，并生成 0A1 消息。  
  
### <a name="btarn-supports-utf-16-in-received-messages"></a>BTARN 支持接收的消息中的 utf-16  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 接收并处理字符集为 utf-16 的消息。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将使用 utf-8 字符集的消息发送。  
  
### <a name="namespaces-must-be-stripped-from-response-messages-mapped-from-request-messages"></a>从请求消息映射的响应消息中必须去掉命名空间  
 如果在双操作方案的专用流程中使用 BizTalk 映射器，BizTalk 映射器将命名空间添加到响应消息实例从请求消息映射中的一些元素标记。 这些命名空间会导致在发送管道中失败。 必须删除这些命名空间。 使用 HeaderHelper 示例执行此操作。 有关详细信息，请参阅[双操作 PIPAutomation 业务流程&#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)并[步骤 4:创建 HeaderHelper 项目&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md)。  
  
### <a name="changing-uri-settings-requires-iisreset"></a>更改 URI 设置需要 IISRESET  
 在运行安装程序时，设置接收和发送.aspx 页使用的 URI 设置和 URI 设置的接收和发送适配器。 如果您更改的计算机上安装了.aspx 页或适配器的名称，必须更改这些设置。 您可以通过重新运行配置过程中，更改这些设置，但这需要重置所有配置设置。 您可以通过更改相关的注册表项来更改 URI 设置 (`AsyncReceivePortURI`， `RNIFSenderURI`，和`SyncReceivePortURI`)。 更改这些注册表设置的任何一个之后, 必须运行 IISRESET 以使更改，才会生效。 这是因为[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]缓存供其使用的设置。 运行 IISRESET 后，您还必须重新启动 BizTalk 服务。  
  
### <a name="btarn-does-not-enforce-restrictions-on-rnif-v11-enumerations"></a>BTARN 不会强制对 RNIF v1.1 枚举的限制  
 RosettaNet 实现框架 (RNIF) 规范 v1.1 指定了对一些 RNIF 架构枚举的限制。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不强制实施这些限制，并不会验证针对这些限制。 限制并不适用于 RNIF v2.01。  
  
 这适用于下列服务头元素：  
  
-   `GlobalBusinessActionCode`  
  
-   `GlobalPartnerClassificationCode`  
  
-   `GlobalBusinessServiceCode`  
  
-   `GlobalProcessCode`  
  
-   `GlobalProcessIndicatorCode`  
  
-   `VersionIdentifier`  
  
### <a name="performancecontrolrequest-parameters-will-not-override-default-process-configuration-settings"></a>PerformanceControlRequest 参数不会覆盖默认流程配置设置  
 传入消息可以包含`PerformanceControlRequest`服务头中的参数。 这些参数包括确认 （接收） 和执行，时间的时间延迟参数的值中的过程配置设置中设置[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不会动态设置基于时间延迟`PerformanceControlRequest`传入消息中的参数。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 始终采用流程配置设置中设置的默认 PIP 值中的时间延迟。 这符合 RosettaNet 实现框架 (RNIF) 规范 v1.1。  
  
### <a name="the-pip-name-and-pip-version-of-double-action-messages-are-case-sensitive"></a>PIP 名称和双操作消息 PIP 版本是区分大小写  
 如果 PIP 名称和响应消息的 PIP 版本具有不同的情况下的相应值比原始双操作请求的消息，发起方[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]拒绝为无效的响应消息，并向响应方返回一个异常。  
  
### <a name="btarn-does-not-support-changing-agreement-settings-while-there-are-active-processes"></a>尽管有活动进程，BTARN 不支持更改协议设置  
 当您单击将应用对协议属性的更改**Apply**或**确定**以接受这些条款。 更改协议后，已运行的进程中的任何新活动或涉及该协议的任何新进程将使用已更改的协议属性。 如果出现运行时更改协议的进程，它可能已使用以前的协议属性的消息。 该过程的新消息将使用新的协议设置，这会产生不可预知的结果。 建议您更改协议设置时没有运行的过程。  
  
### <a name="btarn-will-not-perform-cross-field-validation-after-changes-to-a-process-configuration-profile"></a>BTARN 不会执行跨字段验证后对流程配置配置文件的更改  
 当您创建流程配置配置文件，然后创建一个协议，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]执行跨字段验证，以确保协议和配置文件的属性兼容。 例如，它检查，对于具有标准属性将设置为"CIDX"的配置文件，该协议的 0A1 协议属性设置为"非 0A1"。 但是，如果在创建协议后, 更改流程配置配置文件[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不会执行跨字段验证。 如果更改为"CIDX"的标准属性从"RosettaNet"[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不会验证该协议的 0A1 协议属性设置为"非 0A1"。  
  
### <a name="errors-will-result-if-all-orchestrations-are-not-started"></a>如果未启动所有业务流程将导致错误  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装 9 个业务流程。 有关[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]成功处理消息，必须将绑定、 登记和启动处理之前启动这些业务流程的所有九个。 有关详细信息，请参阅 BizTalk Server 帮助中的"业务流程管理中 BizTalk 资源管理器"管理业务流程"主题。  
  
### <a name="rnifreceiveaspx-does-not-remove-the-mime-bottom-boundary-from-a-message"></a>RNIFReceive.aspx 不删除从一条消息的 MIME 下边界  
 当 RNIFReceive.aspx 页收到消息时从合作伙伴的 RNIFSend.aspx 页时，该消息包含 MIME 头和 MIME 上下边界，用 base64 数字。 RNIFSend.aspx 将头和边界添加到以便进行 RNIF 传输消息。 RNIFReceive.aspx 之前应删除 MIME 头和边界从消息将消息提交到公用流程。 RNIFReceive.aspx 删除 MIME 头和上边界，但它不会删除下边界。 下边界存在不会影响公用流程中消息的处理。  
  
### <a name="btarn-does-not-support-a-case-sensitive-configuration-of-sql-server-databases"></a>BTARN 不支持区分大小写的 SQL Server 数据库配置  
 如果你提出[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库和数据库对象区分大小写，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台中找不到数据库资源，则引发异常。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库和数据库对象必须是不区分大小写。  
  
### <a name="all-queries-in-database-maintenance-scripts-should-be-written-for-utc-time"></a>应为 UTC 时间编写数据库维护脚本中的所有查询  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库使用 UTC （协调通用时间） 时间，以便为维护这些数据库之一而创建的任何查询，必须编写为 UTC 时间。 例如，如果您的维护脚本使用`GetDate()`命令时，您应将其更改为`GetUTCDate()`。  
  
### <a name="a-publicresponder-orchestration-will-reject-a-duplicate-request-action-message"></a>PublicResponder 业务流程将拒绝重复的请求操作消息  
 当`PublicResponder`业务流程 (PublicResponderV11.odx) 收到重复的请求操作消息，它将事件日志中记录一条警告，然后拒绝该消息。 如果响应方业务流程完成后收到重复的消息，则 BizTalk Server 将终止该消息，因为没有任何订阅。  
  
### <a name="transmission-errors-will-not-be-shown-in-bam-if-the-public-process-has-stopped"></a>传输错误将不会显示在 BAM 如果公用流程已停止  
 如果公用流程处理其最后一条消息时出现传输错误，事件日志和 HAT 显示错误，但 BAM 不。 BAM 不能显示该消息，因为该业务流程已停止。  
  
### <a name="the-pipelineexe-tool-cannot-be-used-to-debug-a-btarn-receive-pipeline"></a>Pipeline.exe 工具不能用于调试 BTARN 接收管道  
 如果你想要调试接收管道，您必须创建承载该管道的端口。 无法使用 BizTalk Server 提供的 pipeline.exe 工具调试。  
  
### <a name="an-error-may-be-generated-for-a-retried-message-that-is-successfully-processed-after-the-orchestration-finishes"></a>在业务流程完成后成功处理的重试消息可能会产生错误  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用业务流程来表示流程。 在某些情况下，在其中重试几次重试的消息，业务流程可能会重试的消息到达 BizTalk MessageBox 之前已成功完成。 在这种情况，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]生成相应"已完成但被删除"的错误消息。 您应查看你的业务 (LOB) 应用程序，以确定是否已完成该过程。 如果 LOB 应用程序指示成功完成，则可以忽略"已完成，但已放弃"消息。  
  
### <a name="an-xml-file-exported-from-trackingxls-may-have-incorrect-fields"></a>从 tracking.xls 导出的 XML 文件可能包含错误的字段  
 当您在跟踪 XLS 文件中定义新的跟踪视图并从该跟踪 XLS 文件导出 XML 文件时，某些字段名称将略有修改。 若要更正此问题，验证是否将自定义跟踪中的字段的 XML 文件的标准 tracking.xml 字段进行安装[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序。  
  
### <a name="rnif-11-service-header-schema-for-signals-and-responses-may-need-modification"></a>信号和响应的 RNIF 1.1 服务头架构可能需要修改  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 在初始状态下提供所有 RosettaNet 头架构。 某些实现中使用以不同的方式比其他，信号控制和操作控制节点，如下所述。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 在初始状态下提供如下所示的信号控制元素。 请注意，相同可能操作控件元素，则返回 true。  
  
```  
<!ELEMENT SignalControl (  
          InstanceIdentifier,  
          PartnerRoute,  
          SignalIdentity,  
          inResponseTo)>  
```  
  
 如果你的解决方案需要此序列，然后你不必执行任何操作。  
  
 其他一些实现，但是，使用以下代码：  
  
```  
<!ELEMENT SignalControl (  
          inResponseTo,  
          InstanceIdentifier,  
          PartnerRoute,  
          SignalIdentity)>  
```  
  
 如果你的解决方案需要此序列，请参阅 KB 889523。 此软件更新将更改相应的 XML 架构。 请注意，此更新仅影响 RNIF 1.1 流程。  
  
### <a name="pipautomationgetaction-sql-stored-procedure-needs-update"></a>PipAutomationGetAction SQL 存储过程需要更新  
 你需要更新 PipAutomationGetAction SQL 存储过程才能锁定单个记录。 删除以下行：  
  
```  
IF @@ERROR <> 0  
    UPDATE MessagesToLOB SET Delivered = -1 WHERE MessageID = @tempGUID  
```  
  
 正确的 PipAutomationGetAction 存储过程是按如下所示：  
  
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
  
### <a name="you-can-customize-aspx-code-to-return-the-error-description"></a>你可以自定义 aspx 代码，以返回的错误说明  
 如果需要记录或发送错误说明，可以自定义 aspx 代码，具有在响应中返回的实际文本。 若要执行此操作，请使用 （这是内部 asp 请求的响应对象） 的 HttpResponse.Status 或 HttpWebResponse.StatusDescription (返回由[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]HttpWebRequest 对象的 GetResponse 方法调用)。 若要从一个适用的响应对象中返回的返回值，请设置 Response.Status 值类似于附带的 aspx 代码中设置 Response.StatusCode [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。  
  
### <a name="rnif-11-messages-cannot-be-read-in-plain-text-from-non-repudiation-tables-if-the-encoding-method-is-set-to-base64"></a>如果编码方法设置为 Base64，不能在纯文本形式从不可否认性表中读取 RNIF 1.1 消息  
 只有编码方法设置为 Base64 时，才会出现此问题。 如果编码方法设置为 quoted printable 或 8 位，可以明文形式从不可否认性表中读取消息。 您需要使用 *.eml 扩展名保存消息文件，然后打开使用 Outlook Express 中读取消息和 Outlook Express 将为您解码的消息。 下面的代码也可能用于从不可否认性表中读取 Base64 编码的消息。  
  
```  
byte[] textBytes = Convert.FromBase64String(txtEncodedText.Text);  
string plainText = Encoding.UTF8.GetString(textBytes);  
txtOutput.Text = plainText;  
```  
  
## <a name="see-also"></a>请参阅  
[疑难解答和已知问题](troubleshooting-and-known-issues-in-rosettanet.md)