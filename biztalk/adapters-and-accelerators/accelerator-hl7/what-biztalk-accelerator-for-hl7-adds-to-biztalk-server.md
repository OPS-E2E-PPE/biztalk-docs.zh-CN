---
title: BizTalk Accelerator for HL7 将添加到 BizTalk Server |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, documents
- BTAHL7, batching
- messages, acknowledgements
- messages, auditing
- Configuration Explorer
- BTAHL7, message validation
- BTAHL7, Configuration Explorer
- messages, processing
- BTAHL7, BizTalk Server
- BTAHL7, message processing
- auditing, messages
- BTAHL7, auditing
- validating, messages
- acknowledgements, messages
- BTAHL7, logging
- BizTalk Server, BTAHL7
- messages, validating
- logging
- BTAHL7, acknowledgements
- errors, logging
ms.assetid: 862e9f26-588a-4e91-8ebc-f53aab6f46c2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b9e9d1277c5d037a42fd85ca48ec13c8f1893a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209261"
---
# <a name="what-biztalk-accelerator-for-hl7-adds-to-biztalk-server"></a>BizTalk Accelerator for HL7 将添加到 BizTalk Server
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 生成[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]到卫生保健的集成系统的集成系统。 它将添加卫生保健的组织需要的功能。  
  
 你安装[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]之上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将功能添加到核心[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]引擎。 它将功能、 工具和实用程序添加到那些，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]提供。 它还将应用程序编程接口 (Api) 添加到什么[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SDK 提供。  
  
## <a name="btahl72x-message-processing"></a>BTAHL72X 消息处理  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]添加了大量功能和工具，使系统能够处理 HL7 消息本身，而无需自定义。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]包括所有文档规范、 应用程序，以及你需要开发和部署用于处理完整范围的 HL7 特定事务的组件。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]支持[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X 平面文件架构。 以下[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]组件执行[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X 消息处理：  
  
-   HL7 反汇编程序，并使系统能够分析和本机序列化 HL7 消息的汇编程序。 反汇编程序及其汇编程序属于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管道，后者将执行一系列或处理消息的步骤，包括到或从 XML 转换，解码编码和消息验证。  
  
-   最小较低层协议 (MLLP) 适配器，使系统接收或发送基于 HL7 消息，其中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]通常传输使用 MLLP 协议。 MLLP 适配器可确保[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]是可以与基于 HL7 消息传送应用程序互操作。  
  
-   使系统能够接收 HL7 编码消息的 HL7 消息架构。  
  
## <a name="btahl72xml-message-processing"></a>BTAHL72XML 消息处理  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]添加了大量功能和工具，使系统能够处理 XML 消息。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将 HL7 消息转换为 XML 格式，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，该方法使用 XML 在内部，对消息执行操作。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]仅对 HL7 V2 执行转换为 XML。X 消息，因为它们是以本机方式在平面文件格式。 它不是以 XML 格式的 2.XML 消息执行转换。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析并验证而不进行转换这些消息。  
  
 支持的 XML 消息架构[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML 架构生成的 HL7 V2 的 HL7 组织。XML 版本、 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]用于 HL7 V2 的 2 X 架构。X 版本消息 （采用平面文件格式）。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]包括文档规范、 应用程序，以及你需要处理的完整范围的于开发和部署的组件[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML 事务。 以下[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]组件执行[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML 消息处理：  
  
-   XML 反汇编程序，并使系统能够分析和序列化与 HL7 邮件相对应的 XML 消息的汇编程序。 XML 反汇编程序和汇编程序包括增强功能的功能超出[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML 反汇编程序和汇编程序，包括自动确认和消息验证。  
  
-   HL7 兼容 XML 架构，使系统能够接收 HL7 消息 (这两个 V2。X 和 V2。XML 消息）。 系统将转换 V2。消息转换为 XML 消息 (V2。XML 消息是已在 XML 中），然后将其发送到 XML 启用的另一个系统。 同样，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以收到 XML 消息，并且然后将它们转换为 HL7 用于发送。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]通过使用基于 XML 的文档规范，以及 HL7 分析器、 映射和其他转换 HL7 特有的数据来自或附加到另一种格式[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用架构和映射的工具。 例如，可能收到标准 HL7 V2.0 格式或 V2.5 格式，将交换，并将该数据转换为可以使用现有医疗应用程序的另一种格式。  
  
## <a name="validation"></a>验证  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]执行验证的 HL7 V2。X 消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]无法执行。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]自动执行的标头的 HL7 消息的语法和示意图验证和自动执行的 HL7 消息的正文某种结构验证。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]执行的 HL7 消息正文的示意图验证，如果你启用该功能 (请参阅[验证设置](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md))。  
  
 HL7 编码消息的正文的验证过程包括的架构、 数据格式，某些标头和正文字段和枚举值。 2.XML 消息的验证过程包括根据其架构，这是标准的 XML 验证进行验证。 有关详细信息，请参阅[BTAHL72X 平面文件处理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)和[BTAHL72XML 处理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)。  
  
## <a name="auto-acknowledgment"></a>自动确认  
 若要确保消息传递系统的可靠性，你可能希望要求确认 (ACK) 到 HL7 消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成自动根据配置设置。  
  
 原始模式 Ack 确认验证结果的消息头和正文。 在增强模式下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成两种类型的 Ack： 的接受验证标头，它将发送的 ACK 和一个应用程序完成的消息验证发送的 ACK。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成的业务线应用程序收到来自延迟的 ACK [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]有助于支持双向消息传输的确认处理。  
  
## <a name="batching"></a>批处理  
 你可以处理在批处理模式下，这将节省处理开销的文档。 你可以批处理响应这些批次。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可实现三种类型的批处理的 HL7 2.X 消息：  
  
-   入站批处理，，这是在其中系统作为批处理，接收消息，然后片段它为单个消息。  
  
-   在批处理/批处理 out，在其中系统同时接收和作为批处理发送消息。  
  
-   创建批处理，系统会发送一批作为单独的消息接收的消息。  
  
    > [!NOTE]
    >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不提供 v2 的批处理功能。XML 消息。  
  
## <a name="logging"></a>日志记录  
 若要增强故障排除，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使报告错误或警告由系统组件发送信号。 你可以筛选此类事件，将其存储在任何三个日志存储区 ([!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件日志，WMI，或[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]日志存储区)，或使用自定义它们[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]SDK。  
  
## <a name="configuration-explorer"></a>配置资源管理器  
 你可以配置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]方、 批处理、 确认，和存储中的日志[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，一种管理工具添加到的工具，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]提供。 此工具还使你能够启动方级别的批处理。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] SDK，你可以自定义这些设置以编程方式。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 如何解决的业务需要](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)