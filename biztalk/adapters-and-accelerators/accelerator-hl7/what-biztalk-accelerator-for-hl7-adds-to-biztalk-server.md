---
title: BizTalk Accelerator for HL7 向 BizTalk Server 添加 |Microsoft Docs
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
ms.openlocfilehash: 1ab7cd2d5abe126cc246be678c192c037ee48c90
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980054"
---
# <a name="what-biztalk-accelerator-for-hl7-adds-to-biztalk-server"></a>BizTalk Accelerator for HL7 向 BizTalk Server 的添加
Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 生成[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]到卫生保健集成系统的集成系统。 它会添加医疗保健组织要求的功能。  
  
 在安装[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]顶部的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 将功能添加到核心[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]引擎。 它将功能、 工具和实用程序添加到那些的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]提供。 它还将应用程序编程接口 (Api) 添加到什么[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SDK 提供。  
  
## <a name="btahl72x-message-processing"></a>BTAHL72X 消息处理  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 添加功能和工具，使系统能够本身，而无需自定义处理 HL7 消息的数。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 包括所有文档规范、 应用程序和组件需要开发和部署用于处理的完整范围的 HL7 特定事务。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 支持[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 倍的平面文件架构。 以下[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]组件执行[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X 消息处理：  
  
- HL7 反汇编程序和汇编程序，使系统能够分析和本机序列化 HL7 消息。 拆装器和组装器都属于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]执行一系列处理步骤对消息，其中包括转换到或从 XML、 解码或编码的管道和消息验证。  
  
- 使系统可以接收或发送 HL7 基于消息的最小的较低层协议 (MLLP) 适配器的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]通常会将使用 MLLP 协议传输。 MLLP 适配器可确保[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]是与基于 HL7 消息传送应用程序进行互操作。  
  
- 使系统能够接收 HL7 编码的消息的 HL7 消息架构。  
  
## <a name="btahl72xml-message-processing"></a>BTAHL72XML 消息处理  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 添加功能和工具，使系统能够处理 XML 消息的数。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 若要启用将 HL7 消息转换为 XML 格式[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，该 XML 在内部使用，来对消息执行操作。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 仅对 HL7 V2 执行到 XML 的转换。X 的消息，因为它们是以本机方式在平面文件格式。 它不会为 XML 格式的 2.XML 消息执行转换。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 分析并验证而不转换这些消息。  
  
 支持的 XML 消息架构是[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML 架构生成的 HL7 V2 的 HL7 组织。XML 版本和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X 架构用于 HL7 V2。X 版本的消息 （采用平面文件格式）。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 包括文档规范、 应用程序和所需开发和部署用于处理的全部组件[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML 事务。 以下[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]组件执行[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML 消息处理：  
  
- XML 拆装器和组装器，使系统能够解析和序列化与 HL7 消息相对应的 XML 消息。 XML 拆装器和组装器进行了改进的功能超出[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML 拆装器和组装器，包括自动确认和消息验证。  
  
- HL7 兼容 XML 架构，使系统能够接收 HL7 消息 (这两个 V2。X 和 V2。XML 消息）。 系统会将 V2。X 消息为 XML 消息 (V2。XML 消息已在 XML 中），然后将其发送到已启用 XML 的另一个系统。 同样，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以接收 XML 消息，然后将其转换成 HL7 发送。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 使用基于 XML 的文档规范，连同 HL7 分析器、 映射和其他转换来自或发往另一种格式的 HL7 特定于数据[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用架构和映射的工具。 例如，可能收到的交换标准 HL7 V2.0 格式或版本 2.5 格式，并将该数据转换为另一种格式，可以使用现有的医疗应用程序。  
  
## <a name="validation"></a>验证  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 执行验证的 HL7 V2。X 消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]无法执行。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 自动执行的 HL7 消息标头的语法和示意图验证，并自动执行某些结构验证的 HL7 消息的正文。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 如果启用该功能，则执行的 HL7 消息正文的示意验证 (请参阅[验证设置](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md))。  
  
 HL7 编码的消息的正文的验证包括架构、 数据格式，某些标头和正文字段和枚举值。 2.XML 消息的验证包括根据其架构，这是标准的 XML 验证进行验证。 有关详细信息，请参阅[BTAHL72X 平面文件处理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)并[BTAHL72XML 处理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)。  
  
## <a name="auto-acknowledgment"></a>自动确认  
 若要确保消息传送系统的可靠性，你可能需要确认 (ACK) 到 HL7 消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成自动根据配置设置。  
  
 原始模式 Ack 确认验证结果的消息标头和正文。 在增强模式下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成两种类型的确认： 的接受在验证标头，它将发送的确认和一个应用程序在完整的消息验证发送的确认。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 收到来自业务线应用程序生成了延迟的确认[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 有助于确认处理支持双向消息传输。  
  
## <a name="batching"></a>批处理  
 可以处理在批处理模式下，将保存处理开销的文档。 你还可以批处理对这些批响应。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 支持三种类型的批处理用于 HL7 2.X 消息：  
  
- 入站批处理，在其中系统作为一批接收消息，然后为单个消息片段它。  
  
- 在批处理/批处理，在其中系统同时接收和发送消息以批形式。  
  
- 创建批处理时，系统会发送一批消息视为单条消息接收。  
  
  > [!NOTE]
  >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 不为 V2 提供批处理功能。XML 消息。  
  
## <a name="logging"></a>日志记录  
 若要提高故障排除，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]会生成错误或警告的系统组件发送信号的报告。 可以筛选此类事件，将其存储在任何三个日志存储 ([!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件日志中，WMI，或[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]日志存储区)，或使用自定义它们[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]SDK。  
  
## <a name="configuration-explorer"></a>配置资源管理器  
 你可以配置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]参与方、 批处理、 确认和存储中的日志[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，一种管理工具添加到工具的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]提供。 此工具还可以启动与参与方级别的批处理。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] SDK 允许你自定义这些设置以编程方式。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何满足业务需求](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)