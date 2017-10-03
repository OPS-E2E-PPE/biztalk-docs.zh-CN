---
title: "错误故障排除 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, troubleshooting
- troubleshooting, errors
ms.assetid: 08cc95a3-4be9-450f-a015-e031011158f7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae7ad99b699da29d4d8680375f88e4d4a74ff66a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-errors"></a>排除错误
本部分讲述与相关的问题[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成了错误。  
  
## <a name="the-mllp-adapter-can-run-only-on-a-single-host-instance"></a>只能在单个主机实例下运行 MLLP 适配器  
  
### <a name="symptom"></a>故障现象  
 不能启用与传输类型为 MLLP 接收位置和比另一个现有的接收位置不同的接收处理程序。 此外，无法登记，并开始发送端口不是另一个现有发送端口开始与不同的发送处理程序。  
  
**可能的原因**： 你只能使用一个 MLLP 接收 （或发送） 的单个服务器上的处理程序。 此外，该 URI 指定用于接收位置 （或发送端口） （MLLP 传输属性中的主机名称） 必须是"localhost"或运行其中主机实例接收 （或发送） 适配器处理程序的服务器名称。  
  
**解析**： 一台服务器上的所有 MLLP 接收位置 （或发送端口） 指定相同的接收 （或发送） 处理程序。  
  
## <a name="msh-and-ack-schemas-must-be-added-to-only-one-project"></a>MSH 和 ACK 架构必须添加到只有一个项目  
  
### <a name="symptom"></a>故障现象  
 当你尝试生成项目时，会得到以下错误之一：  
  
`Error: Cannot locate document specification as multiple schemas match the message type "http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF"`
  
`Schema http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF not found`
  
**可能的原因**: MSH 和 ACK 架构 （MSH_25_GLO_DEF.xsd 和 ACK_24_GLO_DEF.xsd） 已部署在多个项目。  
  
**解析**： 确保 MSH_25_GLO_DEF.xsd 和 ACK_24_GLO_DEF.xsd 已添加到只有一个项目。  
  
## <a name="exception-of-type-systemoutofmemoryexception-has-thrown-an-error-in-the-event-log"></a>具有事件日志中引发了错误类型 System.OutOfMemoryException 异常  
  
### <a name="symptom"></a>故障现象  
 事件日志中获取以下或类似错误：  
  
`Exception of type System.OutOfMemoryException has thrown an error.`
  
**可能的原因**： 某些处理大量消息时[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]引擎组件可能会出现内存泄漏。  
  
**解析**： 重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="header-serialization-generates-an-error-in-the-event-viewer"></a>标头序列化在事件查看器中生成错误  
  
### <a name="symptom"></a>故障现象  
 即使在运行状况和活动跟踪 (HAT) 工具消息指示安装成功，可以在事件日志中，收到以下或类似错误：  
  
`An error happened in the header during serialization.`
  
**可能的原因**： 未正确设置消息标头转换值[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
**解析**： 验证 MSH 映射中的值[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
## <a name="duplicate-event-id-4133-serializer-errors-are-logged"></a>重复事件 ID 4133 记录序列化程序错误  
  
### <a name="symptom"></a>故障现象  
 事件 ID 4133 –"过程中发生错误标头中序列化"两次进行 MSH11 值不是有效的消息的每个实例。  
  
**可能的原因**： 而无需重复事件日志中的错误处理 （提交和应用程序确认） 的两个确认时出错。 相反，每两个 Ack 收到一个事件 ID 4133。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]它会生成每个 ACK 为创建一个日志条目。  
  
**解析**： 确保你的消息具有正确格式化和填充 MSH11 字段。  
  
## <a name="send-pipeline-generates-an-error-when-using-the-2-way-mllp-adapter"></a>发送管道将双向 MLLP 适配器时生成错误  
  
### <a name="symptom"></a>故障现象  
 事件日志中获取以下或类似错误：  
  
`There was a failure executing the send pipeline: "[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XPipelines.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XSendPipeline" Source: "[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm" Send Port: "<*host name: port number*>" Reason: Message does not contain a part with name MSHSegment.`
  
**可能的原因**： 接收应用程序不响应与确认和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]预期向接收应用程序的响应。  
  
**解析**： 这是设计使然，并且你可以忽略该错误消息。  
  
## <a name="see-also"></a>另请参阅  
 [在 HL7 疑难解答和已知问题](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)