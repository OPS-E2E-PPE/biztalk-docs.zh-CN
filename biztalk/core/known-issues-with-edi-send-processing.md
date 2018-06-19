---
title: 已知问题的 EDI 发送处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1325dcd9-5dbb-48bb-b5a3-1502d1424d4e
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbebfa213aa125252a8c58e246df376e2a36527d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263309"
---
# <a name="known-issues-with-edi-send-processing"></a>已知的问题的 EDI 发送处理
本主题将介绍在 EDI 发送管道中进行处理时的已知问题。  
  
## <a name="x12-implied-decimal-point-causes-length-validation-to-fail"></a>X12 隐含小数点导致长度验证失败  
 **症状**  
  
 当 EDI 发送管道将中间 XML 中的十进制数值转换为传出 EDI 交换中以 Nn 格式表示的数值时，XML 交换的长度验证将失败。  
  
 **可能的原因**  
  
 当序列化 X12 编码的 EDI 交换时，EDI 发送管道将始终把十进制数值转换为带有隐含小数点的以 Nn 格式表示的数值。 例如，如果中间 XML 文件中有一个值 12.34，则将此值指定为数字类型 N2 时，EDI 发送管道将把 EDI 交换中的值转换为 1234。 十进制数值将比以格式 Nn 表示的数值长一位。 如果以格式 Nn 表示的数值的长度是最大值，则中间 XML 中的十进制数值将无法通过 XML 长度验证。  
  
 只有 X12 编码的交换才存在此问题。  
  
 **解决方法**  
  
 对 XML 数值的最大长度值上加 1。  
  
## <a name="control-numbers-may-need-to-be-reset-archived-or-purged"></a>控制编号可能需要重置、存档或清除  
 如果任何控制编号达到字段的长度限制，则 BizTalk Server 将引发一个错误并挂起交换。 您必须重置在“EDI 属性”或“EDI 全局属性”对话框中输入的控制编号。  
  
 控制编号保存在 BizTalk MessageBox 数据库的 dbo.EdiSequenceNumbers 表中。 您应根据情况从表中清除控制编号或存档控制编号来管理此数据库。  
  
 此外可以通过选择启用自动重置的控制编号**重置为下限超出界限时**在 EDI 属性对话框中。  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a>上下文属性名称中的数据元素名包含下划线，而不是句点  
 EDI 段中的数据元素名（例如 UNB2.1，它是 UNB2 发送方段的标识字段）包含句点。 不过，如果数据元素名是 EDI 上下文属性的组成部分（例如，在发送端口的筛选器表达式中），则会用下划线代替句点。 例如，发送方标识数据元素的上下文属性是 EDI.UNB2_1 而非 EDI.UNB2.1。 这是因为上下文属性名称中不支持使用句点。  
  
## <a name="context-property-values-from-data-elements-must-not-contain-leading-or-trailing-spaces-in-filter-expressions"></a>数据元素的上下文属性值不能在筛选器表达式中包含前导或尾部空格  
 如果 EDI 交换的信封中的数据元素包含前导或尾部空格，接收管道将升级包含该数据元素的值的上下文属性并从该上下文属性中删除前导或尾部空格。 因此，如果您创建了一个带有该上下文属性的筛选器表达式，则必须为该属性输入一个不含前导或尾部空格的值。 如果您的筛选器表达式包含前导或尾部空格，则在使用不包含前导或尾部空格的该上下文属性的匹配中，无法解析筛选器表达式。  
  
## <a name="default-party-as-interchange-receiver-properties-for-preserved-interchange-will-cause-the-send-pipeline-to-fail"></a>保留交换的默认“参与方作为交换接收方”属性将导致发送管道出错  
 如果 BizTalk Server 接收到一个应保留的批处理交换（使用出错时挂起的交换），如果“参与方作为交换接收方”的属性设置为默认值，则订阅该交换的发送管道将出错。 这些属性，比如 ISA5、发送方限定符、ISA6、发送方标识符必须设置为有效值。 BizTalk Server 将发布一个错误，指示该消息因参与方配置无效而不能序列化。 此处理是不正确的，因为保留交换在其标头中具有必需的配置设置，比如发送方限定符和发送方标识符。  
  
