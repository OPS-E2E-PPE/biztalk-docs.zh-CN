---
title: EDI 验证、 架构和消息的已知问题 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 417c3e18-9a97-4d59-bc2b-e96a8c33d388
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a508834ff81814b17bc12f1d698984d65748092
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264557"
---
# <a name="known-issues-with-edi-validation-schemas-and-messages"></a>EDI 验证、架构和消息的已知问题
本主题介绍已知的验证问题。  
  
## <a name="message-is-suspended-with-edi-validation-turned-off"></a>在 EDI 验证关闭的情况下消息被挂起  
 **症状**  
  
 违反了配对规则，因而关闭了验证，但消息被挂起（本应将消息序列化）。  
  
 **可能的原因**  
  
 不执行跨-字段/段验证，即使**EDI 类型**中取消选择属性**验证和确认生成设置**节点**EDI 属性**对话框。 之所以会进行验证，是因为在架构批注中打开了验证。  
  
 **解决方法**  
  
 在架构批注中关闭验证。  
  
## <a name="the-biztalk-service-needs-to-be-restarted-after-a-schema-has-been-edited-and-redeployed"></a>编辑并重新部署架构之后 BizTalk 服务需要重新启动  
 **症状**  
  
 在编辑并重新部署架构之后 BizTalk Server 未成功处理一个有效的消息。  
  
 **可能的原因**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 缓存架构无超时限制。  
  
 **解决方法**  
  
 在编辑并重新部署架构之后，重新启动 BizTalk Server 应用程序服务。 您还必须重新启动承载正在使用所重新部署架构的管道的主机实例。  
  
## <a name="processing-has-been-aborted-for-messages-of-a-single-encoding-type-for-a-single-party"></a>对某一参与方某个编码类型的消息的处理已中止。  
 **症状**  
  
 对某一参与方某个编码类型（如 X12 或 EDIFACT）的所有消息的处理都已中止。 对同一参与方另一编码类型的消息或另一参与方的任何消息的处理均未受影响。  
  
 **可能的原因**  
  
 交换、组或事务集控制编号的长度已超出允许的最大长度。  
  
 对于 X12 消息，控制编号的最大长度为九位。 对于 EDIFACT 消息，控制编号的最大长度为三个字段 14 位。  
  
 **解决方法**  
  
 对于受影响的参与方，重置“EDI 属性”对话框相应属性页中的控制编号。 可以编辑以下属性页中的控制编号：  
  
-   X12 交换控制编号： ISA 段定义 X12 （作为交换收件人节点方） 中的页属性  
  
-   X12 组或事务集控制编号： GS 和 ST 段定义的页 (对于 X12 为交换的接收方节点方中属性)  
  
-   EDIFACT 交换控制编号： UNB 段定义页 （在作为 EDIFACT 属性交换收件人节点方）  
  
-   EDIFACT 组或事务集控制编号： UNG 和新罕布什尔大学段定义页上 （在作为 EDIFACT 属性交换接收方节点方）  
  
## <a name="biztalk-server-validates-with-schemas-that-have-unh-segments-with-seven-data-elements"></a>BizTalk Server 用具有包含七个数据元素的 UNH 段的架构进行验证  
 在早期版本的 EDIFACT 中，UNH 段具有四个元素，而不是像更高版本的 UNH 段那样具有七个元素（其中三个是可选元素）。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用更高版本（具有七个元素用于验证）。  
  
## <a name="error-messages-generated-for-multiple-cross-field-validation-rules-will-not-be-specific-to-the-rule"></a>为多个跨字段验证规则生成的错误消息将不是特定于规则的  
 如果架构包含针对消息中某一数据元素的多个跨字段验证规则，并且该数据元素出现了错误，则会为每个验证规则生成一个单独的错误。 但是，其中每个错误的错误代码和说明均相同；错误将不是特定于验证规则的。  
  
## <a name="if-edi-type-validation-is-disabled-on-receive-and-enabled-on-send-the-send-pipeline-will-not-be-able-to-serialize-the-message"></a>如果在接收时禁用 EDI 类型验证，在发送时启用该验证，则发送管道将无法对消息进行序列化  
 如果在接收端关闭 EDI 类型验证，则 EDI 接收管道将根据接收到的 EDI 消息生成 XML 消息，无论该消息是否有效。 如果在发送端启用 EDI 验证，且 XML 文件包含错误，则 EDI 发送管道将无法将 XML 重新处理成有效的 EDI 文件，因此会产生错误。  
  
## <a name="edi-promoted-properties-are-only-available-if-your-application-has-a-reference-to-the-biztalk-edi-application"></a>仅在应用程序具有对 BizTalk EDI 应用程序的引用的情况下才可使用 EDI 升级属性  
 **症状**  
  
 EDI 命名空间下的升级属性未显示在您正尝试使用的升级属性列表中（如业务流程或发送端口的筛选条件中）。  
  
 **可能的原因**  
  
 您所使用的 BizTalk 应用程序不具有对 BizTalk EDI 应用程序的引用。 EDI 升级属性的属性架构位于 BizTalk EDI 应用程序的“资源”文件夹所包含的 Microsoft.BizTalk.Edi.BaseArtifacts.dll 中。  
  
 **解决方法**  
  
 将对 BizTalk EDI 应用程序的引用添加到您正在处理的 BizTalk 应用程序。  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a>上下文属性名称中的数据元素名包含下划线，而不是句点  
 EDI 段中的数据元素名（例如 UNB2.1，它是 UNB2 发送方段的标识字段）包含句点。 不过，如果数据元素名是 EDI 上下文属性的组成部分，则会用下划线代替句点。 例如，发送方标识数据元素的上下文属性是 EDI.UNB2_1 而非 EDI.UNB2.1。 这是因为上下文属性名称中不支持使用句点。  
  
