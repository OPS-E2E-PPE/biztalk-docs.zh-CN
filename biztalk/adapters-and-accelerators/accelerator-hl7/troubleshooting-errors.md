---
title: 错误故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, troubleshooting
- troubleshooting, errors
ms.assetid: 08cc95a3-4be9-450f-a015-e031011158f7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f5af933f83f292bfae3f92f70d2c247274c159c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976854"
---
# <a name="troubleshooting-errors"></a>错误疑难解答
本部分解决与相关的问题[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成了错误。  
  
## <a name="the-mllp-adapter-can-run-only-on-a-single-host-instance"></a>MLLP 适配器可以仅在单个主机实例上运行  
  
### <a name="symptom"></a>故障现象  
 不能启用与传输类型为 MLLP 的接收位置和不同的接收处理程序比另一个现有的接收位置。 此外，不能登记并启动发送端口与不同的发送处理程序，不是另一个现有发送端口。  
  
**可能的原因**： 你只能使用一个 MLLP 接收 （或发送） 在单个服务器上的处理程序。 此外，该 URI 指定为接收位置 （或发送端口） （MLLP 传输属性中的主机名） 必须是"localhost"或运行主机实例接收 （或发送） 适配器处理程序的位置的服务器名称。  
  
**解析**： 一台服务器上的所有 MLLP 接收位置 （或发送端口） 指定相同的接收 （或发送） 处理程序。  
  
## <a name="msh-and-ack-schemas-must-be-added-to-only-one-project"></a>MSH 和确认架构必须添加到只有一个项目  
  
### <a name="symptom"></a>故障现象  
 在尝试生成项目，将获得以下错误之一：  
  
`Error: Cannot locate document specification as multiple schemas match the message type "http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF"`
  
`Schema http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF not found`
  
**可能的原因**: MSH 和确认架构 （MSH_25_GLO_DEF.xsd 和 ACK_24_GLO_DEF.xsd） 已部署在多个项目中。  
  
**解析**： 请确保 MSH_25_GLO_DEF.xsd 和 ACK_24_GLO_DEF.xsd 已添加到一个项目。  
  
## <a name="exception-of-type-systemoutofmemoryexception-has-thrown-an-error-in-the-event-log"></a>具有事件日志中引发错误异常类型 System.OutOfMemoryException  
  
### <a name="symptom"></a>故障现象  
 事件日志中收到以下或类似错误：  
  
`Exception of type System.OutOfMemoryException has thrown an error.`
  
**可能的原因**： 某些处理大量消息，时[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]引擎组件可能会出现内存泄漏。  
  
**解决方法**： 重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="header-serialization-generates-an-error-in-the-event-viewer"></a>标头序列化事件查看器中生成一个错误  
  
### <a name="symptom"></a>故障现象  
 尽管运行状况与活动跟踪 (HAT) 工具中的消息表示成功事件日志中获取以下或类似错误：  
  
`An error happened in the header during serialization.`
  
**可能的原因**： 未正确设置消息标头转换值[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
**解决方法**： 验证 MSH 映射中的值[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
## <a name="duplicate-event-id-4133-serializer-errors-are-logged"></a>重复事件 ID 4133 序列化程序错误记录  
  
### <a name="symptom"></a>故障现象  
 事件 ID 4133 –"过程中发生错误标头中序列化"两次发生 MSH11 值不是有效的消息的每个实例。  
  
**可能的原因**： 不包含在事件日志中的重复错误处理两个确认 （提交和应用程序的确认） 时出错。 相反，为每个的两个确认收到一个事件 ID 4133。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 创建的每个 ACK 中它将生成一个日志条目。  
  
**解析**： 确保消息是否具有正确格式化和填充 MSH11 字段。  
  
## <a name="send-pipeline-generates-an-error-when-using-the-2-way-mllp-adapter"></a>发送管道时使用 2 种方法处的 MLLP 适配器生成错误  
  
### <a name="symptom"></a>故障现象  
 事件日志中收到以下或类似错误：  
  
`There was a failure executing the send pipeline: "[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XPipelines.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XSendPipeline" Source: "Microsoft.Solutions.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm" Send Port: "<*host name: port number*>" Reason: Message does not contain a part with name MSHSegment.`
  
**可能的原因**： 接收应用程序不响应与确认和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]期望来自接收应用程序的响应。  
  
**解析**： 这是设计使然，并且可以忽略的错误消息。  
  
## <a name="see-also"></a>请参阅  
 [HL7 的疑难解答和已知问题](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)