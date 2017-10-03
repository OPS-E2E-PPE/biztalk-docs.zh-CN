---
title: "协议设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 224a9837-5c85-4511-b6d9-c8fda63a27d1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a8fe9e7024bfe3a9d5f1d5d7727a2115bcd31a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# 协议设置
## 概述
创建用于反映组织内业务部门的业务配置文件之后，企业需要声明用于定义业务配置文件之间如何通信的参数。 这些通信参数被定义为协议设置。 协议设置定义对于特定 B2B 协议如何支持业务事务。 对于合作伙伴可以通过其进行通信的每个 B2B 协议，每个业务配置文件定义用于处理消息（编码）或传输消息（传输）的各种设置。 定义的业务配置文件的通信参数分为以下两个类别：  
  
-   **编码协议设置**： 编码协议控制结构和 B2B 消息的内容。 业务配置文件的编码协议设置定义业务部门用于发送和接收 B2B 消息的编码协议。 编码的协议的一些示例包括 X12、 EDIFACT HL7，等等。有关详细的讨论大约支持编码的协议[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，请参阅[EDI 标准支持](../core/edi-standards-support.md)。 作为编码的协议的一部分，你可以提供各种设置，例如是否发送方需要确认时，是否对消息进行批处理，还是单独，发送等。你始终可以作为贸易合作伙伴协议的一部分来覆盖这些设置。 请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。  
  
-   **传输协议设置**： 传输协议控制传输通道用于发送两个合作伙伴之间来回的消息。 由于传输实质上是在两个传输终结点之间进行，因此每个业务配置文件定义其自身的“传输终结点”配置，并与其贸易合作伙伴的业务配置文件的单一“传输终结点”进行通信。 有关支持的传输协议的信息，请参阅[BizTalk Server 中的 AS2 支持](../core/as2-support-in-biztalk-server.md)。 作为传输协议的一部分，你可以提供各种设置，例如是否应对消息进行签名，是否应对消息进行加密，等等。你始终可以作为贸易合作伙伴协议的一部分来覆盖这些设置。 有关协议的详细信息，请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。  
  
 通过定义协议设置，业务配置文件声明用于在贸易合作伙伴之间发送 B2B 消息的消息格式和传输协议。  
  
> [!NOTE]
>  将协议设置定义为业务配置文件的一部分是可选的。 如果您不指定协议设置作为业务配置文件的一部分，则可以始终在协议中指定这些设置。  
  
 下图说明了贸易合作伙伴、业务配置文件和协议设置如何融合到 TPM 解决方案中。  
  
 ![贸易合作伙伴配置文件和协议设置](../core/media/protocolsettings.gif "ProtocolSettings")  
  
 在上图中，“发货”业务配置文件可以发送和接收通过 AS2 传输协议发送的 X12 编码格式的消息。 同样，“发票”发货配置文件可以发送和接收通过 AS2 传输协议发送的 X12 和 EDIFACT 编码格式的消息。  
  
 现在，如何定义业务配置文件显然对于在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中创建 TPM 解决方案很有帮助。 目前，如图所显，“发货”配置文件只能发送和接收 X12 消息。 因此，与“发货”业务配置文件进行通信的任何业务配置文件将必须符合“发货”业务配置文件的属性设置。 但是，未来，如果“发货”业务配置文件开始接受具有 EDIFACT 编码的消息，则只需将相关属性设置为包括 EDIFACT 支持。 合作伙伴组织不需要为同一发货部门创建新的业务配置文件。  
  
## 创建业务配置文件时，总是需要指定协议设置吗？  
 从理论上来说，是的，业务配置文件必须包含协议设置定义。 但是，这并不意味着在 TPM 用户界面中创建业务配置文件时必须定义协议设置。 TPM 允许您在创建业务配置文件或创建贸易合作伙伴协议时，可根据需要来指定协议设置。 如果定义协议设置作为业务配置文件的一部分，则为该配置文件创建贸易合作伙伴协议时，将可以使用这些设置。 但是，如果将协议设置定义为该协议的一部分，则将必须提供所有值作为该协议的一部分。  
  
> [!IMPORTANT]
>  如果未将协议设置定义为业务配置文件的一部分，则将需要输入值作为该业务配置文件的每个协议的一部分，因此阻止了新 TPM 解决方案的可伸缩性模型。 因此，Microsoft 建议您为每个业务配置文件定义协议设置。 如果需要，您可以在创建贸易合作伙伴协议时始终覆盖这些设置。  

## 了解下一步
[贸易合作伙伴协议](../core/trading-partner-agreement.md)  
[综合： 定义一个贸易合作伙伴管理解决方案](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)  
  
## 另请参阅  
 [贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)