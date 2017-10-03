---
title: "BTAHL7 将消息的路由 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- routing, about routing
- routing, messages
- messages, routing
- BTAHL7, message routing
ms.assetid: 555696c7-6023-44eb-b13d-cf7527bbc92f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61dd223a014ae8ea7de35d8d73f1a7cf7ef35449
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-btahl7-routes-messages"></a>BTAHL7 将消息的路由
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 利用的消息处理功能[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，，但也有几个方面特定于 HL7 消息传送要求对它进行扩展。  

## <a name="routing-overview"></a>路由概述

HL7 从业务线 (LOB) 系统，接收消息，并可能会收到它们使用 MLLP 适配器。 LOB 系统连接到 MLLP 适配器上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]通过 TCP 端口，然后发送消息给 MLLP 适配器。

在**[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本**，HL7 MLLP 接收传输适配器等待远程的 LOB 系统，以连接到 MLLP。 LOB 系统远程 LOB 系统连接后，将使用到 MLLP 消息发送[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 具体来说： 

1. 远程 LOB 系统连接到本地上的 MLLP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用 TCP 端口 
2. BTA4HL7 接收位置使用 MLLP 适配器接受连接 
3. 远程 LOB 系统将一个或多个消息传送 
4. 远程 LOB 系统断开连接

在**[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]和更高版本**、 由 MLLP 适配器中，启动到 LOB 系统的连接，然后 MLLP 到 LOB 系统推送消息接收。 换而言之，远程 LOB 系统等待发送消息传递到 MLLP 之前连接。 具体来说： 

1. 本地[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]连接到远程 LOB 系统使用的 TCP 端口 
2. BTA4HL7 接收位置使用 MLLP 适配器将启动连接 
3. 远程 LOB 系统将一个或多个消息传送 
4. 远程 LOB 系统断开连接 

用于获取向后兼容性，你可以使用原始的默认行为这样远程 LOB 系统会启动连接。 此选项是可配置在 MLLP 接收位置属性。 
 
一旦收到 HL7 消息，然后提交给 HL7 接收管道。 在此管道中 HL7 反汇编程序将分析消息，并将验证根据相应架构定义和验证配置的消息。 此时，可能是确认消息 HL7 生成 （成功或错误），根据消息和相关确认配置的有效性。 从此处，管道将提交的消息实例和可选确认 MessageBox 数据库即可获取进一步的处理和路由。  
  
 在 MessageBox 数据库中，抵达的消息实例后[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]检查基于筛选器的订阅并将消息路由到一个或多个通过 HL7 发送管道发送端口 （可能 MLLP 端口）。 发送管道可能会验证消息实例根据相应架构定义和验证配置。 除了验证，则可以重写在传出消息的 MSH 段中的某些字段值。 如果多个端口已经订阅了一条消息，并且每个接收应用程序在 MSH 段值的唯一预期此替代功能特别有用。  
  
 当然，所有其他[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]发送和接收端口功能将可供 HL7 消息，以及可能是唯一的所选的端口类型，例如 MLLP 发送端口参数的某些功能。 相关示例[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]功能是将转换映射应用到出站消息的能力。  
  
## <a name="how-routing-works"></a>路由的工作原理

[!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)]路由 HL7 消息根据 MessageBox 数据库管理的订阅的实例。 这些订阅定义筛选器用于每个发送端口。 示例筛选器可能包括路由基于接收端口 ID 和/或 HL7 消息类型 (ADT ^ A03，例如) 和/或发送应用程序 （MSH3.1 值）。  
  
 除了设置之外[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]订阅，你需要执行一些会影响 HL7 消息实例的 HL7 特定消息传送配置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将其路由。 此额外的配置，可以将应用唯一的 HL7 验证规则、 自动生成的确认和能够替代 MSH 值。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]应用方级别的此配置。 你需要定义内 BizTalk 资源管理器当事方，并执行中的相关的 HL7 配置[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]配置资源管理器。  
  
 若要将唯一 HL7 消息传送配置 （例如，验证或 MSH 重写） 应用于多个订阅一条消息的发送端口，你需要创建参与方之间的关联和发送端口。 作为 BizTalk 资源管理器中的参与方属性中配置方发送端口关联。  
  
 如果你不需要将消息路由 HL7 到多个发送端口，或将唯一的 HL7 处理配置应用到多个发送端口，则可以消除与发送端口相关联的参与方的步骤。 在这种情况下，[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]将方相关联的 HL7 消息 (MSH 3.1) 中的接收应用程序字段通过其 HL7 消息配置。 这种情况下是最可能出现在 HL7 interrogative （请求/响应） 消息交换。  
  
## <a name="see-also"></a>另请参阅  
 [消息验证](../../adapters-and-accelerators/accelerator-hl7/message-validation.md)