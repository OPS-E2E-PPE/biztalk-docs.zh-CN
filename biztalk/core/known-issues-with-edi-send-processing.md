---
title: 已知问题的 EDI 发送处理 |Microsoft Docs
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
ms.openlocfilehash: 201b93c854411e0aec79258caa5777c8be51d352
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329143"
---
# <a name="known-issues-with-edi-send-processing"></a>已知的问题的 EDI 发送处理
本主题介绍在 EDI 发送管道中处理的已知的问题。  
  
## <a name="x12-implied-decimal-point-causes-length-validation-to-fail"></a>X12 隐含小数点导致长度验证失败  
 **症状**  
  
 当 EDI 发送管道将十进制数字值的中间 XML 到传出的 EDI 交换中的 Nn 格式的数字时，请 XML 交换长度验证将失败。  
  
 **可能的原因**  
  
 在序列化的 X12 编码的 EDI 交换，EDI 发送管道始终会将十进制数字值转换为格式 Nn 带有隐含小数点的数字。 例如，是否存在一个值 12.34 的中间 XML 文件中，EDI 发送管道会将其转换为 1234 指定为数字类型 N2 时 EDI 交换中。 以 10 为基数的数字值的长度将会比以格式 Nn 号的长度。 如果数字的以 Nn 格式的长度最大值，在中间 XML 中的十进制数字值无法通过 XML 长度验证。  
  
 这是问题仅与 X12 编码的交换。  
  
 **解决方法**  
  
 将值 1 添加到 XML 数值的最大长度值。  
  
## <a name="control-numbers-may-need-to-be-reset-archived-or-purged"></a>可能需要重置、 存档或清除控制编号  
 如果任何控制编号达到字段的长度限制，BizTalk Server 将引发错误并挂起该交换。 您将必须重置在 EDI 属性或 EDI 全局属性对话框中输入的控制编号。  
  
 控制编号保存在 dbo。EdiSequenceNumbers BizTalk MessageBox 数据库的表。 应通过从表中清除控制编号或存档控制编号，根据需要来管理此数据库表。  
  
 此外可以通过选择启用自动重置的控制编号**重置为下限值超出界限时**EDI 属性对话框中。  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a>上下文属性名称中的数据元素名称包含下划线，而不是句点  
 EDI 段中的数据元素的名称包含句点，例如 UNB2.1，它是 UNB2 发送方段的标识字段。 但是，如果数据元素名是 EDI 上下文属性 （例如，在发送端口的筛选器表达式） 的一部分，用下划线代替句点。 例如，发送方标识数据元素的上下文属性即为 EDI。UNB2_1，不是 EDI。UNB2.1。 这样做的原因是，一段不支持上下文属性名称中。  
  
## <a name="context-property-values-from-data-elements-must-not-contain-leading-or-trailing-spaces-in-filter-expressions"></a>数据元素的上下文属性值不能包含在筛选表达式中的前导或尾部空格  
 如果 EDI 交换的信封中的数据元素中包含前导或尾随空格，并接收管道将升级包含该数据元素的值的上下文属性，接收管道将从上下文中移除前导或尾部空格属性。 因此，如果与该上下文属性创建筛选器表达式，您必须为不能包含前导或尾随空格的属性输入值。 如果筛选器表达式包含前导或尾随空格，筛选器表达式中，无法解析的上下文属性，将不能包含前导或尾随空格的匹配。  
  
## <a name="default-party-as-interchange-receiver-properties-for-preserved-interchange-will-cause-the-send-pipeline-to-fail"></a>默认参与方作为交换接收方属性，为保留的交换将导致发送管道出错  
 如果 BizTalk Server 接收 （包含出错时挂起交换） 应保留的批处理的交换，则作为交换接收方的参与方属性设置为其默认值，订阅该交换的发送管道将失败值。 这些属性，比如 ISA5、 发送方限定符、 isa6、 发送方标识符必须设置为有效的值。 BizTalk Server 将发布一个错误，指示无法由于参与方配置无效序列消息。 此处理是不正确，因为保留的交换在其标头中具有所需的配置设置，例如发送方限定符和发送方标识符。  
  