## <a name="irrelevant-string-is-appended-to-instance-validation-error-message"></a>不相关的字符串附加到了实例验证错误消息中  
 在实例验证期间无论何时收到错误，字符串“BEC 2004”均会附加到错误消息中。 可以忽略此字符串。  
  
## <a name="edifact-schema-names-are-case-sensitive"></a>EDIFACT 架构名区分大小写  
 EDIFACT 架构的架构名（显示在架构的 root_reference 数据元素中）区分大小写。 例如，EFACT_D98B_ORDERS 与 EFACT_d98B_Orders 将是两个不同的架构。  
  
## <a name="invalid-edi-messages-can-be-suspended-even-if-edi-type-validation-is-disabled"></a>即使 EDI 类型验证已禁用，无效的 EDI 消息仍可能被挂起  
 即使禁用 EDI 类型验证，则不执行 EDI 结构验证。 即使 EDI 类型验证已禁用，未通过基本结构验证的交换也会被挂起。  
  
## <a name="the-edi-assembler-will-serialize-an-unbatched-interchange-even-if-a-separator-character-is-used-in-an-envelope-header"></a>即使在信封头中使用了分隔符，EDI 组装器仍会对未批处理的交换进行序列化  
 按照针对“作为交换接收方的参与方”的规定，切勿在交换、组或事务集的任何头字段或尾字段的定义中使用用于分隔头字段和尾字段的分隔符。 如果使用了这样的分隔符，则在作为发送方的 BizTalk Server 的 EDI 组装器中或在接收方的拆装器中将无法处理交换。 如果交换为出站批，它在 EDI 组装器中将失败，因为组装器会根据头控制（服务）架构验证信封。 如果交换未进行批处理，EDI 组装器会将其序列化，但交换在接收方的拆装器中将无法处理。  
  
## <a name="mismatched-character-sets-can-result-in-suspended-interchanges"></a>字符集不匹配可能会导致交换被挂起  
 用于传出交换的字符集应与用于创建插入交换中的事务集的字符集相同。 如果不相同，则交换很有可能被挂起，同时出现一条指示存在无效字符的错误消息。  
  
 例如，如果使用 UNOA 字符集创建一个 EDIFACT 批，但添加到该批中的事务集包含小写字符，则批处理业务流程会将消息挂起，因为 UNOA 不允许出现小写字符。  
  
 再如，如果使用“基本”字符集配置用于 X12 交换的 EDI 发送管道，但 X12 批处理交换具有小写字符（因为在“作为交换接收方的参与方”的“X12 交换信封生成”页中选择的 X12 字符集设置为“扩展”或“UTF8/Unicode”），那么，在应用信封设置时批处理消息将被挂起。  
  
## <a name="using-unh25-for-schema-resolution-requires-an-update-to-the-schema"></a>将 UNH2.5 用于架构解析时需要更新架构  
 如果将 UNH2.5（协会分配的代码）用于传入 EDIFACT 交换的架构解析，则需要更新 \Program Files\Microsoft BizTalk Server 20xx\Schema 文件夹中的相关文档架构。 还需要将 UNH2.5 的值附加到 root_reference、display_reference 和 xs:element name 的现有值。 例如，如果 UNH2.5 为“EAN008”且您使用的是 EFACT_D96A_INVOIC 架构，则应将 root_reference、display_reference 和 xs:element name 设置为“EFACT_D96A_INVOIC_EAN008”。  
  
## <a name="the-compressed-file-of-schemas-will-be-replaced-when-an-upgrade-is-performed"></a>进行升级时架构的压缩文件将被替换  
 如果将 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 升级到更高版本，则与升级关联的 MicrosoftEdiXSDTemplates.exe 文件将替换安装中的 MicrosoftEdiXSDTemplates.exe 文件。 如果你计划继续使用旧压缩文件的架构，那么除非你备份了旧压缩文件，否则升级之后你将不能再访问此压缩文件。  
  
## <a name="if-a-group-contains-multiple-x12-transaction-sets-all-must-be-of-the-same-type"></a>如果一个组中包含多个 X 12 事务集，则所有的事务集必须属于同一类型  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持在相同的组中混合不同的事务集。 当一个组中包含多个事务时，所有事务的 ST01 值必须相同。  
  
## <a name="receiving-x12-interchanges-that-contain-non-ascii-delimiters-may-result-in-the-message-becoming-suspended"></a>接收包含非 ASCII 分隔符的 x12 交换可能会导致挂起消息  
 **症状**  
  
 接收使用非 ASCII 分隔符的 X12 交换时，可能会挂起消息，并且会在应用程序事件日志中写入错误。  
  
 **可能的原因**  
  
 如果交换没有编码为 utf-8，则会发生此问题。  
  
 **解决方法**  
  
 请确保包含非 ASCII 分隔符的任何传入 X12 交换编码为 UTF-8。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md)   
 [EDI 消息传递](../core/edi-messaging.md)   
 [EDI 消息验证](../core/edi-message-validation.md)   
 [EDI 架构](../core/edi-schemas.md)   
 [开发 EDI 架构](../core/developing-edi-schemas.md)