---
title: 配置全局或后备协议属性 |Microsoft 文档
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
ms.openlocfilehash: 0eb693a17cad17eadaf0d005d12075dde30daa33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233205"
---
# <a name="configuring-global-or-fallback-agreement-properties"></a>配置全局或后备协议属性
当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 没有发现交换要解析到的目标协议时，会使用备用协议属性来处理消息。 如果协议已知，则不使用备用协议属性，并且备用协议属性不应用于任一或所有协议。  
  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到消息时，会尝试将协议的发送方信息与消息中的发送方信息匹配。 对于 X12 消息，发送方信息位于 ISA5 和 ISA6 数据元素中；对于 EDIFACT，则位于 UNB2.1 和 UNB 2.2 数据元素中。 协议信息，请参阅的单向协议选项卡中的标识符选项卡**协议属性**对话框。 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 没有发现协议，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用备用协议属性来确定命名空间、处理消息和发送任何确认。  
  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送消息时，EDI 发送管道通过将订阅 MessageBox 中的 XML 消息的发送端口和协议关联的发送端口匹配，来确定该消息会解析为的目标协议。 如果发送端口不与协议相关联，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用备用协议属性来处理要发送的消息。  
  
> [!NOTE]
>  发送端口关联只是执行协议解析的一种方式。 有关为传出消息的协议解析的详细信息，请参阅[协议解析和传出的 EDI 消息的架构确定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置 X12 回退协议属性](../core/configuring-x12-fallback-agreement-properties.md)  
  
-   [配置 EDIFACT 回退协议属性](../core/configuring-edifact-fallback-agreement-properties.md)  
  
## <a name="see-also"></a>另请参阅  
 [协议在 EDI 处理过程中的角色](../core/the-role-of-agreements-in-edi-processing.md)