---
title: 其他问题疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 1f115f64-45ce-445d-ab18-092f4a6a232c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bab6578c6a9fcbc4a9b1349833604188d1d7884c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286424"
---
# <a name="troubleshooting-other-issues"></a>其他问题疑难解答
解决了与 Microsoft 相关的其他问题[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]。  
  
## <a name="message-rejected-by-the-btahl7-engine"></a>BTAHL7 引擎被拒绝的消息  
  
### <a name="symptom"></a>故障现象  
 由消息引擎将随机拒绝邮件。  
  
**可能的原因**:根据 HL7 标准的枚举值的表 0338年包含"L & 我"的值。 字段 6 PRA 段的可能包含此值。 由于[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]会"&"字符作为分隔符，则消息被拒绝。  
  
**解析**:有三个可能针对此问题的解决方法：  
  
1.  在消息实例中，处理通过转义序列，例如，使用字符组合 L\T\I"&"字符。  
  
2.  在架构中在 PRA 6 添加"LI"的枚举值，并在消息实例中改为使用此值。  
  
3.  在 MSH2; 中使用完全不同的子组件分隔符但是，这个特殊的解决方案可能不可行取决于你的环境。  
  
## <a name="cannot-edit-the-hl7-schema-using-visual-studio"></a>不能编辑使用 Visual Studio 的 HL7 架构  
  
### <a name="symptom"></a>故障现象  
 不能编辑使用 Microsoft 的 HL7 架构[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
**可能的原因**:[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]不支持某些 HL7 架构。  
  
**解析**:使用其他编辑器 （如 Microsoft 记事本） 编辑 HL7 架构。  
  
## <a name="message-handling-fails-with-no-errors-logged"></a>消息处理失败，并记录任何错误  
  
### <a name="symptom"></a>故障现象  
 系统处理消息，而不记录错误消息或将消息放在挂起的消息队列中。  
  
**可能的原因**:**HeaderSpecType**并**DocumentSpecType**属性值不区分大小写。 在部署管道时，这些名称中犯了输入错误可能会导致错误处理和删除，而不记录的错误的消息。  
  
**解析**:使用时，应遵守区分大小写**HeaderSpecType**并**DocumentSpecType**属性值名称。  
  
## <a name="message-header-fields-are-not-validated-correctly"></a>尚未正确验证消息的标头字段  
  
### <a name="symptom"></a>故障现象  
 标头字段的验证失败。  
  
 原因:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序验证升级的属性，而不是实际标头字段上下文属性。  
  
**可能的原因**:通过业务流程或映射的标头与对应的已提升属性发生变化。  
  
**解析**:上下文属性的消息标头 MSH1、 MSH2 和 MSH5{1-3}需要进行更新，以便它们中的数据同步。  
  
## <a name="the-mllp-adapter-is-not-removed-during-uninstall"></a>在卸载过程不会删除 MLLP 适配器  
  
### <a name="symptom"></a>故障现象  
 卸载 BTAHL7 的过程，则 BTAHL7 安装程序未删除 MLLP 适配器。  
  
**可能的原因**:与传输类型为 MLLP 的接收位置或发送端口时出现。 如果在任何 BizTalk Server 项目中引用，则 BTAHL7 安装程序不能删除 MLLP 适配器。  
  
**解析**:在卸载 BTAHL7 的已完成后，请执行以下操作：  
  
1.  在 BizTalk Server 管理控制台中，删除所有接收位置和发送端口的传输类型为 MLLP，或更改接收位置的传输类型或发送端口与另一种类型的端口。  
  
2.  在管理控制台中，删除 MLLP 适配器。  
  
3.  重新启动主机实例。  
  
## <a name="btahl7-cannot-be-uninstalled-if-biztalk-server-has-already-been-uninstalled"></a>如果已卸载 BizTalk Server 无法卸载 BTAHL7  
  
### <a name="symptom"></a>故障现象  
 卸载[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]会导致以下错误：  
  
`A network error while attempting to read from file C:\Windows\Installer\Microsoft BizTalk <version\> Accelerator for HL7.msi`
  
**可能的原因**:[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]在卸载之前卸载[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]尝试。 必须先卸载[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]然后再卸载[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。  
  
**解析**:重新安装[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]，然后卸载[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]，然后卸载[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="messages-are-still-sent-after-the-applicable-mllp-send-port-has-been-stopped"></a>停止适用 MLLP 发送端口后，仍然发送消息  
  
### <a name="symptom"></a>故障现象  
 您不停止的停止 MLLP 发送端口，通过发送该发送端口的消息，之后继续发送。  
  
**可能的原因**:停止发送端口时，连接将仍保持已建立，删除通过停止 BizTalk 主机之前。 因此，停止发送端口后，仍会发送消息。 这是因为 Biztalk Server 不会为处的 MLLP 适配器调用期间启动或停止的发送端口。 BizTalk Server 调用到处的 MLLP 适配器仅在开始和停止主机服务。  
  
**解析**:可以删除该连接，并通过停止你已停止的发送端口的发送处理程序的主机实例停止的消息传输。 但是，停止该主机实例可能会影响你不想要停止其他消息。 如果您知道这种情况，您应在创建时以不同的方式配置发送端口。 应创建另一个主机实例，以用作仅此 MLLP 发送端口 （或发送端口的子集） 的发送处理程序。 然后可以通过停止此主机实例停止此发送端口中的消息传输。 这将不影响其他使用其他发送处理程序的发送端口上的其他消息的传输。  
  
## <a name="see-also"></a>请参阅  
 [HL7 的疑难解答和已知问题](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)