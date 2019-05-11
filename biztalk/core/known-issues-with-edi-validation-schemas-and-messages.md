---
title: 使用 EDI 验证、 架构和消息的已知问题 |Microsoft Docs
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
ms.openlocfilehash: 706b165067fbbed058c12ff096c91851594d945a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380750"
---
# <a name="known-issues-with-edi-validation-schemas-and-messages"></a>EDI 验证、 架构和消息的已知的问题
本主题介绍已知的验证问题。  
  
## <a name="message-is-suspended-with-edi-validation-turned-off"></a>在 EDI 验证关闭，则挂起消息  
 **症状**  
  
 违反了配对的规则，并关闭验证，但消息被挂起 （本应将序列化消息）。  
  
 **可能的原因**  
  
 不执行跨字段/段验证，即使**EDI 类型**属性中取消选中**验证和确认生成设置**节点的**EDI 属性**对话框。 因为在架构批注中开启进行验证。  
  
 **解决方法**  
  
 关闭在架构批注中的验证。  
  
## <a name="the-biztalk-service-needs-to-be-restarted-after-a-schema-has-been-edited-and-redeployed"></a>BizTalk 服务需要编辑并重新部署架构之后，必须重新启动  
 **症状**  
  
 编辑并重新部署架构之后，BizTalk Server 未成功处理了有效的消息。  
  
 **可能的原因**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 缓存架构无超时。  
  
 **解决方法**  
  
 编辑并重新部署架构后, 重新启动 BizTalk Server 应用程序服务。 您还必须重新启动承载正在使用所重新部署的架构的管道的主机实例。  
  
## <a name="processing-has-been-aborted-for-messages-of-a-single-encoding-type-for-a-single-party"></a>处理已中止的消息的编码类型的某一参与方  
 **症状**  
  
 一种编码类型的所有消息的处理 （例如，X12 或 EDIFACT） 的某一参与方已被中止。 另一参与方处理的同一参与方，另一个编码类型的消息或任何消息，具有不受影响。  
  
 **可能的原因**  
  
 交换、 组或事务集控制编号的长度超出了最大允许长度。  
  
 对于 X12 消息，一个控件的最大长度数字为九位。 对于 EDIFACT 消息，控制编号的最大长度是三个字段 14 位数字。  
  
 **解决方法**  
  
 重置受影响的参与方 EDI 属性对话框中的相应属性页中的控制编号。 你可以编辑以下属性页中的控制编号：  
  
-   X12 交换控制编号：适用于 X12 的 ISA 段定义页 （位于参与方作为交换接收方节点） 属性  
  
-   X12 组或事务集控制编号：GS 和 ST 段定义页 (位于 X12 的参与方作为交换接收方节点属性)  
  
-   EDIFACT 交换控制编号：UNB 段定义页 （位于参与方作为交换接收方的 EDIFACT 属性的节点）  
  
-   EDIFACT 组或事务集控制编号：UNG 和 UNH 段定义页 （位于参与方作为交换接收方的 EDIFACT 属性的节点）  
  
## <a name="biztalk-server-validates-with-schemas-that-have-unh-segments-with-seven-data-elements"></a>BizTalk Server 使用已具有七个数据元素的 UNH 段的架构验证  
 在早期版本的 EDIFACT 中，UNH 段具有四个元素，而不是七个元素 （其中三个是可选的） 的 UNH 段具有更高版本中。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用更高版本具有七个元素进行验证。  
  
## <a name="error-messages-generated-for-multiple-cross-field-validation-rules-will-not-be-specific-to-the-rule"></a>为多个跨字段验证规则生成的错误消息将不是特定于规则  
 如果架构包含一条消息中的数据元素的多个跨字段验证规则，并出现错误时使用的数据元素，每个验证规则将生成一个单独的错误。 但是，每个这些错误将具有相同的错误代码和说明;这些错误将不是特定于验证规则。  
  
## <a name="if-edi-type-validation-is-disabled-on-receive-and-enabled-on-send-the-send-pipeline-will-not-be-able-to-serialize-the-message"></a>如果在上禁用 EDI 类型验证接收和发送上启用，发送管道将不能序列化的消息  
 如果关闭在接收端 EDI 类型验证，EDI 接收管道将从收到的 EDI 消息，生成一条 XML 消息，指示为有效的消息。 如果在发送端启用 EDI 验证，EDI 发送管道不能如果 XML 文件包含错误，并且因此将生成错误的 XML 重新处理成有效的 EDI 文件。  
  
## <a name="edi-promoted-properties-are-only-available-if-your-application-has-a-reference-to-the-biztalk-edi-application"></a>EDI 升级属性才可用，如果你的应用程序具有对 BizTalk EDI 应用程序的引用  
 **症状**  
  
 EDI 命名空间下的升级的属性不显示在想要使用的升级属性列表中，例如，在业务流程或发送端口的筛选条件中。  
  
 **可能的原因**  
  
 正在使用的 BizTalk 应用程序没有对 BizTalk EDI 应用程序的引用。 EDI 升级属性的属性架构是 BizTalk EDI 应用程序的资源文件夹中包含的 Microsoft.BizTalk.Edi.BaseArtifacts.dll 中。  
  
 **解决方法**  
  
 您正在使用的 BizTalk 应用程序，添加对 BizTalk EDI 应用程序的引用。  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a>上下文属性名称中的数据元素名称包含下划线，而不是句点  
 EDI 段中的数据元素的名称包含句点，例如 UNB2.1，它是 UNB2 发送方段的标识字段。 但是，如果数据元素名是 EDI 上下文属性的一部分，用下划线代替句点。 例如，发送方标识数据元素的上下文属性即为 EDI。UNB2_1，不是 EDI。UNB2.1。 这样做的原因是，一段不支持上下文属性名称中。  
  
