---
title: 协议设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 224a9837-5c85-4511-b6d9-c8fda63a27d1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c2a61bb26ae330b6ccb1e296d277ecdeebb2d11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398447"
---
# <a name="protocol-settings"></a>协议设置
## <a name="overview"></a>概述
创建业务配置文件，反映组织内的业务部门后, 企业需要声明的参数定义进行业务配置文件之间通信的方式放置。 这些通信参数被定义为协议设置。 协议设置定义的特定 B2B 协议支持业务事务的方式。 每个业务配置文件定义用于处理消息 （编码） 或传输消息 （传输） 合作伙伴可以为每个 B2B 协议对其进行通信的各种设置。 在以下两个类别下定义的业务配置文件的通信参数：  
  
- **编码协议设置**:编码协议控制结构和 B2B 消息的内容。 为业务配置文件的编码协议设置定义业务部门用来发送和接收 B2B 消息的编码协议。 编码协议的一些示例包括 X12、 EDIFACT、 HL7，等等。对于大约详细的讨论受支持的编码协议[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，请参阅[EDI 标准支持](../core/edi-standards-support.md)。 作为编码协议的一部分，您可以提供各种设置，例如是否发送参与方期望确认、 消息进行批处理还是立即发送等。你可以始终覆盖这些设置作为贸易合作伙伴协议的一部分。 请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。  
  
- **传输协议设置**:传输协议控制用于发送两个合作伙伴之间来回的消息的传输通道。 由于传输实质上是两个传输终结点之间，每个业务配置文件定义其自己的"传输终结点"配置和通信的单一"传输终结点"的其贸易合作伙伴的业务配置文件。 有关支持的传输协议的信息，请参阅[BizTalk Server 中的 AS2 支持](../core/as2-support-in-biztalk-server.md)。 作为传输协议的一部分，您可以提供各种设置，例如是否应对消息进行签名，是否应对消息进行加密，等等。你可以始终覆盖这些设置作为贸易合作伙伴协议的一部分。 有关协议的详细信息，请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。  
  
  通过定义协议设置，业务配置文件声明的消息格式和要用于贸易合作伙伴之间发送 B2B 消息的传输协议。  
  
> [!NOTE]
>  作为业务配置文件的一部分定义的协议设置是可选的。 如果不指定协议设置作为业务配置文件的一部分，您始终可以指定这些协议中。  
  
 下图说明了贸易合作伙伴、 业务配置文件和协议设置融合到 TPM 解决方案中：  
  
 ![贸易合作伙伴配置文件和协议设置](../core/media/protocolsettings.gif "ProtocolSettings")  
  
 在上图中，"发货"业务配置文件可以发送和接收的 X12 编码格式通过 AS2 传输协议发送的消息。 同样，"发票"发货配置文件可以通过发送和接收消息的 X12 和 EDIFACT 编码格式的 AS2 传输协议。  
  
 它是现在显而易见如何定义业务配置文件是有助于创建 TPM 解决方案中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 目前，如图所示，"发货"业务配置文件只能发送和接收 X12 消息。 因此，与"发货"业务配置文件进行通信的任何业务配置文件必须遵守属性设置为"Shipping"业务配置文件。 但是，在将来，如果"发货"业务配置文件开始接受具有 EDIFACT 编码的消息，它只需将相关属性设置为包括 EDIFACT 支持。 合作伙伴组织不必创建新的业务配置文件为同一发货部门。  
  
## <a name="do-i-always-need-to-specify-the-protocol-settings-when-creating-a-business-profile"></a>是否始终需要创建业务配置文件时指定的协议设置？  
 从理论上来说，是的业务配置文件必须包含协议设置定义。 但是，这并不意味着在 TPM 用户界面中创建业务配置文件时，必须定义协议设置。 TPM 可创建业务配置文件或创建贸易合作伙伴协议时指定的协议设置的灵活性。 如果定义协议设置作为业务配置文件的一部分，它们将为您创建该配置文件的贸易合作伙伴协议时可用。 但是，如果协议设置定义为协议的一部分，您将必须提供所有值作为协议的一部分。  
  
> [!IMPORTANT]
>  如果未定义协议设置作为业务配置文件的一部分，你需要输入的值作为该业务配置文件中，每个协议的一部分这违背了新 TPM 解决方案的可伸缩性模型。 因此，Microsoft 建议您定义每个业务配置文件的协议设置。 如有必要，创建贸易合作伙伴协议时，始终可以重写这些设置。  

## <a name="learn-next"></a>接下来了解
[贸易合作伙伴协议](../core/trading-partner-agreement.md)  
[配合使用：定义贸易合作伙伴管理解决方案](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)  
  
## <a name="see-also"></a>请参阅  
 [贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)