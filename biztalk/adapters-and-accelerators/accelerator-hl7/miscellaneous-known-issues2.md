---
title: 其他已知问题 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues
ms.assetid: 01cd896f-6c7f-4734-b953-81a92195a5c0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0e845a6a178b66d2a817414666455eb20b5bb4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007854"
---
# <a name="miscellaneous-known-issues"></a>其他已知的问题
本部分包含有关其他错误的有用信息。  
  
## <a name="duplicate-errors-logged-for-the-same-message-segment-sequence-and-field-number"></a>重复的记录的相同消息段、 序列和字段数量的错误  
 如果字段的复杂数据的组件中有错误的类型，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将报告为每个此类错误的一个错误。 分段 ID 和字段编号将完全相同。 错误号和说明可能会有所不同，因为 HL7 错误报告机制不支持报表组件和子组件级别的错误。  
  
## <a name="segment-sequence-errors"></a>段序列错误  
 如果缺少所需的消息段，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]报告中分析引擎的最后一个正确段的"分段序列错误 （找到的消息正文的意外结束）"消息。  
  
## <a name="invalid-error-can-be-recorded-when-the-msh3-header-field-is-structurally-incorrect"></a>结构上不正确 MSH3 标头字段时，可以记录无效的错误  
 结构上不正确，MSH3 标头字段是否[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序不能将 MSH3 字段内容复制到 MSH5 标头，和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]无法发送确认 (ACK)。 这可能指示问题是与 MSH5 字段，不 MSH3 字段。  
  
## <a name="access-database-errors"></a>访问数据库错误  
 HL7 Access 数据库包含以下错误：  
  
- OBR 段 HL7 V2.3 Access 数据库中的字段 27 被错误地标记为非可重复和所需。 在此发生了更改[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]架构字段为可重复和可选的正确的值。  
  
- 字段 2 中 HL7 V2.3 访问数据库被错误地标记为 OBX 段必需的并 OBX 段 HL7 V2.3 Access 数据库中的字段 10 已错误地标记为不可重复。 在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]架构标记为可选字段 2 和 10 字段已标记为可重复。  
  
- 字段 4 中 HL7 适用于版本 V2.3.1 访问数据库被错误地标记为 OBX 段被必需。 在此字段[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]架构标记正确地为可选。  
  
## <a name="logging-service-account-may-not-have-access-to-databases-that-are-not-created-by-the-setup-program"></a>日志记录服务帐户可能没有访问不由安装程序创建的数据库的权限  
 在配置日志记录存储以指向新创建的数据库，安装程序未创建，新的数据库可能没有访问列出的日志记录服务帐户。 请确保日志记录服务帐户有权访问所有新创建的日志记录数据库。  
  
## <a name="leading-spaces-not-allowed-in-nm-and-si-data-types"></a>前导空格 NM 和 SI 数据类型中不允许  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 拒绝包含前导空格和尾随空格的 NM 和 SI 数据类型的实例。  
  
## <a name="btahl7-accepts-a-value-of-0-for-hl7-v21-si-data-type"></a>BTAHL7 接受值为"0"HL7 2.1 版 SI 数据类型  
 HL7 2.1 版的 HL7 标准，不 SI 数据类型的实例中可接受值为"0"。 但是，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接受 SI 数据类型的实例中的有效值为"0"。  
  
## <a name="mismatch-of-source-and-destination-party-namespaces"></a>不匹配的源和目标参与方命名空间  
 如果在中配置命名空间[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]上配置资源管理器**验证**选项卡不会与在架构中的源命名空间不匹配 HL7 v2。消息，序列化程序可能会生成不清楚地确定问题的错误消息。 此类错误消息可能指示找到段序列错误或消息正文的意外的结束。 如果您不能解释一下发生错误的原因，你可能会检查方命名空间不匹配。  
  
## <a name="lack-of-segments-fts-or-bts-results-in-error-but-the-message-still-parses"></a>缺少的段 FTS 或 BTS 导致错误，但消息仍将分析  
 当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]拆装器对批处理消息，它包含段 FHS 或 BHS，但不包含相应分段 FTS 和/或 BTS，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成一个错误，但消息仍将分析。  
  
## <a name="modifying-a-message-header-tag-results-in-multiple-errors"></a>修改消息标头标记导致多个错误  
 如果业务流程设计器修改消息标头标记，可能会看到易于理解，如"无效的第一个段"或"段序列错误"的错误。  
  
## <a name="configuration-data-can-be-affected-by-other-biztalk-server-applications"></a>配置数据可能会受到其他 BizTalk Server 应用程序  
 如果输入中的自定义数据[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器或以编程方式通过配置应用程序编程接口 (Api)、 自定义数据的数据存储在配置数据库中的设置配置。  有关从其他 BizTalk 应用程序的其他特定于参与方的信息，可以使用配置数据库。 如果另一个应用程序会将数据存储在与相同的位置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置数据[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]数据存储不正确。 如果发生这种情况，更改存储位置的其他应用程序的数据，并保存[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]重新配置数据。  
  
## <a name="errors-might-not-be-logged-in-the-error-log-due-to-a-size-limitation-of-the-event-log-store"></a>由于事件日志存储区的大小限制在错误日志中可能不会记录错误  
 当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序生成大量错误，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可能记录的一些错误，由于事件日志存储区的大小限制。 可以在运行状况与活动跟踪 (HAT) 工具中，查看所有错误，但您可能不能在错误日志中查看所有文件。  
  
## <a name="reinstalling-btahl7-under-a-different-folder-will-cause-the-default-receive-locations-not-to-work"></a>重新 BTAHL7 安装在不同的文件夹下将默认值的原因接收位置无法正常工作  
 重新 BTAHL7 安装在不同的文件夹下将导致 BatchControlPort 或启动教程创建的端口不起作用，因为这些端口的 Uri （如在上一次安装中称为） 不匹配由创建的新文件夹的默认位置安装程序。 若要运行这些端口，您将必须更新这些端口的 FILE 传输属性对话框中的文件夹路径。  
  
 如果一个或多个 MLLP 端口存在于 BizTalk 中卸载 BTAHL7 时，将不会删除 MLLP 适配器。 发生这种情况，如果安装在不同位置产品后，所有新的或旧 MLLP 端口将停止运行。 若要运行的 MLLP，您需要卸载并重新安装处的 MLLP 适配器。 详细信息，请参阅"处的 MLLP 适配器期间不会删除卸载"中[解决其他问题](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-other-issues.md)。  
  
## <a name="see-also"></a>请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)