## <a name="the-decimal-notation-in-a-message-will-be-changed-if-the-send-side-party-or-global-setting-specifies-a-different-decimal-notation"></a>消息中的十进制符号在发送方或全局设置指定其他十进制符号时发生更改  
 如果某一交换中使用的十进制符号不同于由 UNA3 参与方属性为传出消息指定的十进制符号，则当 BizTalk Server 序列化该交换以进行发送时将更改该交换的信封中使用的十进制符号。 如果使用 UNA3 全局属性而不是 UNA3 参与方属性，情况与此相同。 例如，如果传入消息中使用的十进制符号是一个句点，且用于确定传出消息的十进制符号的 UNA3 参与方属性或 UNA3 全局属性指定了一个逗号，则 BizTalk Server 将把传出消息中的十进制符号更改为逗号。  
  
## <a name="edi-send-pipelines-cannot-be-executed-from-within-an-orchestration"></a>无法从业务流程内执行 EDI 发送管道  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，您一般可在业务流程的表达式形状中执行发送管道。 不过，此形状将不能与 EDISend 管道或 AS2EdiSend 管道一起使用。 这些管道必须在发送端口内执行。 如果您尝试在业务流程的表达式形状中执行 EDISend 管道或 AS2EdiSend 管道，则该管道将不绑定到发送端口，且消息将被挂起。  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>不得修改 BizTalk EDI 应用程序  
 不得修改或删除 BizTalk EDI 应用程序中的项目。 如果修改了此应用程序，则您将无法通过取消配置和重新配置 EDI 及 AS2 功能来恢复原始应用程序。  
  
## <a name="using-the-default-row-in-the-functional-group-header-grid-can-result-in-a-message-type-mismatch-between-the-interchange-header-and-the-group-header"></a>使用功能组标头网格中的默认行可导致交换标头和组标头之间的消息类型不匹配  
 如果传出 EDIFACT 编码的交换的 UNH2.1 值与 UNG 和 UNH 段定义页的网格中的“对于消息类型 UNH2.1”的值不匹配，则在消息中输入的 UNG1 值与 UNH2.1 的值可能不对应。  
  
 出现这种现象的原因是，BizTalk 将以网格的默认行中的 UNG1 值填充该消息，即使该消息与默认行的 UNH2.1 元素不匹配。  
  
 如果传出 X12 编码的交换的 ST1 值与 GS 和 ST 段定义页的网格中的“对于 ST1”的值不匹配，则根据 ST1 的值动态确定消息中输入的 GS1 值。  
  
## <a name="invalid-character-in-data-element"></a>数据元素中有无效字符  
 **症状**  
  
 使用 EDI 发送管道发送 EDI 交换时，可能会在应用程序事件日志中收到错误，指出“数据元素中有无效字符”。  
  
 **可能的原因**  
  
 如果负载数据中包含的字符还用作分隔符，可能出现此错误。 例如，如果你使用: 为组件分隔符，但负载数据的字符还包含: 字符。  
  
 只有 X12 编码的交换才存在此问题。  
  
 **解决方法**  
  
 使用**替换负载中的分隔符**中设置**ISA 段定义**应替换为要指定在负载数据中找到分隔符字符的 EDI 方属性页发送交换时，请指定替换字符。  
  
 例如，选择**替换负载中的分隔符**并输入 &#124; 字符将替换出现的与负载数据中的分隔符的任何 &#124; 字符时的交换是使用 EDI 发送管道发送。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md)   
 [BizTalk Server 将 EDI 消息的发送](../core/how-biztalk-server-sends-edi-messages.md)   
 [演练 (X12)： 发送 EDI 交换](../core/walkthrough-x12-sending-edi-interchanges.md)