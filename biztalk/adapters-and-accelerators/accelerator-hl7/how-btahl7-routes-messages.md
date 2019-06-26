---
title: BTAHL7 如何路由消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- routing, about routing
- routing, messages
- messages, routing
- BTAHL7, message routing
ms.assetid: 555696c7-6023-44eb-b13d-cf7527bbc92f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b4223648bc62cf748640a9528a831deafdafa2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292933"
---
# <a name="how-btahl7-routes-messages"></a>BTAHL7 如何路由消息
Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 利用的消息处理功能的 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，而且还在特定于 HL7 消息传送要求多种扩展它。  

## <a name="routing-overview"></a>路由概述

HL7 从业务线 (LOB) 系统接收消息，并可能会收到它们使用 MLLP 适配器。 LOB 系统连接到处的 MLLP 适配器上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]通过 TCP 端口，然后向处的 MLLP 适配器发送消息。

在中 **[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本**，HL7 MLLP 接收远程 LOB 系统连接到 MLLP 传输适配器等待。 LOB 系统远程 LOB 系统连接后，将使用为 MLLP 的消息发送[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 具体来说： 

1. 远程 LOB 系统连接到本地处的 MLLP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用 TCP 端口 
2. BTA4HL7 的接收位置处的 MLLP 适配器接受连接 
3. 远程 LOB 系统将一个或多个消息传递 
4. 断开与远程 LOB 系统的连接

在中 **[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]和更高版本**、 由处的 MLLP 适配器，启动与 LOB 系统的连接，并为 MLLP 的 LOB 系统推送消息接收。 换而言之，远程 LOB 系统等待向 MLLP 发送消息传递之前的连接。 具体来说： 

1. 本地[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]连接到远程 LOB 系统使用的 TCP 端口 
2. BTA4HL7 的接收位置处的 MLLP 适配器启动连接 
3. 远程 LOB 系统将一个或多个消息传递 
4. 断开与远程 LOB 系统的连接 

用于向后兼容性，可以使用原始的默认行为，远程 LOB 系统会启动连接。 此选项是可在 MLLP 中配置接收位置属性。 
 
一旦收到 HL7 消息，然后提交到 HL7 接收管道。 在此管道中，HL7 反汇编程序将分析该消息，并将验证根据相应的架构定义和验证配置的消息。 在此情况下，确认消息可能是 HL7 生成 （成功或错误），根据消息和相关确认配置的有效性。 在这里，管道将提交的消息实例和可选确认到 MessageBox 数据库，以进一步处理和路由。  
  
 在 MessageBox 数据库中，收到的消息实例后[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]检查基于筛选器的订阅，并将消息路由到一个或多个通过 HL7 发送管道的发送端口 （可能是 MLLP 端口）。 发送管道可能会验证消息实例根据相应的架构定义和验证配置。 除了验证，则可以重写的传出消息的 MSH 段中的某些字段值。 如果多个端口已订阅的一条消息，并且每个接收应用程序的 MSH 段值内的唯一期望这种重写功能特别有用。  
  
 当然，所有其他[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]发送和接收端口功能将可供 HL7 消息，以及可能是唯一的选择的端口类型，如 MLLP 发送端口参数的某些功能。 相关示例[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]功能是能够将转换映射应用于出站消息。  
  
## <a name="how-routing-works"></a>路由的工作原理

[!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)]路由 HL7 消息根据订阅的 MessageBox 数据库会管理实例。 这些订阅的每个发送端口使用你定义的筛选器。 示例筛选器可能包括路由基于在接收端口 ID 和/或 HL7 消息类型 (ADT ^ A03，例如) 和/或发送应用程序 （MSH3.1 值）。  
  
 除了需要设置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]订阅，您需要执行一些特定于 HL7 的消息传送配置将影响 HL7 消息实例作为[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将其路由。 此附加配置，可应用唯一 HL7 验证规则、 自动生成的确认和重写 MSH 值的功能。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] 应用此配置在参与方级别。 您需要定义参与方在 BizTalk 资源管理器并执行中的相关的 HL7 配置[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]配置资源管理器。  
  
 若要将唯一 HL7 消息传送配置 （例如，验证或 MSH 替代） 应用于多个订阅的消息的发送端口，需要创建参与方之间的关联和发送端口。 为在 BizTalk 浏览器中的参与方属性配置参与方发送端口关联。  
  
 如果您不需要将消息路由 HL7 到多个发送端口，或将唯一 HL7 处理配置应用到多个发送端口，可以排除将参与方与发送端口相关联的步骤。 在这种情况下，[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]将参与方相关联的 HL7 消息 (MSH 3.1) 中的接收应用程序字段通过其 HL7 消息配置。 这种情况下是最可能出现在 HL7 interrogative （请求/响应） 消息交换。  
  
## <a name="see-also"></a>请参阅  
 [消息验证](../../adapters-and-accelerators/accelerator-hl7/message-validation.md)