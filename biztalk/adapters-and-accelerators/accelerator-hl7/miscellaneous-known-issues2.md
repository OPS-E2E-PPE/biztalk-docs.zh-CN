---
title: 杂项已知的问题 2 |Microsoft 文档
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
ms.openlocfilehash: af644ead6ecb825d6d6960145958c176946e844c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="miscellaneous-known-issues"></a>其他已知的问题
本部分包含有关其他错误的有用信息。  
  
## <a name="duplicate-errors-logged-for-the-same-message-segment-sequence-and-field-number"></a>重复相同的消息段、 序列，和字段号记录的错误  
 如果组件中的复杂数据类型，字段有错误[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将报告为每个此类错误的一个错误。 分段 ID 和字段号将完全相同。 错误号和描述可能会有所不同，因为 HL7 错误报告机制不支持报告错误级别的组件和子组件。  
  
## <a name="segment-sequence-errors"></a>段序列错误  
 如果缺少必需的消息段，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]报告中分析引擎的最后一正确段"段序列错误 （意外末尾找到的消息正文）"消息。  
  
## <a name="invalid-error-can-be-recorded-when-the-msh3-header-field-is-structurally-incorrect"></a>结构上不正确的 MSH3 标头字段时，可以记录无效的错误  
 如果 MSH3 标头字段是结构上不正确，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序无法将 MSH3 字段内容复制到 MSH5 标头，和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]无法发送确认 (ACK)。 这可能表明问题是与 MSH5 字段，不 MSH3 字段。  
  
## <a name="access-database-errors"></a>访问数据库错误  
 HL7 Access 数据库包含以下错误：  
  
-   OBR 段 HL7 V2.3 访问数据库中的字段 27 被错误地标记为非可重复和所需。 已发生变化。 在此[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]架构字段可重复和可选的正确值。  
  
-   必需的字段 2 中数据库被错误地标记为 HL7 V2.3 访问 OBX 段，然后 OBX 段 HL7 V2.3 访问数据库中的字段 10 被错误地标记为非可重复。 在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]架构标记为可选，字段 2 和 10 字段标记为可重复。  
  
-   字段 4 中数据库被错误地标记为 HL7 V2.3.1 访问 OBX 段被必需。 在此字段[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]架构标记正确为可选。  
  
## <a name="logging-service-account-may-not-have-access-to-databases-that-are-not-created-by-the-setup-program"></a>日志记录服务帐户可能没有访问权限不由安装程序的数据库  
 当你配置日志记录存储为指向新创建的数据库，安装程序未创建，新的数据库不能用于访问列出的日志记录服务帐户。 确保日志记录服务帐户有权访问所有新创建的日志记录数据库。  
  
## <a name="leading-spaces-not-allowed-in-nm-and-si-data-types"></a>前导空格 NM 和 SI 数据类型中不允许  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]拒绝具有前导和尾随空格的 NM 和 SI 数据类型的实例。  
  
## <a name="btahl7-accepts-a-value-of-0-for-hl7-v21-si-data-type"></a>BTAHL7 接受值为"0"HL7 V2.1 SI 数据类型  
 HL7 2.1 版的 HL7 标准，不在 SI 数据类型的实例可接受值为"0"。 但是，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接受 SI 数据类型的实例中的有效值为"0"。  
  
## <a name="mismatch-of-source-and-destination-party-namespaces"></a>不匹配的源和目标方命名空间  
 如果命名空间配置中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]资源上的配置管理器**验证**选项卡不匹配 HL7 V2 架构中的源命名空间。X 消息，序列化程序可能会生成不清楚地确定问题的错误消息。 此类错误消息可能表示找到段序列错误或消息正文的意外的结束。 如果您不能解释错误的原因，你可能会检查方命名空间不匹配。  
  
## <a name="lack-of-segments-fts-or-bts-results-in-error-but-the-message-still-parses"></a>缺乏段 FT 或 BTS 导致错误，但消息仍分析  
 当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]反汇编程序分析包含段 FHS 或 BHS，但不包含相应的批处理消息段 FT 和/或 BTS，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]一个生成错误，但消息仍分析。  
  
## <a name="modifying-a-message-header-tag-results-in-multiple-errors"></a>修改消息标头标记导致多个错误  
 如果业务流程设计器修改消息标头标记，你可能会看到不易于理解，如"无效的第一条线段"或"段序列错误"的错误。  
  
## <a name="configuration-data-can-be-affected-by-other-biztalk-server-applications"></a>配置数据可能会受到其他 BizTalk Server 应用程序  
 如果输入中的自定义数据[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器或以编程方式通过配置应用程序编程接口 (Api)，自定义数据的数据存储在配置数据库的设置配置。  配置数据库可用于其他 BizTalk 应用程序中的其他方特定信息。 如果另一个应用程序会将数据存储在与相同的位置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置数据[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]数据存储不正确。 如果发生这种情况，更改其他应用程序的数据的存储位置，并将保存[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]再次配置数据。  
  
## <a name="errors-might-not-be-logged-in-the-error-log-due-to-a-size-limitation-of-the-event-log-store"></a>由于事件日志存储区的大小限制错误日志中可能不会记录错误  
 当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序生成大量错误，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可能记录的一些错误，由于事件日志存储区的大小限制。 你可以在运行状况和活动跟踪 (HAT) 工具中，查看所有错误，但你可能不能在错误日志中查看所有文件。  
  
## <a name="reinstalling-btahl7-under-a-different-folder-will-cause-the-default-receive-locations-not-to-work"></a>重新 BTAHL7 安装在不同文件夹下将原因默认接收位置无法正常工作  
 重新 BTAHL7 安装在不同文件夹下将导致 BatchControlPort 或启动教程创建的端口不起作用，因为这些端口的 Uri （如在以前的安装中称为） 将不匹配的创建的新文件夹的默认位置安装程序。 对于工作这些端口，你将需要更新这些端口的文件传输属性对话框中的文件夹路径。  
  
 如果一个或多个 MLLP 端口存在于 BizTalk 中卸载 BTAHL7 时，将不会删除 MLLP 适配器。 发生这种情况，如果安装在不同位置产品后，所有新的或旧 MLLP 端口将停止工作了。 有关 MLLP 工作，你将需要卸载并重新安装 MLLP 适配器。 有关详细信息，请参阅"MLLP 适配器不删除在卸载过程"[解决其他问题](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-other-issues.md)。  
  
## <a name="see-also"></a>另请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)