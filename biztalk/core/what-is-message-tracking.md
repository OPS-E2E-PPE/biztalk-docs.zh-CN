---
title: 什么是消息跟踪？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HAT, metadata
- HAT, messages
- messages, tracking
- data, HAT
- metadata, tracking
- tracking, metadata
- HAT, data security
- tracking, messages
- configuring [HAT tracking], messages
- data, security
ms.assetid: 51cec59d-b411-4d8f-b771-7b2cf0f38945
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e20978905628072269b0acf0990d67dc4582b414
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394027"
---
# <a name="what-is-message-tracking"></a>什么是消息跟踪？
一条消息是通常交换两个之间的数据电子实例运行的业务流程或应用程序。 消息实例消息正文、 消息属性和元数据组成。  
  
 可以使用 BizTalk Server 管理控制台来启用消息正文和消息属性跟踪。 那里您还可以查看跟踪的消息正文，包括架构信息、 强名称，以及所生成消息的升级的所有属性。  
  
## <a name="message-body"></a>消息正文  
 跟踪消息正文，可发送和接收消息的记录。 您必须具有消息正文跟踪，以便将消息保存在服务实例处理后打开已完成。 设置跟踪选项后，它可能需要几分钟之后您可以查看的消息。  
  
> [!IMPORTANT]
>  SQL Server 代理服务必须在所有 MessageBox 数据库上运行。 TrackedMessages_Copy_\<MessageBoxName\>作业，消息正文跟踪查询和 WMI 可。 若要有效地复制消息正文，它们在 MessageBox 数据库中保留和 TrackedMessages_Copy_ 通过定期复制到 BizTalk 跟踪 (BizTalkDTADb) 数据库\<MessageBoxName\>作业。 具有运行的 SQL Server 代理服务也是存档和清除进程才能正常工作的先决条件。  
  
 跟踪的消息可用于提供回执，以实现故障排除，并允许数据挖掘的历史事务确认。 你可以跟踪输入和输出端口、 管道和业务流程的消息正文。 您可以恢复这些消息使用 BizTalk Server 管理控制台，使用操作对象模型 (OM) （推荐） 或通过 Windows Management Instrumentation (WMI) 应用程序编程接口 (Api)。  
  
 BizTalk Server 不会跟踪不成功使其通过其中一个跟踪点的消息。 在某些情况下，如当被挂起一条消息，因为它是无效的或如果没有主机接收消息，它可能被放在挂起队列而不被跟踪。 如果您终止此消息将有它的任何记录。  
  
> [!IMPORTANT]
>  消息正文跟踪不能代替具有法律约束力的审核，并不支持不可否认性。  
  
## <a name="message-properties"></a>消息属性  
 消息属性包括升级的属性，路由信息和贸易合作伙伴数据。 消息属性跟踪，可查找你可能会跟踪的结果列表中每个消息中提供的升级属性的记录与千位特定的消息。 你可以跟踪消息本身的子集使用这些属性之一。  
  
 若要跟踪上下文属性，您定义的上下文中用于存储属性的命名空间的属性架构。 在这里，可以选择想要跟踪的上下文属性。BizTalk Server 跟踪与跟踪升级的消息属性的方式相同。  
  
> [!NOTE]
>  请确保为架构中的属性不同的名称。 如果您创建重复的名称，将显示一条错误消息。  
  
 例如，可以使用架构编辑器将从采购订单架构升级采购订单编号字段。 然后，使用查找消息视图，您会发现消息实例，包含特定值该跟踪字段，如 PO Number = 16995。  
  
 消息属性跟踪产生要少得多的开销比消息正文跟踪，因为消息属性跟踪只跟踪选定的字段。 设置消息属性的跟踪选项后，它可能需要几分钟之后您可以查看的属性。  
  
## <a name="metadata"></a>元数据  
 元数据，例如消息实例标识符、 业务流程或管道记录消息的业务流程或管道记录消息，以及其他相关的跟踪详细信息的点。 对于路由业务流程到 MessageBox 数据库中的消息，它必须包含上下文属性，如消息类型和源。 这些属性将成为元数据。 消息和服务实例跟踪使用订阅条件来查询此类元数据。  
  
 通过 BizTalk Server 管理控制台中，您可以通过选择特定的系统架构升级上下文属性。 系统架构位于 Applications\BizTalk.System\Schemas 节点中。 BizTalk Server 全局跟踪这些上下文属性 — 也就是说，所有消息现在都跟踪特定的上下文属性。 这可以显著提高 BizTalk 跟踪数据库的大小。  
  
## <a name="sensitive-data"></a>敏感数据  
 可以保护以下数据确保它没有显示在相应的架构属性窗口中，从而避免进行跟踪。  
  
-   将应用**isSensitive**属性在属性架构中，任何敏感属性，这样就不再显示在消息属性跟踪的配置选择。  
  
-   所有的开箱传输包含标记为敏感，因此无法跟踪传输的密码。  
  
-   此外，这些敏感属性将不再在管理数据库中，因此，如果您在设置跟踪选项直接在数据库中的，它们用于跟踪不可用。  
  
-   如果您跟踪出站网络上消息正文，跟踪的消息将从所跟踪的消息正文的快捷方式删除所有传输属性。 因此，除了从所跟踪的消息正文的快捷方式中删除出站传输属性，消息跟踪还会删除属性从入站传输。  
  
    > [!IMPORTANT]
    >  升级的属性可以包含敏感数据。 如果从组中心页的跟踪查询跟踪包含敏感数据的属性，有权运行跟踪查询的任何用户可以查看此数据。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 管理控制台配置跟踪](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)
