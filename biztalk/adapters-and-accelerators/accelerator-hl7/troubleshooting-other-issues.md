---
title: 其他问题疑难解答 |Microsoft 文档
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
ms.openlocfilehash: 796482df7234e2699b5b9bd3d1c12f6e98ccb923
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-other-issues"></a>其他问题疑难解答
地址与相关的其他问题[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]。  
  
## <a name="message-rejected-by-the-btahl7-engine"></a>BTAHL7 引擎被拒绝的消息  
  
### <a name="symptom"></a>故障现象  
 由消息引擎随机拒绝消息。  
  
**可能的原因**： 根据 HL7 标准枚举值的表 0338年包含"L & 我"值。 PRA 段的字段 6 可能包含此值。 由于[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将"&"字符作为分隔符，消息被拒绝。  
  
**解析**： 有三个可能的解决方法以解决此问题：  
  
1.  在消息实例中，处理通过转义序列，例如，使用字符组合 L\T\I"&"字符。  
  
2.  添加在 PRA 6 架构中的"I"的枚举值和消息实例中改为使用此值。  
  
3.  在 MSH2; 中使用完全不同的子组件分隔符但是，此特定解决方案可能不可行取决于你的环境。  
  
## <a name="cannot-edit-the-hl7-schema-using-visual-studio"></a>无法编辑使用 Visual Studio 的 HL7 架构  
  
### <a name="symptom"></a>故障现象  
 无法编辑 HL7 架构使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
**可能的原因**:[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]不支持某些 HL7 架构。  
  
**解析**： 使用其他编辑器中，如[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]记事本，以编辑 HL7 架构。  
  
## <a name="message-handling-fails-with-no-errors-logged"></a>消息处理失败，并记录的任何错误  
  
### <a name="symptom"></a>故障现象  
 系统不会记录错误消息或挂起的消息队列中放置消息处理消息。  
  
**可能的原因**: **HeaderSpecType**和**DocumentSpecType**属性值区分大小写。 在部署你管道时，这些名称中犯了输入错误可以导致错误处理和删除，而不记录的错误消息。  
  
**解析**： 观察区分大小写，使用时**HeaderSpecType**和**DocumentSpecType**属性值名称。  
  
## <a name="message-header-fields-are-not-validated-correctly"></a>消息标头字段尚未正确验证  
  
### <a name="symptom"></a>故障现象  
 标头字段的验证失败。  
  
 原因：[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序验证提升的属性，而不是实际的标头字段上下文属性。  
  
**可能的原因**： 对应于通过 orchestration 或地图的标头已提升属性发生更改。  
  
**解析**： 上下文属性的消息标头 MSH1、 MSH2 和 MSH5 {1-3} 需要更新，以便它们中的数据的同步。  
  
## <a name="the-mllp-adapter-is-not-removed-during-uninstall"></a>在卸载期间未删除 MLLP 适配器  
  
### <a name="symptom"></a>故障现象  
 BTAHL7 安装程序未 BTAHL7 卸载期间删除 MLLP 适配器。  
  
**可能的原因**： 没有具有传输类型为 MLLP 的接收位置或发送端口。 如果在任何 BizTalk Server 项目正在引用它，BTAHL7 安装程序无法删除 MLLP 适配器。  
  
**解析**: BTAHL7 卸载已完成后，执行以下操作：  
  
1.  在 BizTalk Server 管理控制台中，删除所有接收位置和发送端口传输类型为 MLLP，或更改接收位置的传输类型或发送到另一种类型的端口。  
  
2.  在管理控制台中，删除 MLLP 适配器。  
  
3.  重新启动主机实例。  
  
## <a name="btahl7-cannot-be-uninstalled-if-biztalk-server-has-already-been-uninstalled"></a>如果 BizTalk Server 已被卸载，则无法卸载 BTAHL7  
  
### <a name="symptom"></a>故障现象  
 卸载[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]会导致以下错误：  
  
`A network error while attempting to read from file C:\Windows\Installer\Microsoft BizTalk <version\> Accelerator for HL7.msi`
  
**可能的原因**:[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]在卸载之前已卸载[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]尝试。 你必须卸载[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]卸载之前[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。  
  
**解析**： 重新安装[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]，然后卸载[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]，然后卸载[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="messages-are-still-sent-after-the-applicable-mllp-send-port-has-been-stopped"></a>完成适用 MLLP 发送端口已停止后，仍会发送消息  
  
### <a name="symptom"></a>故障现象  
 之后你不停止 MLLP 发送端口，发送的消息，通过发送端口的停止，但继续发送。  
  
**可能的原因**： 当你停止发送端口时，则连接将保持建立删除通过停止 BizTalk 主机之前。 因此，停止发送端口后，仍会发送消息。 这是因为 Biztalk Server 不会调入 MLLP 适配器在启动或停止发送端口的过程。 BizTalk Server 调入 MLLP 适配器仅期间的开始和停止主机服务。  
  
**解析**： 你可以通过停止你停止发送端口发送处理程序的主机实例中删除的消息的连接和停止传输。 但是，停止该主机实例，这种情况可能会影响其他不想要停止的消息。 如果你知道这是这种情况，你应在创建时以不同的方式配置发送端口。 你应创建另一个主机实例来充当发送处理程序仅此 MLLP 发送端口 （或发送端口的子集）。 然后，你可以通过停止此主机实例停止此发送端口中的消息传输。 这将不影响其他使用其他发送处理程序的发送端口上的其他消息的传输。  
  
## <a name="see-also"></a>另请参阅  
 [在 HL7 疑难解答和已知问题](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)