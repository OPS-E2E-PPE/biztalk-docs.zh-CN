---
title: 有关实例消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de7fc3d3-57a7-4df9-b981-127e21941e22
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf956fb9f201697ac8c2b7da2135e469e03de55e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224773"
---
# <a name="about-instance-messages"></a>有关实例消息
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送和接收实例消息，每个实例消息通常表示诸如采购订单之类的一个或多个业务文档。 实例消息是由一个或多个架构定义的消息结构的实例。 一个架构或者一起使用的一组架构将定义有效实例消息的组成部分。 例如，采购订单可能定义为在其中具有若干记录（如 ShipTo 记录、BillTo 记录和 Items 记录等）。 这些记录中的每一个都可以定义为包含它们自己的子记录和字段。 相应的架构定义这些记录和字段的潜在内容，相应的实例消息包含实际采购订单，这些采购订单又包含根据架构组织的采购订单数据。  
  
 BizTalk Server 可以通过可扩展的各种格式发送和接收实例消息，但 XML 格式具有特别意义，因为所有消息格式都翻译为该格式以供内部处理。 特定的 XML 文档使用定义好的一组开始和结束标记（按层次结构排列）来组织消息中的数据，确定一个数据项结束、另一个数据项开始的位置。 一个或多个相应 XML 架构将定义可在其他标记内使用的标记及其使用顺序，从而控制一致性消息的结构。  
  
 另一个格式大类（称为平面文件格式）常用于旧系统。 这些格式使用某些分隔符（例如制表符）和固定长度的字段的组合来确定一个数据项结束、另一个数据项开始的位置。  
  
 本部分提供了通常由 BizTalk Server 处理的这两种类型消息的结构的高级概述。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [XML 消息的结构](../core/structure-of-an-xml-message.md)  
  
-   [平面文件消息的结构](../core/structure-of-a-flat-file-message.md)