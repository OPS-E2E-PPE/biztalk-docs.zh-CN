---
title: 配置编码协议属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.ediagreement.properties
ms.assetid: 0cb1146e-177c-42fa-b1d8-a834229c2af9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e6beaea054912934bee2826eaa1aa92b7060ad5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391264"
---
# <a name="configuring-encoding-agreement-properties"></a>配置编码协议属性
贸易合作伙伴协议 (TPA) 是用于通过特定 B2B 协议处理消息的两个贸易合作伙伴之间达成的权威且绑定协议。 简言之，TPA 是一种了解两个业务配置文件使用特定的消息交换 B2B 消息与每个其他编码协议 （x12 或 EDIFACT） 或特定的传输协议 (AS2) 之间。 除了达成的编码和传输协议，协议可用于自定义如何构成和传送消息。  
  
- 作为编码协议设置的一部分，还可以定义消息进行批处理还是立即发送等，发送方是否期望确认、。  
  
- 作为传输协议设置的一部分，您还可以定义是否应对消息进行签名，是否应对消息进行加密，等等。  
  
  > [!NOTE]
  >  有关传输协议 (AS2) 设置的详细信息，请参阅[配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)。  
  
  创建协议时，必须考虑以下注意事项：  
  
- 两个参与方之间的贸易合作伙伴协议是双向的。 可以使用两个参与方 （参与方 A 和参与方 B） 之间的单个协议，以将消息从参与方 A 发送到参与方 B 以及接收消息从参与方 B 到参与方 a。若要表示的用户界面中的双向协议，每个单向协议表示单个选项卡中。因此，在协议用户界面中，您将看到两个选项卡**PartyA-> 参与**（表示消息从参与方 A 发送到参与方 B 的单向协议） 和**参与-> PartyA** (表示单向协议的消息从参与发送到 PartyA。）  
  
- 每个单向协议适用于一个端到端消息事务。 发送或接收确认也是同一消息事务的一部分，因此应在相同的单向协议选项卡上进行配置。例如，考虑到参与方 B 的 EDI 交换的参与方 A 发送和响应，参与方 B 将确认发送回 a 方。因此，必须在与发送交换和需要确认相关的所有属性上都设置**PartyA-> 参与**选项卡。  
  
  > [!NOTE]
  >  即使确认是相同消息事务的一部分，应如何生成确认相关的属性中配置**参与-> PartyA**选项卡。这是必需的因为确认上下文属性发送方和接收方限定符设置为在指定的值相反**PartyA-> 参与**选项卡。例如，如果发送方和接收方标识符在交换消息解析成，则发送方和接收方上下文属性将设置为 US 和 THEM 在确认消息的协议被设置为 THEM 和 US。 通常情况下，其他单向协议选项卡还会发送方和接收方的标识符分别设置为 US 和 THEM。 因此，确认消息将解析为该协议并将有选择地设置的属性。 因此，如果你想要让确认使用不同的元素分隔符或如果想要让确认使用 CR LF，指定的属性中**参与-> PartyA**选项卡。  
  >   
  >  从概念上讲，确认属性将有选择地从任何单向协议选项卡中具有相同的发送方和接收方限定符的确认上下文属性中设置。 但是，对于便于实际使用，可以将通常设置这在您创建该交换将解析到协议的其他单向协议选项卡中。  
  
- 您可以具有编码协议 （以定义要使用的消息编码的消息） 和传输协议 （以定义要用于交换消息的传输协议）。 具有编码协议是必需的。 参与方可以选择他们想要使用 AS2 协议传输消息的情况下，才有 AS2 协议。 例如，如果两个参与方选择通过电子邮件传输消息，则不需要 AS2 协议。  
  
  > [!NOTE]
  >  有关 AS2 协议的详细信息，请参阅[配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置特定于 X12 的协议属性](../core/configuring-x12-specific-agreement-properties.md)  
  
-   [配置特定于 EDIFACT 的协议属性](../core/configuring-edifact-specific-agreement-properties.md)