## <a name="irrelevant-string-is-appended-to-instance-validation-error-message"></a>不相关的字符串追加到实例验证错误消息  
 每当在实例验证过程中收到错误，字符串"BEC 2004"将追加到的错误消息。 你可以忽略此字符串。  
  
## <a name="edifact-schema-names-are-case-sensitive"></a>EDIFACT 架构名区分大小写  
 EDIFACT 架构，架构名称的架构的 root_reference 数据元素中所示是区分大小写。 例如，EFACT_D98B_ORDERS 与 EFACT_d98B_Orders 将是两个不同的架构。  
  
## <a name="invalid-edi-messages-can-be-suspended-even-if-edi-type-validation-is-disabled"></a>无效的 EDI 消息可以被挂起，即使禁用 EDI 类型验证  
 即使禁用 EDI 类型验证，则会执行 EDI 结构验证。 未通过基本结构验证的交换将挂起，即使禁用 EDI 类型验证。  
  
## <a name="the-edi-assembler-will-serialize-an-unbatched-interchange-even-if-a-separator-character-is-used-in-an-envelope-header"></a>即使在信封头中使用分隔符，EDI 组装器将序列化未批处理的交换  
 用于分隔字段标头和尾部字段的分隔符字符必须不能在定义中的任何交换、 组或事务集标头字段或尾字段，为作为交换接收方的参与方定义的一样。 如果是，将无法发送 BizTalk Server 在 EDI 组装器中或在接收方的拆装器处理交换。 交换将失败，EDI 组装器中是否出站批，因为组装器将验证标头控制 （服务） 架构对信封。 如果交换未进行批处理，EDI 组装器将其序列化，但将无法在接收方的拆装器中的处理。  
  
## <a name="mismatched-character-sets-can-result-in-suspended-interchanges"></a>字符集不匹配可能会导致交换被挂起  
 用于传出交换的字符集应与用于创建插入交换的事务集的字符集相同。 如果没有，则交换很可能会挂起与错误消息，指示存在无效字符。  
  
 例如，如果创建一个 EDIFACT 批使用 UNOA 字符集，但事务集添加到批中包含小写字符，批处理业务流程将挂起该消息，因为 UNOA 不允许小写字符。  
  
 另举一例，如果你配置 EDI 发送管道的 X12 交换具有"基本"字符集，但 X12 批处理交换具有小写字符因为在 X12 中选择 X12 字符集交换信封生成页参与方为交换接收方设置为"扩展"或"UTF8/Unicode"，在应用信封设置时，就将挂起的批处理的消息。  
  
## <a name="using-unh25-for-schema-resolution-requires-an-update-to-the-schema"></a>将 UNH2.5 用于架构解析需要的架构更新  
 如果用于传入 EDIFACT 交换的架构解析将 UNH2.5 （协会分配代码），您需要更新 \Program Files\Microsoft BizTalk Server 20xx\Schema 文件夹中的相关文档架构。 您需要将 UNH2.5 的值附加到 root_reference、 display_reference 和 xs: element name 的现有值。 例如，如果 UNH2.5 为"EAN008"并且正在使用的是 EFACT_D96A_INVOIC 架构，您将设置 root_reference、 display_reference 和 xs: element name 为"EFACT_D96A_INVOIC_EAN008"。  
  
## <a name="the-compressed-file-of-schemas-will-be-replaced-when-an-upgrade-is-performed"></a>执行升级时，将替换架构的压缩的文件  
 如果升级 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到更高版本中，您的安装中的 MicrosoftEdiXSDTemplates.exe 文件将被替换为与升级关联的 MicrosoftEdiXSDTemplates.exe 文件。 如果你打算继续使用旧压缩文件中的架构，将不再可以访问到压缩的文件在升级后除非您备份了旧压缩文件。  
  
## <a name="if-a-group-contains-multiple-x12-transaction-sets-all-must-be-of-the-same-type"></a>如果一个组中包含多个 X12 事务集，则所有必须是相同类型的  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持混合使用同一组中的不同的事务集。 当一组包含多个事务时，ST01 的值必须是相同的所有事务。  
  
## <a name="receiving-x12-interchanges-that-contain-non-ascii-delimiters-may-result-in-the-message-becoming-suspended"></a>接收 X12 包含非 ASCII 分隔符的交换可能会导致挂起消息  
 **症状**  
  
 当接收 X12 交换，则使用非 ASCII 分隔符的值，该消息可能会挂起并写入到应用程序事件日志错误。  
  
 **可能的原因**  
  
 如果交换没有编码为 utf-8，则会出现此问题。  
  
 **解决方法**  
  
 请确保任何传入的 X12 交换包含非 ASCII 分隔符的编码为 utf-8。  
  
## <a name="see-also"></a>请参阅  
 [EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md)   
 [EDI 消息传递](../core/edi-messaging.md)   
 [EDI 消息验证](../core/edi-message-validation.md)   
 [EDI 架构](../core/edi-schemas.md)   
 [开发 EDI 架构](../core/developing-edi-schemas.md)