---
title: 规划架构创建 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ecb9154-b457-4209-b9b9-572c186bf5e7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60fc7a3cafb3f13a189383df70d4b9ea0bf98f54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264637"
---
# <a name="planning-for-schema-creation"></a>规划架构创建
使用架构，可以验证应该符合架构的消息实例、定义如何在不同格式的实例消息（XML 和非 XML）之间进行翻译、定义如何将一种结构的 XML 实例消息转换成不同结构的 XML 实例消息。 有关实例消息转换和实例消息转换之间的区别的详细信息，请参阅[转换 vs。转换](../core/data-transformation.md)。  
  
 下表列出了在使用 BizTalk 编辑器规划架构创建时需要回答的一些问题。  
  
|规划问题|建议|  
|-----------------------|--------------------|  
|需要创建哪些架构？|列出要使用 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进行处理的业务文档的列表。 此列表中应包括如采购订单、发票、发货确认等信息。 该列表也可能包括多个这样的业务文档，例如，从一个贸易合作伙伴接收到的采购订单的结构与从另一个贸易合作伙伴接收到的采购订单的结构不同。|  
|我发送和接收的文档是否已经以 XML 形式表示？|向文档列表添加有关发送和接收的每种业务文档的格式信息，可能是 XML 或其他某种格式（例如分隔或位置平面文件格式）。|  
|哪些起点可用于在列表上创建架构？|尽管有时有必要，但创建架构比从支持的源之一生成架构会困难得多。 如果您的架构已经是以 XML 架构定义 (XSD) 语言表示的，则没有必要生成架构，只需在 BizTalk 编辑器中将其打开即可。<br /><br /> 如果您具有格式正确的 XML 实例消息，以文档类型定义 (DTD) 表示的架构或以精简 XML 数据 (XDR) 表示的架构，则您可以自动生成架构。 您可能需要使用 BizTalk 编辑器修改生成的架构，但您将为自己节省一些工作量。 分步说明，请参阅"从非 XSD 源生成架构"的过程中[创建架构的 XML 消息](../core/how-to-create-schemas-for-xml-messages.md)。<br /><br /> 如果这些起点都不可用于列表上的一个或多个业务文档，则需要使用 BizTalk 编辑器创建新的架构并定义其结构。|  
  
## <a name="see-also"></a>另请参阅  
 [How to Create for XML 消息架构](../core/how-to-create-schemas-for-xml-messages.md)   
 [创建使用 BizTalk 编辑器的架构](../core/creating-schemas-using-biztalk-editor.md)