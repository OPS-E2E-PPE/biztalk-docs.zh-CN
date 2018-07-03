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
ms.openlocfilehash: a0323bde34a7ef9abcbba15d8dd8059fee0c51c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012006"
---
# <a name="configuring-encoding-agreement-properties"></a>配置编码协议属性
贸易合作伙伴协议 (TPA) 是两个贸易合作伙伴之间为通过特定 B2B 协议对消息进行事务处理而使用的最终绑定协议。 简言之，TPA 是两个业务配置文件之间为使用特定消息编码协议（X12 或 EDIFACT）或特定传输协议 (AS2) 以及彼此交换 B2B 消息所进行的一种了解。 除了编码和传输协议达成一致之外，协议还可用于自定义如何构成和传送消息。  
  
- 作为编码协议设置的一部分，您还可以定义发送方是否希望确认、消息将进行批处理还是立即发送等。  
  
- 作为传输协议设置的一部分，您还可以定义消息是否已经标记，以及消息是否已经加密等。  
  
  > [!NOTE]
  >  有关传输协议 (AS2) 设置的详细信息，请参阅[配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)。  
  
  创建协议时，必须考虑以下注意事项：  
  
- 两参与方之间的贸易合作伙伴协议是双向的。 两个参与方（参与方 A 和参与方 B）之间的单个协议可用于将消息从参与方 A 发送到参与方 B，还可以接收从参与方 B 到参与方 A 的消息。为在用户界面中表示双向协议，使用一个选项卡表示每个单向协议。因此，在协议用户界面中，您将看到两个选项卡**PartyA-> 参与**（表示消息从参与方 A 发送到参与方 B 的单向协议） 和**参与-> PartyA** (表示单向协议的消息从参与发送到 PartyA。）  
  
- 每个单向协议适用于一个端对端消息事务。 发送或接收确认也是同一消息事务的组成部分，因此应在相同的单向协议选项上进行配置。例如，考虑到参与方 B 的 EDI 交换的参与方 A 发送和响应，参与方 B 将确认发送回 a 方。因此，必须在与发送交换和需要确认相关的所有属性上都设置**PartyA-> 参与**选项卡。  
  
  > [!NOTE]
  >  即使确认是相同消息事务的一部分，应如何生成确认相关的属性中配置**参与-> PartyA**选项卡。这是必需的因为确认上下文属性发送方和接收方限定符设置为在指定的值相反**PartyA-> 参与**选项卡。例如，如果发送方和接收方标识符在交换消息要向其解析的协议中设置为 THEM 和 US，则发送方和接收方的上下文属性在确认中将设置为 US 和 THEM。 通常，其他单向协议选项卡中的发送方和接收方标识符也应分别设置为 US 和 THEM。 因此，确认消息将解析为该协议，并且将提取属性设置。 因此，如果你想要让确认使用不同的元素分隔符或如果想要让确认使用 CR LF，指定的属性中**参与-> PartyA**选项卡。  
  >   
  >  从概念上讲，将从任何单向协议选项卡上提取具有与确认上下文属性中设置的相同发件人和接收方限定符的确认的属性。 但是，为了便于实际使用，你通常会在你创建的交换将解析为的协议的其他单向协议选项卡中设置此属性。  
  
- 您可以具有编码协议（以定义要用于消息的消息编码）和传输协议（以定义要用于交换消息的传输协议）。 具有编码协议是必需的。 仅当参与方希望使用 AS2 协议传输消息时，才能选择 AS2 协议。 例如，如果两个参与方选择通过电子邮件传输消息，则无需选择 AS2 协议。  
  
  > [!NOTE]
  >  有关 AS2 协议的详细信息，请参阅[配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置特定于 X12 的协议属性](../core/configuring-x12-specific-agreement-properties.md)  
  
-   [配置特定于 EDIFACT 的协议属性](../core/configuring-edifact-specific-agreement-properties.md)