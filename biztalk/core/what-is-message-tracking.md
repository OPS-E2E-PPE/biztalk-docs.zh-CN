---
title: "什么是邮件跟踪？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d76a4bd4133906a7949fac9e63816168506f412
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="what-is-message-tracking"></a>什么是邮件跟踪？
消息是一种电子形式的数据实例，通常在两个运行的业务流程或应用程序之间进行交换。 消息实例由消息正文、消息属性和元数据构成。  
  
 可以使用 BizTalk Server 管理控制台来启用消息正文和消息属性的跟踪。 那里还可以查看跟踪的消息正文，包括架构信息、强名称以及所生成消息的全部升级属性。  
  
## <a name="message-body"></a>消息正文  
 跟踪消息正文可以对所发送和接收的消息进行记录。 必须打开消息正文跟踪功能，才能在服务实例处理完成后保存消息。 在设置跟踪选项后，可能需要几分钟才能查看消息。  
  
> [!IMPORTANT]
>  所有 MessageBox 数据库中都必须运行 SQL Server 代理服务。 TrackedMessages_Copy_\<MessageBoxName\>作业使消息正文可用于跟踪查询和 WMI。 若要有效地复制消息正文，它们在 MessageBox 数据库中保留和 TrackedMessages_Copy_ 定期复制到 BizTalk 跟踪 (BizTalkDTADb) 数据库\<MessageBoxName\>作业。 运行 SQL Server 代理服务是存档和清除进程得以正常运转的前提条件。  
  
 使用跟踪的消息可以提供回执确认、进行故障排除并对历史事务进行数据挖掘。 可以跟踪输入与输出端口、管道及业务流程中的消息正文。 使用 BizTalk Server 管理控制台、使用操作对象模型 (OM)（建议），或通过 Windows 管理规范 (WMI) 应用程序编程接口 (API)，可以恢复这些消息。  
  
 如果消息未成功地通过任何一个跟踪点，则 BizTalk Server 不会对其进行跟踪。 在某些情况下，例如当消息由于无效而挂起或没有任何主机接收该消息时，该消息将会放入挂起队列中而不被跟踪。 如果您终止此消息，则不会有它的任何记录。  
  
> [!IMPORTANT]
>  消息正文跟踪不能代替具有法律约束力的审核，不能杜绝抵赖现象。  
  
## <a name="message-properties"></a>消息属性  
 跟踪的消息属性包括升级的属性、路由信息和贸易合作伙伴数据等。 消息属性跟踪功能可以在结果列表中提供对每个消息的升级属性的记录，以便您从所跟踪的数千个消息中找到特定的消息。 然后，您可以使用这些属性中的某一个属性来跟踪消息本身包含的内容。  
  
 为跟踪上下文属性，您还需要为上下文中使用的命名空间定义属性架构，以存储这些属性。 在该视图中可以选择希望跟踪的上下文属性。BizTalk Server 跟踪上下文属性的方式与跟踪升级的消息属性的方式相同。  
  
> [!NOTE]
>  请确保为架构中的属性指定了不同的名称。 如果创建了重复的名称，则会出现错误消息。  
  
 例如，可以使用架构编辑器升级采购订单架构中的“PO Number”字段。 然后使用“查找消息”视图可找到包含该跟踪字段的特定值（如 PO Number = 16995）的消息实例。  
  
 消息属性跟踪比消息正文跟踪所产生的系统开销小得多，因为消息属性跟踪只跟踪选定的字段。 为消息属性设置跟踪选项后，可能需要几分钟才能查看属性。  
  
## <a name="metadata"></a>元数据  
 跟踪的元数据包括消息实例标识符、记录消息的业务流程或管道、业务流程或管道记录消息时的所在点，以及其他相关的跟踪详细信息。 MessageBox 数据库中的消息必须包含上下文属性（如消息类型和来源），才能路由到业务流程。 这些属性将成为元数据。 消息和服务实例跟踪使用订阅条件来查询此类元数据。  
  
 在 BizTalk Server 管理控制台中，通过选择特定的系统架构可以升级上下文属性。 系统架构位于 Applications\BizTalk.System\Schemas 节点中。 BizTalk Server 全局地跟踪这些上下文属性，也就是说，现在所有消息都跟踪特定的上下文属性。 这会显著地增大 BizTalk 跟踪数据库的大小。  
  
## <a name="sensitive-data"></a>敏感数据  
 您可以保护以下数据，确保这些数据不会显示在相应的架构属性窗口中，从而避免对其进行跟踪。  
  
-   应用**isSensitive**属性到在属性架构中，任何敏感属性，以便不再跟踪的配置选择的消息属性中可见。  
  
-   所有全新传输都包含标记为“敏感”的密码，因此不会跟踪此类传输。  
  
-   此外，管理数据库中不再包含这些敏感属性，因此，如果您在该数据库中直接设置跟踪选项，则无法对其进行跟踪。  
  
-   如果您跟踪出站的网络消息正文，则消息跟踪将从所跟踪消息正文的快捷方式中删除所有传输属性。 因此，除了从所跟踪消息正文的快捷方式中删除出站传输属性之外，消息跟踪还会删除入站传输的属性。  
  
    > [!IMPORTANT]
    >  升级的属性可能会包含敏感数据。 如果“组中心”页中的跟踪查询跟踪包含敏感数据的属性，则有权运行跟踪查询的任何用户都可以查看此数据。  
  
## <a name="see-also"></a>另请参阅  
 [配置使用 BizTalk Server 管理控制台的跟踪](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef)