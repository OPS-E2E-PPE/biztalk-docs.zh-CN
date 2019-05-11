---
title: 配置全局或后备协议属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c375d03-6f22-4a67-9eac-d8896de2f7ee
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d44624a4f505cf7d3c4e53fe55e4203917cf41f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391075"
---
# <a name="configuring-global-or-fallback-agreement-properties"></a>配置全局或后备协议属性
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用后备协议属性来处理一条消息时不会发现的交换解析为该协议。 当已知协议时，不使用后备协议属性并不适用于任何或所有协议。  
  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收消息时，它将尝试匹配与消息中的发件人信息协议的发送方信息。 发件人信息位于 ISA5 和 ISA6 数据元素中的 X12 消息，以及对于 EDIFACT UNB2.1 和 UNB 2.2 数据元素。 在单向协议选项卡中的标识符选项卡中的协议信息是**协议属性**对话框。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不会发现协议，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用后备协议属性来确定的命名空间、 处理消息，并发送任何确认。  
  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]协议消息解析到由匹配的发送端口订阅到该 XML 消息在 MessageBox 中，并且与该协议关联的发送端口发送消息，EDI 发送管道确定。 如果发送端口不是与某个协议关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用后备协议属性来处理发送的消息。  
  
> [!NOTE]
>  发送端口关联是执行协议解析的只有一种方法。 有关对传出消息的协议解析的详细信息，请参阅[协议解析和架构确定传出 EDI 消息的](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置 X12 后备协议属性](../core/configuring-x12-fallback-agreement-properties.md)  
  
-   [配置 EDIFACT 后备协议属性](../core/configuring-edifact-fallback-agreement-properties.md)  
  
## <a name="see-also"></a>请参阅  
 [协议在 EDI 处理中的角色](../core/the-role-of-agreements-in-edi-processing.md)