## <a name="the-decimal-notation-in-a-message-will-be-changed-if-the-send-side-party-or-global-setting-specifies-a-different-decimal-notation"></a>如果发送端参与方或全局设置指定不同的十进制表示法，将会更改在消息中的十进制符号  
 如果交换中使用的十进制符号不同于由 UNA3 参与方属性指定为传出消息的十进制表示法，BizTalk Server 将更改时它将其序列化用于发送交换的信封中使用的十进制符号. 如果使用 UNA3 全局属性而不是 UNA3 参与方属性，这也会是这种情况。 例如，如果传入消息中使用的十进制表示法是一段时间，并且 UNA3 参与方属性或 UNA3 全局属性，用于确定传出消息的十进制表示法指定逗号，BizTalk Server 将更改中的十进制符号为逗号的传出消息。  
  
## <a name="edi-send-pipelines-cannot-be-executed-from-within-an-orchestration"></a>EDI 发送管道不能在中执行业务流程  
 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，通常可以在业务流程中执行的表达式形状中的发送管道。 但是，这不会使用 EDISend 管道或 AS2EdiSend 管道。 这些管道必须在发送端口内执行。 如果尝试在业务流程中的表达式形状中执行 EDISend 管道或 AS2EdiSend 管道，管道将不绑定到发送端口，并将挂起该消息。  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>不得修改 BizTalk EDI 应用程序  
 不得修改或删除 BizTalk EDI 应用程序中的项目。 如果修改此应用程序，则没有办法可以恢复到原始应用程序通过取消配置和重新配置 EDI 和 AS2 功能。  
  
## <a name="using-the-default-row-in-the-functional-group-header-grid-can-result-in-a-message-type-mismatch-between-the-interchange-header-and-the-group-header"></a>功能组标头网格中使用的默认行可能会导致消息类型不匹配之间交换标头和组标头  
 如果传出 EDIFACT 编码交换的 UNH2.1 的值不匹配的网格中的 UNG 和 UNH 段定义页的"对于消息类型 UNH2.1"的值，则在消息中输入的 UNG1 值可能不对应 UNH2.1 的值。  
  
 这可能会因为 BizTalk 将填充该消息的值的默认行的网格中的 UNG1 即使该消息没有与默认行的 UNH2.1 元素匹配。  
  
 如果传出 X12 编码交换的 ST1 值与 GS 和 ST 段定义页中的网格中的"对于 ST1"的值不匹配，消息中输入的 GS1 值会动态确定基于 ST1 的值。  
  
## <a name="invalid-character-in-data-element"></a>数据元素中的无效字符  
 **症状**  
  
 发送 EDI 发送管道使用 EDI 交换时，你可能会收到错误中指出，数据元素中的无效字符，则应用程序事件日志。  
  
 **可能的原因**  
  
 如果负载数据中包含的字符也用作分隔符，可以发生此错误。 例如，如果使用的: 字符作为复合元素分隔符，而负载数据还包含: 字符。  
  
 这是问题仅与 X12 编码的交换。  
  
 **解决方法**  
  
 使用**替换为在通过有效负载中的分隔符**中设置**ISA 段定义**应替换为指定的有效负载数据中找到的分隔字符的 EDI 参与方属性页指定的替换字符时发送交换。  
  
 例如，选择**替换为在通过有效负载中的分隔符**并输入&#124;字符将替换具有的有效负载数据中的分隔符字符的任何匹配项&#124;字符时发送的交换使用 EDI 发送管道。  
  
## <a name="see-also"></a>请参阅  
 [EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md)   
 [BizTalk Server 如何发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md)   
 [演练 (X12):发送 EDI 交换](../core/walkthrough-x12-sending-edi-interchanges.md)