---
title: 不同类型的 BizTalk 架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad8847d3-6f0e-4982-b4a8-92a5f39a4b48
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051cd8fb9824cece316ea6f56e318490eacf88c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240277"
---
# <a name="different-types-of-biztalk-schemas"></a>不同类型的 BizTalk 架构
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持以下四种类型的架构：  
  
-   **XML 架构**。 XML 架构用于定义 XML 实例消息类的结构。 由于此类架构使用 XML 架构定义 (XSD) 语言来定义 XML 实例消息的结构，并且 XSD 也专门用于此目的，因此这类架构以一种简便方式使用 XSD。  
  
-   **平面文件架构**。 平面文件架构用于定义使用平面文件格式的实例消息类的结构，可以是分隔格式或位置格式，或者是两种格式的组合。 因为 XSD 的本机语义功能不适应所有定义的平面文件实例消息结构的要求，如可能用于不同的记录和平面文件中的字段的分隔符的各种类型-BizTalk Server 使用 XSD 的批注功能来存储在 XSD 架构中的此额外信息。 BizTalk Server 定义了一组丰富的特定批注标记，可用于存储所需的所有其他信息。  
  
-   **信封架构**。 信封架构是一种特殊类型的 XML 架构。 信封架构用于定义 XML 信封的结构，以用于将一个或多个 XML 业务文档包装到单个 XML 实例消息中。 在将 XML 架构定义为信封架构时，根据是否在信封架构中定义了多个根记录，可能需要其他一些属性设置。  
  
-   **属性架构**。 属性架构要结合 BizTalk Server 中存在的称为属性升级的两种机制之一来使用。 属性升级是将特定的值从实例消息的深层复制到消息上下文的过程。 这样，各种 BizTalk Server 组件可以更容易地从消息上下文访问这些值。 这些组件使用这些值来执行诸如消息路由之类的各种操作。 您也可以按其他方向复制升级的属性值，例如，在实例消息发送到其目标之前，将其从更易于访问的消息上下文复制回实例消息的深层。 属性架构是 BizTalk 架构的简化版本，它在实例消息和消息上下文之间来回复制升级属性的过程中起到一定作用。  
  
 本主题的其余部分介绍有关 BizTalk Server 中这四种类型架构的其他信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [XML 架构](../core/xml-schemas.md)  
  
-   [平面文件架构](../core/flat-file-schemas.md)  
  
-   [信封架构](../core/envelope-schemas.md)  
  
-   [属性架构](../core/property-schemas.md)